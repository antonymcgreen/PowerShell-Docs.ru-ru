---
title: Пример Runspace05 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1685cfc4-b32c-4bed-b221-e0c4482db955
caps.latest.revision: 9
ms.openlocfilehash: eb227b5fa5e91f59b6fc99981ff5affca1cf63fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360883"
---
# <a name="runspace05-sample"></a>Пример Runspace05

В этом примере показано, как добавить оснастку в объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) , чтобы командлет оснастки был доступен при открытии пространства выполнения. Оснастка предоставляет командлет Get-proc (определяемый [образцом GetProcessSample01](../cmdlet/getprocesssample01-sample.md)), который выполняется синхронно с помощью объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

## <a name="requirements"></a>Требования

Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Демонстрирующее

В этом образце демонстрируется следующее.

- Создание объекта [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

- Добавление оснастки в объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

- Создание объекта [System. Management. Automation. пространства выполнения](/dotnet/api/System.Management.Automation.Runspaces.Runspace) , использующего объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .

- Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) , использующего пространство выполнения.

- Добавление командлета Get-proc оснастки в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

- Выполнение команды в синхронном режиме.

- Извлечение свойств из объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) , возвращаемых командой.

## <a name="example"></a>Пример

В этом примере создается пространство выполнения, в котором используется объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) для определения элементов, доступных при открытии пространства выполнения. В этом примере оснастка, которая определяет командлет Get-proc, добавляется в исходное состояние сеанса.

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
  internal class Runspace05
  {
    /// <summary>
    /// This sample shows how to define an initial session state that is
    /// used when creating a runspace. The sample invokes a command from
    /// a Windows PowerShell snap-in that is present in the console file.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample assumes that user has coppied the GetProcessSample01.dll
    /// that is produced by the GetProcessSample01 sample to the current
    /// directory.
    /// This sample demonstrates the following:
    /// 1. Creating a default initial session state.
    /// 2. Adding a snap-in to the initial session state.
    /// 3. Creating a runspace that uses the initial session state.
    /// 4. Creating a PowerShell object that uses the runspace.
    /// 5. Adding the snap-in's get-proc cmdlet to the PowerShell object.
    /// 6. Using PSObject objects to extract and display properties from
    ///    the objects returned by the cmdlet.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create the default initial session state. The default initial
      // session state contains all the elements provided by Windows
      // PowerShell.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      PSSnapInException warning;
      iss.ImportPSSnapIn("GetProcPSSnapIn01", out warning);

      // Create a runspace. Notice that no PSHost object is supplied to the
      // CreateRunspace method so the default host is used. See the Host
      // samples for more information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        // Create a PowerShell object.
        using (PowerShell powershell = PowerShell.Create())
        {
          // Add the snap-in cmdlet and specify the runspace.
          powershell.AddCommand("GetProcPSSnapIn01\\get-proc");
          powershell.Runspace = myRunSpace;

          // Run the cmdlet synchronously.
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