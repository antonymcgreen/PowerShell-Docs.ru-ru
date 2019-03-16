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
ms.openlocfilehash: 065214647dfa6d376b727930fe75140911095faf
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059377"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="22517-102">Методы обработки входных данных командлета</span><span class="sxs-lookup"><span data-stu-id="22517-102">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="22517-103">Командлеты необходимо переопределить один или несколько методов, описанных в этом разделе для выполнения своей работы обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="22517-103">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span> <span data-ttu-id="22517-104">Эти методы позволяют командлет для выполнения предварительной обработки операций, входной операций обработки и постобработки операций.</span><span class="sxs-lookup"><span data-stu-id="22517-104">These methods allow the cmdlet to perform pre-processing operations, input processing operations, and post-processing operations.</span></span> <span data-ttu-id="22517-105">Эти методы позволяют для остановки обработки командлета.</span><span class="sxs-lookup"><span data-stu-id="22517-105">These methods also allow you to stop cmdlet processing.</span></span>

## <a name="pre-processing-tasks"></a><span data-ttu-id="22517-106">Задачи предварительной обработки</span><span class="sxs-lookup"><span data-stu-id="22517-106">Pre-Processing Tasks</span></span>

<span data-ttu-id="22517-107">Командлеты должны переопределять [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод, чтобы добавить любой операции предварительно обработки, которые являются допустимыми для всех записей, которые будут обрабатываться позднее с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="22517-107">Cmdlets should override the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span> <span data-ttu-id="22517-108">Когда Windows PowerShell обрабатывает конвейер команд, Windows PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере.</span><span class="sxs-lookup"><span data-stu-id="22517-108">When Windows PowerShell processes a command pipeline, Windows PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span> <span data-ttu-id="22517-109">Дополнительные сведения о том, как Windows PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span><span class="sxs-lookup"><span data-stu-id="22517-109">For more information about how Windows PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span></span>

<span data-ttu-id="22517-110">Следующий код показывает реализацию [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод.</span><span class="sxs-lookup"><span data-stu-id="22517-110">The following code shows an implementation of the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the BeginProcessing template."
  WriteObject("This is a test of the BeginProcessing template.");
}
```

<span data-ttu-id="22517-111">Более подробный пример использования [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод, см. в разделе [SelectStr руководстве](./selectstr-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="22517-111">For a more detailed example of how to use the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method, see [SelectStr Tutorial](./selectstr-tutorial.md).</span></span> <span data-ttu-id="22517-112">В этом руководстве **выберите Str** командлет использует [System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) метод для генерации регулярное выражение, которое будет использоваться для поиска записей обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="22517-112">In this tutorial, the **Select-Str** cmdlet uses the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method to generate the regular expression that is used to search the input processing records.</span></span>

## <a name="input-processing-tasks"></a><span data-ttu-id="22517-113">Входные данные задачи обработки</span><span class="sxs-lookup"><span data-stu-id="22517-113">Input Processing Tasks</span></span>

<span data-ttu-id="22517-114">Командлеты можно переопределить [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод для обработки входных данных, который отправляется в командлет.</span><span class="sxs-lookup"><span data-stu-id="22517-114">Cmdlets can override the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method to process the input that is sent to the cmdlet.</span></span> <span data-ttu-id="22517-115">Когда Windows PowerShell обрабатывает конвейер команд, этот метод вызывается в Windows PowerShell для каждой входной записи, который обрабатывается с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="22517-115">When Windows PowerShell processes a command pipeline, Windows PowerShell calls this method for each input record that is processed by the cmdlet.</span></span> <span data-ttu-id="22517-116">Дополнительные сведения о том, как Windows PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span><span class="sxs-lookup"><span data-stu-id="22517-116">For more information about how Windows PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span></span>

<span data-ttu-id="22517-117">Следующий код показывает реализацию [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод.</span><span class="sxs-lookup"><span data-stu-id="22517-117">The following code shows an implementation of the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the ProcessRecord template."
  WriteObject("This is a test of the ProcessRecord template.");
}
```

<span data-ttu-id="22517-118">Более подробный пример использования [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод, см. в разделе [SelectStr руководстве](./selectstr-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="22517-118">For a more detailed example of how to use the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method, see [SelectStr Tutorial](./selectstr-tutorial.md).</span></span>

## <a name="post-processing-tasks"></a><span data-ttu-id="22517-119">После обработки задач</span><span class="sxs-lookup"><span data-stu-id="22517-119">Post-Processing Tasks</span></span>

<span data-ttu-id="22517-120">Командлеты должны переопределять [System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) метод, чтобы добавить любые операции постобработки, которые являются допустимыми для всех записей, которые были обработаны с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="22517-120">Cmdlets should override the [System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span> <span data-ttu-id="22517-121">Например, командлет может потребоваться очистить объектные переменные после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="22517-121">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="22517-122">Когда Windows PowerShell обрабатывает конвейер команд, Windows PowerShell этот метод вызывается один раз для каждого экземпляра командлету в конвейере.</span><span class="sxs-lookup"><span data-stu-id="22517-122">When Windows PowerShell processes a command pipeline, Windows PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span> <span data-ttu-id="22517-123">Тем не менее, важно помнить, что среда выполнения Windows PowerShell не вызовет [System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) метод, если командлет отменяется середине до его обработки ввода, или если завершающей в любой части командлета возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="22517-123">However, it is important to remember that the Windows PowerShell runtime will not call the [System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="22517-124">По этой причине следует реализовать полный командлет, который требует очистки объектов [System.IDisposable](/dotnet/api/System.IDisposable) шаблону, в том числе метод завершения, таким образом, чтобы среда выполнения может вызвать оба [ System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) и [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) методы в конце обработки.</span><span class="sxs-lookup"><span data-stu-id="22517-124">For this reason, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the [System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span> <span data-ttu-id="22517-125">Дополнительные сведения о том, как Windows PowerShell вызывает конвейер команд, см. в разделе [жизненного цикла обработки командлета](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span><span class="sxs-lookup"><span data-stu-id="22517-125">For more information about how Windows PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span></span>

<span data-ttu-id="22517-126">Следующий код показывает реализацию [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод.</span><span class="sxs-lookup"><span data-stu-id="22517-126">The following code shows an implementation of the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the EndProcessing template."
  WriteObject("This is a test of the EndProcessing template.");
}
```

<span data-ttu-id="22517-127">Более подробный пример использования [System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) метод, см. в разделе [SelectStr руководстве](./selectstr-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="22517-127">For a more detailed example of how to use the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method, see [SelectStr Tutorial](./selectstr-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22517-128">См. также</span><span class="sxs-lookup"><span data-stu-id="22517-128">See Also</span></span>

[<span data-ttu-id="22517-129">System.Management.Automation.Cmdlet.Beginprocessing%2A? Displayproperty = Fullname</span><span class="sxs-lookup"><span data-stu-id="22517-129">System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname</span></span>](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)

[<span data-ttu-id="22517-130">System.Management.Automation.Cmdlet.Processrecord%2A? Displayproperty = Fullname</span><span class="sxs-lookup"><span data-stu-id="22517-130">System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname</span></span>](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)

[<span data-ttu-id="22517-131">System.Management.Automation.Cmdlet.Endprocessing%2A? Displayproperty = Fullname</span><span class="sxs-lookup"><span data-stu-id="22517-131">System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname</span></span>](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)

[<span data-ttu-id="22517-132">System.IDisposable</span><span class="sxs-lookup"><span data-stu-id="22517-132">System.IDisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="22517-133">Оболочка Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="22517-133">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
