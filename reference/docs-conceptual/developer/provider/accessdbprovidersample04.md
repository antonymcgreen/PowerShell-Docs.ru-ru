---
title: AccessDBProviderSample04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: 7096f8066568c214a5902f6943a2c093932d3b56
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366343"
---
# <a name="accessdbprovidersample04"></a><span data-ttu-id="9fd59-102">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="9fd59-102">AccessDBProviderSample04</span></span>

<span data-ttu-id="9fd59-103">В этом примере показано, как перезаписать методы контейнера для поддержки вызовов командлетов `Copy-Item`, `Get-ChildItem`, `New-Item` и `Remove-Item`.</span><span class="sxs-lookup"><span data-stu-id="9fd59-103">This sample shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span> <span data-ttu-id="9fd59-104">Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами.</span><span class="sxs-lookup"><span data-stu-id="9fd59-104">These methods should be implemented when the data store contains items that are containers.</span></span> <span data-ttu-id="9fd59-105">Контейнер — это группа дочерних элементов в составе общего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="9fd59-105">A container is a group of child items under a common parent item.</span></span> <span data-ttu-id="9fd59-106">Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="9fd59-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="9fd59-107">Демонстрирующее</span><span class="sxs-lookup"><span data-stu-id="9fd59-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fd59-108">Скорее всего, класс поставщика будет производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="9fd59-108">Your provider class will most likely derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span></span>

<span data-ttu-id="9fd59-109">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="9fd59-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="9fd59-110">Объявление атрибута `CmdletProvider`.</span><span class="sxs-lookup"><span data-stu-id="9fd59-110">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="9fd59-111">Определение класса поставщика, производного от класса [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="9fd59-111">Defining a provider class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

- <span data-ttu-id="9fd59-112">Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) для изменения поведения командлета `Copy-Item`, позволяющего пользователю копировать элементы из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="9fd59-112">Overwriting the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to change the behavior of the `Copy-Item` cmdlet which allows the user to copy items from one location to another.</span></span> <span data-ttu-id="9fd59-113">(В этом примере не показано, как добавлять динамические параметры в командлет `Copy-Item`).</span><span class="sxs-lookup"><span data-stu-id="9fd59-113">(This sample does not show how to add dynamic parameters to the `Copy-Item` cmdlet.)</span></span>

- <span data-ttu-id="9fd59-114">Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилдитемс \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) для изменения поведения командлета Get-чилдитемс, который позволяет пользователю получить дочерние элементы родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="9fd59-114">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to change the behavior of the Get-ChildItems cmdlet, which allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="9fd59-115">(В этом примере не показано, как добавлять динамические параметры в командлет Get-Чилдитемс.)</span><span class="sxs-lookup"><span data-stu-id="9fd59-115">(This sample does not show how to add dynamic parameters to the Get-ChildItems cmdlet.)</span></span>

- <span data-ttu-id="9fd59-116">Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. жетчилднамес \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) для изменения поведения командлета Get-чилдитемс при указании параметра `Name` командлета.</span><span class="sxs-lookup"><span data-stu-id="9fd59-116">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to change the behavior of the Get-ChildItems cmdlet when the `Name` parameter of the cmdlet is specified.</span></span>

- <span data-ttu-id="9fd59-117">Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. newItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) для изменения поведения командлета `New-Item`, который позволяет пользователю добавлять элементы в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="9fd59-117">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to change the behavior of the `New-Item` cmdlet, which allows the user to add items to the data store.</span></span> <span data-ttu-id="9fd59-118">(В этом примере не показано, как добавлять динамические параметры в командлет `New-Item`).</span><span class="sxs-lookup"><span data-stu-id="9fd59-118">(This sample does not show how to add dynamic parameters to the `New-Item` cmdlet.)</span></span>

- <span data-ttu-id="9fd59-119">Перезапись метода [System. Management. Automation. Provider. контаинеркмдлетпровидер. RemoveItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) для изменения поведения командлета `Remove-Item`.</span><span class="sxs-lookup"><span data-stu-id="9fd59-119">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to change the behavior of the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="9fd59-120">(В этом примере не показано, как добавлять динамические параметры в командлет `Remove-Item`).</span><span class="sxs-lookup"><span data-stu-id="9fd59-120">(This sample does not show how to add dynamic parameters to the `Remove-Item` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="9fd59-121">Пример</span><span class="sxs-lookup"><span data-stu-id="9fd59-121">Example</span></span>

<span data-ttu-id="9fd59-122">В этом примере показано, как перезаписать методы, необходимые для копирования, создания и удаления элементов, а также методы получения дочерних элементов родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="9fd59-122">This sample shows how to overwrite the methods needed to copy, create, and remove items, as well as methods for getting the child items of a parent item.</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="9fd59-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="9fd59-123">See Also</span></span>

[<span data-ttu-id="9fd59-124">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="9fd59-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="9fd59-125">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="9fd59-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="9fd59-126">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="9fd59-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="9fd59-127">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fd59-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
