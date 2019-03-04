---
title: Вызов командлеты и сценарии в командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: e5dc525a6c80ce135d6d68e12968613056d447e8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855190"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="944d0-102">Вызов командлетов и сценариев внутри командлета</span><span class="sxs-lookup"><span data-stu-id="944d0-102">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="944d0-103">Командлет можно вызывать другие командлеты и сценарии из в метод командлета обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="944d0-103">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="944d0-104">Это позволяет добавить функциональные возможности существующих командлетов и скриптов для командлета не требуется переписывать код.</span><span class="sxs-lookup"><span data-stu-id="944d0-104">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="944d0-105">Вызов метода</span><span class="sxs-lookup"><span data-stu-id="944d0-105">The Invoke Method</span></span>

<span data-ttu-id="944d0-106">Все командлеты могут вызывать существующий командлет с помощью [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) метода в метод, например обработки входных данных [ System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), то есть переопределено с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="944d0-106">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="944d0-107">Тем не менее, можно вызвать только нужные командлеты, которые наследуются от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класса.</span><span class="sxs-lookup"><span data-stu-id="944d0-107">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="944d0-108">Не удается вызвать командлет, который является производным от [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) класса.</span><span class="sxs-lookup"><span data-stu-id="944d0-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="944d0-109">[System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) метод имеет следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="944d0-109">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="944d0-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает командлет объекта и возвращает коллекцию объектов типа «T».</span><span class="sxs-lookup"><span data-stu-id="944d0-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="944d0-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает командлет объекта и возвращает строго типизированный emumerator.</span><span class="sxs-lookup"><span data-stu-id="944d0-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="944d0-112">Этот вариант позволяет использовать объекты в коллекции для выполнения пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="944d0-112">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="944d0-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="944d0-113">Examples</span></span>

|<span data-ttu-id="944d0-114">Пример</span><span class="sxs-lookup"><span data-stu-id="944d0-114">Example</span></span>|<span data-ttu-id="944d0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="944d0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="944d0-116">Вызов командлеты в командлет</span><span class="sxs-lookup"><span data-stu-id="944d0-116">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="944d0-117">В этом примере показано, как для вызова командлета из в другой командлет.</span><span class="sxs-lookup"><span data-stu-id="944d0-117">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="944d0-118">Вызов скриптов в командлет</span><span class="sxs-lookup"><span data-stu-id="944d0-118">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="944d0-119">В этом примере показано, как вызвать скрипт, который передается в командлет в другой командлет.</span><span class="sxs-lookup"><span data-stu-id="944d0-119">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="944d0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="944d0-120">See Also</span></span>

[<span data-ttu-id="944d0-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="944d0-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
