---
title: Типы атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b1026ad-f072-4fca-8052-a2d8eb491c2a
caps.latest.revision: 6
ms.openlocfilehash: 52c75b3ca73706da39029d5b3ead52ff7197a5f1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068665"
---
# <a name="attribute-types"></a><span data-ttu-id="02952-102">Типы атрибутов</span><span class="sxs-lookup"><span data-stu-id="02952-102">Attribute Types</span></span>

<span data-ttu-id="02952-103">Командлет атрибуты могут быть сгруппированы по функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="02952-103">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="02952-104">В следующих разделах описываются доступные атрибуты и описывают, что исполняющая среда создает при вызове атрибута.</span><span class="sxs-lookup"><span data-stu-id="02952-104">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="02952-105">Атрибуты командлета</span><span class="sxs-lookup"><span data-stu-id="02952-105">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="02952-106">Командлет</span><span class="sxs-lookup"><span data-stu-id="02952-106">Cmdlet</span></span>

<span data-ttu-id="02952-107">Определяет класс .NET Framework как командлет.</span><span class="sxs-lookup"><span data-stu-id="02952-107">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="02952-108">Это обязательный базовый атрибут.</span><span class="sxs-lookup"><span data-stu-id="02952-108">This is the required base attribute.</span></span>
<span data-ttu-id="02952-109">Дополнительные сведения см. в разделе [объявление атрибута командлет](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-109">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="02952-110">Атрибуты параметра</span><span class="sxs-lookup"><span data-stu-id="02952-110">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="02952-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="02952-111">Parameter</span></span>

<span data-ttu-id="02952-112">Определяет открытое свойство в классе командлета в виде параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="02952-112">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="02952-113">Дополнительные сведения см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-113">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="02952-114">Alias</span><span class="sxs-lookup"><span data-stu-id="02952-114">Alias</span></span>

<span data-ttu-id="02952-115">Указывает один или несколько псевдонимов для параметра.</span><span class="sxs-lookup"><span data-stu-id="02952-115">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="02952-116">Дополнительные сведения см. в разделе [объявление атрибута псевдоним](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-116">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="02952-117">Атрибуты проверки аргументов</span><span class="sxs-lookup"><span data-stu-id="02952-117">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="02952-118">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="02952-118">ValidateCount</span></span>

<span data-ttu-id="02952-119">Указывает минимальное и максимальное число аргументов, которые разрешены для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="02952-119">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="02952-120">Дополнительные сведения см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-120">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="02952-121">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="02952-121">ValidateLength</span></span>

<span data-ttu-id="02952-122">Указывает минимальное и максимальное количество символов для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="02952-122">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="02952-123">Дополнительные сведения см. в разделе [объявление атрибута ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-123">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="02952-124">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="02952-124">ValidatePattern</span></span>

<span data-ttu-id="02952-125">Указывает шаблон регулярного выражения, которое должно соответствовать аргумент параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="02952-125">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="02952-126">Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-126">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="02952-127">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="02952-127">ValidateRange</span></span>

<span data-ttu-id="02952-128">Задает минимальное и максимальное значения для аргумента параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="02952-128">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="02952-129">Дополнительные сведения см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-129">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="02952-130">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="02952-130">ValidateSet</span></span>

<span data-ttu-id="02952-131">Задает набор допустимых значений для аргумента параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="02952-131">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="02952-132">Дополнительные сведения см. в разделе [объявление атрибута ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="02952-132">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02952-133">См. также</span><span class="sxs-lookup"><span data-stu-id="02952-133">See Also</span></span>

[<span data-ttu-id="02952-134">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02952-134">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
