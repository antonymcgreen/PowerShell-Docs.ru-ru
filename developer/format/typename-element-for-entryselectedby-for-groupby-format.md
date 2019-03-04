---
title: TypeName-элемент для EntrySelectedBy для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8b6739b-770c-432a-95ab-551c7507c51f
caps.latest.revision: 6
ms.openlocfilehash: 3b5ce60d3a0d76988af48f49445a5478a415d498
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861670"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="f4a74-102">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f4a74-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="f4a74-103">Указывает тип .NET, который использует это определение пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f4a74-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="f4a74-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="f4a74-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f4a74-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента TypeName GroupBy (формат) для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f4a74-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4a74-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4a74-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4a74-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f4a74-107">Attributes and Elements</span></span>

<span data-ttu-id="f4a74-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="f4a74-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4a74-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f4a74-109">Attributes</span></span>

<span data-ttu-id="f4a74-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f4a74-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4a74-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f4a74-111">Child Elements</span></span>

<span data-ttu-id="f4a74-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f4a74-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4a74-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f4a74-113">Parent Elements</span></span>

|<span data-ttu-id="f4a74-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4a74-114">Element</span></span>|<span data-ttu-id="f4a74-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f4a74-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4a74-116">Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f4a74-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="f4a74-117">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="f4a74-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f4a74-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f4a74-118">Text Value</span></span>

<span data-ttu-id="f4a74-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="f4a74-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4a74-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="f4a74-120">Remarks</span></span>

<span data-ttu-id="f4a74-121">Каждое определение элемента управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="f4a74-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f4a74-122">Дополнительные сведения о компонентах представления пользовательского элемента управления, см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f4a74-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4a74-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f4a74-123">See Also</span></span>

[<span data-ttu-id="f4a74-124">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="f4a74-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="f4a74-125">Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f4a74-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="f4a74-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4a74-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
