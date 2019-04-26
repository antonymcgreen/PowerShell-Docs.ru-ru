---
title: Как переопределить методы обработки ввода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1ad921-5816-4937-acf1-ed4760fae740
caps.latest.revision: 8
ms.openlocfilehash: cfee55576518cf9ce38501192872ce94054f5213
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067949"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="c3b0a-102">Как переопределить методы обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="c3b0a-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="c3b0a-103">Эти примеры показывают, как перезаписать методы в командлет обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="c3b0a-104">Эти методы используются для выполнения следующих операций:</span><span class="sxs-lookup"><span data-stu-id="c3b0a-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="c3b0a-105">[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод используется для выполнения одноразового запуска операций, которые являются допустимыми для всех объектов, обработанных с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-105">The [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="c3b0a-106">Среда выполнения Windows PowerShell, этот метод вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="c3b0a-107">[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод используется для обработки объектов, переданных в командлет.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-107">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="c3b0a-108">Среда выполнения Windows PowerShell этот метод вызывается для каждого объекта, переданного в командлет.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="c3b0a-109">[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод используется для выполнения операций обработки одноразовый post.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-109">The [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="c3b0a-110">Среда выполнения Windows PowerShell, этот метод вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="c3b0a-111">Чтобы переопределить метод BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="c3b0a-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="c3b0a-112">Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-112">Declare a protected override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="c3b0a-113">Следующий класс печатает пример сообщения.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-113">The following class prints a sample message.</span></span> <span data-ttu-id="c3b0a-114">Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.BeginProcessing ](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="c3b0a-115">Чтобы переопределить метод ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="c3b0a-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="c3b0a-116">Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-116">Declare a protected override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="c3b0a-117">Следующий класс печатает пример сообщения.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-117">The following class prints a sample message.</span></span> <span data-ttu-id="c3b0a-118">Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="c3b0a-119">Чтобы переопределить метод EndProcessing</span><span class="sxs-lookup"><span data-stu-id="c3b0a-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="c3b0a-120">Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-120">Declare a protected override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="c3b0a-121">Следующий класс печатает образец.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-121">The following class prints a sample.</span></span> <span data-ttu-id="c3b0a-122">Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.EndProcessing ](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="c3b0a-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a><span data-ttu-id="c3b0a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c3b0a-123">See Also</span></span>

[<span data-ttu-id="c3b0a-124">System.Management.Automation.Cmdlet.BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="c3b0a-124">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="c3b0a-125">System.Management.Automation.Cmdlet.EndProcessing</span><span class="sxs-lookup"><span data-stu-id="c3b0a-125">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="c3b0a-126">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="c3b0a-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="c3b0a-127">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3b0a-127">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
