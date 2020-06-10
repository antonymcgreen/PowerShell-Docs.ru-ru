---
title: AccessDBProviderSample05 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a26661f2-a63c-4ca7-ad3e-dcb4d32ce5a1
caps.latest.revision: 8
ms.openlocfilehash: 43d18672ec4f52961b2a2460635468a2d6fb41e5
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633385"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="00c7f-102">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="00c7f-102">AccessDBProviderSample05</span></span>

<span data-ttu-id="00c7f-103">В этом примере показано, как перезаписать методы контейнера для поддержки вызовов `Move-Item` `Join-Path` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="00c7f-103">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="00c7f-104">Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="00c7f-104">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="00c7f-105">Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="00c7f-106">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="00c7f-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00c7f-107">Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="00c7f-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="00c7f-108">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="00c7f-109">См. [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="00c7f-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="00c7f-110">Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="00c7f-111">См. [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="00c7f-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="00c7f-112">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="00c7f-113">Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="00c7f-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="00c7f-114">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="00c7f-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="00c7f-115">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="00c7f-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="00c7f-116">Определение класса поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="00c7f-117">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) для изменения поведения `Move-Item` командлета, позволяя пользователю перемещать элементы из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="00c7f-117">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="00c7f-118">(В этом примере не показано, как добавить динамические параметры в `Move-Item` командлет.)</span><span class="sxs-lookup"><span data-stu-id="00c7f-118">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="00c7f-119">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. макепас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) для изменения поведения `Join-Path` командлета.</span><span class="sxs-lookup"><span data-stu-id="00c7f-119">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="00c7f-120">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="00c7f-121">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетчилднаме \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="00c7f-122">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетпарентпас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="00c7f-123">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. нормализерелативепас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) .</span><span class="sxs-lookup"><span data-stu-id="00c7f-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="00c7f-124">Пример</span><span class="sxs-lookup"><span data-stu-id="00c7f-124">Example</span></span>

<span data-ttu-id="00c7f-125">В этом примере показано, как перезаписать методы, необходимые для перемещения элементов в базе данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="00c7f-125">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="00c7f-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="00c7f-126">See Also</span></span>

[<span data-ttu-id="00c7f-127">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="00c7f-127">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="00c7f-128">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="00c7f-128">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="00c7f-129">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="00c7f-129">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="00c7f-130">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00c7f-130">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
