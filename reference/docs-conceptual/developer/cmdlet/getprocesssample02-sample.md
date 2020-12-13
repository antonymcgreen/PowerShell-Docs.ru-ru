---
ms.date: 09/13/2016
ms.topic: reference
title: Пример командлета GetProcessSample02
description: Пример командлета GetProcessSample02
ms.openlocfilehash: a0f43806b707359cb454817341f2c4972033c46a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660518"
---
# <a name="getprocesssample02-sample"></a><span data-ttu-id="a011d-103">Пример командлета GetProcessSample02</span><span class="sxs-lookup"><span data-stu-id="a011d-103">GetProcessSample02 Sample</span></span>

<span data-ttu-id="a011d-104">В этом примере показано, как написать командлет, который получает процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a011d-104">This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="a011d-105">Он предоставляет `Name` параметр, который можно использовать для указания процессов, которые необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="a011d-105">It provides a `Name` parameter that can be used to specify the processes to be retrieved.</span></span> <span data-ttu-id="a011d-106">Этот командлет является упрощенной версией `Get-Process` командлета, предоставляемого Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="a011d-106">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="a011d-107">Как создать пример с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a011d-107">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="a011d-108">С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку GetProcessSample02</span><span class="sxs-lookup"><span data-stu-id="a011d-108">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample02 folder.</span></span> <span data-ttu-id="a011d-109">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span><span class="sxs-lookup"><span data-stu-id="a011d-109">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span></span>

2. <span data-ttu-id="a011d-110">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="a011d-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="a011d-111">Откроется пример проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a011d-111">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="a011d-112">В меню **Построение** выберите команду **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="a011d-112">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="a011d-113">Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a011d-113">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="a011d-114">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="a011d-114">How to run the sample</span></span>

1. <span data-ttu-id="a011d-115">Создайте следующую папку модуля:</span><span class="sxs-lookup"><span data-stu-id="a011d-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. <span data-ttu-id="a011d-116">Скопируйте пример сборки в папку Module.</span><span class="sxs-lookup"><span data-stu-id="a011d-116">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="a011d-117">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a011d-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="a011d-118">Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a011d-118">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module getprossessample02`

5. <span data-ttu-id="a011d-119">Выполните следующую команду, чтобы запустить командлет:</span><span class="sxs-lookup"><span data-stu-id="a011d-119">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="a011d-120">Требования</span><span class="sxs-lookup"><span data-stu-id="a011d-120">Requirements</span></span>

<span data-ttu-id="a011d-121">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="a011d-121">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a011d-122">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="a011d-122">Demonstrates</span></span>

<span data-ttu-id="a011d-123">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="a011d-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="a011d-124">Объявление класса командлета с помощью атрибута командлета.</span><span class="sxs-lookup"><span data-stu-id="a011d-124">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="a011d-125">Объявление параметра командлета с помощью атрибута Parameter.</span><span class="sxs-lookup"><span data-stu-id="a011d-125">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="a011d-126">Указание расположения параметра.</span><span class="sxs-lookup"><span data-stu-id="a011d-126">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="a011d-127">Объявление атрибута проверки для входных параметров.</span><span class="sxs-lookup"><span data-stu-id="a011d-127">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="a011d-128">Пример</span><span class="sxs-lookup"><span data-stu-id="a011d-128">Example</span></span>

<span data-ttu-id="a011d-129">В этом примере показана реализация командлета Get-Proc, который содержит `Name` параметр.</span><span class="sxs-lookup"><span data-stu-id="a011d-129">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;     // Windows PowerShell namespace

  #region GetProcCommand

  /// <summary>
  /// This class implements the get-proc cmdlet.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Parameters

    /// <summary>
    /// The names of the processes retrieved by the cmdlet.
    /// </summary>
    private string[] processNames;

    /// <summary>
    /// Gets or sets the list of process names on which
    /// the Get-Proc cmdlet will work.
    /// </summary>
    [Parameter(Position = 0)]
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
    /// associated process objects to the pipeline.
    /// </summary>
    protected override void ProcessRecord()
    {
      // If no process names are passed to the cmdlet, get all
      // processes.
      if (this.processNames == null)
      {
        WriteObject(Process.GetProcesses(), true);
      }
      else
      {
        // If process names are passed to cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames...).
    } // End ProcessRecord.
    #endregion Cmdlet Overrides
  } // End GetProcCommand class.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="a011d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a011d-130">See Also</span></span>

[<span data-ttu-id="a011d-131">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a011d-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
