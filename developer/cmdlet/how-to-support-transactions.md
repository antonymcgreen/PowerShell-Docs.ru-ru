---
title: Поддержке транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4732e38c-b1a0-4de7-b6de-75dbde850488
caps.latest.revision: 8
ms.openlocfilehash: c5eea216efd8048aee5768c78c0b48617670f091
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067864"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="a437e-102">Как обеспечить поддержку транзакций</span><span class="sxs-lookup"><span data-stu-id="a437e-102">How to Support Transactions</span></span>

<span data-ttu-id="a437e-103">В этом примере показаны элементы базовый код, которые добавляют поддержку транзакций в командлет.</span><span class="sxs-lookup"><span data-stu-id="a437e-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a437e-104">Дополнительные сведения об обработке транзакций в Windows PowerShell см. в разделе [о транзакции][about_Transactions].</span><span class="sxs-lookup"><span data-stu-id="a437e-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="a437e-105">Для поддержки транзакций</span><span class="sxs-lookup"><span data-stu-id="a437e-105">To support transactions</span></span>

1. <span data-ttu-id="a437e-106">При объявлении атрибут командлета, укажите, что командлет поддерживает транзакции.</span><span class="sxs-lookup"><span data-stu-id="a437e-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="a437e-107">Если командлет поддерживает транзакции, Windows PowerShell добавляет `UseTransaction` параметра в командлет при его выполнении.</span><span class="sxs-lookup"><span data-stu-id="a437e-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="a437e-108">В одном из методов обработки ввода, добавьте `if` блок, чтобы определить, доступен ли транзакции.</span><span class="sxs-lookup"><span data-stu-id="a437e-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="a437e-109">Если `if` разрешается инструкции `true`, действия в данной инструкции, которые могут выполняться в контексте текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="a437e-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="a437e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a437e-110">See Also</span></span>

[<span data-ttu-id="a437e-111">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a437e-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
