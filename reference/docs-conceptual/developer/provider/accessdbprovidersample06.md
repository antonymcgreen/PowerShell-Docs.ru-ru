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
ms.openlocfilehash: 9c00ec6de987729fec42dc57245a949d11e31f4b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366333"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="ea164-102">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="ea164-102">AccessDBProviderSample06</span></span>

<span data-ttu-id="ea164-103">В этом примере показано, как перезаписывать методы содержимого для поддержки вызовов `Clear-Content`, `Get-Content`и командлетов `Set-Content`.</span><span class="sxs-lookup"><span data-stu-id="ea164-103">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="ea164-104">Эти методы должны быть реализованы, когда пользователю требуется управлять содержимым элементов в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="ea164-104">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="ea164-105">Класс поставщика в этом примере является производным от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и реализует интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="ea164-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ea164-106">Демонстрация</span><span class="sxs-lookup"><span data-stu-id="ea164-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea164-107">Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="ea164-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="ea164-108">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="ea164-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="ea164-109">См. [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="ea164-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="ea164-110">Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="ea164-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="ea164-111">См. [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="ea164-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="ea164-112">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="ea164-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="ea164-113">Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="ea164-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="ea164-114">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="ea164-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="ea164-115">Объявление атрибута `CmdletProvider`.</span><span class="sxs-lookup"><span data-stu-id="ea164-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="ea164-116">Определение класса поставщика, производного от класса [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) и объявляющего интерфейс [System. Management. Automation. Provider. иконтенткмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="ea164-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

- <span data-ttu-id="ea164-117">Перезапись метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. ClearContent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) для изменения поведения командлета `Clear-Content`, позволяя пользователю удалить содержимое из элемента.</span><span class="sxs-lookup"><span data-stu-id="ea164-117">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="ea164-118">(В этом примере не показано, как добавлять динамические параметры в командлет `Clear-Content`.)</span><span class="sxs-lookup"><span data-stu-id="ea164-118">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>

- <span data-ttu-id="ea164-119">Перезапись метода [System. Management. Automation. Provider. иконтенткмдлетпровидер. жетконтентреадер \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) для изменения поведения командлета `Get-Content`, позволяя пользователю извлекать содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="ea164-119">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="ea164-120">(В этом примере не показано, как добавлять динамические параметры в командлет `Get-Content`.).</span><span class="sxs-lookup"><span data-stu-id="ea164-120">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>

- <span data-ttu-id="ea164-121">Перезапись метода [Microsoft. PowerShell. Commands. филесистемпровидер. жетконтентвритер \*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) для изменения поведения командлета `Set-Content`, позволяя пользователю обновлять содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="ea164-121">Overwriting the [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="ea164-122">(В этом примере не показано, как добавлять динамические параметры в командлет `Set-Content`.)</span><span class="sxs-lookup"><span data-stu-id="ea164-122">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="ea164-123">Пример</span><span class="sxs-lookup"><span data-stu-id="ea164-123">Example</span></span>

<span data-ttu-id="ea164-124">В этом примере показано, как перезаписать методы, необходимые для очистки, получения и установки содержимого элементов в базе данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="ea164-124">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="ea164-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea164-125">See Also</span></span>

[<span data-ttu-id="ea164-126">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="ea164-126">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="ea164-127">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="ea164-127">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="ea164-128">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="ea164-128">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="ea164-129">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea164-129">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
