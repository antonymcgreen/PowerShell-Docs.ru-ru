---
title: Методы обработки входных данных командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual methods (PowerShell SDK]
ms.assetid: b0bb8172-c9fa-454b-9f1b-57c3fe60671b
caps.latest.revision: 12
ms.openlocfilehash: a28c8d3df19bc72bf338d6abc4e02768c5097209
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369873"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="75935-102">Методы обработки входных данных командлета</span><span class="sxs-lookup"><span data-stu-id="75935-102">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="75935-103">Командлеты должны переопределять один или несколько методов обработки ввода, описанных в этом разделе, для выполнения их работы.</span><span class="sxs-lookup"><span data-stu-id="75935-103">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span>
<span data-ttu-id="75935-104">Эти методы позволяют командлету выполнять операции предварительной обработки, обработки входных данных и последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="75935-104">These methods allow the cmdlet to perform operations of pre-processing, input processing, and post-processing.</span></span>
<span data-ttu-id="75935-105">Эти методы также позволяют прерывать обработку командлетов.</span><span class="sxs-lookup"><span data-stu-id="75935-105">These methods also allow you to stop cmdlet processing.</span></span>
<span data-ttu-id="75935-106">Более подробный пример использования этих методов см. в разделе Учебник по [селектстр](selectstr-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="75935-106">For a more detailed example of how to use these methods, see [SelectStr Tutorial](selectstr-tutorial.md).</span></span>

## <a name="pre-processing-operations"></a><span data-ttu-id="75935-107">Операции предварительной обработки</span><span class="sxs-lookup"><span data-stu-id="75935-107">Pre-Processing Operations</span></span>

<span data-ttu-id="75935-108">Командлеты должны переопределять метод [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) для добавления любых операций предварительной обработки, допустимых для всех записей, которые будут обрабатываться этим командлетом позже.</span><span class="sxs-lookup"><span data-stu-id="75935-108">Cmdlets should override the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span>
<span data-ttu-id="75935-109">Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод один раз для каждого экземпляра командлета в конвейере.</span><span class="sxs-lookup"><span data-stu-id="75935-109">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="75935-110">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="75935-110">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="75935-111">В следующем коде показана реализация метода BeginProcessing.</span><span class="sxs-lookup"><span data-stu-id="75935-111">The following code shows an implementation of the BeginProcessing method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a><span data-ttu-id="75935-112">Операции обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="75935-112">Input Processing Operations</span></span>

<span data-ttu-id="75935-113">Командлеты могут переопределять метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) для обработки входных данных, отправляемых в командлет.</span><span class="sxs-lookup"><span data-stu-id="75935-113">Cmdlets can override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the input that is sent to the cmdlet.</span></span>
<span data-ttu-id="75935-114">Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод для каждой входной записи, обрабатываемой командлетом.</span><span class="sxs-lookup"><span data-stu-id="75935-114">When PowerShell processes a command pipeline, PowerShell calls this method for each input record that is processed by the cmdlet.</span></span>
<span data-ttu-id="75935-115">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="75935-115">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="75935-116">В следующем коде показана реализация метода ProcessRecord.</span><span class="sxs-lookup"><span data-stu-id="75935-116">The following code shows an implementation of the ProcessRecord method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a><span data-ttu-id="75935-117">Операции, выполняемые после обработки</span><span class="sxs-lookup"><span data-stu-id="75935-117">Post-Processing Operations</span></span>

<span data-ttu-id="75935-118">Командлеты должны переопределять метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) для добавления любых операций последующей обработки, допустимых для всех записей, обработанных командлетом.</span><span class="sxs-lookup"><span data-stu-id="75935-118">Cmdlets should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span>
<span data-ttu-id="75935-119">Например, командлету может потребоваться очистить переменные объекта после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="75935-119">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="75935-120">Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод один раз для каждого экземпляра командлета в конвейере.</span><span class="sxs-lookup"><span data-stu-id="75935-120">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="75935-121">Однако важно помнить, что среда выполнения PowerShell не будет вызывать метод EndProcessing, если посрединное значение командлета отменяется через входную обработку или если в какой-либо части командлета возникает неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="75935-121">However, it is important to remember that the PowerShell runtime will not call the EndProcessing method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span>
<span data-ttu-id="75935-122">По этой причине командлет, требующий очистки объектов, должен реализовать полный шаблон [System. IDisposable](/dotnet/api/System.IDisposable) , включая метод завершения, чтобы среда выполнения могла вызывать методы EndProcessing и [System. IDisposable. Dispose](/dotnet/api/System.IDisposable.Dispose) в конце обработки.</span><span class="sxs-lookup"><span data-stu-id="75935-122">For this reason, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the EndProcessing and [System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>
<span data-ttu-id="75935-123">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненный цикл обработки командлетов](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="75935-123">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="75935-124">В следующем коде показана реализация метода EndProcessing.</span><span class="sxs-lookup"><span data-stu-id="75935-124">The following code shows an implementation of the EndProcessing method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a><span data-ttu-id="75935-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="75935-125">See Also</span></span>

[<span data-ttu-id="75935-126">System. Management. Automation. командлет. BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="75935-126">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="75935-127">System. Management. Automation. командлет. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="75935-127">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="75935-128">System. Management. Automation. командлет. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="75935-128">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="75935-129">Руководство по Селектстр</span><span class="sxs-lookup"><span data-stu-id="75935-129">SelectStr Tutorial</span></span>](selectstr-tutorial.md)

[<span data-ttu-id="75935-130">System.IDisposable</span><span class="sxs-lookup"><span data-stu-id="75935-130">System.IDisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="75935-131">Пакет SDK оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75935-131">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
