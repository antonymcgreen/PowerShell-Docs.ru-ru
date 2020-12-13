---
ms.date: 09/13/2016
ms.topic: reference
title: Пример командлета StopProcessSample01
description: Пример командлета StopProcessSample01
ms.openlocfilehash: 9024f5c66330f3a1748c28b82e91b3915e956207
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660539"
---
# <a name="stopprocesssample01-sample"></a><span data-ttu-id="32b3e-103">Пример командлета StopProcessSample01</span><span class="sxs-lookup"><span data-stu-id="32b3e-103">StopProcessSample01 Sample</span></span>

<span data-ttu-id="32b3e-104">В этом примере показано, как написать командлет, запрашивающий отзыв от пользователя перед попыткой его завершения, и как реализовать `PassThru` параметр, указывающий, что пользователь хочет, чтобы командлет возвращал объект.</span><span class="sxs-lookup"><span data-stu-id="32b3e-104">This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter indicating that the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="32b3e-105">Этот командлет похож на командлет, `Stop-Process` предоставляемый Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="32b3e-105">This cmdlet is similar to the `Stop-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

### <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="32b3e-106">Как создать пример с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="32b3e-106">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="32b3e-107">С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку StopProcessSample01</span><span class="sxs-lookup"><span data-stu-id="32b3e-107">With the Windows PowerShell 2.0 SDK installed, navigate to the StopProcessSample01 folder.</span></span> <span data-ttu-id="32b3e-108">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="32b3e-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span></span>

2. <span data-ttu-id="32b3e-109">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="32b3e-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="32b3e-110">Откроется пример проекта в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="32b3e-110">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="32b3e-111">В меню **Построение** выберите команду **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="32b3e-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="32b3e-112">Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="32b3e-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="32b3e-113">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="32b3e-113">How to run the sample</span></span>

1. <span data-ttu-id="32b3e-114">Создайте следующую папку модуля:</span><span class="sxs-lookup"><span data-stu-id="32b3e-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/StopProcessSample01`

2. <span data-ttu-id="32b3e-115">Скопируйте пример сборки в папку Module.</span><span class="sxs-lookup"><span data-stu-id="32b3e-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="32b3e-116">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="32b3e-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="32b3e-117">Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="32b3e-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module stopprossessample01`

5. <span data-ttu-id="32b3e-118">Выполните следующую команду, чтобы запустить командлет:</span><span class="sxs-lookup"><span data-stu-id="32b3e-118">Run the following command to run the cmdlet:</span></span>

    `stop-proc`

## <a name="requirements"></a><span data-ttu-id="32b3e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="32b3e-119">Requirements</span></span>

<span data-ttu-id="32b3e-120">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="32b3e-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="32b3e-121">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="32b3e-121">Demonstrates</span></span>

<span data-ttu-id="32b3e-122">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="32b3e-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="32b3e-123">Объявление класса командлета с помощью атрибута командлета.</span><span class="sxs-lookup"><span data-stu-id="32b3e-123">Declaring a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="32b3e-124">Объявление параметров командлета с помощью атрибута Parameter.</span><span class="sxs-lookup"><span data-stu-id="32b3e-124">Declaring a cmdlet parameters by using the Parameter attribute.</span></span>

- <span data-ttu-id="32b3e-125">Вызов метода ShouldProcess для запроса подтверждения.</span><span class="sxs-lookup"><span data-stu-id="32b3e-125">Calling the ShouldProcess method to request confirmation.</span></span>

- <span data-ttu-id="32b3e-126">Реализация `PassThru` параметра, указывающего, хочет ли пользователь командлет вернуть объект.</span><span class="sxs-lookup"><span data-stu-id="32b3e-126">Implementing a `PassThru` parameter that indicates if the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="32b3e-127">По умолчанию этот командлет не возвращает объект в конвейер.</span><span class="sxs-lookup"><span data-stu-id="32b3e-127">By default, this cmdlet does not return an object to the pipeline.</span></span>

## <a name="example"></a><span data-ttu-id="32b3e-128">Пример</span><span class="sxs-lookup"><span data-stu-id="32b3e-128">Example</span></span>

<span data-ttu-id="32b3e-129">В этом примере показано, как реализовать `PassThru` параметр, который указывает, что пользователь хочет, чтобы командлет возвращал объект, и как запросить отзывы пользователей по вызовам `ShouldProcess` `ShouldContinue` методов и.</span><span class="sxs-lookup"><span data-stu-id="32b3e-129">This sample shows how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object, and how to request user feedback by calls to the `ShouldProcess` and `ShouldContinue` methods.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="32b3e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="32b3e-130">See Also</span></span>

[<span data-ttu-id="32b3e-131">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32b3e-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
