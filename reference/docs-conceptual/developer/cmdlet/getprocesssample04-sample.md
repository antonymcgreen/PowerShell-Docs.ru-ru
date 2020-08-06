---
title: Пример GetProcessSample04 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4858c44302f7315625be02dd0dc1d335b9c3f158
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774428"
---
# <a name="getprocesssample04-sample"></a><span data-ttu-id="c5069-102">Пример командлета GetProcessSample04</span><span class="sxs-lookup"><span data-stu-id="c5069-102">GetProcessSample04 Sample</span></span>

<span data-ttu-id="c5069-103">В этом примере показано, как реализовать командлет, который получает процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c5069-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="c5069-104">Она создает неустранимую ошибку в случае возникновения ошибки при получении процесса.</span><span class="sxs-lookup"><span data-stu-id="c5069-104">It generates a nonterminating error if an error occurs while retrieving a process.</span></span> <span data-ttu-id="c5069-105">Этот командлет является упрощенной версией `Get-Process` командлета, предоставляемого Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="c5069-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="c5069-106">Как создать пример с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c5069-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="c5069-107">С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку GetProcessSample04</span><span class="sxs-lookup"><span data-stu-id="c5069-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample04 folder.</span></span> <span data-ttu-id="c5069-108">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span><span class="sxs-lookup"><span data-stu-id="c5069-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span></span>

2. <span data-ttu-id="c5069-109">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="c5069-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="c5069-110">Откроется пример проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c5069-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="c5069-111">В меню **Построение** выберите команду **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="c5069-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="c5069-112">Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5069-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="c5069-113">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="c5069-113">How to run the sample</span></span>

1. <span data-ttu-id="c5069-114">Создайте следующую папку модуля:</span><span class="sxs-lookup"><span data-stu-id="c5069-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. <span data-ttu-id="c5069-115">Скопируйте пример сборки в папку Module.</span><span class="sxs-lookup"><span data-stu-id="c5069-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="c5069-116">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5069-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="c5069-117">Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c5069-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample04`

5. <span data-ttu-id="c5069-118">Выполните следующую команду, чтобы запустить командлет:</span><span class="sxs-lookup"><span data-stu-id="c5069-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="c5069-119">Требования</span><span class="sxs-lookup"><span data-stu-id="c5069-119">Requirements</span></span>

<span data-ttu-id="c5069-120">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="c5069-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c5069-121">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="c5069-121">Demonstrates</span></span>

<span data-ttu-id="c5069-122">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="c5069-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="c5069-123">Объявление класса командлета с помощью атрибута командлета.</span><span class="sxs-lookup"><span data-stu-id="c5069-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="c5069-124">Объявление параметра командлета с помощью атрибута Parameter.</span><span class="sxs-lookup"><span data-stu-id="c5069-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="c5069-125">Указание расположения параметра.</span><span class="sxs-lookup"><span data-stu-id="c5069-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="c5069-126">Указание того, что параметр принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="c5069-126">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="c5069-127">Входные данные могут быть взяты из объекта или значения из свойства объекта, имя свойства которого совпадает с именем параметра.</span><span class="sxs-lookup"><span data-stu-id="c5069-127">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="c5069-128">Объявление атрибута проверки для входных параметров.</span><span class="sxs-lookup"><span data-stu-id="c5069-128">Declaring a validation attribute for the parameter input.</span></span>

- <span data-ttu-id="c5069-129">Перехват незавершающей ошибки и запись сообщения об ошибке в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="c5069-129">Trapping a nonterminating error and writing an error message to the error stream.</span></span>

## <a name="example"></a><span data-ttu-id="c5069-130">Пример</span><span class="sxs-lookup"><span data-stu-id="c5069-130">Example</span></span>

<span data-ttu-id="c5069-131">В этом примере показано, как создать командлет, который обрабатывает неустранимые ошибки и записывает сообщения об ошибках в поток ошибок.</span><span class="sxs-lookup"><span data-stu-id="c5069-131">This sample shows how to create a cmdlet that handles nonterminating errors and writes error messages to the error stream.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c5069-132">См. также</span><span class="sxs-lookup"><span data-stu-id="c5069-132">See Also</span></span>

[<span data-ttu-id="c5069-133">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5069-133">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
