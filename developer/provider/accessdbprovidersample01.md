---
title: AccessDBProviderSample01 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 853b7e5d-76c1-490e-8269-0ef31ba2ff13
caps.latest.revision: 10
ms.openlocfilehash: dc1ae92af8a57d6197b595db8e098256ac444b78
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081127"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="a32b3-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="a32b3-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="a32b3-103">В этом примере показано, как объявить класс поставщика, производный непосредственно от [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a32b3-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="a32b3-104">Он приводится здесь только для полноты картины.</span><span class="sxs-lookup"><span data-stu-id="a32b3-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a32b3-105">Демонстрирует</span><span class="sxs-lookup"><span data-stu-id="a32b3-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a32b3-106">Класс поставщика будет скорее являются производными от одного из следующих классов и возможно реализовать другие интерфейсы поставщика:</span><span class="sxs-lookup"><span data-stu-id="a32b3-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="a32b3-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a32b3-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="a32b3-108">См. в разделе [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="a32b3-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="a32b3-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a32b3-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="a32b3-110">См. в разделе [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="a32b3-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="a32b3-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a32b3-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="a32b3-112">См. в разделе [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="a32b3-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="a32b3-113">Дополнительные сведения о выборе какой класс поставщика, являются производными от поставщика функций, см. в разделе [проектирование ваш поставщик PowerShell Windows](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="a32b3-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="a32b3-114">Этот образец демонстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="a32b3-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="a32b3-115">Объявление `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="a32b3-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="a32b3-116">Определение класса поставщика, который является производным непосредственно от [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) класса.</span><span class="sxs-lookup"><span data-stu-id="a32b3-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="a32b3-117">Пример</span><span class="sxs-lookup"><span data-stu-id="a32b3-117">Example</span></span>

<span data-ttu-id="a32b3-118">В этом примере показано, как определить класс поставщика и как объявить `CmdletProvider` атрибута.</span><span class="sxs-lookup"><span data-stu-id="a32b3-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  /// <summary>
  /// This sample shows how to declare a provider class and how to
  /// declare the CmdletProvider attribute.
  /// </summary>
  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : CmdletProvider
  {
    // Add provider logic here.
  }
}
```

## <a name="see-also"></a><span data-ttu-id="a32b3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a32b3-119">See Also</span></span>

[<span data-ttu-id="a32b3-120">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="a32b3-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="a32b3-121">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="a32b3-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="a32b3-122">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="a32b3-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="a32b3-123">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a32b3-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)