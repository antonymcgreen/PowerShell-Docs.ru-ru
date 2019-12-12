---
title: Типы параметров командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6602730d-3892-4656-80c7-7bca2d14337f
caps.latest.revision: 14
ms.openlocfilehash: f5781c0c03aca41d01a44598a9a8c00d6d21d2fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369313"
---
# <a name="types-of-cmdlet-parameters"></a><span data-ttu-id="cee55-102">Типы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="cee55-102">Types of Cmdlet Parameters</span></span>

<span data-ttu-id="cee55-103">В этом разделе описываются различные типы параметров, которые можно объявить в командлетах.</span><span class="sxs-lookup"><span data-stu-id="cee55-103">This topic describes the different types of parameters that you can declare in cmdlets.</span></span> <span data-ttu-id="cee55-104">Параметры командлета могут быть параметрами позиционированного, именованного, обязательного, необязательного или switch.</span><span class="sxs-lookup"><span data-stu-id="cee55-104">Cmdlet parameters can be positional, named, required, optional, or switch parameters.</span></span>

## <a name="positional-and-named-parameters"></a><span data-ttu-id="cee55-105">Позиционированные и именованные параметры</span><span class="sxs-lookup"><span data-stu-id="cee55-105">Positional and Named Parameters</span></span>

<span data-ttu-id="cee55-106">Все параметры командлета являются либо именованными, либо параметрами позиционирования.</span><span class="sxs-lookup"><span data-stu-id="cee55-106">All cmdlet parameters are either named or positional parameters.</span></span> <span data-ttu-id="cee55-107">Именованный параметр требует ввода имени параметра и аргумента при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="cee55-107">A named parameter requires that you type the parameter name and argument when calling the cmdlet.</span></span> <span data-ttu-id="cee55-108">Для позиционированного параметра требуется только ввод аргументов в относительном порядке.</span><span class="sxs-lookup"><span data-stu-id="cee55-108">A positional parameter requires only that you type the arguments in relative order.</span></span> <span data-ttu-id="cee55-109">Затем система сопоставляет первый безымянный аргумент с первым позиционированным параметром.</span><span class="sxs-lookup"><span data-stu-id="cee55-109">The system then maps the first unnamed argument to the first positional parameter.</span></span> <span data-ttu-id="cee55-110">Система сопоставляет второй безымянный аргумент с вторым неименованным параметром и т. д.</span><span class="sxs-lookup"><span data-stu-id="cee55-110">The system maps the second unnamed argument to the second unnamed parameter, and so on.</span></span> <span data-ttu-id="cee55-111">По умолчанию все параметры командлета являются именованными параметрами.</span><span class="sxs-lookup"><span data-stu-id="cee55-111">By default, all cmdlet parameters are named parameters.</span></span>

<span data-ttu-id="cee55-112">Чтобы определить именованный параметр, опустите ключевое слово `Position` в объявлении атрибута **Parameter** , как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="cee55-112">To define a named parameter, omit the `Position` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="cee55-113">Чтобы определить параметр с указанием места, добавьте ключевое слово `Position` в объявление атрибута Parameter, а затем укажите расположение.</span><span class="sxs-lookup"><span data-stu-id="cee55-113">To define a positional parameter, add the `Position` keyword in the Parameter attribute declaration, and then specify a position.</span></span> <span data-ttu-id="cee55-114">В следующем примере параметр `UserName` объявляется как параметр с положением 0.</span><span class="sxs-lookup"><span data-stu-id="cee55-114">In the following sample, the `UserName` parameter is declared as a positional parameter with position 0.</span></span> <span data-ttu-id="cee55-115">Это означает, что первый аргумент вызова будет автоматически привязан к этому параметру.</span><span class="sxs-lookup"><span data-stu-id="cee55-115">This means that the first argument of the call will be automatically bound to this parameter.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> <span data-ttu-id="cee55-116">Хороший проект командлета рекомендует объявлять наиболее используемые параметры как параметры позиционирования, чтобы пользователь не вводил имя параметра при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="cee55-116">Good cmdlet design recommends that the most-used parameters be declared as positional parameters so that the user does not have to enter the parameter name when the cmdlet is run.</span></span>

<span data-ttu-id="cee55-117">Позиционированные и именованные параметры принимают одиночные аргументы или несколько аргументов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="cee55-117">Positional and named parameters accept single arguments or multiple arguments separated by commas.</span></span> <span data-ttu-id="cee55-118">Несколько аргументов разрешены, только если параметр принимает коллекцию, например массив строк.</span><span class="sxs-lookup"><span data-stu-id="cee55-118">Multiple arguments are allowed only if the parameter accepts a collection such as an array of strings.</span></span> <span data-ttu-id="cee55-119">В одном командлете можно смешивать позиционированные и именованные параметры.</span><span class="sxs-lookup"><span data-stu-id="cee55-119">You may mix positional and named parameters in the same cmdlet.</span></span> <span data-ttu-id="cee55-120">В этом случае система сначала извлекает именованные аргументы, а затем пытается сопоставлять остальные неименованные аргументы с заданными параметрами.</span><span class="sxs-lookup"><span data-stu-id="cee55-120">In this case, the system retrieves the named arguments first, and then attempts to map the remaining unnamed arguments to the positional parameters.</span></span>

<span data-ttu-id="cee55-121">Следующие команды демонстрируют различные способы, с помощью которых можно указать один и несколько аргументов для параметров командлета `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="cee55-121">The following commands show the different ways in which you can specify single and multiple arguments for the parameters of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="cee55-122">Обратите внимание, что в двух последних примерах параметр **-Name** не требуется указывать, так как в качестве параметра `Name` определено значение параметра.</span><span class="sxs-lookup"><span data-stu-id="cee55-122">Notice that in the last two samples, **-name** does not need to be specified because the `Name` parameter is defined as a positional parameter.</span></span>

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a><span data-ttu-id="cee55-123">Обязательные и необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="cee55-123">Mandatory and Optional Parameters</span></span>

<span data-ttu-id="cee55-124">Можно также определить параметры командлета как обязательные или необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="cee55-124">You can also define cmdlet parameters as mandatory or optional parameters.</span></span> <span data-ttu-id="cee55-125">(Обязательный параметр необходимо указать до того, как среда выполнения Windows PowerShell вызовет командлет.)  По умолчанию параметры определяются как необязательные.</span><span class="sxs-lookup"><span data-stu-id="cee55-125">(A mandatory parameter must be specified before the Windows PowerShell runtime invokes the cmdlet.)  By default, parameters are defined as optional.</span></span>

<span data-ttu-id="cee55-126">Чтобы определить обязательный параметр, добавьте ключевое слово `Mandatory` в объявление атрибута Parameter и присвойте ему значение `true`, как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="cee55-126">To define a mandatory parameter, add the `Mandatory` keyword in the Parameter attribute declaration, and set it to `true`, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="cee55-127">Чтобы определить необязательный параметр, опустите ключевое слово `Mandatory` в объявлении атрибута **Parameter** , как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="cee55-127">To define an optional parameter, omit the `Mandatory` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a><span data-ttu-id="cee55-128">Параметры переключателя</span><span class="sxs-lookup"><span data-stu-id="cee55-128">Switch Parameters</span></span>

<span data-ttu-id="cee55-129">Windows PowerShell предоставляет тип [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter) , который позволяет определить параметр, значение которого автоматически устанавливается в `false`, если параметр не указан при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="cee55-129">Windows PowerShell provides a [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type that allows you to define a parameter whose value is automatically set to `false` if the parameter is not specified when the cmdlet is called.</span></span> <span data-ttu-id="cee55-130">Везде, где это возможно, используйте параметры переключения вместо логических параметров.</span><span class="sxs-lookup"><span data-stu-id="cee55-130">Whenever possible, use switch parameters in place of Boolean parameters.</span></span>

<span data-ttu-id="cee55-131">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="cee55-131">Consider the following sample.</span></span> <span data-ttu-id="cee55-132">По умолчанию несколько командлетов Windows PowerShell не передают выходной объект в конвейер.</span><span class="sxs-lookup"><span data-stu-id="cee55-132">By default, several Windows PowerShell cmdlets do not pass an output object down the pipeline.</span></span> <span data-ttu-id="cee55-133">Однако эти командлеты имеют параметр `PassThru`, который переопределяет поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cee55-133">However, these cmdlets have a `PassThru` switch parameter that overrides the default behavior.</span></span> <span data-ttu-id="cee55-134">Если при вызове этих командлетов указан параметр `PassThru`, командлет возвращает выходной объект в конвейер.</span><span class="sxs-lookup"><span data-stu-id="cee55-134">If the `PassThru` parameter is specified when these cmdlets are called, the cmdlet returns an output object to the pipeline.</span></span>

<span data-ttu-id="cee55-135">Если требуется, чтобы параметр имел значение по умолчанию `true` если параметр не указан в вызове, рассмотрите возможность отменять смысл параметра.</span><span class="sxs-lookup"><span data-stu-id="cee55-135">If you need the parameter to have a default value of `true` when the parameter is not specified in the call, consider reversing the sense of the parameter.</span></span> <span data-ttu-id="cee55-136">Например, вместо присвоения атрибуту параметра логического значения `true`объявите свойство как тип [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter) , а затем задайте для параметра значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="cee55-136">For sample, instead of setting the parameter attribute to a Boolean value of `true`, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, and then set the default value of the parameter to `false`.</span></span>

<span data-ttu-id="cee55-137">Чтобы определить параметр переключателя, объявите свойство как тип [System. Management. Automation. переключатель](/dotnet/api/System.Management.Automation.SwitchParameter) , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cee55-137">To define a switch parameter, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, as shown in the following sample.</span></span>

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

<span data-ttu-id="cee55-138">Чтобы командлет действовал для параметра, если он указан, используйте следующую структуру в одном из методов обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="cee55-138">To make the cmdlet act on the parameter when it is specified, use the following structure within one of the input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a><span data-ttu-id="cee55-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="cee55-139">See Also</span></span>

[<span data-ttu-id="cee55-140">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cee55-140">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
