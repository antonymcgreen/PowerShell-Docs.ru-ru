---
description: Предоставляет расширенные функции, которые позволяют создавать командлеты с помощью скриптов.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: 36b354e813c60208960f4cfb826ef0db81435c77
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231001"
---
# <a name="about-functions-advanced"></a><span data-ttu-id="a13ac-104">О функциях Advanced</span><span class="sxs-lookup"><span data-stu-id="a13ac-104">About Functions Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="a13ac-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="a13ac-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="a13ac-106">Предоставляет расширенные функции, которые позволяют создавать командлеты с помощью скриптов.</span><span class="sxs-lookup"><span data-stu-id="a13ac-106">Introduces advanced functions that are a way to create cmdlets using scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="a13ac-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="a13ac-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="a13ac-108">Командлет — это одна команда, которая участвует в семантике конвейера PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a13ac-108">A cmdlet is a single command that participates in the pipeline semantics of PowerShell.</span></span> <span data-ttu-id="a13ac-109">Сюда входят двоичные командлеты, расширенные функции скриптов, CDXML и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="a13ac-109">This includes binary cmdlets, advanced script functions, CDXML, and Workflows.</span></span>

<span data-ttu-id="a13ac-110">Расширенные функции позволяют создавать командлеты, написанные как функция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a13ac-110">Advanced functions allow you create cmdlets that are written as a PowerShell function.</span></span> <span data-ttu-id="a13ac-111">Расширенные функции упрощают создание командлетов без написания и компиляции двоичного командлета.</span><span class="sxs-lookup"><span data-stu-id="a13ac-111">Advanced functions make it easier to create cmdlets without having to write and compile a binary cmdlet.</span></span> <span data-ttu-id="a13ac-112">Двоичные командлеты — это классы .NET, написанные на языке .NET, например C#.</span><span class="sxs-lookup"><span data-stu-id="a13ac-112">Binary cmdlets are .NET classes that are written in a .NET language such as C#.</span></span>

<span data-ttu-id="a13ac-113">Дополнительные функции используют `CmdletBinding` атрибут, чтобы обозначить их как функции, которые действуют как командлеты.</span><span class="sxs-lookup"><span data-stu-id="a13ac-113">Advanced functions use the `CmdletBinding` attribute to identify them as functions that act like cmdlets.</span></span> <span data-ttu-id="a13ac-114">`CmdletBinding`Атрибут аналогичен атрибуту командлета, который используется в скомпилированных классах командлетов для задания класса в качестве командлета.</span><span class="sxs-lookup"><span data-stu-id="a13ac-114">The `CmdletBinding` attribute is similar to the Cmdlet attribute that is used in compiled cmdlet classes to identify the class as a cmdlet.</span></span> <span data-ttu-id="a13ac-115">Дополнительные сведения об этом атрибуте см. в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="a13ac-115">For more information about this attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="a13ac-116">В следующем примере показана функция, которая принимает имя, а затем выводит приветствие с использованием заданного имени.</span><span class="sxs-lookup"><span data-stu-id="a13ac-116">The following example shows a function that accepts a name and then prints a greeting using the supplied name.</span></span> <span data-ttu-id="a13ac-117">Также обратите внимание, что эта функция определяет имя, которое включает пару глагол (Send) и существительное (приветствие), например пару глагол-существительное скомпилированного командлета.</span><span class="sxs-lookup"><span data-stu-id="a13ac-117">Also notice that this function defines a name that includes a verb (Send) and noun (Greeting) pair like the verb-noun pair of a compiled cmdlet.</span></span> <span data-ttu-id="a13ac-118">Однако функции не обязательно должны иметь имя существительное.</span><span class="sxs-lookup"><span data-stu-id="a13ac-118">However, functions are not required to have a verb-noun name.</span></span>

```powershell
function Send-Greeting
{
    [CmdletBinding()]
    Param(
        [Parameter(Mandatory=$true)]
        [string] $Name
    )

    Process
    {
        Write-Host ("Hello " + $Name + "!")
    }
}
```

<span data-ttu-id="a13ac-119">Параметры функции объявляются с помощью атрибута Parameter.</span><span class="sxs-lookup"><span data-stu-id="a13ac-119">The parameters of the function are declared by using the Parameter attribute.</span></span>
<span data-ttu-id="a13ac-120">Этот атрибут можно использовать отдельно или в сочетании с атрибутом Alias или с несколькими другими атрибутами проверки параметров.</span><span class="sxs-lookup"><span data-stu-id="a13ac-120">This attribute can be used alone, or it can be combined with the Alias attribute or with several other parameter validation attributes.</span></span> <span data-ttu-id="a13ac-121">Дополнительные сведения об объявлении параметров (включая динамические параметры, добавляемые во время выполнения) см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a13ac-121">For more information about how to declare parameters (including dynamic parameters that are added at runtime), see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

<span data-ttu-id="a13ac-122">Фактическая работа предыдущей функции выполняется в блоке Process, что эквивалентно методу Процессингрекорд, который используется скомпилированными командлетами для обработки данных, передаваемых в командлет.</span><span class="sxs-lookup"><span data-stu-id="a13ac-122">The actual work of the previous function is performed in the Process block, which is equivalent to the ProcessingRecord method that is used by compiled cmdlets to process the data that is passed to the cmdlet.</span></span> <span data-ttu-id="a13ac-123">Этот блок вместе с блоками Begin и End описан в разделе [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) .</span><span class="sxs-lookup"><span data-stu-id="a13ac-123">This block, along with the Begin and End blocks, is described in the [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) topic.</span></span>

<span data-ttu-id="a13ac-124">Дополнительные функции отличаются от скомпилированных командлетов следующими способами.</span><span class="sxs-lookup"><span data-stu-id="a13ac-124">Advanced functions differ from compiled cmdlets in the following ways:</span></span>

- <span data-ttu-id="a13ac-125">Расширенная привязка параметра функции не вызывает исключение, если массив строк привязан к логическому параметру.</span><span class="sxs-lookup"><span data-stu-id="a13ac-125">Advanced function parameter binding does not throw an exception when an array of strings is bound to a Boolean parameter.</span></span>
- <span data-ttu-id="a13ac-126">Атрибут Validate и атрибут ValidatePattern не могут передавать именованные параметры.</span><span class="sxs-lookup"><span data-stu-id="a13ac-126">The ValidateSet attribute and the ValidatePattern attribute cannot pass named parameters.</span></span>
- <span data-ttu-id="a13ac-127">В транзакциях нельзя использовать дополнительные функции.</span><span class="sxs-lookup"><span data-stu-id="a13ac-127">Advanced functions cannot be used in transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="a13ac-128">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="a13ac-128">SEE ALSO</span></span>

[<span data-ttu-id="a13ac-129">about_Functions</span><span class="sxs-lookup"><span data-stu-id="a13ac-129">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="a13ac-130">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="a13ac-130">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="a13ac-131">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="a13ac-131">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="a13ac-132">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="a13ac-132">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="a13ac-133">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="a13ac-133">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
