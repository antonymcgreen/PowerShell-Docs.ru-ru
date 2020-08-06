---
title: Элемент Кустоментриес для ошибка customcontrol для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b1f494cf1a254d71362830ba9eb0f4905a2a484d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785988"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="64819-102">Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="64819-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="64819-103">Предоставляет определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64819-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="64819-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="64819-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="64819-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="64819-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="64819-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64819-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="64819-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="64819-107">Attributes and Elements</span></span>

<span data-ttu-id="64819-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="64819-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="64819-109">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="64819-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="64819-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="64819-110">Attributes</span></span>

<span data-ttu-id="64819-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="64819-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="64819-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="64819-112">Child Elements</span></span>

|<span data-ttu-id="64819-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="64819-113">Element</span></span>|<span data-ttu-id="64819-114">Описание</span><span class="sxs-lookup"><span data-stu-id="64819-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64819-115">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="64819-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="64819-116">Предоставляет определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64819-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="64819-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="64819-117">Parent Elements</span></span>

|<span data-ttu-id="64819-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="64819-118">Element</span></span>|<span data-ttu-id="64819-119">Описание</span><span class="sxs-lookup"><span data-stu-id="64819-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64819-120">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="64819-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="64819-121">Определяет общий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="64819-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="64819-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="64819-122">Remarks</span></span>

<span data-ttu-id="64819-123">В большинстве случаев элемент управления имеет только одно определение, которое определено в одном `CustomEntry` элементе.</span><span class="sxs-lookup"><span data-stu-id="64819-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="64819-124">Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="64819-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="64819-125">В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="64819-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="64819-126">См. также</span><span class="sxs-lookup"><span data-stu-id="64819-126">See Also</span></span>

[<span data-ttu-id="64819-127">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="64819-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="64819-128">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="64819-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="64819-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="64819-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
