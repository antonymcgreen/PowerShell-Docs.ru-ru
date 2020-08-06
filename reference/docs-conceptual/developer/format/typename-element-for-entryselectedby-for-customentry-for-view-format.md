---
title: Элемент TypeName для Ентриселектедби для Кустоментри для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: f8dc2c808e6eb3d6a7873cdbddc936b95d94c541
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785104"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="8cf8f-102">Элемент TypeName для элемента EntrySelectedBy для элемента CustomEntry для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="8cf8f-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="8cf8f-103">Указывает тип .NET, который использует это определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="8cf8f-104">Количество типов, которое можно указать для определения, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="8cf8f-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления кустоментри для кустоментриес для представления (Format) ентриселектедби для кустоментри для EntrySelectedBy для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="8cf8f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8cf8f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cf8f-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8cf8f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8cf8f-107">Attributes and Elements</span></span>

<span data-ttu-id="8cf8f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8cf8f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8cf8f-109">Attributes</span></span>

<span data-ttu-id="8cf8f-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8cf8f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8cf8f-111">Child Elements</span></span>

<span data-ttu-id="8cf8f-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8cf8f-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8cf8f-113">Parent Elements</span></span>

|<span data-ttu-id="8cf8f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8cf8f-114">Element</span></span>|<span data-ttu-id="8cf8f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8cf8f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8cf8f-116">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="8cf8f-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="8cf8f-117">Определяет типы .NET, которые используют это определение представления пользовательского элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8cf8f-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8cf8f-118">Text Value</span></span>

<span data-ttu-id="8cf8f-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="8cf8f-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8cf8f-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="8cf8f-120">Remarks</span></span>

<span data-ttu-id="8cf8f-121">Для каждого определения представления пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="8cf8f-122">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="8cf8f-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8cf8f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8cf8f-123">See Also</span></span>

[<span data-ttu-id="8cf8f-124">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="8cf8f-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="8cf8f-125">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="8cf8f-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8cf8f-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cf8f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
