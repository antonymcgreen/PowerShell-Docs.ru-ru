---
ms.date: 09/13/2016
ms.topic: reference
title: Пример Runspace07
description: Пример Runspace07
ms.openlocfilehash: 4356f33a1d962a0a6c5ca1ebb8c3e4c579463022
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657657"
---
# <a name="runspace07-sample"></a>Пример Runspace07

В этом примере показано, как создать пространство выполнения, а затем использовать это пространство выполнения для синхронного выполнения двух командлетов с помощью объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

## <a name="requirements"></a>Требования

Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Что демонстрирует

В этом образце демонстрируется следующее.

- Создание объекта [System. Management. Automation. пространства выполнения](/dotnet/api/System.Management.Automation.Runspaces.Runspace) с помощью класса [System. Management. Automation. пространства. рунспацефактори](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) .

- Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) , использующего пространство выполнения.

- Добавление командлетов в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

- Выполнение командлетов в синхронном режиме.

- Извлечение свойств из объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) , возвращаемых командой.

## <a name="example"></a>Пример

В этом примере создается пространство выполнения, которое используется объектом [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) для выполнения командлетов [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Measure-Object](/powershell/module/microsoft.powershell.utility/measure-object) .

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace07
  {
    /// <summary>
    /// This sample shows how to create a runspace and how to run commands
    /// using a PowerShell object. It builds a pipeline that runs the
    /// get-process cmdlet, which is piped to the measure-object
    /// cmdlet to count the number of processes running on the system.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a runspace using the RunspaceFactory class.
    /// 2. Creating a PowerShell object that uses the runspace.
    /// 3. Adding cmdlets to the pipeline of the PowerShell object.
    /// 4. Running the cmdlets synchronously.
    /// 5. Working with PSObject objects to extract properties
    ///    from the objects returned by the cmdlets.
    /// </remarks>
    private static void Main(string[] args)
    {
      Collection<PSObject> result;     // Will hold the result
                                       // of running the cmdlets.

      // Create a runspace. We can not use the RunspaceInvoke class
      // because we need to get at the underlying runspace to
      // explicitly add the commands. Notice that no PSHost object is
      // supplied to the CreateRunspace method so the default host is
      // used. See the Host samples for more information on creating
      // your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace())
      {
        myRunSpace.Open();

        // Create a PowerShell object and specify the runspace.
        PowerShell powershell = PowerShell.Create();
        powershell.Runspace = myRunSpace;

        // Use the using statement so we dispose of the PowerShell object
        // when we're done.
        using (powershell)
        {
          // Add the get-process cmdlet to the PowerShell object. Notice
          // we are specify the name of the cmdlet, not a script.
          powershell.AddCommand("get-process");

          // Add the measure-object cmdlet to count the number
          // of objects being returned. Commands are always added to the end
          // of the pipeline.
          powershell.AddCommand("measure-object");

          // Run the cmdlets synchronously and save the objects returned.
          result = powershell.Invoke();
        }

        // Even after disposing of the pipeLine, we still need to set
        // the powershell variable to null so that the garbage collector
        // can clean it up.
        powershell = null;

        // Display the results of running the commands (checking that
        // everything is ok first.
        if (result == null || result.Count != 1)
        {
          throw new InvalidOperationException(
                    "pipeline.Invoke() returned the wrong number of objects");
        }

        PSMemberInfo count = result[0].Properties["Count"];
        if (count == null)
        {
          throw new InvalidOperationException(
                    "The object returned doesn't have a 'count' property");
        }

        Console.WriteLine(
                   "Runspace07: The Get-Process cmdlet returned {0} objects",
                   count.Value);

        // Close the runspace to release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a>См. также:

[Написание ведущего приложения Windows PowerShell](./writing-a-windows-powershell-host-application.md)
