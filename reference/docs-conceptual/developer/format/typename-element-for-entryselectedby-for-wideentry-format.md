---
title: Элемент TypeName для Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81a91c74-6229-4b64-aa2b-9123e8b7e9e5
caps.latest.revision: 11
ms.openlocfilehash: be35f6e9e2ad0b2d9a21a91c053aa0f70cafaf9c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361623"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="41686-102">Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="41686-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="41686-103">Указывает тип .NET для определения.</span><span class="sxs-lookup"><span data-stu-id="41686-103">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="41686-104">Определение используется при каждом отображении этого объекта.</span><span class="sxs-lookup"><span data-stu-id="41686-104">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="41686-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для элемента TypeName Видинтри (Format) для Видинтри ( Формат</span><span class="sxs-lookup"><span data-stu-id="41686-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41686-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41686-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41686-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="41686-107">Attributes and Elements</span></span>

<span data-ttu-id="41686-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="41686-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41686-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41686-109">Attributes</span></span>

<span data-ttu-id="41686-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="41686-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41686-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="41686-111">Child Elements</span></span>

<span data-ttu-id="41686-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="41686-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41686-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="41686-113">Parent Elements</span></span>

|<span data-ttu-id="41686-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="41686-114">Element</span></span>|<span data-ttu-id="41686-115">Описание</span><span class="sxs-lookup"><span data-stu-id="41686-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41686-116">Элемент Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="41686-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="41686-117">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="41686-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="41686-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="41686-118">Text Value</span></span>

<span data-ttu-id="41686-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="41686-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="41686-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="41686-120">Remarks</span></span>

<span data-ttu-id="41686-121">Каждая широкая запись должна указывать один или несколько типов .NET, набор выбора или условие выбора, которое должно существовать для использования определения.</span><span class="sxs-lookup"><span data-stu-id="41686-121">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="41686-122">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="41686-122">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41686-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="41686-123">See Also</span></span>

[<span data-ttu-id="41686-124">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="41686-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="41686-125">Элемент Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="41686-125">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="41686-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="41686-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
