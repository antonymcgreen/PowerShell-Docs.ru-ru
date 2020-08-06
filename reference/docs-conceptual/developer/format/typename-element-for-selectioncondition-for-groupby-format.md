---
title: Элемент TypeName для Селектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: ea1e0cb50c3a749f6c26d13fff4b001240ce6b95
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772558"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="75cd9-102">Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="75cd9-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="75cd9-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="75cd9-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="75cd9-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="75cd9-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="75cd9-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format). селектионкондитион для EntrySelectedBy for GroupBy в SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="75cd9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="75cd9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75cd9-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="75cd9-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="75cd9-107">Attributes and Elements</span></span>

<span data-ttu-id="75cd9-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="75cd9-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="75cd9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="75cd9-109">Attributes</span></span>

<span data-ttu-id="75cd9-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="75cd9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="75cd9-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="75cd9-111">Child Elements</span></span>

<span data-ttu-id="75cd9-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="75cd9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="75cd9-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="75cd9-113">Parent Elements</span></span>

|<span data-ttu-id="75cd9-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="75cd9-114">Element</span></span>|<span data-ttu-id="75cd9-115">Описание</span><span class="sxs-lookup"><span data-stu-id="75cd9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="75cd9-116">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="75cd9-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="75cd9-117">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="75cd9-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="75cd9-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="75cd9-118">Text Value</span></span>

<span data-ttu-id="75cd9-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="75cd9-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="75cd9-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="75cd9-120">Remarks</span></span>

<span data-ttu-id="75cd9-121">Если этот элемент указан, нельзя указать `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="75cd9-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="75cd9-122">Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="75cd9-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75cd9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="75cd9-123">See Also</span></span>

[<span data-ttu-id="75cd9-124">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="75cd9-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="75cd9-125">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="75cd9-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
