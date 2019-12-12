---
title: Элемент TypeName для Селектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 290d38e3-b9bd-4382-9671-2e28b32b7260
caps.latest.revision: 6
ms.openlocfilehash: a4036b1e9de85da7e0029e02cca9e0eaed462f70
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361483"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="92813-102">Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="92813-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="92813-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="92813-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="92813-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="92813-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="92813-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Ентриселектедби GroupBy для Кустоментри для GroupBy (Format) Селектионкондитион элемента для Ентриселектедби для элемента TypeName для селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92813-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92813-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92813-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="92813-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92813-107">Attributes and Elements</span></span>

<span data-ttu-id="92813-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="92813-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92813-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92813-109">Attributes</span></span>

<span data-ttu-id="92813-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="92813-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92813-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92813-111">Child Elements</span></span>

<span data-ttu-id="92813-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="92813-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92813-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92813-113">Parent Elements</span></span>

|<span data-ttu-id="92813-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="92813-114">Element</span></span>|<span data-ttu-id="92813-115">Описание</span><span class="sxs-lookup"><span data-stu-id="92813-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92813-116">Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92813-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="92813-117">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="92813-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92813-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="92813-118">Text Value</span></span>

<span data-ttu-id="92813-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="92813-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="92813-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="92813-120">Remarks</span></span>

<span data-ttu-id="92813-121">Если этот элемент указан, нельзя указать элемент `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="92813-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="92813-122">Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="92813-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92813-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="92813-123">See Also</span></span>

[<span data-ttu-id="92813-124">Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="92813-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="92813-125">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="92813-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
