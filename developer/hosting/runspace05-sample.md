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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056453"
---
# <a name="runspace05-sample"></a><span data-ttu-id="bc5bb-102">Пример Runspace05</span><span class="sxs-lookup"><span data-stu-id="bc5bb-102">Runspace05 Sample</span></span>

<span data-ttu-id="bc5bb-103">В этом примере показано, как добавить оснастку в [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта, чтобы командлет оснастки был доступен при открытии пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-103">This sample shows how to add a snap-in to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span> <span data-ttu-id="bc5bb-104">Оснастка предоставляет командлет Get-Proc (определяется [пример GetProcessSample01](../cmdlet/getprocesssample01-sample.md)) который запускается синхронно с помощью [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-104">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](../cmdlet/getprocesssample01-sample.md)) that is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc5bb-105">Требования</span><span class="sxs-lookup"><span data-stu-id="bc5bb-105">Requirements</span></span>

<span data-ttu-id="bc5bb-106">В этом примере требуется Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="bc5bb-107">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="bc5bb-107">Demonstrates</span></span>

<span data-ttu-id="bc5bb-108">В этом примере демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="bc5bb-109">Создание [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-109">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="bc5bb-110">Добавление оснастки в [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-110">Adding the snap-in to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="bc5bb-111">Создание [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) объект, который использует [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-111">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="bc5bb-112">Создание [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объект, который использует пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-112">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="bc5bb-113">Добавление оснастки в командлет get-proc в конвейер объекта [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-113">Adding the snap-in's get-proc cmdlet to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="bc5bb-114">Синхронное выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-114">Running the command synchronously.</span></span>

- <span data-ttu-id="bc5bb-115">Извлечение свойств из [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) объектов, возвращаемых командой.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-115">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="bc5bb-116">Пример</span><span class="sxs-lookup"><span data-stu-id="bc5bb-116">Example</span></span>

<span data-ttu-id="bc5bb-117">В этом примере создается пространство выполнения, с использованием [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта для определения элементов, которые доступны при открытии пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-117">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="bc5bb-118">В этом примере это оснастка, который определяет командлет Get-Proc добавляется начального состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="bc5bb-118">In this sample, a snap-in that defines a Get-Proc cmdlet is added to the initial session state.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bc5bb-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bc5bb-119">See Also</span></span>

[<span data-ttu-id="bc5bb-120">Создание приложения Windows PowerShell узла</span><span class="sxs-lookup"><span data-stu-id="bc5bb-120">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)