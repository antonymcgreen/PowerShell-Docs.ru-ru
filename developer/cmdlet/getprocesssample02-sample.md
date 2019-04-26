---
title: Пример GetProcessSample02 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 481f557d-3344-4d33-b2da-4736a0165181
caps.latest.revision: 7
ms.openlocfilehash: fa4cd8a724793e71b615c84a5c5a833aa92c93fc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068085"
---
# <a name="getprocesssample02-sample"></a><span data-ttu-id="89094-102">Пример командлета GetProcessSample02</span><span class="sxs-lookup"><span data-stu-id="89094-102">GetProcessSample02 Sample</span></span>

<span data-ttu-id="89094-103">В этом примере показано, как написать командлет, который извлекает процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="89094-103">This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="89094-104">Он предоставляет `Name` параметр, который может использоваться для указания процессов, которые требуется получить.</span><span class="sxs-lookup"><span data-stu-id="89094-104">It provides a `Name` parameter that can be used to specify the processes to be retrieved.</span></span> <span data-ttu-id="89094-105">Этот командлет представляет упрощенную версию `Get-Process` командлет, предоставляемые Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="89094-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="89094-106">Способы создания образца с использованием Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89094-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="89094-107">С помощью Windows PowerShell 2.0 установлен пакет SDK перейдите к папке GetProcessSample02.</span><span class="sxs-lookup"><span data-stu-id="89094-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample02 folder.</span></span> <span data-ttu-id="89094-108">Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span><span class="sxs-lookup"><span data-stu-id="89094-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span></span>

2. <span data-ttu-id="89094-109">Дважды щелкните значок файла решения (SLN).</span><span class="sxs-lookup"><span data-stu-id="89094-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="89094-110">Откроется пример проекта в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89094-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="89094-111">В **построения** меню, выберите **построить решение**.</span><span class="sxs-lookup"><span data-stu-id="89094-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="89094-112">Библиотеки для образца будет располагаться в папках \bin или \bin\debug по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89094-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="89094-113">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="89094-113">How to run the sample</span></span>

1. <span data-ttu-id="89094-114">Создайте следующую папку модуля:</span><span class="sxs-lookup"><span data-stu-id="89094-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. <span data-ttu-id="89094-115">Скопируйте сборку образца в папке модуля.</span><span class="sxs-lookup"><span data-stu-id="89094-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="89094-116">Запустите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89094-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="89094-117">Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89094-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module getprossessample02`

5. <span data-ttu-id="89094-118">Выполните следующую команду, чтобы запустить командлет:</span><span class="sxs-lookup"><span data-stu-id="89094-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="89094-119">Требования</span><span class="sxs-lookup"><span data-stu-id="89094-119">Requirements</span></span>

<span data-ttu-id="89094-120">В этом примере требуется Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="89094-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="89094-121">Демонстрирует</span><span class="sxs-lookup"><span data-stu-id="89094-121">Demonstrates</span></span>

<span data-ttu-id="89094-122">В этом примере демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="89094-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="89094-123">Объявление класса командлет, используя атрибут командлета.</span><span class="sxs-lookup"><span data-stu-id="89094-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="89094-124">Объявление параметра командлета, с помощью параметра атрибута.</span><span class="sxs-lookup"><span data-stu-id="89094-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="89094-125">Задают позицию задаваемого параметра.</span><span class="sxs-lookup"><span data-stu-id="89094-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="89094-126">Объявление атрибута проверки для входного параметра.</span><span class="sxs-lookup"><span data-stu-id="89094-126">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="89094-127">Пример</span><span class="sxs-lookup"><span data-stu-id="89094-127">Example</span></span>

<span data-ttu-id="89094-128">В этом образце показана реализация командлет Get-Proc, который включает в себя `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="89094-128">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="89094-129">См. также</span><span class="sxs-lookup"><span data-stu-id="89094-129">See Also</span></span>

[<span data-ttu-id="89094-130">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89094-130">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
