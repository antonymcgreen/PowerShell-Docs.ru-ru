---
title: Элемент Итемселектионкондитион для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: f5c388928668e03b96923130fb5849f637548f12
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783625"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="d9069-102">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="d9069-103">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="d9069-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="d9069-104">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес для ListControl (Format) элемент ListItem для листентри для элементов ListItem в ListControl (формат) ListControl для элемента SPListItem (формат) элемент для элементов ListItem для итемселектионкондитион (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d9069-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9069-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9069-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d9069-106">Attributes and Elements</span></span>

<span data-ttu-id="d9069-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="d9069-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9069-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d9069-108">Attributes</span></span>

<span data-ttu-id="d9069-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d9069-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9069-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d9069-110">Child Elements</span></span>

|<span data-ttu-id="d9069-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9069-111">Element</span></span>|<span data-ttu-id="d9069-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d9069-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9069-113">Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="d9069-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d9069-114">Optional element.</span></span><br /><br /> <span data-ttu-id="d9069-115">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="d9069-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d9069-116">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="d9069-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d9069-117">Optional element.</span></span><br /><br /> <span data-ttu-id="d9069-118">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="d9069-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d9069-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d9069-119">Parent Elements</span></span>

|<span data-ttu-id="d9069-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9069-120">Element</span></span>|<span data-ttu-id="d9069-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d9069-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9069-122">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="d9069-123">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="d9069-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9069-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9069-124">Remarks</span></span>

<span data-ttu-id="d9069-125">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="d9069-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9069-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d9069-126">See Also</span></span>

[<span data-ttu-id="d9069-127">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="d9069-128">Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="d9069-129">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9069-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="d9069-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9069-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
