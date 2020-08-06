---
title: Краткое руководство по узлу Windows PowerShell | Документация Майкрософт
ms.date: 09/12/2016
ms.openlocfilehash: fea6bd5ae49ecf552c583271ee9d869b1ccebae8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779409"
---
# <a name="windows-powershell-host-quickstart"></a>Краткое руководство по узлам Windows PowerShell

Для размещения Windows PowerShell в приложении используется класс [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) .
Этот класс предоставляет методы, которые создают конвейер команд, а затем выполняют эти команды в пространстве выполнения.
Самый простой способ создать ведущее приложение — использовать пространство выполнения по умолчанию.
Пространство выполнения по умолчанию содержит все основные команды Windows PowerShell.
Если требуется, чтобы приложение предоставляло только подмножество команд Windows PowerShell, необходимо создать пользовательское пространство выполнения.

## <a name="using-the-default-runspace"></a>Использование пространства выполнения по умолчанию

Для начала мы используем пространство выполнения по умолчанию и с помощью методов класса [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) добавим команды, параметры, инструкции и скрипты в конвейер.

### <a name="addcommand"></a>AddCommand

Для добавления команд в конвейер используется метод [System. Management. Automation. PowerShell. AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) .
Например, предположим, что требуется получить список запущенных процессов на компьютере.
Ниже приведен способ выполнения этой команды.

1. Создайте объект [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) .

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. Добавьте команду, которую требуется выполнить.

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. Вызовите команду.

   ```csharp
   ps.Invoke();
   ```

Если метод AddCommand вызывается несколько раз перед вызовом метода [System. Management. Automation. PowerShell. Invoke](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , результат первой команды передается второму и т. д.
Если вы не хотите передавать результат предыдущей команды команде, добавьте ее, вызвав метод [System. Management. Automation. PowerShell. аддстатемент](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) .

### <a name="addparameter"></a>аддпараметер

В предыдущем примере выполняется одна команда без параметров.
В команду можно добавить параметры с помощью метода [System. Management. Automation. пскомманд. аддпараметер](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) .
Например, следующий код возвращает список всех процессов, имена которых `PowerShell` выполняются на компьютере.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

Можно добавить дополнительные параметры путем многократного вызова метода Аддпараметер.

```csharp                   
PowerShell.Create().AddCommand("Get-ChildItem")
                   .AddParameter("Path", @"c:\Windows")
                   .AddParameter("Filter", "*.exe")
                   .Invoke();
```

Также можно добавить словарь имен и значений параметров, вызвав метод [System. Management. Automation. PowerShell. аддпараметерс](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) .

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Path", @"c:\Windows");
parameters.Add("Filter", "*.exe");

PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>аддстатемент

Пакетную обработку можно имитировать с помощью метода [System. Management. Automation. PowerShell. аддстатемент](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) , который добавляет дополнительный оператор в конец конвейера.
Следующий код возвращает список запущенных процессов с именем `PowerShell` , а затем получает список запущенных служб.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>аддскрипт

Можно запустить существующий скрипт, вызвав метод [System. Management. Automation. PowerShell. аддскрипт](/dotnet/api/System.Management.Automation.PowerShell.AddScript) .
В следующем примере в конвейер добавляется скрипт и выполняется его выполнение.
В этом примере предполагается, что в папке уже есть скрипт с именем `MyScript.ps1` `D:\PSScripts` .

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

Существует также версия метода Аддскрипт, принимающая логический параметр с именем `useLocalScope` .
Если этот параметр имеет значение `true` , скрипт выполняется в локальной области.
Следующий код запустит скрипт в локальной области.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a>Создание пользовательского пространства выполнения

Хотя пространство выполнения по умолчанию, используемое в предыдущих примерах, загружает все основные команды Windows PowerShell, можно создать пользовательское пространство выполнения, которое загружает только указанное подмножество команд.
Это может потребоваться для повышения производительности (загрузка большего количества команд — снижение производительности) или ограничение возможности пользователя выполнять операции.
Пространство выполнения, предоставляющее только ограниченное количество команд, называется ограниченным пространством выполнения.
Для создания ограниченного пространства выполнения используйте классы [System. Management. Automation. пространства выполнения](/dotnet/api/System.Management.Automation.Runspaces.Runspace) и [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

### <a name="creating-an-initialsessionstate-object"></a>Создание объекта InitialSessionState

Чтобы создать пользовательское пространство выполнения, необходимо сначала создать объект [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .
В следующем примере для создания пространства выполнения после создания объекта InitialSessionState по умолчанию мы используем [System. Management. Automation. пространства. рунспацефактори](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) .

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a>Ограничение пространства выполнения

В предыдущем примере мы создали объект [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) по умолчанию, который загружает все встроенные основные ядра Windows PowerShell.
Мы также могли вызвать метод [System.Management.Automation.Runspaces.Iniтиалсессионстате. CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) , чтобы создать объект InitialSessionState, который будет загружать только команды в оснастке Microsoft. PowerShell. Core.
Чтобы создать более ограниченное пространство выполнения, необходимо создать пустой объект InitialSessionState, вызвав метод [System.Management.Automation.Runspaces.Iniтиалсессионстате. Create](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) , а затем добавить команды в InitialSessionState.

Использование пространства выполнения, которое загружает только указанные команды, обеспечивает значительно повышенную производительность.

Методы класса [System. Management. Automation. пространства выполнения. сессионстатекмдлетентри](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) используются для определения командлетов для начального состояния сеанса.
В следующем примере создается пустое начальное состояние сеанса, затем определяется и добавляются `Get-Command` `Import-Module` команды и в исходное состояние сеанса.
Затем создается пространство выполнения, ограниченное этим начальным состоянием сеанса, и выполняются команды в этом пространстве выполнения.

Создайте начальное состояние сеанса.

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

Определение и Добавление команд в исходное состояние сеанса.

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

Создайте и откройте пространство выполнения.

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

Выполните команду и отобразите результат.

```csharp
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
Collection<CommandInfo> result = ps.Invoke<CommandInfo>();
foreach (var entry in result)
{
       Console.WriteLine(entry.Name);
}
```

При запуске результат этого кода будет выглядеть следующим образом.

```powershell
Get-Command
Import-Module
```
