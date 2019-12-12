---
title: Элемент Кустоментриес для ошибка customcontrol для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368823"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="cddbe-102">Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="cddbe-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="cddbe-103">Предоставляет определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cddbe-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="cddbe-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="cddbe-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="cddbe-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Формат</span><span class="sxs-lookup"><span data-stu-id="cddbe-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cddbe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cddbe-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="cddbe-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cddbe-107">Attributes and Elements</span></span>

<span data-ttu-id="cddbe-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomEntries`.</span><span class="sxs-lookup"><span data-stu-id="cddbe-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="cddbe-109">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="cddbe-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cddbe-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cddbe-110">Attributes</span></span>

<span data-ttu-id="cddbe-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="cddbe-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cddbe-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cddbe-112">Child Elements</span></span>

|<span data-ttu-id="cddbe-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="cddbe-113">Element</span></span>|<span data-ttu-id="cddbe-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cddbe-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cddbe-115">Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="cddbe-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="cddbe-116">Предоставляет определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cddbe-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cddbe-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cddbe-117">Parent Elements</span></span>

|<span data-ttu-id="cddbe-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="cddbe-118">Element</span></span>|<span data-ttu-id="cddbe-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cddbe-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cddbe-120">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="cddbe-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="cddbe-121">Определяет общий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="cddbe-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cddbe-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="cddbe-122">Remarks</span></span>

<span data-ttu-id="cddbe-123">В большинстве случаев элемент управления имеет только одно определение, которое определено в одном элементе `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="cddbe-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="cddbe-124">Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="cddbe-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="cddbe-125">В таких случаях можно определить элемент `CustomEntry` для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="cddbe-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="cddbe-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="cddbe-126">See Also</span></span>

[<span data-ttu-id="cddbe-127">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="cddbe-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="cddbe-128">Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="cddbe-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="cddbe-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="cddbe-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
