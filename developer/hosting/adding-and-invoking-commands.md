---
title: Добавление и вызова команд | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62be8432-28c1-4ca2-bcdb-d0350163fa8c
caps.latest.revision: 5
ms.openlocfilehash: 31371797ee57f07075da3436e0b42b2ca01aaffd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857350"
---
# <a name="adding-and-invoking-commands"></a>Добавление и вызов команд

После создания пространства выполнения, можно добавить Windows PowerShellcommands и сценарии конвейера и затем вызвать конвейер синхронно или асинхронно.

## <a name="creating-a-pipeline"></a>Создание конвейера

 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) класс предоставляет несколько методов для добавления команды, параметры и сценарии в конвейер. Конвейер можно вызвать синхронно, вызвав перегрузку [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод, или асинхронно путем вызова перегрузки [ System.Management.Automation.Powershell.Begininvoke*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) и затем [System.Management.Automation.Powershell.Endinvoke*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) метод.

### <a name="addcommand"></a>AddCommand

1. Создание [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.

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

 При вызове метода [System.Management.Automation.Powershell.Addcommand*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) более одного раза, прежде чем вызывать метод [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод, результат Первая команда передается по конвейеру второго и т. д. Если вы не хотите передать результат выполнения предыдущей команды к команде, добавьте его, вызвав [System.Management.Automation.Powershell.Addstatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) вместо этого.

### <a name="addparameter"></a>AddParameter

 В предыдущем примере выполняется одну команду без параметров. Можно добавить параметры к команде с помощью [System.Management.Automation.Pscommand.Addparameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) метод к примеру, следующий код получает список всех процессов, которые называются `PowerShell` под управлением компьютер.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 Можно добавить дополнительные параметры, вызвав [System.Management.Automation.Pscommand.Addparameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) несколько раз.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 Можно также добавить словарь имен и значений параметров, вызвав [System.Management.Automation.Powershell.Addparameters*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) метод.

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>AddStatement

 Вы можете имитировать пакетной обработки с помощью [System.Management.Automation.Powershell.Addstatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) метод, который добавляет дополнительные инструкции для завершения работы конвейера, следующий код получает список запущенных процессов с именем `PowerShell`, а затем возвращает список запущенных служб.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

 Вы можете запустить существующий скрипт, вызов [System.Management.Automation.Powershell.Addscript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод. В следующем примере добавляется сценарий в конвейер и запускает его. В этом примере предполагается, что уже имеется сценарий с именем `MyScript.ps1` в папку с именем `D:\PSScripts`.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 Есть также версия [System.Management.Automation.Powershell.Addscript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод, который принимает логический параметр с именем `useLocalScope`. Если этот параметр имеет значение `true`, а затем сценарий выполняется в локальной области. Следующий код выполняет скрипт в локальной области.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a>Вызов конвейера синхронно

 После добавления элементов в конвейер, ее можно вызвать. Для вызова конвейера синхронно, вызовите перегрузку [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод. В следующем примере показано, как синхронный вызов конвейера.

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

### <a name="invoking-a-pipeline-asynchronously"></a>Вызов конвейера асинхронно

 Вызов конвейера асинхронно путем вызова перегрузки [System.Management.Automation.Powershell.Begininvoke*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) для создания [IAsyncResult](http://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) объекта и последующего вызова [ System.Management.Automation.Powershell.Endinvoke*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) метод.

 Приведенный ниже показано, как вызвать asynchronoulsy конвейера.

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
      // Get-Process cmdlet. Do not include spaces immediatly
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

 [Создание ограниченное пространство выполнения](./creating-a-constrained-runspace.md)
