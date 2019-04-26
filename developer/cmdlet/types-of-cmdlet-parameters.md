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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067201"
---
# <a name="types-of-cmdlet-parameters"></a><span data-ttu-id="b06a4-102">Типы параметров командлета</span><span class="sxs-lookup"><span data-stu-id="b06a4-102">Types of Cmdlet Parameters</span></span>

<span data-ttu-id="b06a4-103">В этом разделе описываются различные типы параметров, которые можно объявить в командлетах.</span><span class="sxs-lookup"><span data-stu-id="b06a4-103">This topic describes the different types of parameters that you can declare in cmdlets.</span></span> <span data-ttu-id="b06a4-104">Параметры командлета можно позиционные, именованные, необходимые, необязательные или параметры-переключатели.</span><span class="sxs-lookup"><span data-stu-id="b06a4-104">Cmdlet parameters can be positional, named, required, optional, or switch parameters.</span></span>

## <a name="positional-and-named-parameters"></a><span data-ttu-id="b06a4-105">Позиционные и именованные параметры</span><span class="sxs-lookup"><span data-stu-id="b06a4-105">Positional and Named Parameters</span></span>

<span data-ttu-id="b06a4-106">Все параметры командлета — именованные или позиционные параметры.</span><span class="sxs-lookup"><span data-stu-id="b06a4-106">All cmdlet parameters are either named or positional parameters.</span></span> <span data-ttu-id="b06a4-107">Именованный параметр требует ввода имени параметра и аргумент при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="b06a4-107">A named parameter requires that you type the parameter name and argument when calling the cmdlet.</span></span> <span data-ttu-id="b06a4-108">Позиционный параметр требуется только, что аргументы типа в относительный порядок.</span><span class="sxs-lookup"><span data-stu-id="b06a4-108">A positional parameter requires only that you type the arguments in relative order.</span></span> <span data-ttu-id="b06a4-109">Первый неименованный аргумент будет затем сопоставляется первый позиционный параметр.</span><span class="sxs-lookup"><span data-stu-id="b06a4-109">The system then maps the first unnamed argument to the first positional parameter.</span></span> <span data-ttu-id="b06a4-110">Система второй неименованный аргумент сопоставляется второй неименованных параметров и т. д.</span><span class="sxs-lookup"><span data-stu-id="b06a4-110">The system maps the second unnamed argument to the second unnamed parameter, and so on.</span></span> <span data-ttu-id="b06a4-111">По умолчанию все параметры командлета являются именованными параметрами.</span><span class="sxs-lookup"><span data-stu-id="b06a4-111">By default, all cmdlet parameters are named parameters.</span></span>

<span data-ttu-id="b06a4-112">Чтобы определить именованный параметр, опустите `Position` ключевое слово в **параметр** атрибут объявления, как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="b06a4-112">To define a named parameter, omit the `Position` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="b06a4-113">Чтобы определить позиционным параметром, добавьте `Position` ключевое слово в параметре объявление атрибута, а затем укажите позицию.</span><span class="sxs-lookup"><span data-stu-id="b06a4-113">To define a positional parameter, add the `Position` keyword in the Parameter attribute declaration, and then specify a position.</span></span> <span data-ttu-id="b06a4-114">В следующем примере `UserName` параметр, объявленный как позиционным с позиции 0.</span><span class="sxs-lookup"><span data-stu-id="b06a4-114">In the following sample, the `UserName` parameter is declared as a positional parameter with position 0.</span></span> <span data-ttu-id="b06a4-115">Это означает, что первый аргумент при вызове будет автоматически привязан к этот параметр.</span><span class="sxs-lookup"><span data-stu-id="b06a4-115">This means that the first argument of the call will be automatically bound to this parameter.</span></span>

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
> <span data-ttu-id="b06a4-116">Хороший командлет структура рекомендует использовать, что наиболее часто используемые параметры объявляться как позиционные параметры, чтобы пользователю не нужно было вводить имя параметра при выполнении командлета.</span><span class="sxs-lookup"><span data-stu-id="b06a4-116">Good cmdlet design recommends that the most-used parameters be declared as positional parameters so that the user does not have to enter the parameter name when the cmdlet is run.</span></span>

<span data-ttu-id="b06a4-117">Позиционные и именованные параметры принимают аргументы одной или нескольких аргументов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="b06a4-117">Positional and named parameters accept single arguments or multiple arguments separated by commas.</span></span> <span data-ttu-id="b06a4-118">Несколько аргументов разрешены только в том случае, если параметр принимает коллекцию строк, таких как массив.</span><span class="sxs-lookup"><span data-stu-id="b06a4-118">Multiple arguments are allowed only if the parameter accepts a collection such as an array of strings.</span></span> <span data-ttu-id="b06a4-119">Вы можете использовать позиционные и именованные параметры в тот же командлет.</span><span class="sxs-lookup"><span data-stu-id="b06a4-119">You may mix positional and named parameters in the same cmdlet.</span></span> <span data-ttu-id="b06a4-120">В этом случае система сначала извлекает именованные аргументы, и затем пытается сопоставить оставшиеся неименованные аргументы для позиционных параметров.</span><span class="sxs-lookup"><span data-stu-id="b06a4-120">In this case, the system retrieves the named arguments first, and then attempts to map the remaining unnamed arguments to the positional parameters.</span></span>

<span data-ttu-id="b06a4-121">Следующие команды показывают, различными способами, в котором можно указать один или несколько аргументов для параметров `Get-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="b06a4-121">The following commands show the different ways in which you can specify single and multiple arguments for the parameters of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="b06a4-122">Обратите внимание, что в двух последних выборок, **-имя** не нужно указать, так как `Name` параметр определен как позиционным.</span><span class="sxs-lookup"><span data-stu-id="b06a4-122">Notice that in the last two samples, **-name** does not need to be specified because the `Name` parameter is defined as a positional parameter.</span></span>

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a><span data-ttu-id="b06a4-123">Обязательные и необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="b06a4-123">Mandatory and Optional Parameters</span></span>

<span data-ttu-id="b06a4-124">Можно также определить параметры командлета как обязательные или необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="b06a4-124">You can also define cmdlet parameters as mandatory or optional parameters.</span></span> <span data-ttu-id="b06a4-125">(Обязательный параметр чтобы должны быть заданы, среда выполнения Windows PowerShell вызывает командлет.)  По умолчанию определены как необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="b06a4-125">(A mandatory parameter must be specified before the Windows PowerShell runtime invokes the cmdlet.)  By default, parameters are defined as optional.</span></span>

<span data-ttu-id="b06a4-126">Чтобы определить обязательный параметр, добавьте `Mandatory` ключевое слово в параметре объявление атрибута и присвойте ему значение `true`, как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="b06a4-126">To define a mandatory parameter, add the `Mandatory` keyword in the Parameter attribute declaration, and set it to `true`, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="b06a4-127">Чтобы определить параметр как необязательный, опустите `Mandatory` ключевое слово в **параметр** атрибут объявления, как показано в следующем объявлении параметра.</span><span class="sxs-lookup"><span data-stu-id="b06a4-127">To define an optional parameter, omit the `Mandatory` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a><span data-ttu-id="b06a4-128">Параметры-переключатели</span><span class="sxs-lookup"><span data-stu-id="b06a4-128">Switch Parameters</span></span>

<span data-ttu-id="b06a4-129">Windows PowerShell предоставляет [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) автоматически присваивается тип, который можно задать параметр, значение которого `false` Если этот параметр не указан, получением командлетом вызывается.</span><span class="sxs-lookup"><span data-stu-id="b06a4-129">Windows PowerShell provides a [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type that allows you to define a parameter whose value is automatically set to `false` if the parameter is not specified when the cmdlet is called.</span></span> <span data-ttu-id="b06a4-130">По возможности используйте параметры-переключатели вместо логических параметров.</span><span class="sxs-lookup"><span data-stu-id="b06a4-130">Whenever possible, use switch parameters in place of Boolean parameters.</span></span>

<span data-ttu-id="b06a4-131">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="b06a4-131">Consider the following sample.</span></span> <span data-ttu-id="b06a4-132">По умолчанию несколько командлетов Windows PowerShell не передавайте выходного объекта по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b06a4-132">By default, several Windows PowerShell cmdlets do not pass an output object down the pipeline.</span></span> <span data-ttu-id="b06a4-133">Тем не менее, эти командлеты имеют `PassThru` параметр, который переопределяет поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b06a4-133">However, these cmdlets have a `PassThru` switch parameter that overrides the default behavior.</span></span> <span data-ttu-id="b06a4-134">Если `PassThru` параметр указан в том случае, когда вызываются эти командлеты, командлет возвращает объект выходные данные в конвейер.</span><span class="sxs-lookup"><span data-stu-id="b06a4-134">If the `PassThru` parameter is specified when these cmdlets are called, the cmdlet returns an output object to the pipeline.</span></span>

<span data-ttu-id="b06a4-135">Если необходим параметр иметь значение по умолчанию `true` когда этот параметр не указан в вызове, рассмотрите возможность обращения смысле параметра.</span><span class="sxs-lookup"><span data-stu-id="b06a4-135">If you need the parameter to have a default value of `true` when the parameter is not specified in the call, consider reversing the sense of the parameter.</span></span> <span data-ttu-id="b06a4-136">Для примера, вместо задания атрибут параметра в значение типа Boolean из `true`, свойство объявляется как [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) введите и выберите значение по умолчанию параметра `false`.</span><span class="sxs-lookup"><span data-stu-id="b06a4-136">For sample, instead of setting the parameter attribute to a Boolean value of `true`, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, and then set the default value of the parameter to `false`.</span></span>

<span data-ttu-id="b06a4-137">Чтобы определить параметр-переключатель, свойство объявляется как [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) тип, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b06a4-137">To define a switch parameter, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, as shown in the following sample.</span></span>

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

<span data-ttu-id="b06a4-138">Чтобы сделать командлет работать параметра, когда он указан, используется следующая структура в одном из методов обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="b06a4-138">To make the cmdlet act on the parameter when it is specified, use the following structure within one of the input processing methods.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b06a4-139">См. также</span><span class="sxs-lookup"><span data-stu-id="b06a4-139">See Also</span></span>

[<span data-ttu-id="b06a4-140">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b06a4-140">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
