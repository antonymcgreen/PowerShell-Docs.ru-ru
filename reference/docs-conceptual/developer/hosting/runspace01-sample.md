---
ms.date: 09/13/2016
ms.topic: reference
title: Пример Runspace01
description: Пример Runspace01
ms.openlocfilehash: f47f79dd507db258119016353dc5a72d110d9252
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657919"
---
# <a name="runspace01-sample"></a>Пример Runspace01

В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения командлета [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) . Командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) возвращает объекты [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) для каждого процесса, выполняемого на локальном компьютере. Значения свойств [System. Diagnostics. Process. ProcessName *](/dotnet/api/System.Diagnostics.Process.ProcessName) и [System. Diagnostics. Process. HandleCount *](/dotnet/api/System.Diagnostics.Process.Handlecount) затем извлекаются из возвращенных объектов и отображаются в окне консоли.

## <a name="requirements"></a>Требования

 Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Что демонстрирует

- Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения команды.

- Добавление команды в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

- Выполнение команды в синхронном режиме.

- Использование объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) для извлечения свойств из объектов, возвращаемых командой.

## <a name="example"></a>Пример

 В этом примере командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) выполняется синхронно в пространстве выполнения по умолчанию, предоставляемом Windows PowerShell.

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace01
  {
    /// <summary>
    /// This sample uses the PowerShell class to execute
    /// the get-process cmdlet synchronously. The name and
    /// handlecount are then extracted from the PSObjects
    /// returned and displayed.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run a command.
    /// 2. Adding a command to the pipeline of the PowerShell object.
    /// 3. Running the command synchronously.
    /// 4. Using PSObject objects to extract properties from the objects
    ///    returned by the command.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create().AddCommand("get-process"))
      {
        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the command synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke())
        {
          Console.WriteLine(
                      "{0,-20} {1}",
                      result.Members["ProcessName"].Value,
                      result.Members["HandleCount"].Value);
        }
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a>См. также
