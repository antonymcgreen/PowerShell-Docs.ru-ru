---
title: Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364073"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="65e13-102">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="65e13-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="65e13-103">Предоставляет определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65e13-103">Provides a definition of the common control.</span></span> <span data-ttu-id="65e13-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="65e13-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="65e13-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol элементов управления в конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="65e13-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65e13-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65e13-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="65e13-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="65e13-107">Attributes and Elements</span></span>

<span data-ttu-id="65e13-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="65e13-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="65e13-109">Необходимо указать элементы, отображаемые в определении.</span><span class="sxs-lookup"><span data-stu-id="65e13-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="65e13-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="65e13-110">Attributes</span></span>

<span data-ttu-id="65e13-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="65e13-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65e13-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="65e13-112">Child Elements</span></span>

|<span data-ttu-id="65e13-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="65e13-113">Element</span></span>|<span data-ttu-id="65e13-114">Описание</span><span class="sxs-lookup"><span data-stu-id="65e13-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65e13-115">Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="65e13-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="65e13-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="65e13-116">Optional element.</span></span><br /><br /> <span data-ttu-id="65e13-117">Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65e13-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="65e13-118">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="65e13-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="65e13-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="65e13-119">Required element.</span></span><br /><br /> <span data-ttu-id="65e13-120">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="65e13-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="65e13-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="65e13-121">Parent Elements</span></span>

|<span data-ttu-id="65e13-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="65e13-122">Element</span></span>|<span data-ttu-id="65e13-123">Описание</span><span class="sxs-lookup"><span data-stu-id="65e13-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65e13-124">Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="65e13-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="65e13-125">Предоставляет определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65e13-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="65e13-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="65e13-126">Remarks</span></span>

<span data-ttu-id="65e13-127">В большинстве случаев для каждого общего пользовательского элемента управления требуется только одно определение, но существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="65e13-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="65e13-128">В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="65e13-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="65e13-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="65e13-129">See Also</span></span>

[<span data-ttu-id="65e13-130">Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="65e13-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="65e13-131">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="65e13-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="65e13-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="65e13-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
