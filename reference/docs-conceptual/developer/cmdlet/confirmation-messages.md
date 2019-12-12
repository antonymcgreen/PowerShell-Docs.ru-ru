---
title: Сообщения подтверждения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a886a26d-7730-4586-aeac-fd3f0bc60b88
caps.latest.revision: 8
ms.openlocfilehash: 229725b5b9f1f0082592dcebe11564fd2f630ce1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365733"
---
# <a name="confirmation-messages"></a>Сообщения подтверждения

Ниже приведены различные сообщения с подтверждением, которые могут отображаться в зависимости от того, какие методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызываются.

> [!IMPORTANT]
> Пример кода, демонстрирующий запрос подтверждений, см. [в разделе как запросить подтверждения](./how-to-request-confirmations.md).

## <a name="specifying-the-resource"></a>Указание ресурса

Вы можете указать ресурс, который собираетесь изменить, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) . В этом случае ресурс предоставляется с помощью параметра `target` метода, а операция добавляется Windows PowerShell. В следующем сообщении текст "MyResource" — это ресурс, на котором выполняется операция, а в качестве операции используется имя команды, выполняющей вызов.

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Если пользователь выбирает **Да** или **Да для всех** запросов подтверждения (как показано в следующем примере), вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , что приводит к отображению второго сообщения с подтверждением.

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a>Указание операции и ресурса

Можно указать ресурс, который будет изменен, и операцию, которую должна выполнить команда, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) . В этом случае ресурс предоставляется с помощью параметра `target` и операции с помощью параметра `target`. В следующем сообщении текст "MyResource" — это работающий с ресурсом, а "Мяктион" — выполняемая операция.

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Если пользователь выбирает **Да** или **Да для всех** предыдущих сообщений, вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , что приводит к отображению второго сообщения подтверждения.

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
