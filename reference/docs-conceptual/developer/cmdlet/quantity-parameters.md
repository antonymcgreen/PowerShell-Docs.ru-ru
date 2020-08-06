---
title: Параметры количества | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7ff6562380bb6336b08879b31d8d9fed47bfb6a7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781823"
---
# <a name="quantity-parameters"></a><span data-ttu-id="c6359-102">Параметры количества</span><span class="sxs-lookup"><span data-stu-id="c6359-102">Quantity Parameters</span></span>

<span data-ttu-id="c6359-103">В следующей таблице перечислены рекомендуемые имена и функциональные возможности для количественных параметров.</span><span class="sxs-lookup"><span data-stu-id="c6359-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="c6359-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="c6359-104">Parameter</span></span>|<span data-ttu-id="c6359-105">функциональное назначение;</span><span class="sxs-lookup"><span data-stu-id="c6359-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="c6359-106">**все**</span><span class="sxs-lookup"><span data-stu-id="c6359-106">**All**</span></span><br><span data-ttu-id="c6359-107">Тип данных: логический</span><span class="sxs-lookup"><span data-stu-id="c6359-107">Data type: Boolean</span></span>|<span data-ttu-id="c6359-108">Реализуйте этот параметр, чтобы он `true` обозначает, что вместо подмножества ресурсов по умолчанию должны выполняться действия для всех ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c6359-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="c6359-109">Реализуйте этот параметр, чтобы `false` обозначать подмножество ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c6359-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="c6359-110">**Allocation**</span><span class="sxs-lookup"><span data-stu-id="c6359-110">**Allocation**</span></span><br><span data-ttu-id="c6359-111">Тип данных: Int32</span><span class="sxs-lookup"><span data-stu-id="c6359-111">Data type: Int32</span></span>|<span data-ttu-id="c6359-112">Реализуйте этот параметр, чтобы пользователь мог указать число выделяемых элементов.</span><span class="sxs-lookup"><span data-stu-id="c6359-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="c6359-113">**блокккаунт**</span><span class="sxs-lookup"><span data-stu-id="c6359-113">**BlockCount**</span></span><br><span data-ttu-id="c6359-114">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="c6359-114">Data type: Int64</span></span>|<span data-ttu-id="c6359-115">Реализуйте этот параметр, чтобы пользователь мог указать число блоков.</span><span class="sxs-lookup"><span data-stu-id="c6359-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="c6359-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="c6359-116">**Count**</span></span><br><span data-ttu-id="c6359-117">Тип данных: Int64</span><span class="sxs-lookup"><span data-stu-id="c6359-117">Data type: Int64</span></span>|<span data-ttu-id="c6359-118">Реализуйте этот параметр, чтобы пользователь мог указать число.</span><span class="sxs-lookup"><span data-stu-id="c6359-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="c6359-119">**Область**</span><span class="sxs-lookup"><span data-stu-id="c6359-119">**Scope**</span></span><br><span data-ttu-id="c6359-120">Тип данных: ключевое слово</span><span class="sxs-lookup"><span data-stu-id="c6359-120">Data type: Keyword</span></span>|<span data-ttu-id="c6359-121">Реализуйте этот параметр, чтобы пользователь мог указать область действия.</span><span class="sxs-lookup"><span data-stu-id="c6359-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c6359-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c6359-122">See Also</span></span>

[<span data-ttu-id="c6359-123">Параметры командлета</span><span class="sxs-lookup"><span data-stu-id="c6359-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="c6359-124">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6359-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="c6359-125">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6359-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
