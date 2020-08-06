---
title: AccessDBProviderSample05 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 67a10d9192350b339da1b82d9eb367ee4af6ef86
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786855"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="756ed-102">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="756ed-102">AccessDBProviderSample05</span></span>

<span data-ttu-id="756ed-103">В этом примере показано, как перезаписать методы контейнера для поддержки вызовов `Move-Item` `Join-Path` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="756ed-103">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="756ed-104">Эти методы должны быть реализованы, когда пользователю требуется переместить элементы в контейнере, если хранилище данных содержит вложенные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="756ed-104">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="756ed-105">Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="756ed-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="756ed-106">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="756ed-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="756ed-107">Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="756ed-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="756ed-108">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="756ed-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="756ed-109">См. [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="756ed-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="756ed-110">Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="756ed-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="756ed-111">См. [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="756ed-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="756ed-112">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="756ed-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="756ed-113">Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="756ed-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="756ed-114">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="756ed-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="756ed-115">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="756ed-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="756ed-116">Определение класса поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="756ed-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="756ed-117">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. мовеитем \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) для изменения поведения `Move-Item` командлета, позволяя пользователю перемещать элементы из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="756ed-117">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="756ed-118">(В этом примере не показано, как добавить динамические параметры в `Move-Item` командлет.)</span><span class="sxs-lookup"><span data-stu-id="756ed-118">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="756ed-119">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. макепас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) для изменения поведения `Join-Path` командлета.</span><span class="sxs-lookup"><span data-stu-id="756ed-119">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="756ed-120">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. иситемконтаинер \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) .</span><span class="sxs-lookup"><span data-stu-id="756ed-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="756ed-121">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетчилднаме \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) .</span><span class="sxs-lookup"><span data-stu-id="756ed-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="756ed-122">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. жетпарентпас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) .</span><span class="sxs-lookup"><span data-stu-id="756ed-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="756ed-123">Перезапись метода [System. Management. Automation. Provider. Navigationcmdletprovider. нормализерелативепас \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) .</span><span class="sxs-lookup"><span data-stu-id="756ed-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="756ed-124">Пример</span><span class="sxs-lookup"><span data-stu-id="756ed-124">Example</span></span>

<span data-ttu-id="756ed-125">В этом примере показано, как перезаписать методы, необходимые для перемещения элементов в базе данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="756ed-125">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="756ed-126">См. также</span><span class="sxs-lookup"><span data-stu-id="756ed-126">See Also</span></span>

[<span data-ttu-id="756ed-127">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="756ed-127">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="756ed-128">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="756ed-128">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="756ed-129">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="756ed-129">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="756ed-130">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="756ed-130">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
