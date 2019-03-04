---
title: Запрос на подтверждение из командлетов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConfirmImpact [PowerShell Programmer's Guide], described
- ShouldContinue [PowerShell Programmer's Guide], described
- user feedback [PowerShell Programmer's Guide], requesting
- ShouldProcess [PowerShell Programmer's Guide], described
- ConfirmPreference [PowerShell Programmer's Guide], described
ms.assetid: 37d6e87f-57b7-40bd-b645-392cf0b6e88e
caps.latest.revision: 13
ms.openlocfilehash: ec441831f5e3231a44c9875d1b6d2bf6280a6965
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853400"
---
# <a name="requesting-confirmation-from-cmdlets"></a>Запрос на подтверждение от командлетов

Командлеты следует запрашивать подтверждение, когда они будут внесены изменения в системе за пределами среды Windows PowerShell. Например если командлет является добавление учетной записи пользователя или остановить процесс, командлет должна требовать подтверждения от пользователя перед началом. Напротив Если командлет является изменением переменной Windows PowerShell, командлет не требует подтверждения.

Чтобы сделать запрос на подтверждение, необходимо указать командлет, он поддерживает запросы на подтверждение, что он должен вызвать [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [ System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (необязательно) методы, чтобы отобразить сообщение с подтверждением запроса.

## <a name="supporting-confirmation-requests"></a>Поддержка запросов подтверждения

Для поддержки запросов подтверждения, необходимо задать командлет `SupportsShouldProcess` параметр атрибута командлет, чтобы `true`. Это позволяет `Confirm` и `WhatIf` параметры командлета, предоставляемые Windows PowerShell. `Confirm` Параметр позволяет пользователю управлять ли отображается запрос на подтверждение. `WhatIf` Параметр позволяет пользователю определить, следует ли командлет выводит сообщение, или выполнение его действия. Не добавляйте вручную `Confirm` и `WhatIf` параметров командлета.

Следующий пример показывает объявление атрибута командлет, которая поддерживает запросы подтверждения.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a>Вызов методов запроса подтверждения

В коде командлета, вызов [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод перед выполнением операции, изменений в системе. Создать командлет, поэтому, если вызов возвращает значение `false`, эта операция не выполнена, и командлет обрабатывает следующей операции.

## <a name="calling-the-shouldcontinue-method"></a>Вызов метода ShouldContinue

Большинство командлетов запросить подтверждение только с помощью [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод. Однако в некоторых случаях могут потребовать дополнительного подтверждения. В этих случаях дополнить [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызывать с помощью вызова [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод. Это позволяет командлета или поставщика, чтобы более точно управлять областью **Да для всех** ответ на запрос на подтверждение.

Если командлет вызывает [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод, командлет должен также содержать `Force` параметр-переключатель. Если пользователь указывает `Force` когда пользователь вызывает командлет, командлет должен по-прежнему вызывать [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess), но его нужно пропустить вызов [ System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).

[System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) приведет к возникновению исключения при вызове из Неинтерактивный режим среды где пользователь не смогут получить уведомления. Добавление `Force` параметр гарантирует, что при вызове в среде с неинтерактивной по-прежнему может выполняться команда.

В следующем примере показан вызов [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

Поведение [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызов может изменяться в зависимости от среды, в котором вызывается командлет. С помощью предыдущего руководства помогут убедиться, что командлет работает согласованно с другими командлетами, независимо от того, хост-среды.

Пример вызова [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод, см. в разделе [как запросить подтверждения](./how-to-request-confirmations.md).

## <a name="specify-the-impact-level"></a>Укажите уровень влияния

При создании командлета, укажите уровень влияния (серьезность) изменения. Чтобы сделать это, установите для параметра `ConfirmImpact` параметра атрибута командлет на высокий, средний или низкий. Можно указать значение для `ConfirmImpact` только также указывая `SupportsShouldProcess` параметра командлета.

Для большинства командлетов, нет необходимости явно указывать `ConfirmImpact`.  Вместо этого используйте параметр по умолчанию параметра, Medium. Если задать `ConfirmImpact` высокий приоритет, операция будет подтвержден по умолчанию. Зарезервируйте этот параметр для действий с высокой может нарушить работу системы, например переформатирование тома жесткого диска.

## <a name="calling-non-confirmation-methods"></a>Вызов методов без подтверждения

Если командлет или поставщика необходимо отправить сообщение, но не запросит подтверждение, оно может вызвать следующие три метода. Избегайте использования [System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) метод для отправки сообщений из этих типов, так как [System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) обычные выходные данные с обычной выходные данные командлета или поставщика услуг, что затрудняет написание скрипта.

- Чтобы предупредить пользователя и продолжить операцию, можно вызвать командлет или поставщика [System.Management.Automation.Cmdlet.Writewarning*](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) метод.

- Для предоставления дополнительных сведений, пользователя можно получить с помощью `Verbose` параметр, командлет или поставщика можно вызвать [System.Management.Automation.Cmdlet.Writeverbose*](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) метод.

- Для предоставления сведений о отладки на уровне, для других разработчиков или технической поддержки, можно вызвать командлет или поставщика [System.Management.Automation.Cmdlet.Writedebug*](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) метод. Пользователь может получить эти сведения с помощью `Debug` параметра.

Командлеты и поставщики первый вызов следующих методов запросит подтверждение, перед тем как пытаться выполнить операцию, которая изменяет системе за пределами Windows PowerShell:

- [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [System.Management.Automation.Provider.Cmdletprovider.Shouldprocess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

Это делается посредством вызова [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод, который предлагает пользователю подтвердить операцию, в зависимости от того, как пользователь вызывает команду.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
