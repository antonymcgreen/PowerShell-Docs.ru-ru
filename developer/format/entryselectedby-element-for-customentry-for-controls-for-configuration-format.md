---
title: Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066300"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="b4dae-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b4dae-103">Определяет типы .NET, использующих определение общего элемента управления или условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="b4dae-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="b4dae-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="b4dae-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b4dae-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b4dae-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4dae-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b4dae-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b4dae-107">Attributes and Elements</span></span>

<span data-ttu-id="b4dae-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="b4dae-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b4dae-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4dae-109">Attributes</span></span>

<span data-ttu-id="b4dae-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="b4dae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b4dae-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4dae-111">Child Elements</span></span>

|<span data-ttu-id="b4dae-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4dae-112">Element</span></span>|<span data-ttu-id="b4dae-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b4dae-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4dae-114">Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="b4dae-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4dae-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b4dae-116">Определяет условие, которое должен существовать для распространенных определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="b4dae-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="b4dae-117">Элемент SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="b4dae-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4dae-118">Optional element.</span></span><br /><br /> <span data-ttu-id="b4dae-119">Задает набор типов .NET, которые используют это определение стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b4dae-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="b4dae-120">TypeName-элемент для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="b4dae-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4dae-121">Optional element.</span></span><br /><br /> <span data-ttu-id="b4dae-122">Указывает тип .NET, который использует это определение стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b4dae-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b4dae-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b4dae-123">Parent Elements</span></span>

|<span data-ttu-id="b4dae-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4dae-124">Element</span></span>|<span data-ttu-id="b4dae-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b4dae-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4dae-126">Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="b4dae-127">Предоставляет определение стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b4dae-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b4dae-128">Замечания</span><span class="sxs-lookup"><span data-stu-id="b4dae-128">Remarks</span></span>

<span data-ttu-id="b4dae-129">Как минимум каждое определение должен иметь по крайней мере один тип .NET, выбора или выделение условие, заданное.</span><span class="sxs-lookup"><span data-stu-id="b4dae-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="b4dae-130">Не ограничено максимальное число типов, выбор наборов или условий выборки, которые можно задать.</span><span class="sxs-lookup"><span data-stu-id="b4dae-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4dae-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b4dae-131">See Also</span></span>

[<span data-ttu-id="b4dae-132">Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="b4dae-133">Элемент SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="b4dae-134">Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="b4dae-135">TypeName-элемент для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4dae-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="b4dae-136">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4dae-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
