---
title: Поддержка транзакций | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6fda27394091195b589afef5ee53c6d3bec4efc0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786617"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="a10e4-102">Как обеспечить поддержку транзакций</span><span class="sxs-lookup"><span data-stu-id="a10e4-102">How to Support Transactions</span></span>

<span data-ttu-id="a10e4-103">В этом примере показаны основные элементы кода, которые добавляют поддержку транзакций в командлет.</span><span class="sxs-lookup"><span data-stu-id="a10e4-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a10e4-104">Дополнительные сведения о том, как Windows PowerShell обрабатывает транзакции, см. в разделе [About Transactions][about_Transactions].</span><span class="sxs-lookup"><span data-stu-id="a10e4-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="a10e4-105">Для поддержки транзакций</span><span class="sxs-lookup"><span data-stu-id="a10e4-105">To support transactions</span></span>

1. <span data-ttu-id="a10e4-106">При объявлении атрибута командлета укажите, что командлет поддерживает транзакции.</span><span class="sxs-lookup"><span data-stu-id="a10e4-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="a10e4-107">Если командлет поддерживает транзакции, Windows PowerShell добавляет `UseTransaction` параметр в командлет при его запуске.</span><span class="sxs-lookup"><span data-stu-id="a10e4-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="a10e4-108">В одном из методов обработки входных данных добавьте `if` блок, чтобы определить, доступна ли транзакция.</span><span class="sxs-lookup"><span data-stu-id="a10e4-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="a10e4-109">Если `if` инструкция разрешается в `true` , действия в этой инструкции могут выполняться в контексте текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="a10e4-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="a10e4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a10e4-110">See Also</span></span>

[<span data-ttu-id="a10e4-111">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a10e4-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
