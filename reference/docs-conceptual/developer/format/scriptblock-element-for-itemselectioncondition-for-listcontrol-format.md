---
title: Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 38dc952bfadd6aed24bae8cbef05adcd22e61dd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787637"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="73865-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="73865-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="73865-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="73865-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="73865-104">При вычислении этого скрипта выполняется `true` условие, и используется элемент списка.</span><span class="sxs-lookup"><span data-stu-id="73865-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="73865-105">Этот элемент используется при определении представления списка.</span><span class="sxs-lookup"><span data-stu-id="73865-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="73865-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес для ListControl (Format) элемент ListItem для листентри для элемента списка элементов управления "список" (формат) ListControl для элемента SPListItem в итемселектионкондитион (Format) элемент ScriptBlock для ListControl в ItemSelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="73865-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="73865-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73865-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="73865-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73865-108">Attributes and Elements</span></span>

<span data-ttu-id="73865-109">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="73865-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="73865-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73865-110">Attributes</span></span>

<span data-ttu-id="73865-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73865-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="73865-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73865-112">Child Elements</span></span>

<span data-ttu-id="73865-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73865-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="73865-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73865-114">Parent Elements</span></span>

|<span data-ttu-id="73865-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="73865-115">Element</span></span>|<span data-ttu-id="73865-116">Описание</span><span class="sxs-lookup"><span data-stu-id="73865-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="73865-117">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="73865-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="73865-118">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="73865-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="73865-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="73865-119">Text Value</span></span>

<span data-ttu-id="73865-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="73865-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="73865-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="73865-121">Remarks</span></span>

<span data-ttu-id="73865-122">Если используется этот элемент, нельзя указать `PropertyName` элемент при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="73865-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="73865-123">См. также</span><span class="sxs-lookup"><span data-stu-id="73865-123">See Also</span></span>

[<span data-ttu-id="73865-124">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="73865-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
