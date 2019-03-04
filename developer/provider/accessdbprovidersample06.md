---
title: AccessDBProviderSample06 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46dc0657-110f-4367-8bb6-a95dca2c5016
caps.latest.revision: 8
ms.openlocfilehash: 59832ed8a4fad3b07a171946bff28fb3e1dbe442
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854660"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="aaf7a-102">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="aaf7a-102">AccessDBProviderSample06</span></span>

<span data-ttu-id="aaf7a-103">В этом примере показано, как перезаписать методы содержимого для поддержки вызовов в `Clear-Content`, `Get-Content`, и `Set-Content` командлетов.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-103">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="aaf7a-104">Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-104">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="aaf7a-105">Класс поставщика в этом примере является производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класс, который реализует [ System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="aaf7a-106">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="aaf7a-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aaf7a-107">Класс поставщика будет скорее являются производными от одного из следующих классов и возможно реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="aaf7a-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="aaf7a-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="aaf7a-109">См. в разделе [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="aaf7a-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="aaf7a-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="aaf7a-111">См. в разделе [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="aaf7a-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="aaf7a-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="aaf7a-113">Дополнительные сведения о выборе какой класс поставщика, являются производными от поставщика функций, см. в разделе [проектирование ваш поставщик PowerShell Windows](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="aaf7a-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="aaf7a-114">Этот образец демонстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="aaf7a-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="aaf7a-115">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="aaf7a-116">Определение класса поставщика, который является производным от [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса и объявляет [ System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

- <span data-ttu-id="aaf7a-117">Перезапись [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) метод, чтобы изменить поведение `Clear-Content` командлета, позволяя пользователю удалить содержимое из элемента.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-117">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="aaf7a-118">(В этом примере показано, как добавлять динамические параметры для `Clear-Content` командлет.)</span><span class="sxs-lookup"><span data-stu-id="aaf7a-118">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>

- <span data-ttu-id="aaf7a-119">Перезапись [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) метод, чтобы изменить поведение `Get-Content` командлета, позволяя пользователю извлекать содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-119">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="aaf7a-120">(В этом примере показано, как добавлять динамические параметры для `Get-Content` командлет.).</span><span class="sxs-lookup"><span data-stu-id="aaf7a-120">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>

- <span data-ttu-id="aaf7a-121">Перезапись [Microsoft.Powershell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) метод, чтобы изменить поведение `Set-Content` командлет, что позволяет пользователю изменить содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-121">Overwriting the [Microsoft.Powershell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="aaf7a-122">(В этом примере показано, как добавлять динамические параметры для `Set-Content` командлет.)</span><span class="sxs-lookup"><span data-stu-id="aaf7a-122">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="aaf7a-123">Пример</span><span class="sxs-lookup"><span data-stu-id="aaf7a-123">Example</span></span>

<span data-ttu-id="aaf7a-124">В этом примере показано, как перезаписать методы, необходимые для очистки, получение и установка базового содержимого для элементов в данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="aaf7a-124">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="aaf7a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="aaf7a-125">See Also</span></span>

[<span data-ttu-id="aaf7a-126">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="aaf7a-126">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="aaf7a-127">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="aaf7a-127">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="aaf7a-128">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="aaf7a-128">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="aaf7a-129">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaf7a-129">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)