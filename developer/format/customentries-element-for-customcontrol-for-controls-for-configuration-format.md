---
title: Элемент CustomEntries для пользовательский элемент управления для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856310"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="93990-102">Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="93990-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="93990-103">Предоставляет определения стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="93990-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="93990-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="93990-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="93990-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Формат)</span><span class="sxs-lookup"><span data-stu-id="93990-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93990-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93990-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="93990-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="93990-107">Attributes and Elements</span></span>

<span data-ttu-id="93990-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomEntries` элемент.</span><span class="sxs-lookup"><span data-stu-id="93990-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="93990-109">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="93990-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="93990-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93990-110">Attributes</span></span>

<span data-ttu-id="93990-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="93990-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93990-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93990-112">Child Elements</span></span>

|<span data-ttu-id="93990-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="93990-113">Element</span></span>|<span data-ttu-id="93990-114">Описание</span><span class="sxs-lookup"><span data-stu-id="93990-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93990-115">Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="93990-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="93990-116">Предоставляет определение стандартного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="93990-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="93990-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93990-117">Parent Elements</span></span>

|<span data-ttu-id="93990-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="93990-118">Element</span></span>|<span data-ttu-id="93990-119">Описание</span><span class="sxs-lookup"><span data-stu-id="93990-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93990-120">Пользовательский элемент управления элемент для элемента управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="93990-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="93990-121">Определяет общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="93990-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="93990-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="93990-122">Remarks</span></span>

<span data-ttu-id="93990-123">В большинстве случаев элемент управления имеет только одно определение, который определен в одном `CustomEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="93990-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="93990-124">Тем не менее существует возможность иметь несколько определений, если вы хотите использовать тот же элемент управления для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="93990-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="93990-125">В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="93990-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="93990-126">См. также</span><span class="sxs-lookup"><span data-stu-id="93990-126">See Also</span></span>

[<span data-ttu-id="93990-127">Пользовательский элемент управления элемент для элемента управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="93990-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="93990-128">Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="93990-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="93990-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="93990-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
