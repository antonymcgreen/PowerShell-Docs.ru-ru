---
title: Пример StopProcessSample01 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bed607-369b-4507-87fa-f6011c2f1970
caps.latest.revision: 9
ms.openlocfilehash: 2ce146df05ef876d9c17f560628ebac2c39e57bf
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059207"
---
# <a name="stopprocesssample01-sample"></a><span data-ttu-id="75cb4-102">Пример командлета StopProcessSample01</span><span class="sxs-lookup"><span data-stu-id="75cb4-102">StopProcessSample01 Sample</span></span>

<span data-ttu-id="75cb4-103">В этом примере показано, как создать командлет, который запрашивает отзывы от пользователя, прежде чем она пытается остановить процесс, а также способы реализации `PassThru` параметр, указывающий, что пользователь хочет командлет вернуть объект.</span><span class="sxs-lookup"><span data-stu-id="75cb4-103">This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter indicating that the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="75cb4-104">Этот командлет аналогичен `Stop-Process` командлет, предоставляемые Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="75cb4-104">This cmdlet is similar to the `Stop-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

### <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="75cb4-105">Как построить образец с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75cb4-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="75cb4-106">С помощью Windows PowerShell 2.0 установлен пакет SDK перейдите к папке StopProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="75cb4-106">With the Windows PowerShell 2.0 SDK installed, navigate to the StopProcessSample01 folder.</span></span> <span data-ttu-id="75cb4-107">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="75cb4-107">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span></span>

2. <span data-ttu-id="75cb4-108">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="75cb4-108">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="75cb4-109">Пример проекта откроется в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75cb4-109">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="75cb4-110">В **построения** меню, выберите **построить решение**.</span><span class="sxs-lookup"><span data-stu-id="75cb4-110">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="75cb4-111">Библиотеки для образца будет располагаться в папках \bin или \bin\debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75cb4-111">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="75cb4-112">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="75cb4-112">How to run the sample</span></span>

1. <span data-ttu-id="75cb4-113">Создайте следующую папку модуля:</span><span class="sxs-lookup"><span data-stu-id="75cb4-113">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/StopProcessSample01`

2. <span data-ttu-id="75cb4-114">Скопируйте сборку образца в папке модуля.</span><span class="sxs-lookup"><span data-stu-id="75cb4-114">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="75cb4-115">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75cb4-115">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="75cb4-116">Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75cb4-116">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module stopprossessample01`

5. <span data-ttu-id="75cb4-117">Выполните следующую команду, чтобы запустить командлет:</span><span class="sxs-lookup"><span data-stu-id="75cb4-117">Run the following command to run the cmdlet:</span></span>

    `stop-proc`

## <a name="requirements"></a><span data-ttu-id="75cb4-118">Требования</span><span class="sxs-lookup"><span data-stu-id="75cb4-118">Requirements</span></span>

<span data-ttu-id="75cb4-119">В этом примере требуется Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="75cb4-119">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="75cb4-120">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="75cb4-120">Demonstrates</span></span>

<span data-ttu-id="75cb4-121">В этом примере демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="75cb4-121">This sample demonstrates the following.</span></span>

- <span data-ttu-id="75cb4-122">Объявление класса командлет с помощью атрибута командлет.</span><span class="sxs-lookup"><span data-stu-id="75cb4-122">Declaring a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="75cb4-123">Объявление параметров командлета с помощью параметра атрибута.</span><span class="sxs-lookup"><span data-stu-id="75cb4-123">Declaring a cmdlet parameters by using the Parameter attribute.</span></span>

- <span data-ttu-id="75cb4-124">Вызов метода ShouldProcess запросит подтверждение.</span><span class="sxs-lookup"><span data-stu-id="75cb4-124">Calling the ShouldProcess method to request confirmation.</span></span>

- <span data-ttu-id="75cb4-125">Реализация `PassThru` параметр, указывающий, если пользователь хочет командлет для возвращения объекта.</span><span class="sxs-lookup"><span data-stu-id="75cb4-125">Implementing a `PassThru` parameter that indicates if the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="75cb4-126">По умолчанию этот командлет возвращает объект в конвейер.</span><span class="sxs-lookup"><span data-stu-id="75cb4-126">By default, this cmdlet does not return an object to the pipeline.</span></span>

## <a name="example"></a><span data-ttu-id="75cb4-127">Пример</span><span class="sxs-lookup"><span data-stu-id="75cb4-127">Example</span></span>

<span data-ttu-id="75cb4-128">В этом примере показано, как реализовать `PassThru` параметр, который указывает, что пользователь хочет командлет возвращает объект, и как запрос на отзыв пользователя путем вызовов к `ShouldProcess` и `ShouldContinue` методы.</span><span class="sxs-lookup"><span data-stu-id="75cb4-128">This sample shows how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object, and how to request user feedback by calls to the `ShouldProcess` and `ShouldContinue` methods.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Collections;
using Win32Exception = System.ComponentModel.Win32Exception;
using System.Management.Automation;    // Windows PowerShell namespace
using System.Globalization;

namespace Microsoft.Samples.PowerShell.Commands
{
   #region StopProcCommand

    /// <summary>
   /// This class implements the stop-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsLifecycle.Stop, "Proc",
       SupportsShouldProcess = true)]
   public class StopProcCommand : Cmdlet
   {
       #region Parameters

      /// <summary>
      /// This parameter provides the list of process names on
      /// which the Stop-Proc cmdlet will work.
      /// </summary>
       [Parameter(
          Position = 0,
          Mandatory = true,
          ValueFromPipeline = true,
          ValueFromPipelineByPropertyName = true
       )]
       public string[] Name
       {
           get { return processNames; }
           set { processNames = value; }
       }
       private string[] processNames;

       /// <summary>
       /// This parameter overrides the ShouldContinue call to force
       /// the cmdlet to stop its operation. This parameter should always
       /// be used with caution.
       /// </summary>
       [Parameter]
       public SwitchParameter Force
       {
           get { return force; }
           set { force = value; }
       }
       private bool force;

       /// <summary>
       /// This parameter indicates that the cmdlet should return
       /// an object to the pipeline after the processing has been
       /// completed.
       /// </summary>
       [Parameter]
       public SwitchParameter PassThru
       {
           get { return passThru; }
           set { passThru = value; }
       }
       private bool passThru;

       #endregion Parameters

       #region Cmdlet Overrides

       /// <summary>
       /// The ProcessRecord method does the following for each of the
       /// requested process names:
       /// 1) Check that the process is not a critical process.
       /// 2) Attempt to stop that process.
       /// If no process is requested then nothing occurs.
       /// </summary>
       protected override void ProcessRecord()
       {
           foreach (string name in processNames)
           {
               // For every process name passed to the cmdlet, get the associated
               // processes.
               // Write a nonterminating error for failure to retrieve
               // a process.
               Process[] processes;

               try
               {
                   processes = Process.GetProcessesByName(name);
               }
               catch (InvalidOperationException ioe)
               {
                   WriteError(new ErrorRecord(ioe,"UnableToAccessProcessByName",
                       ErrorCategory.InvalidOperation, name));

                   continue;
               }

               // Try to stop the processes that have been retrieved.
               foreach (Process process in processes)
               {
                   string processName;

                   try
                   {
                       processName = process.ProcessName;
                   }
                   catch (Win32Exception e)
                   {
                      WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                                           ErrorCategory.ReadError, process));
                      continue;
                   }

                   // Confirm the operation with the user first.
                   // This is always false if the WhatIf parameter is set.
                   if (!ShouldProcess(string.Format(CultureInfo.CurrentCulture,"{0} ({1})", processName,
                               process.Id)))
                   {
                       continue;
                   }

                   // Make sure that the user really wants to stop a critical
                   // process that could possibly stop the computer.
                   bool criticalProcess =
                       criticalProcessNames.Contains(processName.ToLower(CultureInfo.CurrentCulture));

                   if (criticalProcess &&!force)
                   {
                       string message = String.Format
                           (CultureInfo.CurrentCulture,
                                "The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                                    processName);

                       // It is possible that the ProcessRecord method is called
                       // multiple times when objects are received as inputs from
                       // the pipeline. So to retain YesToAll and NoToAll input that
                       // the user may enter across multiple calls to this function,
                       // they are stored as private members of the cmdlet.
                       if (!ShouldContinue(message, "Warning!",
                                               ref yesToAll, ref noToAll))
                       {
                           continue;
                       }
                   } // if (criticalProcess...

                   // Stop the named process.
                   try
                   {
                       process.Kill();
                   }
                   catch (Exception e)
                   {
                       if ((e is Win32Exception) || (e is SystemException) ||
                          (e is InvalidOperationException))
                       {
                           // This process could not be stopped so write
                           // a nonterminating error.
                           WriteError(new ErrorRecord(e, "CouldNotStopProcess",
                                           ErrorCategory.CloseError, process));
                           continue;
                       } // if ((e is...
                       else throw;
                   } // catch

                   // If the PassThru parameter is
                   // specified, return the terminated process.
                   if (passThru)
                   {
                       WriteObject(process);
                   }
               } // foreach (Process...
           } // foreach (string...
       } // ProcessRecord

       #endregion Cmdlet Overrides

       #region Private Data

       private bool yesToAll, noToAll;

       /// <summary>
       /// Partial list of critical processes that should not be
       /// stopped.  Lower case is used for case insensitive matching.
       /// </summary>
       private ArrayList criticalProcessNames = new ArrayList(
          new string[] { "system", "winlogon", "spoolsv" }
       );

       #endregion Private Data

   } // StopProcCommand

   #endregion StopProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="75cb4-129">См. также</span><span class="sxs-lookup"><span data-stu-id="75cb4-129">See Also</span></span>

[<span data-ttu-id="75cb4-130">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75cb4-130">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
