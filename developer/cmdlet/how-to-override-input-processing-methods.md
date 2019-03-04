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
ms.openlocfilehash: eff40a01b60985788ae0e21156fec7ec4e27fcf1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855920"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="39412-102">Как переопределить методы обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="39412-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="39412-103">Эти примеры показывают, как перезаписать методы в командлет обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="39412-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="39412-104">Эти методы используются для выполнения следующих операций:</span><span class="sxs-lookup"><span data-stu-id="39412-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="39412-105">[System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод используется для выполнения одноразового запуска операций, которые являются допустимыми для всех объектов, обработанных с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="39412-105">The [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="39412-106">Среда выполнения Windows PowerShell, этот метод вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="39412-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="39412-107">[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод используется для обработки объектов, переданных в командлет.</span><span class="sxs-lookup"><span data-stu-id="39412-107">The [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="39412-108">Среда выполнения Windows PowerShell этот метод вызывается для каждого объекта, переданного в командлет.</span><span class="sxs-lookup"><span data-stu-id="39412-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="39412-109">[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод используется для выполнения операций обработки одноразовый post.</span><span class="sxs-lookup"><span data-stu-id="39412-109">The [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="39412-110">Среда выполнения Windows PowerShell, этот метод вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="39412-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="39412-111">Чтобы переопределить метод BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="39412-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="39412-112">Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="39412-112">Declare a protected override of the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="39412-113">Следующий класс печатает пример сообщения.</span><span class="sxs-lookup"><span data-stu-id="39412-113">The following class prints a sample message.</span></span> <span data-ttu-id="39412-114">Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.Beginprocessing ](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="39412-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

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

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="39412-115">Чтобы переопределить метод ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="39412-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="39412-116">Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="39412-116">Declare a protected override of the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="39412-117">Следующий класс печатает пример сообщения.</span><span class="sxs-lookup"><span data-stu-id="39412-117">The following class prints a sample message.</span></span> <span data-ttu-id="39412-118">Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.Processrecord\* ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="39412-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

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

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="39412-119">Чтобы переопределить метод EndProcessing</span><span class="sxs-lookup"><span data-stu-id="39412-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="39412-120">Объявите защищенных переопределение метода [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="39412-120">Declare a protected override of the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="39412-121">Следующий класс печатает образец.</span><span class="sxs-lookup"><span data-stu-id="39412-121">The following class prints a sample.</span></span> <span data-ttu-id="39412-122">Чтобы использовать этот класс, изменить глагол и существительное в атрибуте командлета, измените имя класса в соответствии с новой глагол и существительное и затем добавление функциональных возможностей, требуемых для переопределение метода [System.Management.Automation.Cmdlet.Endprocessing\* ](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="39412-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="39412-123">См. также</span><span class="sxs-lookup"><span data-stu-id="39412-123">See Also</span></span>

[<span data-ttu-id="39412-124">System.Management.Automation.Cmdlet.Beginprocessing\*</span><span class="sxs-lookup"><span data-stu-id="39412-124">System.Management.Automation.Cmdlet.Beginprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="39412-125">System.Management.Automation.Cmdlet.Endprocessing\*</span><span class="sxs-lookup"><span data-stu-id="39412-125">System.Management.Automation.Cmdlet.Endprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="39412-126">System.Management.Automation.Cmdlet.Processrecord\*</span><span class="sxs-lookup"><span data-stu-id="39412-126">System.Management.Automation.Cmdlet.Processrecord\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="39412-127">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39412-127">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
