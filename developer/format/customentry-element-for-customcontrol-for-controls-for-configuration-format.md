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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066479"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="98998-102">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="98998-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="98998-103">Предоставляет определение стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="98998-103">Provides a definition of the common control.</span></span> <span data-ttu-id="98998-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="98998-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="98998-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="98998-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="98998-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98998-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="98998-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="98998-107">Attributes and Elements</span></span>

<span data-ttu-id="98998-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="98998-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="98998-109">Необходимо указать элементы, отображаемые с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="98998-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="98998-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="98998-110">Attributes</span></span>

<span data-ttu-id="98998-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="98998-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="98998-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="98998-112">Child Elements</span></span>

|<span data-ttu-id="98998-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="98998-113">Element</span></span>|<span data-ttu-id="98998-114">Описание</span><span class="sxs-lookup"><span data-stu-id="98998-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="98998-115">Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="98998-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="98998-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="98998-116">Optional element.</span></span><br /><br /> <span data-ttu-id="98998-117">Определяет типы .NET, использующих определение общего элемента управления или условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="98998-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="98998-118">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="98998-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="98998-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="98998-119">Required element.</span></span><br /><br /> <span data-ttu-id="98998-120">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="98998-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="98998-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="98998-121">Parent Elements</span></span>

|<span data-ttu-id="98998-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="98998-122">Element</span></span>|<span data-ttu-id="98998-123">Описание</span><span class="sxs-lookup"><span data-stu-id="98998-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="98998-124">Элемент CustomEntries для пользовательский элемент управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="98998-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="98998-125">Предоставляет определения стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="98998-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="98998-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="98998-126">Remarks</span></span>

<span data-ttu-id="98998-127">В большинстве случаев для каждого распространенных пользовательского элемента управления необходим только одно определение, но можно иметь несколько определений, если вы хотите использовать тот же элемент управления для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="98998-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="98998-128">В таком случае можно задать отдельный определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="98998-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="98998-129">См. также</span><span class="sxs-lookup"><span data-stu-id="98998-129">See Also</span></span>

[<span data-ttu-id="98998-130">Элемент CustomEntries для пользовательский элемент управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="98998-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="98998-131">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="98998-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="98998-132">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="98998-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
