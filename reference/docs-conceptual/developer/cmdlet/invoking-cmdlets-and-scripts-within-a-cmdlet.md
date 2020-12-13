---
ms.date: 09/13/2016
ms.topic: reference
title: Вызов командлетов и сценариев внутри командлета
description: Вызов командлетов и сценариев внутри командлета
ms.openlocfilehash: 246c61661f2d290e7e7ac62a8ad303b05bdc7582
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652648"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="6df88-103">Вызов командлетов и сценариев внутри командлета</span><span class="sxs-lookup"><span data-stu-id="6df88-103">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="6df88-104">Командлет может вызывать другие командлеты и скрипты в методе обработки входных данных командлета.</span><span class="sxs-lookup"><span data-stu-id="6df88-104">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="6df88-105">Это позволяет добавлять в командлет функциональные возможности существующих командлетов и скриптов без необходимости переписывать код.</span><span class="sxs-lookup"><span data-stu-id="6df88-105">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="6df88-106">Метод Invoke</span><span class="sxs-lookup"><span data-stu-id="6df88-106">The Invoke Method</span></span>

<span data-ttu-id="6df88-107">Все командлеты могут вызывать существующий командлет, вызывая метод [System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) из метода обработки входных данных, например [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), который переопределяется командлетом.</span><span class="sxs-lookup"><span data-stu-id="6df88-107">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="6df88-108">Однако можно вызывать только те командлеты, которые являются производными непосредственно от класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="6df88-108">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="6df88-109">Нельзя вызвать командлет, производный от класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="6df88-109">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="6df88-110">Метод [System. Management. Automation. командлет. Invoke \*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) имеет следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="6df88-110">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="6df88-111">[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этот вариант вызывает объект командлета и возвращает коллекцию объектов типа "T".</span><span class="sxs-lookup"><span data-stu-id="6df88-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="6df88-112">[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает объект командлета и возвращает строго типизированный емумератор.</span><span class="sxs-lookup"><span data-stu-id="6df88-112">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="6df88-113">Этот вариант позволяет пользователю использовать объекты в коллекции для выполнения пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="6df88-113">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="6df88-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="6df88-114">Examples</span></span>

|<span data-ttu-id="6df88-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6df88-115">Example</span></span>|<span data-ttu-id="6df88-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6df88-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6df88-117">Вызов командлетов в командлете</span><span class="sxs-lookup"><span data-stu-id="6df88-117">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="6df88-118">В этом примере показано, как вызвать командлет из другого командлета.</span><span class="sxs-lookup"><span data-stu-id="6df88-118">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="6df88-119">Вызов скриптов в командлете</span><span class="sxs-lookup"><span data-stu-id="6df88-119">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="6df88-120">В этом примере показано, как вызвать скрипт, передаваемый в командлет из другого командлета.</span><span class="sxs-lookup"><span data-stu-id="6df88-120">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6df88-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6df88-121">See Also</span></span>

[<span data-ttu-id="6df88-122">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6df88-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
