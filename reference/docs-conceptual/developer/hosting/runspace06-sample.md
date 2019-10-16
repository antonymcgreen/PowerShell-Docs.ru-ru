---
title: Пример Runspace06 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 471c85f3-9287-45c2-b4bc-833caa1b7634
caps.latest.revision: 8
ms.openlocfilehash: 3850aec88bc800718a82f51c91fbd0cb3c705089
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367593"
---
# <a name="runspace06-sample"></a>Пример Runspace06

В этом примере показано, как добавить модуль в объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) , чтобы модуль загружался при открытии пространства выполнения. Модуль предоставляет командлет Get-proc (определяемый [образцом GetProcessSample02](../cmdlet/getprocesssample02-sample.md)), который выполняется синхронно с помощью объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

## <a name="requirements"></a>Требования

Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Демонстрирующее

В этом образце демонстрируется следующее.

- Создание объекта [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

- Добавление модуля в объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

- Создание объекта [System. Management. Automation. пространства выполнения](/dotnet/api/System.Management.Automation.Runspaces.Runspace) , использующего объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

- Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) , использующего пространство выполнения.

- Добавление командлета Get-proc модуля в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

- Выполнение команды в синхронном режиме.

- Извлечение свойств из объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) , возвращаемых командой.

## <a name="example"></a>Пример

В этом примере создается пространство выполнения, в котором используется объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) для определения элементов, доступных при открытии пространства выполнения. В этом примере модуль, определяющий командлет Get-proc, добавляется в исходное состояние сеанса.

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
  internal class Runspace06
  {
    /// <summary>
    /// This sample shows how to define an initial session state that is
    /// used when creating a runspace. The sample invokes a command from
    /// a binary module that is loaded by the initial session state.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample assumes that user has coppied the GetProcessSample02.dll
    /// that is produced by the GetProcessSample02 sample to the current
    /// directory.
    /// This sample demonstrates the following:
    /// 1. Creating a default initial session state.
    /// 2. Adding a module to the initial session state.
    /// 3. Creating a runspace that uses the initial session state.
    /// 4. Creating a PowerShell object that uses the runspace.
    /// 5. Adding the module's get-proc cmdlet to the PowerShell object.
    /// 6. Running the command synchronously.
    /// 7. Using PSObject objects to extract and display properties from
    ///    the objects returned by the cmdlet.
    /// </remarks>
    private static void Main(string[] args)
    {
        // Create the default initial session state and add the module.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      iss.ImportPSModule(new string[] { @".\GetProcessSample02.dll" });

      // Create a runspace. Notice that no PSHost object is supplied to the
      // CreateRunspace method so the default host is used. See the Host
      // samples for more information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        // Create a PowerShell object.
        using (PowerShell powershell = PowerShell.Create())
        {
          // Add the cmdlet and specify the runspace.
          powershell.AddCommand(@"GetProcessSample02\get-proc");
          powershell.Runspace = myRunSpace;

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

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

[Написание ведущего приложения Windows PowerShell](./writing-a-windows-powershell-host-application.md)