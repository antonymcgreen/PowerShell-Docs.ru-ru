---
title: Пример кода AccessDbProviderSample04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9374c4a-e499-4516-9eb6-107c59df98d9
caps.latest.revision: 7
ms.openlocfilehash: 43f01b9cd6af3ab6c26f88ee0c1e9269499b2bc3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853610"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="5fc95-102">Пример кода AccessDbProviderSample04</span><span class="sxs-lookup"><span data-stu-id="5fc95-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="5fc95-103">В следующем коде показано реализации поставщика Windows PowerShell, описанные в [Создание поставщика Windows PowerShell контейнера](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5fc95-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span> <span data-ttu-id="5fc95-104">Этот поставщик работает в хранилищах данных нескольких слоев.</span><span class="sxs-lookup"><span data-stu-id="5fc95-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="5fc95-105">Для этого типа хранилища данных верхнем уровне хранилища содержит корневых элементов, и каждый последующий уровень называется узлом дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="5fc95-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="5fc95-106">Позволяя пользователям работать на эти дочерние узлы, пользователь может иерархически взаимодействовать через хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="5fc95-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5fc95-107">Пример кода</span><span class="sxs-lookup"><span data-stu-id="5fc95-107">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="5fc95-108">См. также</span><span class="sxs-lookup"><span data-stu-id="5fc95-108">See Also</span></span>

[<span data-ttu-id="5fc95-109">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fc95-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)