---
title: Элемент Controls для конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369003"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="bbed1-102">Элемент Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="bbed1-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="bbed1-103">Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="bbed1-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="bbed1-104">Элемент Configuration (Format) управляет элементом конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="bbed1-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bbed1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbed1-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bbed1-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bbed1-106">Attributes and Elements</span></span>

<span data-ttu-id="bbed1-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Controls`.</span><span class="sxs-lookup"><span data-stu-id="bbed1-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bbed1-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbed1-108">Attributes</span></span>

<span data-ttu-id="bbed1-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="bbed1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bbed1-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bbed1-110">Child Elements</span></span>

|<span data-ttu-id="bbed1-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbed1-111">Element</span></span>|<span data-ttu-id="bbed1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bbed1-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbed1-113">Элемент Control для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="bbed1-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="bbed1-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbed1-114">Required element.</span></span><br /><br /> <span data-ttu-id="bbed1-115">Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="bbed1-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bbed1-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bbed1-116">Parent Elements</span></span>

|<span data-ttu-id="bbed1-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbed1-117">Element</span></span>|<span data-ttu-id="bbed1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="bbed1-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbed1-119">Элемент Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bbed1-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="bbed1-120">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="bbed1-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bbed1-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="bbed1-121">Remarks</span></span>

<span data-ttu-id="bbed1-122">Можно создать любое количество стандартных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="bbed1-122">You can create any number of common controls.</span></span> <span data-ttu-id="bbed1-123">Для каждого элемента управления необходимо указать имя, которое используется для ссылки на элемент управления и компоненты элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bbed1-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbed1-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="bbed1-124">See Also</span></span>

[<span data-ttu-id="bbed1-125">Элемент Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="bbed1-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="bbed1-126">Элемент Control для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="bbed1-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="bbed1-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbed1-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
