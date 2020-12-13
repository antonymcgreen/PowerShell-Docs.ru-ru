---
ms.date: 09/13/2016
ms.topic: reference
title: Типы атрибутов
description: Типы атрибутов
ms.openlocfilehash: 65640f2f8449887dedb9fae137eb16b6252f1d57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667119"
---
# <a name="attribute-types"></a><span data-ttu-id="7da7b-103">Типы атрибутов</span><span class="sxs-lookup"><span data-stu-id="7da7b-103">Attribute Types</span></span>

<span data-ttu-id="7da7b-104">Атрибуты командлета могут быть сгруппированы по функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="7da7b-104">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="7da7b-105">В следующих разделах описываются доступные атрибуты и описываются действия, выполняемые средой выполнения при вызове атрибута.</span><span class="sxs-lookup"><span data-stu-id="7da7b-105">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="7da7b-106">Атрибуты командлета</span><span class="sxs-lookup"><span data-stu-id="7da7b-106">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="7da7b-107">Командлет</span><span class="sxs-lookup"><span data-stu-id="7da7b-107">Cmdlet</span></span>

<span data-ttu-id="7da7b-108">Идентифицирует класс .NET Framework в качестве командлета.</span><span class="sxs-lookup"><span data-stu-id="7da7b-108">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="7da7b-109">Это обязательный базовый атрибут.</span><span class="sxs-lookup"><span data-stu-id="7da7b-109">This is the required base attribute.</span></span>
<span data-ttu-id="7da7b-110">Дополнительные сведения см. в разделе [объявление атрибута командлета](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7da7b-110">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="7da7b-111">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="7da7b-111">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="7da7b-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="7da7b-112">Parameter</span></span>

<span data-ttu-id="7da7b-113">Определяет открытое свойство в классе командлета как параметр командлета.</span><span class="sxs-lookup"><span data-stu-id="7da7b-113">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="7da7b-114">Дополнительные сведения см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7da7b-114">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="7da7b-115">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="7da7b-115">Alias</span></span>

<span data-ttu-id="7da7b-116">Указывает один или несколько псевдонимов для параметра.</span><span class="sxs-lookup"><span data-stu-id="7da7b-116">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="7da7b-117">Дополнительные сведения см. в разделе [объявление атрибута Alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7da7b-117">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="7da7b-118">Атрибуты проверки аргументов</span><span class="sxs-lookup"><span data-stu-id="7da7b-118">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="7da7b-119">валидатекаунт</span><span class="sxs-lookup"><span data-stu-id="7da7b-119">ValidateCount</span></span>

<span data-ttu-id="7da7b-120">Указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="7da7b-120">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="7da7b-121">Дополнительные сведения см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7da7b-121">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="7da7b-122">валидателенгс</span><span class="sxs-lookup"><span data-stu-id="7da7b-122">ValidateLength</span></span>

<span data-ttu-id="7da7b-123">Указывает минимальное и максимальное число символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="7da7b-123">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="7da7b-124">Дополнительные сведения см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7da7b-124">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="7da7b-125">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="7da7b-125">ValidatePattern</span></span>

<span data-ttu-id="7da7b-126">Указывает шаблон регулярного выражения, которому должен соответствовать аргумент параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="7da7b-126">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="7da7b-127">Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7da7b-127">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="7da7b-128">валидатеранже</span><span class="sxs-lookup"><span data-stu-id="7da7b-128">ValidateRange</span></span>

<span data-ttu-id="7da7b-129">Указывает минимальное и максимальное значения для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="7da7b-129">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="7da7b-130">Дополнительные сведения см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="7da7b-130">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="7da7b-131">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="7da7b-131">ValidateSet</span></span>

<span data-ttu-id="7da7b-132">Задает набор допустимых значений для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="7da7b-132">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="7da7b-133">Дополнительные сведения см. в разделе [объявление атрибута "Validate](./validateset-attribute-declaration.md)".</span><span class="sxs-lookup"><span data-stu-id="7da7b-133">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7da7b-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="7da7b-134">See Also</span></span>

[<span data-ttu-id="7da7b-135">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7da7b-135">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
