---
title: Пример Runspace07 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7bf81e-4f95-4150-afc3-c0872b24d026
caps.latest.revision: 7
ms.openlocfilehash: a39a6bd83f5a41ad341d7fe3d465eb73ba1d034d
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565229"
---
# <a name="runspace07-sample"></a><span data-ttu-id="d4ebf-102">Пример Runspace07</span><span class="sxs-lookup"><span data-stu-id="d4ebf-102">Runspace07 Sample</span></span>

<span data-ttu-id="d4ebf-103">В этом примере показано, как создать пространство выполнения, а затем использовать это пространство выполнения для синхронного выполнения двух командлетов с помощью объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="d4ebf-103">This sample shows how to create a runspace, and then use that runspace to run two cmdlets synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4ebf-104">Требования</span><span class="sxs-lookup"><span data-stu-id="d4ebf-104">Requirements</span></span>

<span data-ttu-id="d4ebf-105">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="d4ebf-105">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d4ebf-106">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="d4ebf-106">Demonstrates</span></span>

<span data-ttu-id="d4ebf-107">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="d4ebf-107">This sample demonstrates the following.</span></span>

- <span data-ttu-id="d4ebf-108">Создание объекта [System. Management. Automation. пространства выполнения](/dotnet/api/System.Management.Automation.Runspaces.Runspace) с помощью класса [System. Management. Automation. пространства. рунспацефактори](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) .</span><span class="sxs-lookup"><span data-stu-id="d4ebf-108">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object by using the [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) class.</span></span>

- <span data-ttu-id="d4ebf-109">Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) , использующего пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4ebf-109">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="d4ebf-110">Добавление командлетов в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="d4ebf-110">Adding cmdlets to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="d4ebf-111">Выполнение командлетов в синхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="d4ebf-111">Running the cmdlets synchronously.</span></span>

- <span data-ttu-id="d4ebf-112">Извлечение свойств из объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) , возвращаемых командой.</span><span class="sxs-lookup"><span data-stu-id="d4ebf-112">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="d4ebf-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d4ebf-113">Example</span></span>

<span data-ttu-id="d4ebf-114">В этом примере создается пространство выполнения, которое используется объектом [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) для выполнения командлетов [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Measure-Object](/powershell/module/microsoft.powershell.utility/measure-object) .</span><span class="sxs-lookup"><span data-stu-id="d4ebf-114">This sample creates a runspace that used by a [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) object to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Measure-Object](/powershell/module/microsoft.powershell.utility/measure-object) cmdlets.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d4ebf-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4ebf-115">See Also</span></span>

[<span data-ttu-id="d4ebf-116">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4ebf-116">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
