---
title: Элемент TypeName для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8b6739b-770c-432a-95ab-551c7507c51f
caps.latest.revision: 6
ms.openlocfilehash: 3b5ce60d3a0d76988af48f49445a5478a415d498
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361673"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="e3738-102">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e3738-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="e3738-103">Указывает тип .NET, использующий это определение пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e3738-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="e3738-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="e3738-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e3738-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Ентриселектедби GroupBy (Format) для Кустоментри для GroupBy (Format) элемент TypeName для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e3738-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3738-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3738-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3738-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3738-107">Attributes and Elements</span></span>

<span data-ttu-id="e3738-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="e3738-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3738-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3738-109">Attributes</span></span>

<span data-ttu-id="e3738-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="e3738-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3738-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3738-111">Child Elements</span></span>

<span data-ttu-id="e3738-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="e3738-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3738-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3738-113">Parent Elements</span></span>

|<span data-ttu-id="e3738-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3738-114">Element</span></span>|<span data-ttu-id="e3738-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e3738-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3738-116">Элемент Ентриселектедби для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e3738-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e3738-117">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="e3738-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e3738-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e3738-118">Text Value</span></span>

<span data-ttu-id="e3738-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="e3738-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3738-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="e3738-120">Remarks</span></span>

<span data-ttu-id="e3738-121">Для каждого определения элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="e3738-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e3738-122">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e3738-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3738-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3738-123">See Also</span></span>

[<span data-ttu-id="e3738-124">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="e3738-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e3738-125">Элемент Ентриселектедби для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e3738-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e3738-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3738-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
