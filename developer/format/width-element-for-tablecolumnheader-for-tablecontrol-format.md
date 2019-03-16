---
title: Ширина элемента для TableColumnHeader для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94eb0535-8002-4f17-9a2b-4be75ec20e5c
caps.latest.revision: 18
ms.openlocfilehash: 4a25c9d81df670dc10955065bfb66766cdb1bd33
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055195"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="a18ac-102">Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a18ac-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="a18ac-103">Определяет ширину (в символах) столбца.</span><span class="sxs-lookup"><span data-stu-id="a18ac-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="a18ac-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableHeaders элемент конфигурации для TableHeaders элемент TableColumnHeader TableControl (формат) для элемента ширины TableControl (формат) TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a18ac-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a18ac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a18ac-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a18ac-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a18ac-106">Attributes and Elements</span></span>

<span data-ttu-id="a18ac-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `Width` элемент, используемый при определении заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="a18ac-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="a18ac-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a18ac-108">Attributes</span></span>

<span data-ttu-id="a18ac-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="a18ac-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a18ac-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a18ac-110">Child Elements</span></span>

<span data-ttu-id="a18ac-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="a18ac-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a18ac-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a18ac-112">Parent Elements</span></span>

|<span data-ttu-id="a18ac-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="a18ac-113">Element</span></span>|<span data-ttu-id="a18ac-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a18ac-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a18ac-115">Элемент TableColumnHeader для TableHeaders для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a18ac-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="a18ac-116">Определяет метку, ширину и выравнивания данных для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="a18ac-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a18ac-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a18ac-117">Text Value</span></span>

<span data-ttu-id="a18ac-118">Если на все возможные следует укажите ширину (в символах), больше, чем длина значения отображаемого свойства.</span><span class="sxs-lookup"><span data-stu-id="a18ac-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="a18ac-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="a18ac-119">Remarks</span></span>

<span data-ttu-id="a18ac-120">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="a18ac-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a18ac-121">Пример</span><span class="sxs-lookup"><span data-stu-id="a18ac-121">Example</span></span>

<span data-ttu-id="a18ac-122">В следующем примере показан `TableColumnHeader` элемента, ширина которого составляет 16 символов.</span><span class="sxs-lookup"><span data-stu-id="a18ac-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="a18ac-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a18ac-123">See Also</span></span>

[<span data-ttu-id="a18ac-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="a18ac-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a18ac-125">Элемент TableColumnHeader для TableHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a18ac-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="a18ac-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a18ac-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
