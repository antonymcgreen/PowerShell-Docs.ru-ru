---
title: Разработка поставщика Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a54ce657-e0e0-4b3e-b9dc-aed39876f933
caps.latest.revision: 11
ms.openlocfilehash: 58252956184703fdcdb3aa9b1db617c6e91294c1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860060"
---
# <a name="writing-a-windows-powershell-provider"></a><span data-ttu-id="88a29-102">Написание поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88a29-102">Writing a Windows PowerShell Provider</span></span>

<span data-ttu-id="88a29-103">«Разработка поставщика Windows PowerShell» — для руководителей программ, которые при разработке поставщиков Windows PowerShell и разработчиками, реализующими код поставщика.</span><span class="sxs-lookup"><span data-stu-id="88a29-103">"Writing a Windows PowerShell Provider" is for program managers who are designing Windows PowerShell providers and for developers who are implementing provider code.</span></span> <span data-ttu-id="88a29-104">Он поможет вам понять, как работают поставщики Windows PowerShell, а также пример кода, который можно использовать для запуска проектирование или написании собственных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="88a29-104">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="88a29-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="88a29-105">In This Section</span></span>

<span data-ttu-id="88a29-106">[Примеры поставщика Windows PowerShell](./windows-powershell-provider-quickstart.md) код примера и пошаговое руководство по очень простой поставщик.</span><span class="sxs-lookup"><span data-stu-id="88a29-106">[Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md) Example code and walkthrough of a very basic provider.</span></span>

<span data-ttu-id="88a29-107">[Общие сведения о поставщике Windows PowerShell](./windows-powershell-provider-overview.md) этот раздел содержит разделы, описывающие поставщиков Windows PowerShell, и как они работают.</span><span class="sxs-lookup"><span data-stu-id="88a29-107">[Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md) This section contains topics that describe what Windows PowerShell providers are and how they work.</span></span>

<span data-ttu-id="88a29-108">[Создание поставщика элемента](./writing-an-item-provider.md) код примера и пошаговое руководство по методам, которые поддерживают получение и задание элементов.</span><span class="sxs-lookup"><span data-stu-id="88a29-108">[Writing an item provider](./writing-an-item-provider.md) Example code and walkthrough of methods that support getting and setting items.</span></span>

<span data-ttu-id="88a29-109">[Разработка поставщика контейнера](./writing-a-container-provider.md) код примера и пошаговое руководство по методам, которые поддерживают контейнеры (элементы, содержащие другие элементы, как дочерние элементы).</span><span class="sxs-lookup"><span data-stu-id="88a29-109">[Writing a container provider](./writing-a-container-provider.md) Example code and walkthrough of methods that support containers (items that have other items as children).</span></span>

<span data-ttu-id="88a29-110">[Разработка поставщика навигации](./writing-a-navigation-provider.md) код примера и пошаговое руководство по методам, которые поддерживают вложенные контейнеры, относительные пути и перемещение элементов из одного пути на другой.</span><span class="sxs-lookup"><span data-stu-id="88a29-110">[Writing a navigation provider](./writing-a-navigation-provider.md) Example code and walkthrough of methods that support nested containers, relative paths, and moving items from one path to another.</span></span>

<span data-ttu-id="88a29-111">[Примеры поставщиков](./provider-samples.md) этот раздел содержит примеры поставщиков.</span><span class="sxs-lookup"><span data-stu-id="88a29-111">[Provider Samples](./provider-samples.md) This section provides samples of providers.</span></span>

## <a name="see-also"></a><span data-ttu-id="88a29-112">См. также</span><span class="sxs-lookup"><span data-stu-id="88a29-112">See Also</span></span>

[<span data-ttu-id="88a29-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88a29-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)