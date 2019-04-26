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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067541"
---
# <a name="quantity-parameters"></a><span data-ttu-id="a0bea-102">Параметры количества</span><span class="sxs-lookup"><span data-stu-id="a0bea-102">Quantity Parameters</span></span>

<span data-ttu-id="a0bea-103">Ниже перечислены рекомендуемые имена и функции для количество параметров.</span><span class="sxs-lookup"><span data-stu-id="a0bea-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="a0bea-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="a0bea-104">Parameter</span></span>|<span data-ttu-id="a0bea-105">Функции</span><span class="sxs-lookup"><span data-stu-id="a0bea-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="a0bea-106">**Все**</span><span class="sxs-lookup"><span data-stu-id="a0bea-106">**All**</span></span><br><span data-ttu-id="a0bea-107">Тип данных: Логический</span><span class="sxs-lookup"><span data-stu-id="a0bea-107">Data type: Boolean</span></span>|<span data-ttu-id="a0bea-108">Реализуйте этот параметр, чтобы `true` указывает, что все ресурсы должны обрабатываться, а не подмножество ресурсов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a0bea-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="a0bea-109">Реализуйте этот параметр, чтобы `false` указывает подмножество ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a0bea-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="a0bea-110">**Выделение**</span><span class="sxs-lookup"><span data-stu-id="a0bea-110">**Allocation**</span></span><br><span data-ttu-id="a0bea-111">Тип данных: Int32</span><span class="sxs-lookup"><span data-stu-id="a0bea-111">Data type: Int32</span></span>|<span data-ttu-id="a0bea-112">Реализуйте этот параметр, чтобы пользователь может указать число элементов для выделения.</span><span class="sxs-lookup"><span data-stu-id="a0bea-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="a0bea-113">**BlockCount**</span><span class="sxs-lookup"><span data-stu-id="a0bea-113">**BlockCount**</span></span><br><span data-ttu-id="a0bea-114">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="a0bea-114">Data type: Int64</span></span>|<span data-ttu-id="a0bea-115">Реализуйте этот параметр, благодаря которому пользователь может указать число блоков.</span><span class="sxs-lookup"><span data-stu-id="a0bea-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="a0bea-116">**число**</span><span class="sxs-lookup"><span data-stu-id="a0bea-116">**Count**</span></span><br><span data-ttu-id="a0bea-117">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="a0bea-117">Data type: Int64</span></span>|<span data-ttu-id="a0bea-118">Реализуйте этот параметр, чтобы пользователь может указать число.</span><span class="sxs-lookup"><span data-stu-id="a0bea-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="a0bea-119">**Область**</span><span class="sxs-lookup"><span data-stu-id="a0bea-119">**Scope**</span></span><br><span data-ttu-id="a0bea-120">Тип данных: Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="a0bea-120">Data type: Keyword</span></span>|<span data-ttu-id="a0bea-121">Реализуйте этот параметр, таким образом, пользователь может указать область для работы.</span><span class="sxs-lookup"><span data-stu-id="a0bea-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a0bea-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a0bea-122">See Also</span></span>

[<span data-ttu-id="a0bea-123">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="a0bea-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="a0bea-124">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0bea-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="a0bea-125">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0bea-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
