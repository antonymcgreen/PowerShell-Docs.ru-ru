---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 56bd04c9af74bdaa7a186a208fc15a67cb08b004
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772864"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="0335f-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0335f-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="0335f-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="0335f-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="0335f-104">При вычислении этого скрипта выполняется `true` условие, и используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="0335f-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="0335f-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0335f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0335f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0335f-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0335f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0335f-107">Attributes and Elements</span></span>

<span data-ttu-id="0335f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="0335f-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0335f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0335f-109">Attributes</span></span>

<span data-ttu-id="0335f-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0335f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0335f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0335f-111">Child Elements</span></span>

<span data-ttu-id="0335f-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0335f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0335f-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0335f-113">Parent Elements</span></span>

|<span data-ttu-id="0335f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0335f-114">Element</span></span>|<span data-ttu-id="0335f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0335f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0335f-116">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="0335f-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="0335f-117">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="0335f-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0335f-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0335f-118">Text Value</span></span>

<span data-ttu-id="0335f-119">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="0335f-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="0335f-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="0335f-120">Remarks</span></span>

<span data-ttu-id="0335f-121">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="0335f-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="0335f-122">(Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для использования записи или элемента представления](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="0335f-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="0335f-123">Дополнительные сведения о других компонентах представления списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="0335f-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0335f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0335f-124">See Also</span></span>

[<span data-ttu-id="0335f-125">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="0335f-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="0335f-126">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="0335f-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="0335f-127">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="0335f-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="0335f-128">Представление списка</span><span class="sxs-lookup"><span data-stu-id="0335f-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="0335f-129">Определение условий для использования записи или элемента представления</span><span class="sxs-lookup"><span data-stu-id="0335f-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0335f-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0335f-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
