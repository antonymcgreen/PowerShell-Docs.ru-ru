---
title: Элемент SelectionSetName для EntrySelectedBy для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b594a064-746f-4900-99e4-7be7bf5aa5a2
caps.latest.revision: 7
ms.openlocfilehash: d540c99707f4e0796b2d408f2161a9208257ab32
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075653"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="3daeb-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3daeb-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="3daeb-103">Задает набор типов .NET, которые используют это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3daeb-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="3daeb-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="3daeb-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="3daeb-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элементов управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента представления (формат) SelectionSetName для EntrySelectedBy для элементов управления (представление Формат)</span><span class="sxs-lookup"><span data-stu-id="3daeb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3daeb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3daeb-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="3daeb-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3daeb-107">Attributes and Elements</span></span>

<span data-ttu-id="3daeb-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="3daeb-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3daeb-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3daeb-109">Attributes</span></span>

<span data-ttu-id="3daeb-110">Нет</span><span class="sxs-lookup"><span data-stu-id="3daeb-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="3daeb-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3daeb-111">Child Elements</span></span>

<span data-ttu-id="3daeb-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="3daeb-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3daeb-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3daeb-113">Parent Elements</span></span>

|<span data-ttu-id="3daeb-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="3daeb-114">Element</span></span>|<span data-ttu-id="3daeb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3daeb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3daeb-116">Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3daeb-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="3daeb-117">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="3daeb-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3daeb-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="3daeb-118">Text Value</span></span>

<span data-ttu-id="3daeb-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="3daeb-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="3daeb-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="3daeb-120">Remarks</span></span>

<span data-ttu-id="3daeb-121">Каждое определение элемента управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="3daeb-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="3daeb-122">Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="3daeb-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="3daeb-123">Дополнительные сведения об определении наборов выбора см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="3daeb-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3daeb-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3daeb-124">See Also</span></span>

[<span data-ttu-id="3daeb-125">Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3daeb-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="3daeb-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3daeb-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
