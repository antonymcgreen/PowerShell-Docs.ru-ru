---
ms.date: 09/13/2016
ms.topic: reference
title: Пример командлета GetProcessSample01
description: Пример командлета GetProcessSample01
ms.openlocfilehash: 159c277d17a8551d2b5c52377a230babacafc9ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652772"
---
# <a name="getprocesssample01-sample"></a><span data-ttu-id="91128-103">Пример командлета GetProcessSample01</span><span class="sxs-lookup"><span data-stu-id="91128-103">GetProcessSample01 Sample</span></span>

<span data-ttu-id="91128-104">В этом примере показано, как реализовать командлет, который получает процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="91128-104">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="91128-105">Этот командлет является упрощенной версией `Get-Process` командлета, предоставляемого Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="91128-105">This cmdlet is a simplified version of the `Get-Process` cmdlet that is provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="91128-106">Как создать пример с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="91128-106">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="91128-107">С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку GetProcessSample01</span><span class="sxs-lookup"><span data-stu-id="91128-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample01 folder.</span></span> <span data-ttu-id="91128-108">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="91128-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.</span></span>

2. <span data-ttu-id="91128-109">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="91128-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="91128-110">Откроется пример проекта в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="91128-110">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="91128-111">В меню **Построение** выберите команду **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="91128-111">In the **Build** menu, select **Build Solution**.</span></span>

  <span data-ttu-id="91128-112">Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91128-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="91128-113">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="91128-113">How to run the sample</span></span>

1. <span data-ttu-id="91128-114">Откройте окно командной строки и</span><span class="sxs-lookup"><span data-stu-id="91128-114">Open a Command Prompt window.</span></span>

2. <span data-ttu-id="91128-115">Перейдите к каталогу, содержащему файл Sample. dll.</span><span class="sxs-lookup"><span data-stu-id="91128-115">Navigate to the directory containing the sample .dll file.</span></span>

3. <span data-ttu-id="91128-116">Запустите InstallUtil "GetProcessSample01.dll".</span><span class="sxs-lookup"><span data-stu-id="91128-116">Run installutil "GetProcessSample01.dll".</span></span>

4. <span data-ttu-id="91128-117">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91128-117">Start Windows PowerShell.</span></span>

5. <span data-ttu-id="91128-118">Выполните следующую команду, чтобы добавить оснастку в оболочку.</span><span class="sxs-lookup"><span data-stu-id="91128-118">Run the following command to add the snap-in to the shell.</span></span>

   `Add-PSSnapin GetProcPSSnapIn01`

6. <span data-ttu-id="91128-119">Введите следующую команду, чтобы запустить командлет.</span><span class="sxs-lookup"><span data-stu-id="91128-119">Enter the following command to run the cmdlet.</span></span> `get-proc`

   `get-proc`

   <span data-ttu-id="91128-120">Ниже приведен пример выходных данных, которые выполняются в результате выполнения этих действий.</span><span class="sxs-lookup"><span data-stu-id="91128-120">This is a sample output that results from following these steps.</span></span>

   ```output
   Id              Name            State      HasMoreData     Location             Command
   --              ----            -----      -----------     --------             -------
   1               26932870-d3b... NotStarted False                                 Write-Host "A f...

   ```

   ```powershell
   Set-Content $env:temp\test.txt "This is a test file"
   ```

   ```output
   A file was created in the TEMP directory
   ```

## <a name="requirements"></a><span data-ttu-id="91128-121">Требования</span><span class="sxs-lookup"><span data-stu-id="91128-121">Requirements</span></span>

<span data-ttu-id="91128-122">Для работы с этим образцом требуется Windows PowerShell 1,0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="91128-122">This sample requires Windows PowerShell 1.0 or later.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="91128-123">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="91128-123">Demonstrates</span></span>

<span data-ttu-id="91128-124">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="91128-124">This sample demonstrates the following.</span></span>

- <span data-ttu-id="91128-125">Создание простого примера командлета.</span><span class="sxs-lookup"><span data-stu-id="91128-125">Creating a basic sample cmdlet.</span></span>

- <span data-ttu-id="91128-126">Определение класса командлета с помощью атрибута командлета.</span><span class="sxs-lookup"><span data-stu-id="91128-126">Defining a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="91128-127">Создание оснастки, которая работает как с Windows PowerShell 1,0, так и с Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="91128-127">Creating a snap-in that works with both Windows PowerShell 1.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="91128-128">В последующих примерах используются модули вместо оснасток, поэтому для них требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="91128-128">Subsequent samples use modules instead of snap-ins so they require Windows PowerShell 2.0.</span></span>

## <a name="example"></a><span data-ttu-id="91128-129">Пример</span><span class="sxs-lookup"><span data-stu-id="91128-129">Example</span></span>

<span data-ttu-id="91128-130">В этом примере показано, как создать простой командлет и его оснастку.</span><span class="sxs-lookup"><span data-stu-id="91128-130">This sample shows how to create a simple cmdlet and its snap-in.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace
using System.ComponentModel;

namespace Microsoft.Samples.PowerShell.Commands
{

   #region GetProcCommand

   /// <summary>
   /// This class implements the Get-Proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Cmdlet Overrides

      /// <summary>
      /// The ProcessRecord method calls the Process.GetProcesses
      /// method to retrieve the processes of the local computer.
      /// Then, the WriteObject method writes the associated processes
      /// to the pipeline.
      /// </summary>
      protected override void ProcessRecord()
      {
         // Retrieve the current processes.
         Process[] processes = Process.GetProcesses();

         // Write the processes to the pipeline to make them available
         // to the next cmdlet. The second argument (true) tells Windows
         // PowerShell to enumerate the array and to send one process
         // object at a time to the pipeline.
         WriteObject(processes, true);
      }

      #endregion Overrides

   } //GetProcCommand

   #endregion GetProcCommand

   #region PowerShell snap-in

   /// <summary>
   /// Create this sample as an PowerShell snap-in
   /// </summary>
   [RunInstaller(true)]
   public class GetProcPSSnapIn01 : PSSnapIn
   {
       /// <summary>
       /// Create an instance of the GetProcPSSnapIn01
       /// </summary>
       public GetProcPSSnapIn01()
           : base()
       {
       }

       /// <summary>
       /// Get a name for this PowerShell snap-in. This name will be used in registering
       /// this PowerShell snap-in.
       /// </summary>
       public override string Name
       {
           get
           {
               return "GetProcPSSnapIn01";
           }
       }

       /// <summary>
       /// Vendor information for this PowerShell snap-in.
       /// </summary>
       public override string Vendor
       {
           get
           {
               return "Microsoft";
           }
       }

       /// <summary>
       /// Gets resource information for vendor. This is a string of format:
       /// resourceBaseName,resourceName.
       /// </summary>
       public override string VendorResource
       {
           get
           {
               return "GetProcPSSnapIn01,Microsoft";
           }
       }

       /// <summary>
       /// Description of this PowerShell snap-in.
       /// </summary>
       public override string Description
       {
           get
           {
               return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
           }
       }
   }

   #endregion PowerShell snap-in
}
```

## <a name="see-also"></a><span data-ttu-id="91128-131">См. также</span><span class="sxs-lookup"><span data-stu-id="91128-131">See Also</span></span>

[<span data-ttu-id="91128-132">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91128-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
