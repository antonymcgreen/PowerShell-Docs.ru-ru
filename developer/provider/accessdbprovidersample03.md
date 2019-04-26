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
ms.openlocfilehash: 57b6cfaa5f29300c60a5a745797111b6beba3133
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081076"
---
# <a name="accessdbprovidersample03"></a><span data-ttu-id="0d0c7-102">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="0d0c7-102">AccessDBProviderSample03</span></span>

<span data-ttu-id="0d0c7-103">В этом примере показано, как перезаписать [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) и [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) методы для поддержки вызовов в `Get-Item` и `Set-Item` командлетов.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-103">This sample shows how to overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span> <span data-ttu-id="0d0c7-104">Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-104">The provider class in this sample derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="0d0c7-105">Демонстрирует</span><span class="sxs-lookup"><span data-stu-id="0d0c7-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d0c7-106">Класс поставщика будет скорее являются производными от одного из следующих классов и возможно реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="0d0c7-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="0d0c7-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
> -   <span data-ttu-id="0d0c7-108">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-108">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="0d0c7-109">См. в разделе [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="0d0c7-109">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="0d0c7-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-110">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="0d0c7-111">См. в разделе [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="0d0c7-111">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="0d0c7-112">Дополнительные сведения о выборе какой класс поставщика, являются производными от поставщика функций, см. в разделе [проектирование ваш поставщик PowerShell Windows](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="0d0c7-112">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="0d0c7-113">Этот образец демонстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="0d0c7-113">This sample demonstrates the following:</span></span>

- <span data-ttu-id="0d0c7-114">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-114">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="0d0c7-115">Определение класса поставщика, который является производным от [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-115">Defining a provider class that derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

- <span data-ttu-id="0d0c7-116">Перезапись [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) метод, чтобы изменить поведение `New-PSDrive` командлет, что позволяет пользователю создавать новые диски.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-116">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to change the behavior of the `New-PSDrive` cmdlet, allowing the user to create new drives.</span></span> <span data-ttu-id="0d0c7-117">(В этом примере показано, как добавлять динамические параметры для `New-PSDrive` командлет.)</span><span class="sxs-lookup"><span data-stu-id="0d0c7-117">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>

- <span data-ttu-id="0d0c7-118">Перезапись [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) метод для поддержки удаления существующих дисков.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-118">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>

- <span data-ttu-id="0d0c7-119">Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) метод, чтобы изменить поведение `Get-Item` командлета, позволяя пользователю извлекать элементы из хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-119">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method to change the behavior of the `Get-Item` cmdlet, allowing the user to retrieve items from the data store.</span></span> <span data-ttu-id="0d0c7-120">(В этом примере показано, как добавлять динамические параметры для `Get-Item` командлет.)</span><span class="sxs-lookup"><span data-stu-id="0d0c7-120">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="0d0c7-121">Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) метод, чтобы изменить поведение `Set-Item` командлета, позволяя пользователю обновлять элементы в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-121">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method to change the behavior of the `Set-Item` cmdlet, allowing the user to update the items in the data store.</span></span> <span data-ttu-id="0d0c7-122">(В этом примере показано, как добавлять динамические параметры для `Get-Item` командлет.)</span><span class="sxs-lookup"><span data-stu-id="0d0c7-122">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>

- <span data-ttu-id="0d0c7-123">Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) метод, чтобы изменить поведение `Test-Path` командлета.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-123">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method to change the behavior of the `Test-Path` cmdlet.</span></span> <span data-ttu-id="0d0c7-124">(В этом примере показано, как добавлять динамические параметры для `Test-Path` командлет.)</span><span class="sxs-lookup"><span data-stu-id="0d0c7-124">(This sample does not show how to add dynamic parameters to the `Test-Path` cmdlet.)</span></span>

- <span data-ttu-id="0d0c7-125">Перезапись [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) метод, чтобы определить, если указанный путь является допустимым.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-125">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method to determine if the provided path is valid.</span></span>

## <a name="example"></a><span data-ttu-id="0d0c7-126">Пример</span><span class="sxs-lookup"><span data-stu-id="0d0c7-126">Example</span></span>

<span data-ttu-id="0d0c7-127">В этом примере показано, как перезаписать методы, необходимые для получения и задания базовых элементов данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="0d0c7-127">This sample shows how to overwrite the methods needed to get and set items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="0d0c7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0d0c7-128">See Also</span></span>

[<span data-ttu-id="0d0c7-129">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="0d0c7-129">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="0d0c7-130">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="0d0c7-130">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="0d0c7-131">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="0d0c7-131">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="0d0c7-132">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d0c7-132">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)