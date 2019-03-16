---
title: Элемент ScriptBlock для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: f2f6b9af7740b1231881294c2f32bf97b5a1568b
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054431"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="2d7ab-102">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2d7ab-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="2d7ab-103">Указывает сценарий, который запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="2d7ab-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) ScriptBlock для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2d7ab-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2d7ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d7ab-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2d7ab-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2d7ab-106">Attributes and Elements</span></span>

<span data-ttu-id="2d7ab-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2d7ab-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2d7ab-108">Attributes</span></span>

<span data-ttu-id="2d7ab-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2d7ab-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2d7ab-110">Child Elements</span></span>

<span data-ttu-id="2d7ab-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2d7ab-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2d7ab-112">Parent Elements</span></span>

|<span data-ttu-id="2d7ab-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="2d7ab-113">Element</span></span>|<span data-ttu-id="2d7ab-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2d7ab-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2d7ab-115">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2d7ab-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="2d7ab-116">Определяет порядок отображения группы объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2d7ab-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2d7ab-117">Text Value</span></span>

<span data-ttu-id="2d7ab-118">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d7ab-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="2d7ab-119">Remarks</span></span>

<span data-ttu-id="2d7ab-120">Windows PowerShell запускает новую группу, при каждом изменении значения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-120">Windows PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="2d7ab-121">Если этот элемент указан, нельзя указать [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676) элемент, чтобы начать новую группу.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-121">When this element is specified, you cannot specify the [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d7ab-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2d7ab-122">See Also</span></span>

[<span data-ttu-id="2d7ab-123">Элемент PropertyName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2d7ab-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="2d7ab-124">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2d7ab-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="2d7ab-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d7ab-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
