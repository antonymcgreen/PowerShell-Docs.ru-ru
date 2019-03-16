---
title: Пример Runspace08 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1100d91d-249d-4af7-9854-2d6a423ac2f4
caps.latest.revision: 7
ms.openlocfilehash: 70577a6a42ce26e9791360fa30baae9d7a492daf
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057745"
---
# <a name="runspace08-sample"></a><span data-ttu-id="8fe3a-102">Пример Runspace08</span><span class="sxs-lookup"><span data-stu-id="8fe3a-102">Runspace08 Sample</span></span>

<span data-ttu-id="8fe3a-103">В этом примере показано, как добавить команды и аргументы в конвейер объекта [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) и запустить команды синхронно.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-103">This sample shows how to add commands and arguments to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

## <a name="requirements"></a><span data-ttu-id="8fe3a-104">Требования</span><span class="sxs-lookup"><span data-stu-id="8fe3a-104">Requirements</span></span>

<span data-ttu-id="8fe3a-105">В этом примере требуется Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-105">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="8fe3a-106">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="8fe3a-106">Demonstrates</span></span>

<span data-ttu-id="8fe3a-107">В этом примере демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-107">This sample demonstrates the following.</span></span>

- <span data-ttu-id="8fe3a-108">Создание [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) объекта с помощью [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) класса.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-108">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object by using the [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) class.</span></span>

- <span data-ttu-id="8fe3a-109">Создание [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объект, который использует пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-109">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="8fe3a-110">Добавление командлетов в конвейер объекта [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-110">Adding cmdlets to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="8fe3a-111">Синхронное выполнение командлетов.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-111">Running the cmdlets synchronously.</span></span>

- <span data-ttu-id="8fe3a-112">Извлечение свойств из [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) объектов, возвращаемых командой.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-112">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="8fe3a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="8fe3a-113">Example</span></span>

<span data-ttu-id="8fe3a-114">В этом примере выполняется [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) командлетов с помощью [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.</span><span class="sxs-lookup"><span data-stu-id="8fe3a-114">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace08
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands. The
    /// PowerShell object builds a pipeline that include the get-process cmdlet,
    /// which is then piped to the sort-object cmdlet. Parameters are added to the
    /// sort-object cmdlet to sort the HandleCount property in descending order.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates:
    /// 1. Creating a PowerShell object
    /// 2. Adding individual commands to the PowerShell object.
    /// 3. Adding parameters to the commands.
    /// 4. Running the pipeline of the PowerShell object synchronously.
    /// 5. Working with PSObject objects to extract properties
    ///    from the objects returned by the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      Collection<PSObject> results; // Holds the result of the pipeline execution.

      // Create the PowerShell object. Notice that no runspace is specified so a
      // new default runspace is used.
      PowerShell powershell = PowerShell.Create();

      // Use the using statement so that we can dispose of the PowerShell object
      // when we are done.
      using (powershell)
      {
        // Add the get-process cmdlet to the pipeline of the PowerShell object.
        powershell.AddCommand("get-process");

        // Add the sort-object cmdlet and its parameters to the pipeline of
        // the PowerShell object so that we can sort the HandleCount property
        //  in descending order.
        powershell.AddCommand("sort-object").AddParameter("descending").AddParameter("property", "handlecount");

        // Run the commands of the pipeline synchronously.
        results = powershell.Invoke();
      }

      // Even after disposing of the PowerShell object, we still
      // need to set the powershell variable to null so that the
      // garbage collector can clean it up.
      powershell = null;

      Console.WriteLine("Process              HandleCount");
      Console.WriteLine("--------------------------------");

      // Display the results returned by the commands.
      foreach (PSObject result in results)
      {
        Console.WriteLine(
                          "{0,-20} {1}",
                          result.Members["ProcessName"].Value,
                          result.Members["HandleCount"].Value);
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="8fe3a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8fe3a-115">See Also</span></span>

[<span data-ttu-id="8fe3a-116">Создание приложения Windows PowerShell узла</span><span class="sxs-lookup"><span data-stu-id="8fe3a-116">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)