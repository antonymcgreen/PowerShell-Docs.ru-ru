---
description: Предоставляет расширенные функции, которые позволяют создавать командлеты с помощью скриптов.
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: a0b8b027c91f2adedfcecd07bfc80392c1b1e071
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602488"
---
# <a name="about-functions-advanced"></a><span data-ttu-id="f209f-103">О функциях Advanced</span><span class="sxs-lookup"><span data-stu-id="f209f-103">About Functions Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="f209f-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f209f-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f209f-105">Предоставляет расширенные функции, которые позволяют создавать командлеты с помощью скриптов.</span><span class="sxs-lookup"><span data-stu-id="f209f-105">Introduces advanced functions that are a way to create cmdlets using scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="f209f-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f209f-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="f209f-107">Командлет — это одна команда, которая участвует в семантике конвейера PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f209f-107">A cmdlet is a single command that participates in the pipeline semantics of PowerShell.</span></span> <span data-ttu-id="f209f-108">Сюда входят двоичные командлеты, расширенные функции скриптов, CDXML и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="f209f-108">This includes binary cmdlets, advanced script functions, CDXML, and Workflows.</span></span>

<span data-ttu-id="f209f-109">Расширенные функции позволяют создавать командлеты, написанные как функция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f209f-109">Advanced functions allow you create cmdlets that are written as a PowerShell function.</span></span> <span data-ttu-id="f209f-110">Расширенные функции упрощают создание командлетов без написания и компиляции двоичного командлета.</span><span class="sxs-lookup"><span data-stu-id="f209f-110">Advanced functions make it easier to create cmdlets without having to write and compile a binary cmdlet.</span></span> <span data-ttu-id="f209f-111">Двоичные командлеты — это классы .NET, написанные на языке .NET, например C#.</span><span class="sxs-lookup"><span data-stu-id="f209f-111">Binary cmdlets are .NET classes that are written in a .NET language such as C#.</span></span>

<span data-ttu-id="f209f-112">Дополнительные функции используют `CmdletBinding` атрибут, чтобы обозначить их как функции, которые действуют как командлеты.</span><span class="sxs-lookup"><span data-stu-id="f209f-112">Advanced functions use the `CmdletBinding` attribute to identify them as functions that act like cmdlets.</span></span> <span data-ttu-id="f209f-113">`CmdletBinding`Атрибут аналогичен атрибуту командлета, который используется в скомпилированных классах командлетов для задания класса в качестве командлета.</span><span class="sxs-lookup"><span data-stu-id="f209f-113">The `CmdletBinding` attribute is similar to the Cmdlet attribute that is used in compiled cmdlet classes to identify the class as a cmdlet.</span></span> <span data-ttu-id="f209f-114">Дополнительные сведения об этом атрибуте см. в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="f209f-114">For more information about this attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="f209f-115">В следующем примере показана функция, которая принимает имя, а затем выводит приветствие с использованием заданного имени.</span><span class="sxs-lookup"><span data-stu-id="f209f-115">The following example shows a function that accepts a name and then prints a greeting using the supplied name.</span></span> <span data-ttu-id="f209f-116">Также обратите внимание, что эта функция определяет имя, которое включает пару глагол (Send) и существительное (приветствие), например пару глагол-существительное скомпилированного командлета.</span><span class="sxs-lookup"><span data-stu-id="f209f-116">Also notice that this function defines a name that includes a verb (Send) and noun (Greeting) pair like the verb-noun pair of a compiled cmdlet.</span></span> <span data-ttu-id="f209f-117">Однако функции не обязательно должны иметь имя существительное.</span><span class="sxs-lookup"><span data-stu-id="f209f-117">However, functions are not required to have a verb-noun name.</span></span>

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

<span data-ttu-id="f209f-118">Параметры функции объявляются с помощью атрибута Parameter.</span><span class="sxs-lookup"><span data-stu-id="f209f-118">The parameters of the function are declared by using the Parameter attribute.</span></span>
<span data-ttu-id="f209f-119">Этот атрибут можно использовать отдельно или в сочетании с атрибутом Alias или с несколькими другими атрибутами проверки параметров.</span><span class="sxs-lookup"><span data-stu-id="f209f-119">This attribute can be used alone, or it can be combined with the Alias attribute or with several other parameter validation attributes.</span></span> <span data-ttu-id="f209f-120">Дополнительные сведения об объявлении параметров (включая динамические параметры, добавляемые во время выполнения) см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f209f-120">For more information about how to declare parameters (including dynamic parameters that are added at runtime), see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

<span data-ttu-id="f209f-121">Фактическая работа предыдущей функции выполняется в блоке Process, что эквивалентно методу Процессингрекорд, который используется скомпилированными командлетами для обработки данных, передаваемых в командлет.</span><span class="sxs-lookup"><span data-stu-id="f209f-121">The actual work of the previous function is performed in the Process block, which is equivalent to the ProcessingRecord method that is used by compiled cmdlets to process the data that is passed to the cmdlet.</span></span> <span data-ttu-id="f209f-122">Этот блок вместе с блоками Begin и End описан в разделе [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) .</span><span class="sxs-lookup"><span data-stu-id="f209f-122">This block, along with the Begin and End blocks, is described in the [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) topic.</span></span>

<span data-ttu-id="f209f-123">Дополнительные функции отличаются от скомпилированных командлетов следующими способами.</span><span class="sxs-lookup"><span data-stu-id="f209f-123">Advanced functions differ from compiled cmdlets in the following ways:</span></span>

- <span data-ttu-id="f209f-124">Расширенная привязка параметра функции не вызывает исключение, если массив строк привязан к логическому параметру.</span><span class="sxs-lookup"><span data-stu-id="f209f-124">Advanced function parameter binding does not throw an exception when an array of strings is bound to a Boolean parameter.</span></span>
- <span data-ttu-id="f209f-125">Атрибут Validate и атрибут ValidatePattern не могут передавать именованные параметры.</span><span class="sxs-lookup"><span data-stu-id="f209f-125">The ValidateSet attribute and the ValidatePattern attribute cannot pass named parameters.</span></span>
- <span data-ttu-id="f209f-126">В транзакциях нельзя использовать дополнительные функции.</span><span class="sxs-lookup"><span data-stu-id="f209f-126">Advanced functions cannot be used in transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f209f-127">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="f209f-127">SEE ALSO</span></span>

[<span data-ttu-id="f209f-128">about_Functions</span><span class="sxs-lookup"><span data-stu-id="f209f-128">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="f209f-129">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="f209f-129">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="f209f-130">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="f209f-130">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="f209f-131">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="f209f-131">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="f209f-132">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="f209f-132">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
