---
ms.date: 09/13/2016
ms.topic: reference
title: Как переопределить методы обработки входных данных
description: Как переопределить методы обработки входных данных
ms.openlocfilehash: 4e8d71a34a1480ce63435ac6cc5dce60d4219c03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667017"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="6e52c-103">Как переопределить методы обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="6e52c-103">How to Override Input Processing Methods</span></span>

<span data-ttu-id="6e52c-104">В этих примерах показано, как перезаписать методы обработки ввода в командлете.</span><span class="sxs-lookup"><span data-stu-id="6e52c-104">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="6e52c-105">Эти методы используются для выполнения следующих операций:</span><span class="sxs-lookup"><span data-stu-id="6e52c-105">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="6e52c-106">Метод [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) используется для выполнения одноразовых операций запуска, допустимых для всех объектов, обрабатываемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="6e52c-106">The [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="6e52c-107">Среда выполнения Windows PowerShell вызывает этот метод только один раз.</span><span class="sxs-lookup"><span data-stu-id="6e52c-107">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="6e52c-108">Метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) используется для обработки объектов, передаваемых в командлет.</span><span class="sxs-lookup"><span data-stu-id="6e52c-108">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="6e52c-109">Среда выполнения Windows PowerShell вызывает этот метод для каждого объекта, передаваемого в командлет.</span><span class="sxs-lookup"><span data-stu-id="6e52c-109">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="6e52c-110">Метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) используется для выполнения операций однократной завершающей обработки.</span><span class="sxs-lookup"><span data-stu-id="6e52c-110">The [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="6e52c-111">Среда выполнения Windows PowerShell вызывает этот метод только один раз.</span><span class="sxs-lookup"><span data-stu-id="6e52c-111">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="6e52c-112">Переопределение метода BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="6e52c-112">To override the BeginProcessing method</span></span>

- <span data-ttu-id="6e52c-113">Объявите защищенное переопределение метода [System. Management. Automation. командлета. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) .</span><span class="sxs-lookup"><span data-stu-id="6e52c-113">Declare a protected override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="6e52c-114">Следующий класс выводит образец сообщения.</span><span class="sxs-lookup"><span data-stu-id="6e52c-114">The following class prints a sample message.</span></span> <span data-ttu-id="6e52c-115">Чтобы использовать этот класс, измените глагол и существительное в атрибуте командлета, измените имя класса, чтобы отразить новую глагол и существительное, а затем добавьте функциональные возможности, необходимые для переопределения метода [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) .</span><span class="sxs-lookup"><span data-stu-id="6e52c-115">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

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

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="6e52c-116">Переопределение метода ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="6e52c-116">To override the ProcessRecord method</span></span>

- <span data-ttu-id="6e52c-117">Объявите защищенное переопределение метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="6e52c-117">Declare a protected override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="6e52c-118">Следующий класс выводит образец сообщения.</span><span class="sxs-lookup"><span data-stu-id="6e52c-118">The following class prints a sample message.</span></span> <span data-ttu-id="6e52c-119">Чтобы использовать этот класс, измените глагол и существительное в атрибуте командлета, измените имя класса, чтобы отразить новую глагол и существительное, а затем добавьте функциональные возможности, необходимые для переопределения метода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="6e52c-119">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

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

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="6e52c-120">Переопределение метода EndProcessing</span><span class="sxs-lookup"><span data-stu-id="6e52c-120">To override the EndProcessing method</span></span>

- <span data-ttu-id="6e52c-121">Объявите защищенное переопределение метода [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="6e52c-121">Declare a protected override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="6e52c-122">Следующий класс выводит пример.</span><span class="sxs-lookup"><span data-stu-id="6e52c-122">The following class prints a sample.</span></span> <span data-ttu-id="6e52c-123">Чтобы использовать этот класс, измените глагол и существительное в атрибуте командлета, измените имя класса, чтобы отразить новую глагол и существительное, а затем добавьте функциональные возможности, необходимые для переопределения метода [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="6e52c-123">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6e52c-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e52c-124">See Also</span></span>

[<span data-ttu-id="6e52c-125">System. Management. Automation. командлет. BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="6e52c-125">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="6e52c-126">System. Management. Automation. командлет. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="6e52c-126">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="6e52c-127">System. Management. Automation. командлет. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="6e52c-127">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="6e52c-128">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e52c-128">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
