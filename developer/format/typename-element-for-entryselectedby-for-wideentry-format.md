---
title: TypeName-элемент для EntrySelectedBy для WideEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81a91c74-6229-4b64-aa2b-9123e8b7e9e5
caps.latest.revision: 11
ms.openlocfilehash: be35f6e9e2ad0b2d9a21a91c053aa0f70cafaf9c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862650"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="35f1c-102">Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="35f1c-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="35f1c-103">Указывает тип .NET для определения.</span><span class="sxs-lookup"><span data-stu-id="35f1c-103">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="35f1c-104">Определение используется в том случае, когда отображается этот объект.</span><span class="sxs-lookup"><span data-stu-id="35f1c-104">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="35f1c-105">Элемент (формат) ViewDefinitions элемент (формат) представление элемент (формат) элемент WideControl (формат) элемент WideEntries (формат) WideEntry элемент (формат) EntrySelectedBy элемент конфигурации для элемент TypeName WideEntry (формат) (WideEntry Формат)</span><span class="sxs-lookup"><span data-stu-id="35f1c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="35f1c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35f1c-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="35f1c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="35f1c-107">Attributes and Elements</span></span>

<span data-ttu-id="35f1c-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="35f1c-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="35f1c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="35f1c-109">Attributes</span></span>

<span data-ttu-id="35f1c-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="35f1c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="35f1c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="35f1c-111">Child Elements</span></span>

<span data-ttu-id="35f1c-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="35f1c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="35f1c-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="35f1c-113">Parent Elements</span></span>

|<span data-ttu-id="35f1c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="35f1c-114">Element</span></span>|<span data-ttu-id="35f1c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="35f1c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35f1c-116">Элемент EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="35f1c-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="35f1c-117">Определяет типы .NET, использующих эту запись широкий или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="35f1c-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="35f1c-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="35f1c-118">Text Value</span></span>

<span data-ttu-id="35f1c-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="35f1c-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="35f1c-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="35f1c-120">Remarks</span></span>

<span data-ttu-id="35f1c-121">Каждая запись широкий необходимо указать один или несколько типов .NET, выбора или условию выбора, которые нужны для определения для использования.</span><span class="sxs-lookup"><span data-stu-id="35f1c-121">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="35f1c-122">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="35f1c-122">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35f1c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="35f1c-123">See Also</span></span>

[<span data-ttu-id="35f1c-124">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="35f1c-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="35f1c-125">Элемент EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="35f1c-125">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="35f1c-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="35f1c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
