---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)
description: Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666677"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="acdfa-103">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-103">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="acdfa-104">Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="acdfa-104">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="acdfa-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="acdfa-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="acdfa-106">Элемент конфигурации (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для элемента Ошибка customcontrol для элемента Configuration (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Ентриселектедби для кустоментри для элементов управления конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="acdfa-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="acdfa-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acdfa-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="acdfa-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="acdfa-108">Attributes and Elements</span></span>

<span data-ttu-id="acdfa-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="acdfa-109">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="acdfa-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="acdfa-110">Attributes</span></span>

<span data-ttu-id="acdfa-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="acdfa-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="acdfa-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="acdfa-112">Child Elements</span></span>

|<span data-ttu-id="acdfa-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="acdfa-113">Element</span></span>|<span data-ttu-id="acdfa-114">Описание</span><span class="sxs-lookup"><span data-stu-id="acdfa-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="acdfa-115">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-115">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="acdfa-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="acdfa-116">Optional element.</span></span><br /><br /> <span data-ttu-id="acdfa-117">Определяет условие, которое должно существовать для использования определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="acdfa-117">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="acdfa-118">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-118">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="acdfa-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="acdfa-119">Optional element.</span></span><br /><br /> <span data-ttu-id="acdfa-120">Указывает набор типов .NET, использующих это определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="acdfa-120">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="acdfa-121">Элемент TypeName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-121">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="acdfa-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="acdfa-122">Optional element.</span></span><br /><br /> <span data-ttu-id="acdfa-123">Указывает тип .NET, использующий это определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="acdfa-123">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="acdfa-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="acdfa-124">Parent Elements</span></span>

|<span data-ttu-id="acdfa-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="acdfa-125">Element</span></span>|<span data-ttu-id="acdfa-126">Описание</span><span class="sxs-lookup"><span data-stu-id="acdfa-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="acdfa-127">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-127">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="acdfa-128">Предоставляет определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="acdfa-128">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="acdfa-129">Комментарии</span><span class="sxs-lookup"><span data-stu-id="acdfa-129">Remarks</span></span>

<span data-ttu-id="acdfa-130">Как минимум, каждому определению должно быть назначено по крайней мере один тип .NET, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="acdfa-130">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="acdfa-131">Максимальное число типов, наборов выбора или условий выбора, которые можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="acdfa-131">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="acdfa-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="acdfa-132">See Also</span></span>

[<span data-ttu-id="acdfa-133">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-133">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="acdfa-134">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-134">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="acdfa-135">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-135">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="acdfa-136">Элемент TypeName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="acdfa-136">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="acdfa-137">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="acdfa-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
