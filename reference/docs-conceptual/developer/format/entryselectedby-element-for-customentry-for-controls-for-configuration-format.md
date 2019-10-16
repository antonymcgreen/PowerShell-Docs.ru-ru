---
title: Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368773"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="4c85f-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4c85f-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4c85f-103">Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c85f-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="4c85f-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="4c85f-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4c85f-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри для элементов управления конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="4c85f-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4c85f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c85f-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4c85f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c85f-107">Attributes and Elements</span></span>

<span data-ttu-id="4c85f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="4c85f-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4c85f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c85f-109">Attributes</span></span>

<span data-ttu-id="4c85f-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="4c85f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4c85f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c85f-111">Child Elements</span></span>

|<span data-ttu-id="4c85f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c85f-112">Element</span></span>|<span data-ttu-id="4c85f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4c85f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c85f-114">Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="4c85f-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c85f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4c85f-116">Определяет условие, которое должно существовать для использования определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c85f-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="4c85f-117">Элемент Селектионсетнаме для Ентриселектедби для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="4c85f-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c85f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4c85f-119">Указывает набор типов .NET, использующих это определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c85f-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="4c85f-120">Элемент TypeName для Ентриселектедби для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="4c85f-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c85f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4c85f-122">Указывает тип .NET, использующий это определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c85f-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4c85f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c85f-123">Parent Elements</span></span>

|<span data-ttu-id="4c85f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c85f-124">Element</span></span>|<span data-ttu-id="4c85f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="4c85f-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c85f-126">Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="4c85f-127">Предоставляет определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c85f-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4c85f-128">Замечания</span><span class="sxs-lookup"><span data-stu-id="4c85f-128">Remarks</span></span>

<span data-ttu-id="4c85f-129">Как минимум, каждому определению должно быть назначено по крайней мере один тип .NET, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="4c85f-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="4c85f-130">Максимальное число типов, наборов выбора или условий выбора, которые можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="4c85f-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c85f-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c85f-131">See Also</span></span>

[<span data-ttu-id="4c85f-132">Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="4c85f-133">Элемент Селектионсетнаме для Ентриселектедби для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4c85f-134">Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="4c85f-135">Элемент TypeName для Ентриселектедби для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="4c85f-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4c85f-136">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c85f-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
