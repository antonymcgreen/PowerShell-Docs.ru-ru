---
title: AccessDBProviderSample03 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e576199-49c7-4355-9686-f9ed40c64a5f
caps.latest.revision: 10
ms.openlocfilehash: aa67bb605f90c1ea40323b4583766069ff1226fb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359993"
---
# <a name="accessdbprovidersample03"></a><span data-ttu-id="36676-102">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="36676-102">AccessDBProviderSample03</span></span>

<span data-ttu-id="36676-103">В этом примере показано, как перезаписать методы [System. Management. Automation. Provider. итемкмдлетпровидер. DataItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для поддержки вызовов `Get-Item` и @no__ Командлеты t-3.</span><span class="sxs-lookup"><span data-stu-id="36676-103">This sample shows how to overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span> <span data-ttu-id="36676-104">Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="36676-104">The provider class in this sample derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="36676-105">Демонстрирующее</span><span class="sxs-lookup"><span data-stu-id="36676-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36676-106">Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="36676-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="36676-107">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="36676-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
> -   <span data-ttu-id="36676-108">Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="36676-108">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="36676-109">См. [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="36676-109">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="36676-110">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="36676-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="36676-111">См. [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="36676-111">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="36676-112">Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="36676-112">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="36676-113">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="36676-113">This sample demonstrates the following:</span></span>

- <span data-ttu-id="36676-114">Объявление атрибута `CmdletProvider`.</span><span class="sxs-lookup"><span data-stu-id="36676-114">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="36676-115">Определение класса поставщика, производного от класса [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="36676-115">Defining a provider class that derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

- <span data-ttu-id="36676-116">Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. невдриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) для изменения поведения командлета `New-PSDrive`, позволяя пользователю создавать новые диски.</span><span class="sxs-lookup"><span data-stu-id="36676-116">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to change the behavior of the `New-PSDrive` cmdlet, allowing the user to create new drives.</span></span> <span data-ttu-id="36676-117">(В этом примере не показано, как добавлять динамические параметры в командлет `New-PSDrive`).</span><span class="sxs-lookup"><span data-stu-id="36676-117">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>

- <span data-ttu-id="36676-118">Перезапись метода [System. Management. Automation. Provider. дривекмдлетпровидер. ремоведриве \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) для поддержки удаления существующих дисков.</span><span class="sxs-lookup"><span data-stu-id="36676-118">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>

- <span data-ttu-id="36676-119">Перезапись метода [System. Management. автоматизации. Provider. итемкмдлетпровидер. DataItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) для изменения поведения командлета `Get-Item`, позволяя пользователю получать элементы из хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="36676-119">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method to change the behavior of the `Get-Item` cmdlet, allowing the user to retrieve items from the data store.</span></span> <span data-ttu-id="36676-120">(В этом примере не показано, как добавлять динамические параметры в командлет `Get-Item`).</span><span class="sxs-lookup"><span data-stu-id="36676-120">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="36676-121">Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. сетитем \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) для изменения поведения командлета `Set-Item`, позволяя пользователю обновлять элементы в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="36676-121">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method to change the behavior of the `Set-Item` cmdlet, allowing the user to update the items in the data store.</span></span> <span data-ttu-id="36676-122">(В этом примере не показано, как добавлять динамические параметры в командлет `Get-Item`).</span><span class="sxs-lookup"><span data-stu-id="36676-122">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="36676-123">Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. итемексистс \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) для изменения поведения командлета `Test-Path`.</span><span class="sxs-lookup"><span data-stu-id="36676-123">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method to change the behavior of the `Test-Path` cmdlet.</span></span> <span data-ttu-id="36676-124">(В этом примере не показано, как добавлять динамические параметры в командлет `Test-Path`).</span><span class="sxs-lookup"><span data-stu-id="36676-124">(This sample does not show how to add dynamic parameters to the `Test-Path` cmdlet.)</span></span>

- <span data-ttu-id="36676-125">Перезапись метода [System. Management. Automation. Provider. итемкмдлетпровидер. исвалидпас \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) , чтобы определить, является ли указанный путь допустимым.</span><span class="sxs-lookup"><span data-stu-id="36676-125">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method to determine if the provided path is valid.</span></span>

## <a name="example"></a><span data-ttu-id="36676-126">Пример</span><span class="sxs-lookup"><span data-stu-id="36676-126">Example</span></span>

<span data-ttu-id="36676-127">В этом примере показано, как перезаписать методы, необходимые для получения и задания элементов в базе данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="36676-127">This sample shows how to overwrite the methods needed to get and set items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="36676-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="36676-128">See Also</span></span>

[<span data-ttu-id="36676-129">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="36676-129">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="36676-130">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="36676-130">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="36676-131">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="36676-131">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="36676-132">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36676-132">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
