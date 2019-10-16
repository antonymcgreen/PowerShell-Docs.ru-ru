---
title: Создание поставщика Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a54ce657-e0e0-4b3e-b9dc-aed39876f933
caps.latest.revision: 11
ms.openlocfilehash: 58252956184703fdcdb3aa9b1db617c6e91294c1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366193"
---
# <a name="writing-a-windows-powershell-provider"></a><span data-ttu-id="e50e6-102">Написание поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e50e6-102">Writing a Windows PowerShell Provider</span></span>

<span data-ttu-id="e50e6-103">«Написание поставщика Windows PowerShell» предназначено для руководителей программ, создающих поставщиков Windows PowerShell, и для разработчиков, которые реализуют код поставщика.</span><span class="sxs-lookup"><span data-stu-id="e50e6-103">"Writing a Windows PowerShell Provider" is for program managers who are designing Windows PowerShell providers and for developers who are implementing provider code.</span></span> <span data-ttu-id="e50e6-104">Он поможет понять, как работают поставщики Windows PowerShell, и предоставляет пример кода, который можно использовать для начала разработки или написания собственных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="e50e6-104">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e50e6-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="e50e6-105">In This Section</span></span>

<span data-ttu-id="e50e6-106">[Краткое руководство по поставщику Windows PowerShell](./windows-powershell-provider-quickstart.md) Пример кода и пошаговое руководство для очень базового поставщика.</span><span class="sxs-lookup"><span data-stu-id="e50e6-106">[Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md) Example code and walkthrough of a very basic provider.</span></span>

<span data-ttu-id="e50e6-107">[Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md) В этом разделе содержатся разделы, в которых описывается, что представляют собой поставщики Windows PowerShell и как они работают.</span><span class="sxs-lookup"><span data-stu-id="e50e6-107">[Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md) This section contains topics that describe what Windows PowerShell providers are and how they work.</span></span>

<span data-ttu-id="e50e6-108">[Написание поставщика элементов](./writing-an-item-provider.md) Пример кода и пошаговое руководство по методам, которые поддерживают получение и установку элементов.</span><span class="sxs-lookup"><span data-stu-id="e50e6-108">[Writing an item provider](./writing-an-item-provider.md) Example code and walkthrough of methods that support getting and setting items.</span></span>

<span data-ttu-id="e50e6-109">[Создание поставщика контейнера](./writing-a-container-provider.md) Пример кода и пошаговое руководство по методам, поддерживающим контейнеры (элементы, имеющие другие элементы в качестве дочерних элементов).</span><span class="sxs-lookup"><span data-stu-id="e50e6-109">[Writing a container provider](./writing-a-container-provider.md) Example code and walkthrough of methods that support containers (items that have other items as children).</span></span>

<span data-ttu-id="e50e6-110">[Создание поставщика навигации](./writing-a-navigation-provider.md) Пример кода и пошаговое руководство по методам, поддерживающим вложенные контейнеры, относительные пути и перемещение элементов из одного пути в другой.</span><span class="sxs-lookup"><span data-stu-id="e50e6-110">[Writing a navigation provider](./writing-a-navigation-provider.md) Example code and walkthrough of methods that support nested containers, relative paths, and moving items from one path to another.</span></span>

<span data-ttu-id="e50e6-111">[Примеры поставщиков](./provider-samples.md) В этом разделе приводятся примеры поставщиков.</span><span class="sxs-lookup"><span data-stu-id="e50e6-111">[Provider Samples](./provider-samples.md) This section provides samples of providers.</span></span>

## <a name="see-also"></a><span data-ttu-id="e50e6-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="e50e6-112">See Also</span></span>

[<span data-ttu-id="e50e6-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e50e6-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)