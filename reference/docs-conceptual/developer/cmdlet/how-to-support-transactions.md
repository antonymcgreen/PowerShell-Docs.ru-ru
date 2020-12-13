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
# <a name="how-to-support-transactions"></a>Как обеспечить поддержку транзакций

В этом примере показаны основные элементы кода, которые добавляют поддержку транзакций в командлет.

> [!IMPORTANT]
> Дополнительные сведения о том, как Windows PowerShell обрабатывает транзакции, см. в разделе [About Transactions][about_Transactions].

## <a name="to-support-transactions"></a>Для поддержки транзакций

1. При объявлении атрибута командлета укажите, что командлет поддерживает транзакции.
   Если командлет поддерживает транзакции, Windows PowerShell добавляет `UseTransaction` параметр в командлет при его запуске.

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. В одном из методов обработки входных данных добавьте `if` блок, чтобы определить, доступна ли транзакция.
   Если `if` инструкция разрешается в `true` , действия в этой инструкции могут выполняться в контексте текущей транзакции.

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
