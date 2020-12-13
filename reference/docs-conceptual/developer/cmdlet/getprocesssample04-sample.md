---
ms.date: 09/13/2016
ms.topic: reference
title: Пример командлета GetProcessSample04
description: Пример командлета GetProcessSample04
ms.openlocfilehash: 4b2b7f7ed5fd87711d0d7872caaf75d453de4832
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652728"
---
# <a name="getprocesssample04-sample"></a><span data-ttu-id="ef4cb-103">Пример командлета GetProcessSample04</span><span class="sxs-lookup"><span data-stu-id="ef4cb-103">GetProcessSample04 Sample</span></span>

<span data-ttu-id="ef4cb-104">В этом примере показано, как реализовать командлет, который получает процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-104">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="ef4cb-105">Он создает неустранимую ошибку, если при получении процесса возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-105">It generates a nonterminating error if an error occurs while retrieving a process.</span></span> <span data-ttu-id="ef4cb-106">Этот командлет является упрощенной версией `Get-Process` командлета, предоставляемого Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-106">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="ef4cb-107">Как создать пример с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-107">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="ef4cb-108">С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку GetProcessSample04</span><span class="sxs-lookup"><span data-stu-id="ef4cb-108">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample04 folder.</span></span> <span data-ttu-id="ef4cb-109">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-109">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span></span>

2. <span data-ttu-id="ef4cb-110">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="ef4cb-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="ef4cb-111">Откроется пример проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-111">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="ef4cb-112">В меню **Построение** выберите команду **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-112">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="ef4cb-113">Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-113">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="ef4cb-114">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="ef4cb-114">How to run the sample</span></span>

1. <span data-ttu-id="ef4cb-115">Создайте следующую папку модуля:</span><span class="sxs-lookup"><span data-stu-id="ef4cb-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. <span data-ttu-id="ef4cb-116">Скопируйте пример сборки в папку Module.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-116">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="ef4cb-117">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="ef4cb-118">Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ef4cb-118">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample04`

5. <span data-ttu-id="ef4cb-119">Выполните следующую команду, чтобы запустить командлет:</span><span class="sxs-lookup"><span data-stu-id="ef4cb-119">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="ef4cb-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ef4cb-120">Requirements</span></span>

<span data-ttu-id="ef4cb-121">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-121">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ef4cb-122">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="ef4cb-122">Demonstrates</span></span>

<span data-ttu-id="ef4cb-123">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="ef4cb-124">Объявление класса командлета с помощью атрибута командлета.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-124">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="ef4cb-125">Объявление параметра командлета с помощью атрибута Parameter.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-125">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="ef4cb-126">Указание расположения параметра.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-126">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="ef4cb-127">Указание того, что параметр принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-127">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="ef4cb-128">Входные данные могут быть взяты из объекта или значения из свойства объекта, имя свойства которого совпадает с именем параметра.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-128">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="ef4cb-129">Объявление атрибута проверки для входных параметров.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-129">Declaring a validation attribute for the parameter input.</span></span>

- <span data-ttu-id="ef4cb-130">Перехват незавершающей ошибки и запись сообщения об ошибке в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-130">Trapping a nonterminating error and writing an error message to the error stream.</span></span>

## <a name="example"></a><span data-ttu-id="ef4cb-131">Пример</span><span class="sxs-lookup"><span data-stu-id="ef4cb-131">Example</span></span>

<span data-ttu-id="ef4cb-132">В этом примере показано, как создать командлет, который обрабатывает неустранимые ошибки и записывает сообщения об ошибках в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-132">This sample shows how to create a cmdlet that handles nonterminating errors and writes error messages to the error stream.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
    using System;
    using System.Diagnostics;
    using System.Management.Automation;      // Windows PowerShell namespace.
   #region GetProcCommand

   /// <summary>
   /// This class implements the get-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Parameters

       /// <summary>
       /// The names of the processes to act on.
       /// </summary>
       private string[] processNames;

      /// <summary>
      /// Gets or sets the list of process names on
      /// which the Get-Proc cmdlet will work.
      /// </summary>
      [Parameter(
         Position = 0,
         ValueFromPipeline = true,
         ValueFromPipelineByPropertyName = true)]
      [ValidateNotNullOrEmpty]
      public string[] Name
      {
         get { return this.processNames; }
         set { this.processNames = value; }
      }

      #endregion Parameters

      #region Cmdlet Overrides

      /// <summary>
      /// The ProcessRecord method calls the Process.GetProcesses
      /// method to retrieve the processes specified by the Name
      /// parameter. Then, the WriteObject method writes the
      /// associated processes to the pipeline.
      /// </summary>
      protected override void ProcessRecord()
      {
          // If no process names are passed to cmdlet, get all
          // processes.
          if (this.processNames == null)
          {
              WriteObject(Process.GetProcesses(), true);
          }
          else
          {
              // If process names are passed to the cmdlet, get and write
              // the associated processes.
              // If a nonterminating error occurs while retrieving processes,
              // call the WriteError method to send an error record to the
              // error stream.
              foreach (string name in this.processNames)
              {
                  Process[] processes;

                  try
                  {
                      processes = Process.GetProcessesByName(name);
                  }
                  catch (InvalidOperationException ex)
                  {
                      WriteError(new ErrorRecord(
                         ex,
                         "UnableToAccessProcessByName",
                         ErrorCategory.InvalidOperation,
                         name));
                      continue;
                  }

                  WriteObject(processes, true);
              } // foreach (string name...
          } // else
      } // ProcessRecord

      #endregion Overrides
    } // End GetProcCommand class.

   #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="ef4cb-133">См. также</span><span class="sxs-lookup"><span data-stu-id="ef4cb-133">See Also</span></span>

[<span data-ttu-id="ef4cb-134">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef4cb-134">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
