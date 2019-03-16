---
title: Примеры использования Windows PowerShell узла | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a134b81-bd0c-4e1c-a2f0-9acbe852745a
caps.latest.revision: 9
ms.openlocfilehash: cc014487a680747ad59437052f79d4576154a1cb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059683"
---
# <a name="windows-powershell-host-quickstart"></a>Краткое руководство по узлам Windows PowerShell

Чтобы разместить Windows PowerShell в приложении, используйте [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) класса. Этот класс предоставляет методы, создать конвейер команд, а затем выполните эти команды в пространстве выполнения. Создание ведущего приложения проще всего использовать пространству выполнения по умолчанию. Пространству выполнения по умолчанию содержит все основные команды Windows PowerShell. Если требуется обновлять приложение, чтобы предоставить некоторое подмножество команд Windows PowerShell, необходимо создать пользовательские пространства выполнения.

## <a name="using-the-default-runspace"></a>Использование пространства имен по умолчанию

Для начала мы использовать пространству выполнения по умолчанию и использовать методы [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) класс, чтобы добавить команды, параметры, инструкций и скриптов в конвейер.

### <a name="addcommand"></a>AddCommand

Использовании [System.Management.Automation.Powershell.AddCommand*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) метод [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) класс, чтобы добавить команды в конвейер. Например предположим, что вы хотите получить список выполняющихся процессов на компьютере. Способ выполнения этой команды выглядит следующим образом.

1. Создание [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) объекта.

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. Добавьте в команду, которую требуется выполнить.

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. Вызовите команду.

   ```csharp
   ps.Invoke();
   ```

При вызове метода [System.Management.Automation.Powershell.AddCommand*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) более одного раза, прежде чем вызывать метод [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод, результат Первая команда передается по конвейеру второго и т. д. Если вы не хотите передать результат выполнения предыдущей команды к команде, добавьте его, вызвав [System.Management.Automation.Powershell.AddStatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) вместо этого.

### <a name="addparameter"></a>AddParameter

В предыдущем примере выполняется одну команду без параметров. Можно добавить параметры к команде с помощью [System.Management.Automation.PSCommand.AddParameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) метод к примеру, следующий код получает список всех процессов, которые называются `PowerShell` под управлением компьютер.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

Можно добавить дополнительные параметры, вызвав [System.Management.Automation.PSCommand.AddParameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) несколько раз.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

Можно также добавить словарь имен и значений параметров, вызвав [System.Management.Automation.PowerShell.AddParameters*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) метод.

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>AddStatement

Вы можете имитировать пакетной обработки с помощью [System.Management.Automation.PowerShell.AddStatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) метод, который добавляет дополнительные инструкции для завершения работы конвейера, следующий код получает список запущенных процессов с именем `PowerShell`, а затем возвращает список запущенных служб.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

Вы можете запустить существующий скрипт, вызов [System.Management.Automation.PowerShell.AddScript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод. В следующем примере добавляется сценарий в конвейер и запускает его. В этом примере предполагается, что уже имеется сценарий с именем `MyScript.ps1` в папку с именем `D:\PSScripts`.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

Есть также версия [System.Management.Automation.PowerShell.AddScript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод, который принимает логический параметр с именем `useLocalScope`. Если этот параметр имеет значение `true`, а затем сценарий выполняется в локальной области. Следующий код выполняет скрипт в локальной области.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a>Создание пользовательского пространства выполнения

Хотя пространству выполнения по умолчанию, используемый в предыдущих примерах загружает все команды Windows PowerShell core, можно создать пользовательские пространства выполнения, который загружает только конкретному подмножеству все команды. Может потребоваться выполнить, чтобы повысить производительность (идет загрузка большее количество команд является снижение производительности), или чтобы ограничить возможности пользователя для выполнения операций. Пространства выполнения, которая предоставляет только ограниченный набор команд, называется ограниченное пространство выполнения. Чтобы создать ограниченное пространство выполнения, используйте [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) и [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) классы.

### <a name="creating-an-initialsessionstate-object"></a>Создание объекта InitialSessionState

Чтобы создать пользовательские пространства выполнения, необходимо сначала создать [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта. В следующем примере мы используем [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) создать пространство выполнения после создания по умолчанию [System.Management.Automation.Runspaces.InitialSessionState ](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта.

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

В предыдущем примере мы создали по умолчанию [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объект, который загружает все встроенные ядра Windows PowerShell. Мы также мог бы вызвать [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) метод для создания объекта InitialSessionState, который будет загружать только команды в Microsoft.PowerShell.Core Оснастка. Чтобы создать более ограниченное пространство выполнения, необходимо создать пустой [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) путем вызова метода [ System.Management.Automation.Runspaces.InitialSessionState.Create*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) метод и чтобы InitialSessionState команд.

Использование пространства имен, который загружает только те команды, указываемые обеспечивает значительно улучшенную производительность.

Использование методов [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) класс определяет командлеты для начального состояния сеанса. В следующем примере создается пустой начальное состояние сеанса, а затем определяет и добавляет `Get-Command` и `Import-Module` команды для начального состояния сеанса. Затем мы создания пространства выполнения, ограничены, начальное состояние сеанса и выполните команды в этом пространстве выполнения.

Создание начального состояния сеанса.

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

Определение и добавлены команды для начального состояния сеанса.

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

Создайте и откройте пространства выполнения.

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

Выполнение команды и отображения результатов.

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

При запуске, результат выполнения этого кода будет выглядеть следующим образом.

```powershell
Get-Command
Import-Module
```
