---
ms.date: 09/13/2016
ms.topic: reference
title: Сообщения подтверждения
description: Сообщения подтверждения
ms.openlocfilehash: 76302b2f8d8ca6dcdfe1b3c36f71aad23a53f7cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355193"
---
# <a name="confirmation-messages"></a>Сообщения подтверждения

Ниже приведены различные сообщения с подтверждением, которые могут отображаться в зависимости от того, какие методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызываются.

> [!IMPORTANT]
> Пример кода, демонстрирующий запрос подтверждений, см. [в разделе как запросить подтверждения](./how-to-request-confirmations.md).

## <a name="specifying-the-resource"></a>Указание ресурса

Вы можете указать ресурс, который собираетесь изменить, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . В этом случае вы предоставляете ресурс с помощью `target` параметра метода, и эта операция добавляется Windows PowerShell. В следующем сообщении текст "MyResource" — это ресурс, на котором выполняется операция, а в качестве операции используется имя команды, выполняющей вызов.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Если пользователь выбирает **Да** или **Да для всех** запросов подтверждения (как показано в следующем примере), вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , что приводит к отображению второго сообщения с подтверждением.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a>Указание операции и ресурса

Можно указать ресурс, который будет изменен, и операцию, которую должна выполнить команда, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . В этом случае вы предоставляете ресурс с помощью `target` параметра и операции с помощью `target` параметра. В следующем сообщении текст "MyResource" — это работающий с ресурсом, а "Мяктион" — выполняемая операция.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Если пользователь выбирает **Да** или **Да для всех** предыдущих сообщений, вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , что приводит к отображению второго сообщения подтверждения.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
