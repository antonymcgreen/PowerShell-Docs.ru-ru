---
title: Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859810"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="7f9af-102">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="7f9af-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7f9af-103">Предоставляет определение стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7f9af-103">Provides a definition of the common control.</span></span> <span data-ttu-id="7f9af-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="7f9af-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7f9af-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7f9af-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7f9af-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f9af-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f9af-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7f9af-107">Attributes and Elements</span></span>

<span data-ttu-id="7f9af-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="7f9af-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="7f9af-109">Необходимо указать элементы, отображаемые с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="7f9af-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f9af-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f9af-110">Attributes</span></span>

<span data-ttu-id="7f9af-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="7f9af-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7f9af-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f9af-112">Child Elements</span></span>

|<span data-ttu-id="7f9af-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f9af-113">Element</span></span>|<span data-ttu-id="7f9af-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7f9af-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f9af-115">Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7f9af-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="7f9af-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7f9af-116">Optional element.</span></span><br /><br /> <span data-ttu-id="7f9af-117">Определяет типы .NET, использующих определение общего элемента управления или условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="7f9af-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="7f9af-118">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="7f9af-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="7f9af-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7f9af-119">Required element.</span></span><br /><br /> <span data-ttu-id="7f9af-120">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="7f9af-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7f9af-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f9af-121">Parent Elements</span></span>

|<span data-ttu-id="7f9af-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f9af-122">Element</span></span>|<span data-ttu-id="7f9af-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7f9af-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f9af-124">Элемент CustomEntries для пользовательский элемент управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7f9af-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="7f9af-125">Предоставляет определения стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7f9af-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f9af-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="7f9af-126">Remarks</span></span>

<span data-ttu-id="7f9af-127">В большинстве случаев для каждого распространенных пользовательского элемента управления необходим только одно определение, но можно иметь несколько определений, если вы хотите использовать тот же элемент управления для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="7f9af-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="7f9af-128">В таком случае можно задать отдельный определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="7f9af-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f9af-129">См. также</span><span class="sxs-lookup"><span data-stu-id="7f9af-129">See Also</span></span>

[<span data-ttu-id="7f9af-130">Элемент CustomEntries для пользовательский элемент управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7f9af-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="7f9af-131">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="7f9af-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="7f9af-132">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f9af-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
