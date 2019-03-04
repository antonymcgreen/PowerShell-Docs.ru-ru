---
title: Подтверждение | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a886a26d-7730-4586-aeac-fd3f0bc60b88
caps.latest.revision: 8
ms.openlocfilehash: 75214a3fe4bc019836f75db19fb873bd081f200f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861420"
---
# <a name="confirmation-messages"></a>Сообщения подтверждения

Ниже приведены различные подтверждающих сообщений, которые могут отображаться в зависимости от того, варианты [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [ System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы, вызываемые.

> [!IMPORTANT]
> Пример кода, показывающий, как для запроса подтверждения, см. в разделе [как подтверждения](./how-to-request-confirmations.md).

## <a name="specifying-the-resource"></a>Указание ресурса

Можно указать ресурс, который собираетесь изменить, вызвав [System.Management.Automation.Cmdlet.Shouldprocess%2A? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) метод. В этом случае указать ресурс с помощью `target` добавлен параметр метода, и операции с Windows PowerShell. В следующее сообщение: текст «MyResource» — это ресурс, обрабатываемого и операции является имя команды, которая выполняет вызов.

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Если пользователь выбирает **Да** или **Да для всех** для подтверждения запроса (как показано в следующем примере), вызов [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод будет установлено, что вызывает второе сообщение с подтверждением для отображения.

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a>Задание операции и ресурсов

Можно указать ресурс должен быть изменен и операцию, команда должна выполнить путем вызова [System.Management.Automation.Cmdlet.Shouldprocess%2A? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) метод. В этом случае указать ресурс с помощью `target` параметр и операцию, используя `target` параметра. В следующее сообщение: текст «MyResource» — это ресурс, обрабатываемого, а «MyAction» — операцию для выполнения.

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Если пользователь выбирает **Да** или **Да для всех** к предыдущему сообщению, вызов [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод будет установлено, что приводит второе сообщение с подтверждением для отображения.

```output
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
