---
title: Пример GetProcessSample01 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b48bf80-cbf0-4cb1-8d5b-3b8d06196598
caps.latest.revision: 10
ms.openlocfilehash: 00190c7350cb0f1cfc5c389b56e48e9397480446
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859840"
---
# <a name="getprocesssample01-sample"></a><span data-ttu-id="1bf2b-102">Пример командлета GetProcessSample01</span><span class="sxs-lookup"><span data-stu-id="1bf2b-102">GetProcessSample01 Sample</span></span>

<span data-ttu-id="1bf2b-103">В этом примере показано, как выполнить командлет, который извлекает процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="1bf2b-104">Этот командлет представляет упрощенную версию `Get-Process` командлет, предоставляемый Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-104">This cmdlet is a simplified version of the `Get-Process` cmdlet that is provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="1bf2b-105">Как построить образец с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="1bf2b-106">С помощью Windows PowerShell 2.0 установлен пакет SDK перейдите к папке GetProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-106">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample01 folder.</span></span> <span data-ttu-id="1bf2b-107">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-107">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.</span></span>

2. <span data-ttu-id="1bf2b-108">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="1bf2b-108">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="1bf2b-109">Пример проекта откроется в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-109">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="1bf2b-110">В **построения** меню, выберите **построить решение**.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-110">In the **Build** menu, select **Build Solution**.</span></span>

  <span data-ttu-id="1bf2b-111">Библиотеки для образца будет располагаться в папках \bin или \bin\debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-111">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="1bf2b-112">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="1bf2b-112">How to run the sample</span></span>

1. <span data-ttu-id="1bf2b-113">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-113">Open a Command Prompt window.</span></span>

2. <span data-ttu-id="1bf2b-114">Перейдите в каталог, содержащий пример DLL-файла.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-114">Navigate to the directory containing the sample .dll file.</span></span>

3. <span data-ttu-id="1bf2b-115">Выполнение программы installutil «GetProcessSample01.dll».</span><span class="sxs-lookup"><span data-stu-id="1bf2b-115">Run installutil "GetProcessSample01.dll".</span></span>

4. <span data-ttu-id="1bf2b-116">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-116">Start Windows PowerShell.</span></span>

5. <span data-ttu-id="1bf2b-117">Выполните следующую команду, чтобы добавить оснастку в оболочку.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-117">Run the following command to add the snap-in to the shell.</span></span>

   `Add-PSSnapin GetProcPSSnapIn01`

6. <span data-ttu-id="1bf2b-118">Введите следующую команду, чтобы запустить командлет.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-118">Enter the following command to run the cmdlet.</span></span> `get-proc`

   `get-proc`

   <span data-ttu-id="1bf2b-119">Это пример выходных данных, полученный в результате следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-119">This is a sample output that results from following these steps.</span></span>

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

## <a name="requirements"></a><span data-ttu-id="1bf2b-120">Требования</span><span class="sxs-lookup"><span data-stu-id="1bf2b-120">Requirements</span></span>

<span data-ttu-id="1bf2b-121">Этого образца необходима среда Windows PowerShell 1.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-121">This sample requires Windows PowerShell 1.0 or later.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1bf2b-122">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="1bf2b-122">Demonstrates</span></span>

<span data-ttu-id="1bf2b-123">В этом примере демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="1bf2b-124">Создание простой пример командлета.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-124">Creating a basic sample cmdlet.</span></span>

- <span data-ttu-id="1bf2b-125">Определение класса командлета с помощью атрибута командлет.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-125">Defining a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="1bf2b-126">Создание оснастки, работает с Windows PowerShell 1.0 и Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-126">Creating a snap-in that works with both Windows PowerShell 1.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="1bf2b-127">В следующих примерах используйте модули вместо оснастки, поэтому им требуется Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-127">Subsequent samples use modules instead of snap-ins so they require Windows PowerShell 2.0.</span></span>

## <a name="example"></a><span data-ttu-id="1bf2b-128">Пример</span><span class="sxs-lookup"><span data-stu-id="1bf2b-128">Example</span></span>

<span data-ttu-id="1bf2b-129">В этом примере показано, как создать простой командлет и его оснастку.</span><span class="sxs-lookup"><span data-stu-id="1bf2b-129">This sample shows how to create a simple cmdlet and its snap-in.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1bf2b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1bf2b-130">See Also</span></span>

[<span data-ttu-id="1bf2b-131">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bf2b-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)