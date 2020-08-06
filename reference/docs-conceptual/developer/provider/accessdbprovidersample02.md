---
title: AccessDBProviderSample02 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e9a0444d17bec230633e1dd1709455f6ba83dd5c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786906"
---
# <a name="accessdbprovidersample02"></a><span data-ttu-id="9e536-102">AccessDBProviderSample02</span><span class="sxs-lookup"><span data-stu-id="9e536-102">AccessDBProviderSample02</span></span>

<span data-ttu-id="9e536-103">В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки вызовов `New-PSDrive` `Remove-PSDrive` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="9e536-103">This sample shows how to overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods to support calls to the `New-PSDrive` and `Remove-PSDrive` cmdlets.</span></span> <span data-ttu-id="9e536-104">Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="9e536-104">The provider class in this sample derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="9e536-105">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="9e536-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e536-106">Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="9e536-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="9e536-107">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="9e536-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="9e536-108">См. [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="9e536-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="9e536-109">Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="9e536-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="9e536-110">См. [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="9e536-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="9e536-111">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="9e536-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="9e536-112">См. [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="9e536-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="9e536-113">Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="9e536-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="9e536-114">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="9e536-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="9e536-115">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="9e536-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="9e536-116">Определение класса поставщика, который управляется от класса [System. Management. Automation. Provider. дривекмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="9e536-116">Defining a provider class that drives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span>

- <span data-ttu-id="9e536-117">Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) для поддержки создания новых дисков.</span><span class="sxs-lookup"><span data-stu-id="9e536-117">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to support creating new drives.</span></span> <span data-ttu-id="9e536-118">(В этом примере не показано, как добавить динамические параметры в `New-PSDrive` командлет.)</span><span class="sxs-lookup"><span data-stu-id="9e536-118">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>

- <span data-ttu-id="9e536-119">Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки удаления существующих дисков.</span><span class="sxs-lookup"><span data-stu-id="9e536-119">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>

## <a name="example"></a><span data-ttu-id="9e536-120">Пример</span><span class="sxs-lookup"><span data-stu-id="9e536-120">Example</span></span>

<span data-ttu-id="9e536-121">В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) и [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) .</span><span class="sxs-lookup"><span data-stu-id="9e536-121">This sample shows how to overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods.</span></span> <span data-ttu-id="9e536-122">Для этого примера поставщика при создании диска сведения о его соединении хранятся в `AccessDBPsDriveInfo` объекте.</span><span class="sxs-lookup"><span data-stu-id="9e536-122">For this sample provider, when a drive is created its connection information is stored in an `AccessDBPsDriveInfo` object.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a><span data-ttu-id="9e536-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9e536-123">See Also</span></span>

[<span data-ttu-id="9e536-124">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="9e536-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="9e536-125">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="9e536-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="9e536-126">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="9e536-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="9e536-127">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e536-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
