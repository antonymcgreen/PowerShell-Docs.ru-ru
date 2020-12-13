---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample01
description: AccessDBProviderSample01
ms.openlocfilehash: 8bdfa3ad492935a22ce06846294c02961cab2c65
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653747"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="d3692-103">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="d3692-103">AccessDBProviderSample01</span></span>

<span data-ttu-id="d3692-104">В этом примере показано, как объявить класс поставщика, производный непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d3692-104">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="d3692-105">Он приводится здесь только для полноты картины.</span><span class="sxs-lookup"><span data-stu-id="d3692-105">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d3692-106">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="d3692-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3692-107">Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="d3692-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="d3692-108">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d3692-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="d3692-109">См. [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="d3692-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="d3692-110">Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d3692-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="d3692-111">См. [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="d3692-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="d3692-112">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d3692-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="d3692-113">См. [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="d3692-113">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="d3692-114">Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="d3692-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="d3692-115">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="d3692-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="d3692-116">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="d3692-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="d3692-117">Определение класса поставщика, производного непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="d3692-117">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="d3692-118">Пример</span><span class="sxs-lookup"><span data-stu-id="d3692-118">Example</span></span>

<span data-ttu-id="d3692-119">В этом примере показано, как определить класс поставщика и как объявить `CmdletProvider` атрибут.</span><span class="sxs-lookup"><span data-stu-id="d3692-119">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="d3692-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3692-120">See Also</span></span>

[<span data-ttu-id="d3692-121">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="d3692-121">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="d3692-122">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="d3692-122">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="d3692-123">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="d3692-123">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="d3692-124">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3692-124">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
