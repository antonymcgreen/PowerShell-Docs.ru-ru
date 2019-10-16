---
title: Поддержка транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4732e38c-b1a0-4de7-b6de-75dbde850488
caps.latest.revision: 8
ms.openlocfilehash: c5eea216efd8048aee5768c78c0b48617670f091
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365543"
---
# <a name="how-to-support-transactions"></a>Как обеспечить поддержку транзакций

В этом примере показаны основные элементы кода, которые добавляют поддержку транзакций в командлет.

> [!IMPORTANT]
> Дополнительные сведения о том, как Windows PowerShell обрабатывает транзакции, см. в разделе [About Transactions][about_Transactions].

## <a name="to-support-transactions"></a>Для поддержки транзакций

1. При объявлении атрибута командлета укажите, что командлет поддерживает транзакции.
   Если командлет поддерживает транзакции, Windows PowerShell добавляет параметр `UseTransaction` в командлет при его запуске.

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. В одном из методов обработки входных данных добавьте блок `if`, чтобы определить, доступна ли транзакция.
   Если инструкция `if` разрешается в `true`, действия в этой инструкции могут выполняться в контексте текущей транзакции.

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
