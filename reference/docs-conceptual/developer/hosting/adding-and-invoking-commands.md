---
title: Добавление и вызов команд | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b51c4ae3fa5c5239e3c5c5e65bf7aa63c58c4da9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779800"
---
# <a name="adding-and-invoking-commands"></a>Добавление и вызов команд

После создания пространства выполнения можно добавить в конвейер Повершеллкоммандс и скрипты Windows, а затем вызывать конвейер синхронно или асинхронно.

## <a name="creating-a-pipeline"></a>Создание конвейера

 Класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) предоставляет несколько методов для добавления команд, параметров и скриптов в конвейер. Конвейер можно вызвать синхронно, вызвав перегрузку метода [System. Management. Automation. PowerShell. Invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke) или асинхронно, вызвав перегрузку метода [System. Management. Automation. PowerShell. BeginInvoke *](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) , а затем метод [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .

### <a name="addcommand"></a>AddCommand

1. Создайте объект [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

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

 Если метод [System. Management. Automation. PowerShell. AddCommand *](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) вызывается более одного раза перед вызовом метода [System. Management. Automation. PowerShell. Invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , результат первой команды передается второму и т. д. Если вы не хотите передавать результат предыдущей команды команде, добавьте ее, вызвав метод [System. Management. Automation. PowerShell. аддстатемент *](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) .

### <a name="addparameter"></a>аддпараметер

 В предыдущем примере выполняется одна команда без параметров. Можно добавить параметры в команду с помощью метода [System. Management. Automation. пскомманд. аддпараметер *.](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) например, следующий код возвращает список всех процессов, именованных `PowerShell` на компьютере.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 Можно добавить дополнительные параметры путем многократного вызова [System. Management. Automation. пскомманд. аддпараметер *](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) .

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 Также можно добавить словарь имен и значений параметров, вызвав метод [System. Management. Automation. PowerShell. аддпараметерс *](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) .

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>аддстатемент

 Пакетную обработку можно имитировать с помощью метода [System. Management. Automation. PowerShell. аддстатемент *](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) , который добавляет дополнительный оператор в конец конвейера. следующий код возвращает список запущенных процессов с именем `PowerShell` , а затем получает список запущенных служб.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>аддскрипт

 Можно запустить существующий скрипт, вызвав метод [System. Management. Automation. PowerShell. аддскрипт *](/dotnet/api/System.Management.Automation.PowerShell.AddScript) . В следующем примере в конвейер добавляется скрипт и выполняется его выполнение. В этом примере предполагается, что в папке уже есть скрипт с именем `MyScript.ps1` `D:\PSScripts` .

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 Существует также версия метода [System. Management. Automation. PowerShell. аддскрипт *](/dotnet/api/System.Management.Automation.PowerShell.AddScript) , принимающая логический параметр с именем `useLocalScope` . Если этот параметр имеет значение `true` , скрипт выполняется в локальной области. Следующий код запустит скрипт в локальной области.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a>Синхронный вызов конвейера

 После добавления элементов в конвейер вы вызываете его. Для синхронного вызова конвейера вызывается перегрузка метода [System. Management. Automation. PowerShell. Invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke) . В следующем примере показано, как синхронно вызвать конвейер.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS1e
{
  class HostPS1e
  {
    static void Main(string[] args)
    {
      // Using the PowerShell.Create and AddCommand
      // methods, create a command pipeline.
      PowerShell ps = PowerShell.Create().AddCommand ("Sort-Object");

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the supplied input.
      foreach (PSObject result in ps.Invoke(new int[] { 3, 1, 6, 2, 5, 4 }))
      {
          Console.WriteLine("{0}", result);
      } // End foreach.
    } // End Main.
  } // End HostPS1e.
}
```

### <a name="invoking-a-pipeline-asynchronously"></a>Асинхронный вызов конвейера

 Асинхронный вызов конвейера вызывает перегрузку [System. Management. Automation. PowerShell. BeginInvoke *](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) для создания объекта [IAsyncResult](https://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) и последующего вызова метода [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .

 В следующем примере показано, как вызвать конвейер асинхронно.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS3
{
  class HostPS3
  {
    static void Main(string[] args)
    {
      // Use the PowerShell.Create and PowerShell.AddCommand
      // methods to create a command pipeline that includes
      // Get-Process cmdlet. Do not include spaces immediately
      // before or after the cmdlet name as that will cause
      // the command to fail.
      PowerShell ps = PowerShell.Create().AddCommand("Get-Process");

      // Create an IAsyncResult object and call the
      // BeginInvoke method to start running the
      // command pipeline asynchronously.
      IAsyncResult async = ps.BeginInvoke();

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the default runspace.
      foreach (PSObject result in ps.EndInvoke(async))
      {
        Console.WriteLine("{0,-20}{1}",
                result.Members["ProcessName"].Value,
                result.Members["Id"].Value);
      } // End foreach.
      System.Console.WriteLine("Hit any key to exit.");
      System.Console.ReadKey();
    } // End Main.
  } // End HostPS3.
}
```

## <a name="see-also"></a>См. также

 [Создание InitialSessionState](./creating-an-initialsessionstate.md)

 [Создание ограниченного пространства выполнения](./creating-a-constrained-runspace.md)
