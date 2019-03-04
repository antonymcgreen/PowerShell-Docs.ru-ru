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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857120"
---
# <a name="how-to-support-transactions"></a>Как обеспечить поддержку транзакций

В этом примере показаны элементы базовый код, которые добавляют поддержку транзакций в командлет.

> [!IMPORTANT]
> Дополнительные сведения об обработке транзакций в Windows PowerShell см. в разделе [о транзакции][about_Transactions].

## <a name="to-support-transactions"></a>Для поддержки транзакций

1. При объявлении атрибут командлета, укажите, что командлет поддерживает транзакции.
   Если командлет поддерживает транзакции, Windows PowerShell добавляет `UseTransaction` параметра в командлет при его выполнении.

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. В одном из методов обработки ввода, добавьте `if` блок, чтобы определить, доступен ли транзакции.
   Если `if` разрешается инструкции `true`, действия в данной инструкции, которые могут выполняться в контексте текущей транзакции.

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
