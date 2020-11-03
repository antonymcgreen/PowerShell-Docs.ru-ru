---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: ce2046a9df5d4d02d718d6408c7a196a753c9914
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233082"
---
# Get-WSManCredSSP

## Краткий обзор
Получает конфигурацию CredSSP для клиента.

## SYNTAX

```
Get-WSManCredSSP [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-WSManCredSSP** возвращает конфигурацию клиента и сервера, связанную с поставщиком поддержки безопасности учетных данных.
В выходных данных указано, включена ли аутентификация CredSSP,
Этот командлет также отображает сведения о конфигурации для политики **Алловфрешкредентиалс** CredSSP.

При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.
Этот тип проверки подлинности предназначен для команд, которые создают удаленный сеанс из другого удаленного сеанса.
Например, если вы хотите запустить фоновое задание на удаленном компьютере, используйте такой тип проверки подлинности.

Командлет выполняет следующие операции:

- Возвращает параметр WS-Management CredSSP на клиенте ( **\<localhost|computername\> \клиент\аус\кредссп** ).
- Получает параметр политики CredSSP Windows **алловфрешкредентиалс** .
- Возвращает параметр WS-Management CredSSP на сервере ( **\<localhost|computername\> \сервице\аус\кредссп** ).

Внимание! проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.
Это повышает угрозу безопасности при работе в удаленном режиме.
Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.

## Примеры

### Пример 1. Отображение конфигурации CredSSP

```
PS C:\> Get-WSManCredSSP
```

Эта команда отображает сведения о конфигурации CredSSP как для клиента, так и для сервера.

В выходных данных указано, настроен ли этот компьютер для CredSSP.

Если компьютер настроен для CredSSP, выходные данные имеют следующий вид:

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

Если компьютер не настроен для CredSSP, выходные данные имеют следующий вид:

`The machine is not configured to allow delegating fresh credentials.`

## PARAMETERS

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Этот командлет не принимает никаких входных данных.

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Чтобы отключить аутентификацию CredSSP, воспользуйтесь командлетом Disable-WSManCredSSP. Чтобы включить аутентификацию CredSSP, воспользуйтесь командлетом Enable-WSManCredSSP.

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
