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
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067677"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="d8361-102">Вызов командлетов и сценариев внутри командлета</span><span class="sxs-lookup"><span data-stu-id="d8361-102">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="d8361-103">Командлет можно вызывать другие командлеты и сценарии из в метод командлета обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="d8361-103">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="d8361-104">Это позволяет добавить функциональные возможности существующих командлетов и скриптов для командлета не требуется переписывать код.</span><span class="sxs-lookup"><span data-stu-id="d8361-104">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="d8361-105">Вызов метода</span><span class="sxs-lookup"><span data-stu-id="d8361-105">The Invoke Method</span></span>

<span data-ttu-id="d8361-106">Все командлеты могут вызывать существующий командлет с помощью [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) метода в метод, например обработки входных данных [ System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), то есть переопределено с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="d8361-106">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="d8361-107">Тем не менее, можно вызвать только нужные командлеты, которые наследуются от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класса.</span><span class="sxs-lookup"><span data-stu-id="d8361-107">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="d8361-108">Не удается вызвать командлет, который является производным от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) класса.</span><span class="sxs-lookup"><span data-stu-id="d8361-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="d8361-109">[System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) метод имеет следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="d8361-109">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="d8361-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает командлет объекта и возвращает коллекцию объектов типа «T».</span><span class="sxs-lookup"><span data-stu-id="d8361-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="d8361-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) этого варианта вызывает командлет объекта и возвращает строго типизированный emumerator.</span><span class="sxs-lookup"><span data-stu-id="d8361-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="d8361-112">Этот вариант позволяет использовать объекты в коллекции для выполнения пользовательских операций.</span><span class="sxs-lookup"><span data-stu-id="d8361-112">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="d8361-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="d8361-113">Examples</span></span>

|<span data-ttu-id="d8361-114">Пример</span><span class="sxs-lookup"><span data-stu-id="d8361-114">Example</span></span>|<span data-ttu-id="d8361-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d8361-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d8361-116">Вызов командлеты в командлет</span><span class="sxs-lookup"><span data-stu-id="d8361-116">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="d8361-117">В этом примере показано, как для вызова командлета из в другой командлет.</span><span class="sxs-lookup"><span data-stu-id="d8361-117">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="d8361-118">Вызов скриптов в командлет</span><span class="sxs-lookup"><span data-stu-id="d8361-118">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="d8361-119">В этом примере показано, как вызвать скрипт, который передается в командлет в другой командлет.</span><span class="sxs-lookup"><span data-stu-id="d8361-119">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d8361-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d8361-120">See Also</span></span>

[<span data-ttu-id="d8361-121">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8361-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
