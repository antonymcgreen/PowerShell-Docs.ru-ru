---
title: Пример кода AccessDbProviderSample04 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 05509c5b36475bcd3f91c9ab7413974994d668d6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787280"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="b1265-102">Пример кода AccessDbProviderSample04</span><span class="sxs-lookup"><span data-stu-id="b1265-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="b1265-103">В следующем коде показана реализация поставщика Windows PowerShell, описанного в статье [Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="b1265-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="b1265-104">Этот поставщик работает с хранилищами данных с несколькими уровнями.</span><span class="sxs-lookup"><span data-stu-id="b1265-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="b1265-105">Для этого типа хранилища данных верхний уровень хранилища содержит корневые элементы, а каждый последующий уровень называется узлом дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="b1265-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="b1265-106">Разрешая пользователю работать с этими дочерними узлами, пользователь может выполнять иерархическую работу через хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="b1265-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b1265-107">Образец кода</span><span class="sxs-lookup"><span data-stu-id="b1265-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="b1265-108">См. также</span><span class="sxs-lookup"><span data-stu-id="b1265-108">See Also</span></span>

[<span data-ttu-id="b1265-109">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1265-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
