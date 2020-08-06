---
title: Типы атрибутов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 96fdd38ba10eb748ab0762f0c910463dd472494d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782384"
---
# <a name="attribute-types"></a><span data-ttu-id="639d7-102">Типы атрибутов</span><span class="sxs-lookup"><span data-stu-id="639d7-102">Attribute Types</span></span>

<span data-ttu-id="639d7-103">Атрибуты командлета могут быть сгруппированы по функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="639d7-103">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="639d7-104">В следующих разделах описываются доступные атрибуты и описываются действия, выполняемые средой выполнения при вызове атрибута.</span><span class="sxs-lookup"><span data-stu-id="639d7-104">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="639d7-105">Атрибуты командлета</span><span class="sxs-lookup"><span data-stu-id="639d7-105">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="639d7-106">Командлет</span><span class="sxs-lookup"><span data-stu-id="639d7-106">Cmdlet</span></span>

<span data-ttu-id="639d7-107">Идентифицирует класс .NET Framework в качестве командлета.</span><span class="sxs-lookup"><span data-stu-id="639d7-107">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="639d7-108">Это обязательный базовый атрибут.</span><span class="sxs-lookup"><span data-stu-id="639d7-108">This is the required base attribute.</span></span>
<span data-ttu-id="639d7-109">Дополнительные сведения см. в разделе [объявление атрибута командлета](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="639d7-109">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="639d7-110">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="639d7-110">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="639d7-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="639d7-111">Parameter</span></span>

<span data-ttu-id="639d7-112">Определяет открытое свойство в классе командлета как параметр командлета.</span><span class="sxs-lookup"><span data-stu-id="639d7-112">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="639d7-113">Дополнительные сведения см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="639d7-113">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="639d7-114">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="639d7-114">Alias</span></span>

<span data-ttu-id="639d7-115">Указывает один или несколько псевдонимов для параметра.</span><span class="sxs-lookup"><span data-stu-id="639d7-115">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="639d7-116">Дополнительные сведения см. в разделе [объявление атрибута Alias](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="639d7-116">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="639d7-117">Атрибуты проверки аргументов</span><span class="sxs-lookup"><span data-stu-id="639d7-117">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="639d7-118">валидатекаунт</span><span class="sxs-lookup"><span data-stu-id="639d7-118">ValidateCount</span></span>

<span data-ttu-id="639d7-119">Указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="639d7-119">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="639d7-120">Дополнительные сведения см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="639d7-120">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="639d7-121">валидателенгс</span><span class="sxs-lookup"><span data-stu-id="639d7-121">ValidateLength</span></span>

<span data-ttu-id="639d7-122">Указывает минимальное и максимальное число символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="639d7-122">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="639d7-123">Дополнительные сведения см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="639d7-123">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="639d7-124">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="639d7-124">ValidatePattern</span></span>

<span data-ttu-id="639d7-125">Указывает шаблон регулярного выражения, которому должен соответствовать аргумент параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="639d7-125">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="639d7-126">Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="639d7-126">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="639d7-127">валидатеранже</span><span class="sxs-lookup"><span data-stu-id="639d7-127">ValidateRange</span></span>

<span data-ttu-id="639d7-128">Указывает минимальное и максимальное значения для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="639d7-128">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="639d7-129">Дополнительные сведения см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="639d7-129">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="639d7-130">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="639d7-130">ValidateSet</span></span>

<span data-ttu-id="639d7-131">Задает набор допустимых значений для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="639d7-131">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="639d7-132">Дополнительные сведения см. в разделе [объявление атрибута "Validate](./validateset-attribute-declaration.md)".</span><span class="sxs-lookup"><span data-stu-id="639d7-132">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="639d7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="639d7-133">See Also</span></span>

[<span data-ttu-id="639d7-134">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="639d7-134">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
