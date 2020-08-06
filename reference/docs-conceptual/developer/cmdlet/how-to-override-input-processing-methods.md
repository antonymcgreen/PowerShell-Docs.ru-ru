---
title: Как переопределить методы обработки ввода | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b245dc56b78ce9b7f1dea80b5d4988057c2f125f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784118"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="ed85e-102">Как переопределить методы обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="ed85e-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="ed85e-103">В этих примерах показано, как перезаписать методы обработки ввода в командлете.</span><span class="sxs-lookup"><span data-stu-id="ed85e-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="ed85e-104">Эти методы используются для выполнения следующих операций:</span><span class="sxs-lookup"><span data-stu-id="ed85e-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="ed85e-105">Метод [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) используется для выполнения одноразовых операций запуска, допустимых для всех объектов, обрабатываемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="ed85e-105">The [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="ed85e-106">Среда выполнения Windows PowerShell вызывает этот метод только один раз.</span><span class="sxs-lookup"><span data-stu-id="ed85e-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="ed85e-107">Метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) используется для обработки объектов, передаваемых в командлет.</span><span class="sxs-lookup"><span data-stu-id="ed85e-107">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="ed85e-108">Среда выполнения Windows PowerShell вызывает этот метод для каждого объекта, передаваемого в командлет.</span><span class="sxs-lookup"><span data-stu-id="ed85e-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="ed85e-109">Метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) используется для выполнения операций однократной завершающей обработки.</span><span class="sxs-lookup"><span data-stu-id="ed85e-109">The [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="ed85e-110">Среда выполнения Windows PowerShell вызывает этот метод только один раз.</span><span class="sxs-lookup"><span data-stu-id="ed85e-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="ed85e-111">Переопределение метода BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="ed85e-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="ed85e-112">Объявите защищенное переопределение метода [System. Management. Automation. командлета. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) .</span><span class="sxs-lookup"><span data-stu-id="ed85e-112">Declare a protected override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="ed85e-113">Следующий класс выводит образец сообщения.</span><span class="sxs-lookup"><span data-stu-id="ed85e-113">The following class prints a sample message.</span></span> <span data-ttu-id="ed85e-114">Чтобы использовать этот класс, измените глагол и существительное в атрибуте командлета, измените имя класса, чтобы отразить новую глагол и существительное, а затем добавьте функциональные возможности, необходимые для переопределения метода [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) .</span><span class="sxs-lookup"><span data-stu-id="ed85e-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

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

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="ed85e-115">Переопределение метода ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="ed85e-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="ed85e-116">Объявите защищенное переопределение метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="ed85e-116">Declare a protected override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="ed85e-117">Следующий класс выводит образец сообщения.</span><span class="sxs-lookup"><span data-stu-id="ed85e-117">The following class prints a sample message.</span></span> <span data-ttu-id="ed85e-118">Чтобы использовать этот класс, измените глагол и существительное в атрибуте командлета, измените имя класса, чтобы отразить новую глагол и существительное, а затем добавьте функциональные возможности, необходимые для переопределения метода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="ed85e-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

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

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="ed85e-119">Переопределение метода EndProcessing</span><span class="sxs-lookup"><span data-stu-id="ed85e-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="ed85e-120">Объявите защищенное переопределение метода [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="ed85e-120">Declare a protected override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="ed85e-121">Следующий класс выводит пример.</span><span class="sxs-lookup"><span data-stu-id="ed85e-121">The following class prints a sample.</span></span> <span data-ttu-id="ed85e-122">Чтобы использовать этот класс, измените глагол и существительное в атрибуте командлета, измените имя класса, чтобы отразить новую глагол и существительное, а затем добавьте функциональные возможности, необходимые для переопределения метода [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="ed85e-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ed85e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ed85e-123">See Also</span></span>

[<span data-ttu-id="ed85e-124">System. Management. Automation. командлет. BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="ed85e-124">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="ed85e-125">System. Management. Automation. командлет. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="ed85e-125">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="ed85e-126">System. Management. Automation. командлет. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="ed85e-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="ed85e-127">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed85e-127">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
