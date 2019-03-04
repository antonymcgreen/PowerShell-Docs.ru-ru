---
title: Количество параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c0bd8a9-1749-4885-ab24-38c0a4d9f2cb
caps.latest.revision: 6
ms.openlocfilehash: 7a3efc60fcc8729d833f6de070016cfd08cc9b88
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251376"
---
# <a name="quantity-parameters"></a><span data-ttu-id="14f2a-102">Параметры количества</span><span class="sxs-lookup"><span data-stu-id="14f2a-102">Quantity Parameters</span></span>

<span data-ttu-id="14f2a-103">Ниже перечислены рекомендуемые имена и функции для количество параметров.</span><span class="sxs-lookup"><span data-stu-id="14f2a-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="14f2a-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="14f2a-104">Parameter</span></span>|<span data-ttu-id="14f2a-105">Функции</span><span class="sxs-lookup"><span data-stu-id="14f2a-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="14f2a-106">**Все**</span><span class="sxs-lookup"><span data-stu-id="14f2a-106">**All**</span></span><br><span data-ttu-id="14f2a-107">Тип данных: Логический</span><span class="sxs-lookup"><span data-stu-id="14f2a-107">Data type: Boolean</span></span>|<span data-ttu-id="14f2a-108">Реализуйте этот параметр, чтобы `true` указывает, что все ресурсы должны обрабатываться, а не подмножество ресурсов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14f2a-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="14f2a-109">Реализуйте этот параметр, чтобы `false` указывает подмножество ресурсов.</span><span class="sxs-lookup"><span data-stu-id="14f2a-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="14f2a-110">**Выделение**</span><span class="sxs-lookup"><span data-stu-id="14f2a-110">**Allocation**</span></span><br><span data-ttu-id="14f2a-111">Тип данных: Int32</span><span class="sxs-lookup"><span data-stu-id="14f2a-111">Data type: Int32</span></span>|<span data-ttu-id="14f2a-112">Реализуйте этот параметр, чтобы пользователь может указать число элементов для выделения.</span><span class="sxs-lookup"><span data-stu-id="14f2a-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="14f2a-113">**BlockCount**</span><span class="sxs-lookup"><span data-stu-id="14f2a-113">**BlockCount**</span></span><br><span data-ttu-id="14f2a-114">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="14f2a-114">Data type: Int64</span></span>|<span data-ttu-id="14f2a-115">Реализуйте этот параметр, благодаря которому пользователь может указать число блоков.</span><span class="sxs-lookup"><span data-stu-id="14f2a-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="14f2a-116">**число**</span><span class="sxs-lookup"><span data-stu-id="14f2a-116">**Count**</span></span><br><span data-ttu-id="14f2a-117">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="14f2a-117">Data type: Int64</span></span>|<span data-ttu-id="14f2a-118">Реализуйте этот параметр, чтобы пользователь может указать число.</span><span class="sxs-lookup"><span data-stu-id="14f2a-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="14f2a-119">**Область**</span><span class="sxs-lookup"><span data-stu-id="14f2a-119">**Scope**</span></span><br><span data-ttu-id="14f2a-120">Тип данных: Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="14f2a-120">Data type: Keyword</span></span>|<span data-ttu-id="14f2a-121">Реализуйте этот параметр, таким образом, пользователь может указать область для работы.</span><span class="sxs-lookup"><span data-stu-id="14f2a-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="14f2a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="14f2a-122">See Also</span></span>

[<span data-ttu-id="14f2a-123">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="14f2a-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="14f2a-124">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14f2a-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="14f2a-125">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14f2a-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
