---
title: Параметры количества | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c0bd8a9-1749-4885-ab24-38c0a4d9f2cb
caps.latest.revision: 6
ms.openlocfilehash: 7a3efc60fcc8729d833f6de070016cfd08cc9b88
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369563"
---
# <a name="quantity-parameters"></a><span data-ttu-id="ed311-102">Параметры количества</span><span class="sxs-lookup"><span data-stu-id="ed311-102">Quantity Parameters</span></span>

<span data-ttu-id="ed311-103">В следующей таблице перечислены рекомендуемые имена и функциональные возможности для количественных параметров.</span><span class="sxs-lookup"><span data-stu-id="ed311-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="ed311-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="ed311-104">Parameter</span></span>|<span data-ttu-id="ed311-105">Функция</span><span class="sxs-lookup"><span data-stu-id="ed311-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="ed311-106">**Каждого**</span><span class="sxs-lookup"><span data-stu-id="ed311-106">**All**</span></span><br><span data-ttu-id="ed311-107">Тип данных: логический</span><span class="sxs-lookup"><span data-stu-id="ed311-107">Data type: Boolean</span></span>|<span data-ttu-id="ed311-108">Реализуйте этот параметр, чтобы `true` обозначает, что вместо подмножества ресурсов по умолчанию должны выполняться действия для всех ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ed311-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="ed311-109">Реализуйте этот параметр, чтобы `false` обозначает подмножество ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ed311-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="ed311-110">**Заблокирован**</span><span class="sxs-lookup"><span data-stu-id="ed311-110">**Allocation**</span></span><br><span data-ttu-id="ed311-111">Тип данных: Int32</span><span class="sxs-lookup"><span data-stu-id="ed311-111">Data type: Int32</span></span>|<span data-ttu-id="ed311-112">Реализуйте этот параметр, чтобы пользователь мог указать число выделяемых элементов.</span><span class="sxs-lookup"><span data-stu-id="ed311-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="ed311-113">**блокккаунт**</span><span class="sxs-lookup"><span data-stu-id="ed311-113">**BlockCount**</span></span><br><span data-ttu-id="ed311-114">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="ed311-114">Data type: Int64</span></span>|<span data-ttu-id="ed311-115">Реализуйте этот параметр, чтобы пользователь мог указать число блоков.</span><span class="sxs-lookup"><span data-stu-id="ed311-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="ed311-116">**Расчета**</span><span class="sxs-lookup"><span data-stu-id="ed311-116">**Count**</span></span><br><span data-ttu-id="ed311-117">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="ed311-117">Data type: Int64</span></span>|<span data-ttu-id="ed311-118">Реализуйте этот параметр, чтобы пользователь мог указать число.</span><span class="sxs-lookup"><span data-stu-id="ed311-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="ed311-119">**Которых**</span><span class="sxs-lookup"><span data-stu-id="ed311-119">**Scope**</span></span><br><span data-ttu-id="ed311-120">Тип данных: ключевое слово</span><span class="sxs-lookup"><span data-stu-id="ed311-120">Data type: Keyword</span></span>|<span data-ttu-id="ed311-121">Реализуйте этот параметр, чтобы пользователь мог указать область действия.</span><span class="sxs-lookup"><span data-stu-id="ed311-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ed311-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed311-122">See Also</span></span>

[<span data-ttu-id="ed311-123">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="ed311-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="ed311-124">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed311-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="ed311-125">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed311-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
