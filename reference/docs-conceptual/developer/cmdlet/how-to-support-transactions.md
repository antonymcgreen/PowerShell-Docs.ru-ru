---
ms.date: 09/13/2016
ms.topic: reference
title: Как обеспечить поддержку транзакций
description: Как обеспечить поддержку транзакций
ms.openlocfilehash: 5691c246830dab9f4808801c04353ebfb2c3e981
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666966"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="af5ae-103">Как обеспечить поддержку транзакций</span><span class="sxs-lookup"><span data-stu-id="af5ae-103">How to Support Transactions</span></span>

<span data-ttu-id="af5ae-104">В этом примере показаны основные элементы кода, которые добавляют поддержку транзакций в командлет.</span><span class="sxs-lookup"><span data-stu-id="af5ae-104">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af5ae-105">Дополнительные сведения о том, как Windows PowerShell обрабатывает транзакции, см. в разделе [About Transactions][about_Transactions].</span><span class="sxs-lookup"><span data-stu-id="af5ae-105">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="af5ae-106">Для поддержки транзакций</span><span class="sxs-lookup"><span data-stu-id="af5ae-106">To support transactions</span></span>

1. <span data-ttu-id="af5ae-107">При объявлении атрибута командлета укажите, что командлет поддерживает транзакции.</span><span class="sxs-lookup"><span data-stu-id="af5ae-107">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="af5ae-108">Если командлет поддерживает транзакции, Windows PowerShell добавляет `UseTransaction` параметр в командлет при его запуске.</span><span class="sxs-lookup"><span data-stu-id="af5ae-108">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="af5ae-109">В одном из методов обработки входных данных добавьте `if` блок, чтобы определить, доступна ли транзакция.</span><span class="sxs-lookup"><span data-stu-id="af5ae-109">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="af5ae-110">Если `if` инструкция разрешается в `true` , действия в этой инструкции могут выполняться в контексте текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="af5ae-110">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="af5ae-111">См. также</span><span class="sxs-lookup"><span data-stu-id="af5ae-111">See Also</span></span>

[<span data-ttu-id="af5ae-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af5ae-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
