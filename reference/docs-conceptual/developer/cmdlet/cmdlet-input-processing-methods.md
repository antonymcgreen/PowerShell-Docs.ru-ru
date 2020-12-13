---
ms.date: 09/13/2016
ms.topic: reference
title: Методы обработки входных данных командлета
description: Методы обработки входных данных командлета
ms.openlocfilehash: e1a7b58517d6285250edbf16d14810388c242218
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653393"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="60089-103">Методы обработки входных данных командлета</span><span class="sxs-lookup"><span data-stu-id="60089-103">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="60089-104">Командлеты должны переопределять один или несколько методов обработки ввода, описанных в этом разделе, для выполнения их работы.</span><span class="sxs-lookup"><span data-stu-id="60089-104">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span>
<span data-ttu-id="60089-105">Эти методы позволяют командлету выполнять операции предварительной обработки, обработки входных данных и последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="60089-105">These methods allow the cmdlet to perform operations of pre-processing, input processing, and post-processing.</span></span>
<span data-ttu-id="60089-106">Эти методы также позволяют прерывать обработку командлетов.</span><span class="sxs-lookup"><span data-stu-id="60089-106">These methods also allow you to stop cmdlet processing.</span></span>
<span data-ttu-id="60089-107">Более подробный пример использования этих методов см. в разделе Учебник по [селектстр](selectstr-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="60089-107">For a more detailed example of how to use these methods, see [SelectStr Tutorial](selectstr-tutorial.md).</span></span>

## <a name="pre-processing-operations"></a><span data-ttu-id="60089-108">Операции предварительной обработки</span><span class="sxs-lookup"><span data-stu-id="60089-108">Pre-Processing Operations</span></span>

<span data-ttu-id="60089-109">Командлеты должны переопределять метод [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) для добавления любых операций предварительной обработки, допустимых для всех записей, которые будут обрабатываться этим командлетом позже.</span><span class="sxs-lookup"><span data-stu-id="60089-109">Cmdlets should override the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span>
<span data-ttu-id="60089-110">Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод один раз для каждого экземпляра командлета в конвейере.</span><span class="sxs-lookup"><span data-stu-id="60089-110">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="60089-111">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="60089-111">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="60089-112">В следующем коде показана реализация метода BeginProcessing.</span><span class="sxs-lookup"><span data-stu-id="60089-112">The following code shows an implementation of the BeginProcessing method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a><span data-ttu-id="60089-113">Операции обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="60089-113">Input Processing Operations</span></span>

<span data-ttu-id="60089-114">Командлеты могут переопределять метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) для обработки входных данных, отправляемых в командлет.</span><span class="sxs-lookup"><span data-stu-id="60089-114">Cmdlets can override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the input that is sent to the cmdlet.</span></span>
<span data-ttu-id="60089-115">Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод для каждой входной записи, обрабатываемой командлетом.</span><span class="sxs-lookup"><span data-stu-id="60089-115">When PowerShell processes a command pipeline, PowerShell calls this method for each input record that is processed by the cmdlet.</span></span>
<span data-ttu-id="60089-116">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="60089-116">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="60089-117">В следующем коде показана реализация метода ProcessRecord.</span><span class="sxs-lookup"><span data-stu-id="60089-117">The following code shows an implementation of the ProcessRecord method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a><span data-ttu-id="60089-118">Операции, выполняемые после обработки</span><span class="sxs-lookup"><span data-stu-id="60089-118">Post-Processing Operations</span></span>

<span data-ttu-id="60089-119">Командлеты должны переопределять метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) для добавления любых операций последующей обработки, допустимых для всех записей, обработанных командлетом.</span><span class="sxs-lookup"><span data-stu-id="60089-119">Cmdlets should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span>
<span data-ttu-id="60089-120">Например, командлету может потребоваться очистить переменные объекта после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="60089-120">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="60089-121">Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод один раз для каждого экземпляра командлета в конвейере.</span><span class="sxs-lookup"><span data-stu-id="60089-121">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="60089-122">Однако важно помнить, что среда выполнения PowerShell не будет вызывать метод EndProcessing, если посрединное значение командлета отменяется через входную обработку или если в какой-либо части командлета возникает неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="60089-122">However, it is important to remember that the PowerShell runtime will not call the EndProcessing method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span>
<span data-ttu-id="60089-123">По этой причине командлет, требующий очистки объектов, должен реализовать полный шаблон [System. IDisposable](/dotnet/api/System.IDisposable) , включая метод завершения, чтобы среда выполнения могла вызывать методы EndProcessing и [System. IDisposable. Dispose](/dotnet/api/System.IDisposable.Dispose) в конце обработки.</span><span class="sxs-lookup"><span data-stu-id="60089-123">For this reason, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the EndProcessing and [System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>
<span data-ttu-id="60089-124">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="60089-124">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="60089-125">В следующем коде показана реализация метода EndProcessing.</span><span class="sxs-lookup"><span data-stu-id="60089-125">The following code shows an implementation of the EndProcessing method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a><span data-ttu-id="60089-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="60089-126">See Also</span></span>

[<span data-ttu-id="60089-127">System. Management. Automation. командлет. BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="60089-127">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="60089-128">System. Management. Automation. командлет. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="60089-128">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="60089-129">System. Management. Automation. командлет. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="60089-129">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="60089-130">Руководство по SelectStr</span><span class="sxs-lookup"><span data-stu-id="60089-130">SelectStr Tutorial</span></span>](selectstr-tutorial.md)

[<span data-ttu-id="60089-131">System.IDisposable</span><span class="sxs-lookup"><span data-stu-id="60089-131">System.IDisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="60089-132">Пакет SDK Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60089-132">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
