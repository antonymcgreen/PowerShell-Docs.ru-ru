---
title: Элемент ScriptBlock для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e761e02a7910cd598449d564e827889162da9f25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787688"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="53ca6-102">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="53ca6-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="53ca6-103">Задает скрипт, запускающий новую группу при изменении ее значения.</span><span class="sxs-lookup"><span data-stu-id="53ca6-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="53ca6-104">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента ScriptBlock представления (Format) для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="53ca6-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="53ca6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53ca6-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="53ca6-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53ca6-106">Attributes and Elements</span></span>

<span data-ttu-id="53ca6-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="53ca6-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="53ca6-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53ca6-108">Attributes</span></span>

<span data-ttu-id="53ca6-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="53ca6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="53ca6-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53ca6-110">Child Elements</span></span>

<span data-ttu-id="53ca6-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="53ca6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="53ca6-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53ca6-112">Parent Elements</span></span>

|<span data-ttu-id="53ca6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="53ca6-113">Element</span></span>|<span data-ttu-id="53ca6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="53ca6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53ca6-115">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="53ca6-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="53ca6-116">Определяет, как отображается группа объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="53ca6-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="53ca6-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="53ca6-117">Text Value</span></span>

<span data-ttu-id="53ca6-118">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="53ca6-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="53ca6-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="53ca6-119">Remarks</span></span>

<span data-ttu-id="53ca6-120">PowerShell запускает новую группу при каждом изменении значения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="53ca6-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="53ca6-121">Если этот элемент указан, нельзя указать элемент [PropertyName](propertyname-element-for-groupby-format.md) для запуска новой группы.</span><span class="sxs-lookup"><span data-stu-id="53ca6-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="53ca6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="53ca6-122">See Also</span></span>

[<span data-ttu-id="53ca6-123">Элемент PropertyName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="53ca6-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="53ca6-124">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="53ca6-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="53ca6-125">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="53ca6-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
