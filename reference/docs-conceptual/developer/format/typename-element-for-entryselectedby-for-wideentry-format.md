---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)
description: Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)
ms.openlocfilehash: 2e0facd6ff7c6fec96dabf488449a8502429bcff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654794"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="0f0e3-103">Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0f0e3-103">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="0f0e3-104">Указывает тип .NET для определения.</span><span class="sxs-lookup"><span data-stu-id="0f0e3-104">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="0f0e3-105">Определение используется при каждом отображении этого объекта.</span><span class="sxs-lookup"><span data-stu-id="0f0e3-105">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="0f0e3-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) элемент TypeName для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0f0e3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0f0e3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f0e3-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f0e3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f0e3-108">Attributes and Elements</span></span>

<span data-ttu-id="0f0e3-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="0f0e3-109">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f0e3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f0e3-110">Attributes</span></span>

<span data-ttu-id="0f0e3-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f0e3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f0e3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f0e3-112">Child Elements</span></span>

<span data-ttu-id="0f0e3-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f0e3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f0e3-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f0e3-114">Parent Elements</span></span>

|<span data-ttu-id="0f0e3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f0e3-115">Element</span></span>|<span data-ttu-id="0f0e3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0f0e3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f0e3-117">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0f0e3-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="0f0e3-118">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="0f0e3-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0f0e3-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0f0e3-119">Text Value</span></span>

<span data-ttu-id="0f0e3-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="0f0e3-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f0e3-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0f0e3-121">Remarks</span></span>

<span data-ttu-id="0f0e3-122">Каждая широкая запись должна указывать один или несколько типов .NET, набор выбора или условие выбора, которое должно существовать для использования определения.</span><span class="sxs-lookup"><span data-stu-id="0f0e3-122">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="0f0e3-123">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="0f0e3-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f0e3-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f0e3-124">See Also</span></span>

[<span data-ttu-id="0f0e3-125">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="0f0e3-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0f0e3-126">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0f0e3-126">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="0f0e3-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f0e3-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
