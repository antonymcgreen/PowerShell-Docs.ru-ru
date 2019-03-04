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
ms.openlocfilehash: fd013384a4b588bcdb397d7771425fe5c031c48f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856700"
---
# <a name="accessdbprovidersample04"></a><span data-ttu-id="b2b70-102">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="b2b70-102">AccessDBProviderSample04</span></span>

<span data-ttu-id="b2b70-103">В этом примере показано, как перезаписать методы контейнера для поддержки вызовов в `Copy-Item`, `Get-ChildItem`, `New-Item`, и `Remove-Item` командлетов.</span><span class="sxs-lookup"><span data-stu-id="b2b70-103">This sample shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span> <span data-ttu-id="b2b70-104">Эти методы должны быть реализованы, когда хранилище данных содержит элементы, являющиеся контейнерами.</span><span class="sxs-lookup"><span data-stu-id="b2b70-104">These methods should be implemented when the data store contains items that are containers.</span></span> <span data-ttu-id="b2b70-105">Контейнер — это группа дочерних элементов в составе общего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="b2b70-105">A container is a group of child items under a common parent item.</span></span> <span data-ttu-id="b2b70-106">Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="b2b70-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="b2b70-107">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="b2b70-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2b70-108">Класс поставщика, скорее всего будут производными от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span><span class="sxs-lookup"><span data-stu-id="b2b70-108">Your provider class will most likely derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span></span>

<span data-ttu-id="b2b70-109">Этот образец демонстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="b2b70-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="b2b70-110">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="b2b70-110">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="b2b70-111">Определение класса поставщика, который является производным от [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="b2b70-111">Defining a provider class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

- <span data-ttu-id="b2b70-112">Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Copyitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) метод, чтобы изменить поведение `Copy-Item` командлет, который позволяет пользователю копировать элементы из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="b2b70-112">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Copyitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to change the behavior of the `Copy-Item` cmdlet which allows the user to copy items from one location to another.</span></span> <span data-ttu-id="b2b70-113">(В этом примере показано, как добавлять динамические параметры для `Copy-Item` командлет.)</span><span class="sxs-lookup"><span data-stu-id="b2b70-113">(This sample does not show how to add dynamic parameters to the `Copy-Item` cmdlet.)</span></span>

- <span data-ttu-id="b2b70-114">Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) метод, чтобы изменить поведение командлет Get-ChildItems, который позволяет пользователю получить дочерние элементы родительского элемента .</span><span class="sxs-lookup"><span data-stu-id="b2b70-114">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to change the behavior of the Get-ChildItems cmdlet, which allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="b2b70-115">(В этом примере показано, как добавлять динамические параметры в командлет Get-ChildItems.)</span><span class="sxs-lookup"><span data-stu-id="b2b70-115">(This sample does not show how to add dynamic parameters to the Get-ChildItems cmdlet.)</span></span>

- <span data-ttu-id="b2b70-116">Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) метод, чтобы изменить поведение командлета Get-ChildItems при `Name` указан параметр командлета.</span><span class="sxs-lookup"><span data-stu-id="b2b70-116">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to change the behavior of the Get-ChildItems cmdlet when the `Name` parameter of the cmdlet is specified.</span></span>

- <span data-ttu-id="b2b70-117">Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) метод, чтобы изменить поведение `New-Item` командлет, который позволяет пользователю добавлять элементы в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="b2b70-117">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to change the behavior of the `New-Item` cmdlet, which allows the user to add items to the data store.</span></span> <span data-ttu-id="b2b70-118">(В этом примере показано, как добавлять динамические параметры для `New-Item` командлет.)</span><span class="sxs-lookup"><span data-stu-id="b2b70-118">(This sample does not show how to add dynamic parameters to the `New-Item` cmdlet.)</span></span>

- <span data-ttu-id="b2b70-119">Перезапись [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) метод, чтобы изменить поведение `Remove-Item` командлета.</span><span class="sxs-lookup"><span data-stu-id="b2b70-119">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to change the behavior of the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="b2b70-120">(В этом примере показано, как добавлять динамические параметры для `Remove-Item` командлет.)</span><span class="sxs-lookup"><span data-stu-id="b2b70-120">(This sample does not show how to add dynamic parameters to the `Remove-Item` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="b2b70-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b2b70-121">Example</span></span>

<span data-ttu-id="b2b70-122">В этом примере показано, как перезаписать методы, необходимые для копирования, создавать и удалять элементы, а также методы для получения дочерних элементов родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="b2b70-122">This sample shows how to overwrite the methods needed to copy, create, and remove items, as well as methods for getting the child items of a parent item.</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="b2b70-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b2b70-123">See Also</span></span>

[<span data-ttu-id="b2b70-124">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="b2b70-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="b2b70-125">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="b2b70-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="b2b70-126">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="b2b70-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="b2b70-127">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2b70-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)