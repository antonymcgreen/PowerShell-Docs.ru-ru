---
title: AccessDBProviderSample01 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 50ec218e8d0fe6b2be5c8ac00956f72c6723f84a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786923"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="dd731-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="dd731-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="dd731-103">В этом примере показано, как объявить класс поставщика, производный непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="dd731-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="dd731-104">Он приводится здесь только для полноты картины.</span><span class="sxs-lookup"><span data-stu-id="dd731-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="dd731-105">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="dd731-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd731-106">Скорее всего, класс поставщика будет производным от одного из следующих классов и, возможно, реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="dd731-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="dd731-107">Класс [System. Management. Automation. Provider. итемкмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="dd731-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="dd731-108">См. [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="dd731-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="dd731-109">Класс [System. Management. Automation. Provider. контаинеркмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="dd731-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="dd731-110">См. [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="dd731-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="dd731-111">Класс [System. Management. Automation. Provider. Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="dd731-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="dd731-112">См. [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="dd731-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="dd731-113">Дополнительные сведения о выборе класса поставщика, производного от, на основе функций поставщика см. в разделе [Разработка поставщика Windows PowerShell](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="dd731-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="dd731-114">В этом образце демонстрируется следующее:</span><span class="sxs-lookup"><span data-stu-id="dd731-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="dd731-115">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="dd731-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="dd731-116">Определение класса поставщика, производного непосредственно от класса [System. Management. Automation. Provider. кмдлетпровидер](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) .</span><span class="sxs-lookup"><span data-stu-id="dd731-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="dd731-117">Пример</span><span class="sxs-lookup"><span data-stu-id="dd731-117">Example</span></span>

<span data-ttu-id="dd731-118">В этом примере показано, как определить класс поставщика и как объявить `CmdletProvider` атрибут.</span><span class="sxs-lookup"><span data-stu-id="dd731-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="dd731-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dd731-119">See Also</span></span>

[<span data-ttu-id="dd731-120">System. Management. Automation. Provider. Итемкмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="dd731-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="dd731-121">System. Management. Automation. Provider. Контаинеркмдлетпровидер</span><span class="sxs-lookup"><span data-stu-id="dd731-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="dd731-122">System. Management. Automation. Provider. Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="dd731-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="dd731-123">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd731-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
