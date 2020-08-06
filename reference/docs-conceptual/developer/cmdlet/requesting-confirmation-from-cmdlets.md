---
title: Запрос подтверждения из командлетов | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ConfirmImpact [PowerShell Programmer's Guide], described
- ShouldContinue [PowerShell Programmer's Guide], described
- user feedback [PowerShell Programmer's Guide], requesting
- ShouldProcess [PowerShell Programmer's Guide], described
- ConfirmPreference [PowerShell Programmer's Guide], described
ms.openlocfilehash: bcc4c766d0012e7173550e3b6cb3ef058baa06bb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781806"
---
# <a name="requesting-confirmation-from-cmdlets"></a>Запрос на подтверждение от командлетов

Командлеты должны запрашивать подтверждение, когда они собирается внести изменения в систему, которая находится за пределами среды Windows PowerShell. Например, если командлет собирается добавить учетную запись пользователя или приостанавливает процесс, командлет должен потребовать подтверждения от пользователя перед тем, как оно будет продолжено. Напротив, если командлет собирается изменить переменную Windows PowerShell, командлету не требуется требовать подтверждения.

Чтобы сделать запрос на подтверждение, командлет должен указать, что он поддерживает запросы на подтверждение, и он должен вызвать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (необязательные) для отображения сообщения запроса подтверждения.

## <a name="supporting-confirmation-requests"></a>Поддержка запросов на подтверждение

Для поддержки запросов на подтверждение командлет должен задать `SupportsShouldProcess` для параметра атрибута командлета значение `true` . Это включает `Confirm` `WhatIf` параметры командлета и, предоставляемые Windows PowerShell. `Confirm`Параметр позволяет пользователю контролировать, отображается ли запрос подтверждения. `WhatIf`Параметр позволяет пользователю определить, должен ли командлет отображать сообщение или выполнить его действие. Не добавляйте `Confirm` `WhatIf` Параметры и в командлет вручную.

В следующем примере показано объявление атрибута командлета, которое поддерживает запросы на подтверждение.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a>Вызов методов запроса подтверждения

В коде командлета вызовите метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) перед операцией, которая изменяет систему. Разработайте командлет таким образом, чтобы, если вызов возвращает значение `false` , операция не выполняется, а командлет обрабатывает следующую операцию.

## <a name="calling-the-shouldcontinue-method"></a>Вызов метода ShouldContinue

Большинство командлетов запрашивают подтверждение, используя только метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) . Однако в некоторых случаях может потребоваться дополнительное подтверждение. В этих случаях дополнит вызов метода [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , вызвав метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) . Это позволяет командлету или поставщику более точно контролировать область действия **Да для всех** ответов на запрос подтверждения.

Если командлет вызывает метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , командлет также должен предоставить `Force` параметр Switch. Если пользователь указывает `Force` , когда пользователь вызывает командлет, командлет должен по-прежнему вызывать метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess), но не должен обходить вызов [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).

[System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) будет вызывать исключение при вызове из неинтерактивной среды, в которой пользователю не удается получить запрос. Добавление `Force` параметра гарантирует, что команда будет по-прежнему выполняться при ее вызове в неинтерактивной среде.

В следующем примере показано, как вызвать [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

Поведение вызова [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) может различаться в зависимости от среды, в которой вызывается командлет. Использование описанных выше правил поможет обеспечить согласованность командлета с другими командлетами независимо от среды размещения.

Пример вызова метода [System. Management. Automation. командлета. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) см. [в разделе как запросить подтверждения](./how-to-request-confirmations.md).

## <a name="specify-the-impact-level"></a>Укажите уровень влияния

При создании командлета укажите уровень влияния (серьезность) изменения. Для этого задайте `ConfirmImpact` для параметра атрибута командлета значение высокий, средний или низкий. Можно указать значение `ConfirmImpact` только в том случае, если также указать `SupportsShouldProcess` параметр для командлета.

Для большинства командлетов не нужно явно указывать `ConfirmImpact` .  Вместо этого используйте параметр по умолчанию, который является средним. Если задано значение `ConfirmImpact` высокий, операция будет подтверждена по умолчанию. Зарезервируйте этот параметр для критических действий, таких как переформатирование тома жесткого диска.

## <a name="calling-non-confirmation-methods"></a>Вызов методов без подтверждения

Если командлет или поставщик должен отправить сообщение, но не запрашивать подтверждение, он может вызвать следующие три метода. Избегайте использования метода [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) для отправки сообщений этих типов, так как выходные данные [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) запутанной с обычными выходными данными командлета или поставщика, что затрудняет написание сценариев.

- Для предупреждения пользователя и продолжения операции командлет или поставщик может вызвать метод [System. Management. Automation. командлет. вритеварнинг](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) .

- Чтобы предоставить дополнительные сведения, которые пользователь может получить с помощью `Verbose` параметра, командлет или поставщик может вызвать метод [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) .

- Чтобы предоставить сведения на уровне отладки для других разработчиков или для поддержки продукта, командлет или поставщик может вызвать метод [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) . Пользователь может получить эти сведения с помощью `Debug` параметра.

Командлеты и поставщики сначала вызывают следующие методы, чтобы запросить подтверждение, прежде чем они попытаются выполнить операцию, которая изменяет систему за пределами Windows PowerShell:

- [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [System. Management. Automation. Provider. Кмдлетпровидер. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

Это можно сделать, вызвав метод [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , который предлагает пользователю подтвердить операцию в зависимости от того, как пользователь вызвал команду.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
