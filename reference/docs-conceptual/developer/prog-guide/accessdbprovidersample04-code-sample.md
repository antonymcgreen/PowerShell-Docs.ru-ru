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
ms.openlocfilehash: 60f0ed4e3d39ee93ab63023161d09a6c7b914798
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978582"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="57a98-102">Пример кода AccessDbProviderSample04</span><span class="sxs-lookup"><span data-stu-id="57a98-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="57a98-103">В следующем коде показана реализация поставщика Windows PowerShell, описанного в статье [Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="57a98-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="57a98-104">Этот поставщик работает с хранилищами данных с несколькими уровнями.</span><span class="sxs-lookup"><span data-stu-id="57a98-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="57a98-105">Для этого типа хранилища данных верхний уровень хранилища содержит корневые элементы, а каждый последующий уровень называется узлом дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="57a98-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="57a98-106">Разрешая пользователю работать с этими дочерними узлами, пользователь может выполнять иерархическую работу через хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="57a98-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="57a98-107">Образец кода</span><span class="sxs-lookup"><span data-stu-id="57a98-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="57a98-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="57a98-108">See Also</span></span>

[<span data-ttu-id="57a98-109">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57a98-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
