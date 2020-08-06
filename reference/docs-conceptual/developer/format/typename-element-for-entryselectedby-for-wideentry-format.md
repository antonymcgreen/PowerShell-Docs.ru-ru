---
title: Элемент TypeName для Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9af443067467f590df824b28636f57b807a4fc94
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780191"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="db635-102">Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="db635-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="db635-103">Указывает тип .NET для определения.</span><span class="sxs-lookup"><span data-stu-id="db635-103">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="db635-104">Определение используется при каждом отображении этого объекта.</span><span class="sxs-lookup"><span data-stu-id="db635-104">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="db635-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) элемент TypeName для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="db635-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db635-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db635-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db635-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="db635-107">Attributes and Elements</span></span>

<span data-ttu-id="db635-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="db635-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db635-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="db635-109">Attributes</span></span>

<span data-ttu-id="db635-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="db635-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db635-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="db635-111">Child Elements</span></span>

<span data-ttu-id="db635-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="db635-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="db635-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="db635-113">Parent Elements</span></span>

|<span data-ttu-id="db635-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="db635-114">Element</span></span>|<span data-ttu-id="db635-115">Описание</span><span class="sxs-lookup"><span data-stu-id="db635-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db635-116">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="db635-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="db635-117">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="db635-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="db635-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="db635-118">Text Value</span></span>

<span data-ttu-id="db635-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="db635-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="db635-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="db635-120">Remarks</span></span>

<span data-ttu-id="db635-121">Каждая широкая запись должна указывать один или несколько типов .NET, набор выбора или условие выбора, которое должно существовать для использования определения.</span><span class="sxs-lookup"><span data-stu-id="db635-121">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="db635-122">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="db635-122">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db635-123">См. также</span><span class="sxs-lookup"><span data-stu-id="db635-123">See Also</span></span>

[<span data-ttu-id="db635-124">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="db635-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="db635-125">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="db635-125">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="db635-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="db635-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
