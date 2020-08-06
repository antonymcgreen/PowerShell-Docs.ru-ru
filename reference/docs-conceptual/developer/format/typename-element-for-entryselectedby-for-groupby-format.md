---
title: Элемент TypeName для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e62762cf142bd2d20b21ad8f4249285bd3679280
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780273"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="e7d33-102">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e7d33-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="e7d33-103">Указывает тип .NET, использующий это определение пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e7d33-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="e7d33-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="e7d33-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e7d33-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри для GroupBy.</span><span class="sxs-lookup"><span data-stu-id="e7d33-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e7d33-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7d33-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7d33-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7d33-107">Attributes and Elements</span></span>

<span data-ttu-id="e7d33-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="e7d33-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7d33-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7d33-109">Attributes</span></span>

<span data-ttu-id="e7d33-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7d33-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e7d33-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7d33-111">Child Elements</span></span>

<span data-ttu-id="e7d33-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7d33-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e7d33-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7d33-113">Parent Elements</span></span>

|<span data-ttu-id="e7d33-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7d33-114">Element</span></span>|<span data-ttu-id="e7d33-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e7d33-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7d33-116">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e7d33-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e7d33-117">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="e7d33-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e7d33-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e7d33-118">Text Value</span></span>

<span data-ttu-id="e7d33-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="e7d33-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7d33-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7d33-120">Remarks</span></span>

<span data-ttu-id="e7d33-121">Для каждого определения элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="e7d33-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e7d33-122">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e7d33-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7d33-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e7d33-123">See Also</span></span>

[<span data-ttu-id="e7d33-124">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="e7d33-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e7d33-125">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="e7d33-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e7d33-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7d33-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
