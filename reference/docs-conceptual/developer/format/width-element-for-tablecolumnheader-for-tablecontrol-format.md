---
title: Элемент Width для Таблеколумнхеадер для Таблеконтрол (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e9540d3d351041ad7cb98a21bb360ebea7eca117
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779919"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="f98ae-102">Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f98ae-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="f98ae-103">Определяет ширину (в символах) столбца.</span><span class="sxs-lookup"><span data-stu-id="f98ae-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="f98ae-104">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент Таблеконтрол (Format) элемент Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер элемент Таблехеадерс для TableControl (формат) элемент TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f98ae-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f98ae-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f98ae-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f98ae-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f98ae-106">Attributes and Elements</span></span>

<span data-ttu-id="f98ae-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Width` элемента, используемого при определении заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="f98ae-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="f98ae-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f98ae-108">Attributes</span></span>

<span data-ttu-id="f98ae-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f98ae-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f98ae-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f98ae-110">Child Elements</span></span>

<span data-ttu-id="f98ae-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f98ae-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f98ae-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f98ae-112">Parent Elements</span></span>

|<span data-ttu-id="f98ae-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f98ae-113">Element</span></span>|<span data-ttu-id="f98ae-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f98ae-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f98ae-115">Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f98ae-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="f98ae-116">Определяет метку, ширину и выравнивание данных для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="f98ae-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f98ae-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f98ae-117">Text Value</span></span>

<span data-ttu-id="f98ae-118">Когда это возможно, укажите ширину (в символах), превышающую длину отображаемых значений свойств.</span><span class="sxs-lookup"><span data-stu-id="f98ae-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="f98ae-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="f98ae-119">Remarks</span></span>

<span data-ttu-id="f98ae-120">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f98ae-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f98ae-121">Пример</span><span class="sxs-lookup"><span data-stu-id="f98ae-121">Example</span></span>

<span data-ttu-id="f98ae-122">В следующем примере показан `TableColumnHeader` элемент, ширина которого составляет 16 символов.</span><span class="sxs-lookup"><span data-stu-id="f98ae-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="f98ae-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f98ae-123">See Also</span></span>

[<span data-ttu-id="f98ae-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="f98ae-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f98ae-125">Элемент Таблеколумнхеадер для Таблехеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f98ae-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="f98ae-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f98ae-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
