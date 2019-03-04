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
ms.openlocfilehash: 41a6aaa24e5850bd390c8e3b6505cc88fc80b7b5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856210"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="6857f-102">Элемент ScriptBlock для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6857f-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="6857f-103">Указывает сценарий, который запускает новую группу, при каждом изменении его значения.</span><span class="sxs-lookup"><span data-stu-id="6857f-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="6857f-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) ScriptBlock для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6857f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6857f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6857f-105">Syntax</span></span>

```xml
<ScriptBolck>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6857f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6857f-106">Attributes and Elements</span></span>

<span data-ttu-id="6857f-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="6857f-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6857f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6857f-108">Attributes</span></span>

<span data-ttu-id="6857f-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="6857f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6857f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6857f-110">Child Elements</span></span>

<span data-ttu-id="6857f-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="6857f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6857f-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6857f-112">Parent Elements</span></span>

|<span data-ttu-id="6857f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="6857f-113">Element</span></span>|<span data-ttu-id="6857f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6857f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6857f-115">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6857f-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="6857f-116">Определяет порядок отображения группы объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="6857f-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6857f-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="6857f-117">Text Value</span></span>

<span data-ttu-id="6857f-118">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="6857f-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="6857f-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="6857f-119">Remarks</span></span>

<span data-ttu-id="6857f-120">Windows PowerShell запускает новую группу, при каждом изменении значения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="6857f-120">Windows PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="6857f-121">Если этот элемент указан, нельзя указать [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676) элемент, чтобы начать новую группу.</span><span class="sxs-lookup"><span data-stu-id="6857f-121">When this element is specified, you cannot specify the [PropertyName](http://msdn.microsoft.com/en-us/396dede0-039a-4a87-a5ef-3ecabb729676) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="6857f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6857f-122">See Also</span></span>

[<span data-ttu-id="6857f-123">Элемент PropertyName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6857f-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="6857f-124">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6857f-124">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="6857f-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6857f-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
