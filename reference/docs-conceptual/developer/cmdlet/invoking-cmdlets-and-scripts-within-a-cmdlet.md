---
title: Вызов командлетов и скриптов в командлете | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364293"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="5ef53-102">Вызов командлетов и сценариев внутри командлета</span><span class="sxs-lookup"><span data-stu-id="5ef53-102">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="5ef53-103">Командлет может вызывать другие командлеты и скрипты в методе обработки входных данных командлета.</span><span class="sxs-lookup"><span data-stu-id="5ef53-103">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="5ef53-104">Это позволяет добавлять в командлет функциональные возможности существующих командлетов и скриптов без необходимости переписывать код.</span><span class="sxs-lookup"><span data-stu-id="5ef53-104">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="5ef53-105">Метод Invoke</span><span class="sxs-lookup"><span data-stu-id="5ef53-105">The Invoke Method</span></span>

<span data-ttu-id="5ef53-106">Все командлеты могут вызывать существующий командлет, вызывая метод [System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) из метода обработки входных данных, например [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), который переопределяется командлетом.</span><span class="sxs-lookup"><span data-stu-id="5ef53-106">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="5ef53-107">Однако можно вызывать только те командлеты, которые являются производными непосредственно от класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="5ef53-107">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="5ef53-108">Нельзя вызвать командлет, производный от класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="5ef53-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="5ef53-109">Метод [System. Management. Automation. командлет. Invoke \*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) имеет следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="5ef53-109">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="5ef53-110">[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этот вариант вызывает объект командлета и возвращает коллекцию объектов типа "T".</span><span class="sxs-lookup"><span data-stu-id="5ef53-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="5ef53-111">[System. Management. Automation. командлет. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает объект командлета и возвращает строго типизированный емумератор.</span><span class="sxs-lookup"><span data-stu-id="5ef53-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="5ef53-112">Этот вариант позволяет пользователю использовать объекты в коллекции для выполнения пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="5ef53-112">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="5ef53-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="5ef53-113">Examples</span></span>

|<span data-ttu-id="5ef53-114">Пример</span><span class="sxs-lookup"><span data-stu-id="5ef53-114">Example</span></span>|<span data-ttu-id="5ef53-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5ef53-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ef53-116">Вызов командлетов в командлете</span><span class="sxs-lookup"><span data-stu-id="5ef53-116">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="5ef53-117">В этом примере показано, как вызвать командлет из другого командлета.</span><span class="sxs-lookup"><span data-stu-id="5ef53-117">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="5ef53-118">Вызов скриптов в командлете</span><span class="sxs-lookup"><span data-stu-id="5ef53-118">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="5ef53-119">В этом примере показано, как вызвать скрипт, передаваемый в командлет из другого командлета.</span><span class="sxs-lookup"><span data-stu-id="5ef53-119">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5ef53-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ef53-120">See Also</span></span>

[<span data-ttu-id="5ef53-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ef53-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
