---
ms.date: 07/09/2020
ms.topic: reference
title: Члены класса системы расширенного типа
description: Члены класса системы расширенного типа
ms.openlocfilehash: 06488ce423f363a285ab53b21ab45989654346dc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666847"
---
# <a name="extended-type-system-class-members"></a><span data-ttu-id="85378-103">Члены класса системы расширенного типа</span><span class="sxs-lookup"><span data-stu-id="85378-103">Extended Type System class members</span></span>

<span data-ttu-id="85378-104">ETS ссылается на ряд различных видов членов, типы которых определяются перечислением **псмембертипес** .</span><span class="sxs-lookup"><span data-stu-id="85378-104">ETS refers to a number of different kinds of members whose types are defined by the **PSMemberTypes** enumeration.</span></span> <span data-ttu-id="85378-105">К этим типам членов относятся свойства, методы, члены и наборы элементов, определяемые их собственным типом CLR.</span><span class="sxs-lookup"><span data-stu-id="85378-105">These member types include properties, methods, members, and member sets that are each defined by their own CLR type.</span></span> <span data-ttu-id="85378-106">Например, **NoteProperty** определяется собственным типом **пснотепроперти** .</span><span class="sxs-lookup"><span data-stu-id="85378-106">For example, a **NoteProperty** is defined by its own **PSNoteProperty** type.</span></span> <span data-ttu-id="85378-107">Эти отдельные типы CLR имеют свои собственные уникальные свойства и общие свойства, унаследованные от [класса псмемберинфо](/dotnet/api/system.management.automation.psmemberinfo).</span><span class="sxs-lookup"><span data-stu-id="85378-107">These individual CLR types have both their own unique properties and common properties that are inherited from the [PSMemberInfo class](/dotnet/api/system.management.automation.psmemberinfo).</span></span>

## <a name="the-psmemberinfo-class"></a><span data-ttu-id="85378-108">Класс Псмемберинфо</span><span class="sxs-lookup"><span data-stu-id="85378-108">The PSMemberInfo class</span></span>

<span data-ttu-id="85378-109">Класс **псмемберинфо** выступает в качестве базового класса для всех типов элементов ETS.</span><span class="sxs-lookup"><span data-stu-id="85378-109">The **PSMemberInfo** class serves as a base class for all ETS member types.</span></span> <span data-ttu-id="85378-110">Этот класс предоставляет следующие базовые свойства для всех типов CLR элементов.</span><span class="sxs-lookup"><span data-stu-id="85378-110">This class provides the following base properties to all member CLR types.</span></span>

- <span data-ttu-id="85378-111">**Имя** свойство: имя элемента.</span><span class="sxs-lookup"><span data-stu-id="85378-111">**Name** property: The name of the member.</span></span> <span data-ttu-id="85378-112">Это имя может быть определено базовым объектом или определено с помощью PowerShell, когда предоставляются адаптированные члены или расширенные члены.</span><span class="sxs-lookup"><span data-stu-id="85378-112">This name can be defined by the base-object or defined by PowerShell when adapted members or extended members are exposed.</span></span>
- <span data-ttu-id="85378-113">Свойство **value** — значение, возвращенное из конкретного элемента.</span><span class="sxs-lookup"><span data-stu-id="85378-113">**Value** property: The value returned from the particular member.</span></span> <span data-ttu-id="85378-114">Каждый тип элемента определяет, как он обрабатывает его значение элемента.</span><span class="sxs-lookup"><span data-stu-id="85378-114">Each member type defines how it handles its member value.</span></span>
- <span data-ttu-id="85378-115">Свойство **типенамеофвалуе** : это имя типа CLR значения, возвращаемого свойством Value.</span><span class="sxs-lookup"><span data-stu-id="85378-115">**TypeNameOfValue** property: This is the name of the CLR type of the value that is returned by the Value property.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="85378-116">Доступ к членам</span><span class="sxs-lookup"><span data-stu-id="85378-116">Accessing members</span></span>

<span data-ttu-id="85378-117">Доступ к коллекциям элементов можно получить с помощью свойств **Members**, **Methods** и **Properties** объекта **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="85378-117">Collections of members can be accessed through the **Members**, **Methods**, and **Properties** properties of the **PSObject** object.</span></span>

## <a name="ets-properties"></a><span data-ttu-id="85378-118">Свойства ETS</span><span class="sxs-lookup"><span data-stu-id="85378-118">ETS properties</span></span>

<span data-ttu-id="85378-119">Свойства ETS — это члены, которые можно рассматривать как свойства.</span><span class="sxs-lookup"><span data-stu-id="85378-119">ETS properties are members that can be treated as a property.</span></span> <span data-ttu-id="85378-120">По сути, они могут присутствовать в левой части выражения.</span><span class="sxs-lookup"><span data-stu-id="85378-120">Essentially, they can appear on the left-hand side of an expression.</span></span> <span data-ttu-id="85378-121">К ним относятся свойства псевдонима, свойства кода, свойства PowerShell, свойства примечаний и свойства скриптов.</span><span class="sxs-lookup"><span data-stu-id="85378-121">They include alias properties, code properties, PowerShell properties, note properties, and script properties.</span></span> <span data-ttu-id="85378-122">Дополнительные сведения об этих типах свойств см. в разделе [Свойства ETS](properties.md).</span><span class="sxs-lookup"><span data-stu-id="85378-122">For more information about these types of properties, see [ETS properties](properties.md).</span></span>

## <a name="ets-methods"></a><span data-ttu-id="85378-123">Методы ETS</span><span class="sxs-lookup"><span data-stu-id="85378-123">ETS methods</span></span>

<span data-ttu-id="85378-124">Методы ETS — это члены, которые могут принимать аргументы, могут возвращать результаты и не могут отображаться в левой части выражения.</span><span class="sxs-lookup"><span data-stu-id="85378-124">ETS methods are members that can take arguments, may return results, and cannot appear on the left-hand side of an expression.</span></span> <span data-ttu-id="85378-125">К ним относятся методы кода, методы PowerShell и методы скриптов.</span><span class="sxs-lookup"><span data-stu-id="85378-125">They include code methods, PowerShell methods, and script methods.</span></span>
<span data-ttu-id="85378-126">Дополнительные сведения об этих типах методов см. в разделе [методы ETS](methods.md).</span><span class="sxs-lookup"><span data-stu-id="85378-126">For more information about these types of methods, see [ETS methods](methods.md).</span></span>
