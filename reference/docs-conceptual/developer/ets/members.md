---
title: Члены класса системы расширенного типа
ms.date: 07/09/2020
ms.topic: conceptual
ms.openlocfilehash: c066bd69c0ab20cceff96aa789654e80443758e5
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217985"
---
# <a name="extended-type-system-class-members"></a><span data-ttu-id="be212-102">Члены класса системы расширенного типа</span><span class="sxs-lookup"><span data-stu-id="be212-102">Extended Type System class members</span></span>

<span data-ttu-id="be212-103">ETS ссылается на ряд различных видов членов, типы которых определяются перечислением **псмембертипес** .</span><span class="sxs-lookup"><span data-stu-id="be212-103">ETS refers to a number of different kinds of members whose types are defined by the **PSMemberTypes** enumeration.</span></span> <span data-ttu-id="be212-104">К этим типам членов относятся свойства, методы, члены и наборы элементов, определяемые их собственным типом CLR.</span><span class="sxs-lookup"><span data-stu-id="be212-104">These member types include properties, methods, members, and member sets that are each defined by their own CLR type.</span></span> <span data-ttu-id="be212-105">Например, **NoteProperty** определяется собственным типом **пснотепроперти** .</span><span class="sxs-lookup"><span data-stu-id="be212-105">For example, a **NoteProperty** is defined by its own **PSNoteProperty** type.</span></span> <span data-ttu-id="be212-106">Эти отдельные типы CLR имеют свои собственные уникальные свойства и общие свойства, унаследованные от [класса псмемберинфо](/dotnet/api/system.management.automation.psmemberinfo).</span><span class="sxs-lookup"><span data-stu-id="be212-106">These individual CLR types have both their own unique properties and common properties that are inherited from the [PSMemberInfo class](/dotnet/api/system.management.automation.psmemberinfo).</span></span>

## <a name="the-psmemberinfo-class"></a><span data-ttu-id="be212-107">Класс Псмемберинфо</span><span class="sxs-lookup"><span data-stu-id="be212-107">The PSMemberInfo class</span></span>

<span data-ttu-id="be212-108">Класс **псмемберинфо** выступает в качестве базового класса для всех типов элементов ETS.</span><span class="sxs-lookup"><span data-stu-id="be212-108">The **PSMemberInfo** class serves as a base class for all ETS member types.</span></span> <span data-ttu-id="be212-109">Этот класс предоставляет следующие базовые свойства для всех типов CLR элементов.</span><span class="sxs-lookup"><span data-stu-id="be212-109">This class provides the following base properties to all member CLR types.</span></span>

- <span data-ttu-id="be212-110">**Имя** свойство: имя элемента.</span><span class="sxs-lookup"><span data-stu-id="be212-110">**Name** property: The name of the member.</span></span> <span data-ttu-id="be212-111">Это имя может быть определено базовым объектом или определено с помощью PowerShell, когда предоставляются адаптированные члены или расширенные члены.</span><span class="sxs-lookup"><span data-stu-id="be212-111">This name can be defined by the base-object or defined by PowerShell when adapted members or extended members are exposed.</span></span>
- <span data-ttu-id="be212-112">Свойство **value** — значение, возвращенное из конкретного элемента.</span><span class="sxs-lookup"><span data-stu-id="be212-112">**Value** property: The value returned from the particular member.</span></span> <span data-ttu-id="be212-113">Каждый тип элемента определяет, как он обрабатывает его значение элемента.</span><span class="sxs-lookup"><span data-stu-id="be212-113">Each member type defines how it handles its member value.</span></span>
- <span data-ttu-id="be212-114">Свойство **типенамеофвалуе** : это имя типа CLR значения, возвращаемого свойством Value.</span><span class="sxs-lookup"><span data-stu-id="be212-114">**TypeNameOfValue** property: This is the name of the CLR type of the value that is returned by the Value property.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="be212-115">Доступ к членам</span><span class="sxs-lookup"><span data-stu-id="be212-115">Accessing members</span></span>

<span data-ttu-id="be212-116">Доступ к коллекциям элементов можно получить с помощью свойств **Members**, **Methods**и **Properties** объекта **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="be212-116">Collections of members can be accessed through the **Members**, **Methods**, and **Properties** properties of the **PSObject** object.</span></span>

## <a name="ets-properties"></a><span data-ttu-id="be212-117">Свойства ETS</span><span class="sxs-lookup"><span data-stu-id="be212-117">ETS properties</span></span>

<span data-ttu-id="be212-118">Свойства ETS — это члены, которые можно рассматривать как свойства.</span><span class="sxs-lookup"><span data-stu-id="be212-118">ETS properties are members that can be treated as a property.</span></span> <span data-ttu-id="be212-119">По сути, они могут присутствовать в левой части выражения.</span><span class="sxs-lookup"><span data-stu-id="be212-119">Essentially, they can appear on the left-hand side of an expression.</span></span> <span data-ttu-id="be212-120">К ним относятся свойства псевдонима, свойства кода, свойства PowerShell, свойства примечаний и свойства скриптов.</span><span class="sxs-lookup"><span data-stu-id="be212-120">They include alias properties, code properties, PowerShell properties, note properties, and script properties.</span></span> <span data-ttu-id="be212-121">Дополнительные сведения об этих типах свойств см. в разделе [Свойства ETS](properties.md).</span><span class="sxs-lookup"><span data-stu-id="be212-121">For more information about these types of properties, see [ETS properties](properties.md).</span></span>

## <a name="ets-methods"></a><span data-ttu-id="be212-122">Методы ETS</span><span class="sxs-lookup"><span data-stu-id="be212-122">ETS methods</span></span>

<span data-ttu-id="be212-123">Методы ETS — это члены, которые могут принимать аргументы, могут возвращать результаты и не могут отображаться в левой части выражения.</span><span class="sxs-lookup"><span data-stu-id="be212-123">ETS methods are members that can take arguments, may return results, and cannot appear on the left-hand side of an expression.</span></span> <span data-ttu-id="be212-124">К ним относятся методы кода, методы PowerShell и методы скриптов.</span><span class="sxs-lookup"><span data-stu-id="be212-124">They include code methods, PowerShell methods, and script methods.</span></span>
<span data-ttu-id="be212-125">Дополнительные сведения об этих типах методов см. в разделе [методы ETS](methods.md).</span><span class="sxs-lookup"><span data-stu-id="be212-125">For more information about these types of methods, see [ETS methods](methods.md).</span></span>
