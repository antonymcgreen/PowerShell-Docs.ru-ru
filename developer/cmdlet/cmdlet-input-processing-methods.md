---
title: Методы обработки ввода, командлет | Документация Майкрософт
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
ms.sourcegitcommit: 00cf9a99972ce40db7c25b9a3fc6152dec6bddb6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64670304"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="3948a-102">Методы обработки входных данных командлета</span><span class="sxs-lookup"><span data-stu-id="3948a-102">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="3948a-103">Командлеты необходимо переопределить один или несколько методов, описанных в этом разделе для выполнения своей работы обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="3948a-103">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span>
<span data-ttu-id="3948a-104">Эти методы позволяют выполнять операции предварительной обработки, обработки ввода и завершающей обработки командлета.</span><span class="sxs-lookup"><span data-stu-id="3948a-104">These methods allow the cmdlet to perform operations of pre-processing, input processing, and post-processing.</span></span>
<span data-ttu-id="3948a-105">Эти методы позволяют для остановки обработки командлета.</span><span class="sxs-lookup"><span data-stu-id="3948a-105">These methods also allow you to stop cmdlet processing.</span></span>
<span data-ttu-id="3948a-106">Более подробный пример использования этих методов, см. в разделе [SelectStr руководстве](selectstr-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="3948a-106">For a more detailed example of how to use these methods, see [SelectStr Tutorial](selectstr-tutorial.md).</span></span>

## <a name="pre-processing-operations"></a><span data-ttu-id="3948a-107">Перед обработкой операции</span><span class="sxs-lookup"><span data-stu-id="3948a-107">Pre-Processing Operations</span></span>

<span data-ttu-id="3948a-108">Командлеты должны переопределять [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод, чтобы добавить любой операции предварительно обработки, которые являются допустимыми для всех записей, которые будут обрабатываться позднее с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="3948a-108">Cmdlets should override the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span>
<span data-ttu-id="3948a-109">Когда PowerShell обрабатывает конвейер команд, PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере.</span><span class="sxs-lookup"><span data-stu-id="3948a-109">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="3948a-110">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3948a-110">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="3948a-111">Следующий код показывает реализацию метода BeginProcessing.</span><span class="sxs-lookup"><span data-stu-id="3948a-111">The following code shows an implementation of the BeginProcessing method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a><span data-ttu-id="3948a-112">Операции обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="3948a-112">Input Processing Operations</span></span>

<span data-ttu-id="3948a-113">Командлеты можно переопределить [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки входных данных, который отправляется в командлет.</span><span class="sxs-lookup"><span data-stu-id="3948a-113">Cmdlets can override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the input that is sent to the cmdlet.</span></span>
<span data-ttu-id="3948a-114">Когда PowerShell обрабатывает конвейер команд, PowerShell вызывает этот метод для каждой входной записи, который обрабатывается с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="3948a-114">When PowerShell processes a command pipeline, PowerShell calls this method for each input record that is processed by the cmdlet.</span></span>
<span data-ttu-id="3948a-115">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3948a-115">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="3948a-116">Следующий код показывает реализацию метода ProcessRecord.</span><span class="sxs-lookup"><span data-stu-id="3948a-116">The following code shows an implementation of the ProcessRecord method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a><span data-ttu-id="3948a-117">После обработки операции</span><span class="sxs-lookup"><span data-stu-id="3948a-117">Post-Processing Operations</span></span>

<span data-ttu-id="3948a-118">Командлеты должны переопределять [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод, чтобы добавить любые операции постобработки, которые являются допустимыми для всех записей, которые были обработаны с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="3948a-118">Cmdlets should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span>
<span data-ttu-id="3948a-119">Например, командлет может потребоваться очистить объектные переменные после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="3948a-119">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="3948a-120">Когда PowerShell обрабатывает конвейер команд, PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере.</span><span class="sxs-lookup"><span data-stu-id="3948a-120">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="3948a-121">Тем не менее важно помнить, что среда PowerShell не вызовет метод EndProcessing если командлет середине отменяется до его обработки ввода, или если происходит неустранимая ошибка в любой части командлета.</span><span class="sxs-lookup"><span data-stu-id="3948a-121">However, it is important to remember that the PowerShell runtime will not call the EndProcessing method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span>
<span data-ttu-id="3948a-122">По этой причине следует реализовать полный командлет, который требует очистки объектов [System.IDisposable](/dotnet/api/System.IDisposable) шаблону, в том числе метод завершения, таким образом, среда выполнения может вызывать оба EndProcessing и [ System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) методы в конце обработки.</span><span class="sxs-lookup"><span data-stu-id="3948a-122">For this reason, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the EndProcessing and [System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>
<span data-ttu-id="3948a-123">Дополнительные сведения о том, как PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3948a-123">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="3948a-124">Следующий код показывает реализацию метода EndProcessing.</span><span class="sxs-lookup"><span data-stu-id="3948a-124">The following code shows an implementation of the EndProcessing method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a><span data-ttu-id="3948a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3948a-125">See Also</span></span>

[<span data-ttu-id="3948a-126">System.Management.Automation.Cmdlet.BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="3948a-126">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="3948a-127">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="3948a-127">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="3948a-128">System.Management.Automation.Cmdlet.EndProcessing</span><span class="sxs-lookup"><span data-stu-id="3948a-128">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="3948a-129">Учебник SelectStr</span><span class="sxs-lookup"><span data-stu-id="3948a-129">SelectStr Tutorial</span></span>](selectstr-tutorial.md)

[<span data-ttu-id="3948a-130">System.IDisposable</span><span class="sxs-lookup"><span data-stu-id="3948a-130">System.IDisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="3948a-131">Оболочка Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3948a-131">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
