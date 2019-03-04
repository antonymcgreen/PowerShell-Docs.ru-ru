---
title: TypeName-элемент для SelectionCondition для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 290d38e3-b9bd-4382-9671-2e28b32b7260
caps.latest.revision: 6
ms.openlocfilehash: a4036b1e9de85da7e0029e02cca9e0eaed462f70
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858810"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="b0eee-102">Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b0eee-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="b0eee-103">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="b0eee-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="b0eee-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="b0eee-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b0eee-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента SelectionCondition GroupBy (формат) для EntrySelectedBy элемента TypeName GroupBy (формат) для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b0eee-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b0eee-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0eee-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b0eee-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b0eee-107">Attributes and Elements</span></span>

<span data-ttu-id="b0eee-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="b0eee-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b0eee-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b0eee-109">Attributes</span></span>

<span data-ttu-id="b0eee-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="b0eee-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b0eee-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b0eee-111">Child Elements</span></span>

<span data-ttu-id="b0eee-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="b0eee-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b0eee-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b0eee-113">Parent Elements</span></span>

|<span data-ttu-id="b0eee-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b0eee-114">Element</span></span>|<span data-ttu-id="b0eee-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b0eee-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b0eee-116">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b0eee-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="b0eee-117">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="b0eee-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b0eee-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b0eee-118">Text Value</span></span>

<span data-ttu-id="b0eee-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="b0eee-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0eee-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="b0eee-120">Remarks</span></span>

<span data-ttu-id="b0eee-121">Если этот элемент указан, нельзя указать `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="b0eee-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="b0eee-122">Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b0eee-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b0eee-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b0eee-123">See Also</span></span>

[<span data-ttu-id="b0eee-124">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b0eee-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="b0eee-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0eee-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
