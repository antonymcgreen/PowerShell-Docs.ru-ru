---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода AccessDbProviderSample04
description: Пример кода AccessDbProviderSample04
ms.openlocfilehash: bb70ce9f1b1c94349c354a8771fedf7fcb1bb320
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647568"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="0a8ce-103">Пример кода AccessDbProviderSample04</span><span class="sxs-lookup"><span data-stu-id="0a8ce-103">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="0a8ce-104">В следующем коде показана реализация поставщика Windows PowerShell, описанного в статье [Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0a8ce-104">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="0a8ce-105">Этот поставщик работает с хранилищами данных с несколькими уровнями.</span><span class="sxs-lookup"><span data-stu-id="0a8ce-105">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="0a8ce-106">Для этого типа хранилища данных верхний уровень хранилища содержит корневые элементы, а каждый последующий уровень называется узлом дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="0a8ce-106">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="0a8ce-107">Разрешая пользователю работать с этими дочерними узлами, пользователь может выполнять иерархическую работу через хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="0a8ce-107">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="0a8ce-108">Образец кода</span><span class="sxs-lookup"><span data-stu-id="0a8ce-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="0a8ce-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a8ce-109">See Also</span></span>

[<span data-ttu-id="0a8ce-110">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a8ce-110">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
