---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 3260c88d57e98c0072af8621600a02901c561acb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599813"
---
# Disable-WSManCredSSP

## Краткий обзор
Отключает проверку подлинности CredSSP на компьютере.

## SYNTAX

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Disable-WSManCredSSP** отключает проверку подлинности на уровне поставщика поддержки учетных данных (CredSSP) на клиенте или на компьютере сервера.
При использовании проверки подлинности CredSSP учетные данные пользователя передаются на удаленный компьютер для проверки подлинности.

Используйте этот командлет для отключения CredSSP на клиенте, указав Client в параметре *Role* .
Этот командлет выполняет следующие действия:

- Отключает CredSSP на клиенте. Этот командлет задает для параметра WS-Management **\<localhost|computername\> \клиент\аус\кредссп** значение false.
- Удаляет все параметры WSMan/* из политики Windows CredSSP, **алловфрешкредентиалс** на клиенте.

Используйте этот командлет для отключения CredSSP на сервере путем указания сервера в *роли*.
Этот командлет выполняет следующее действие:

- Отключает CredSSP на сервере. Этот командлет задает для параметра WS-Management **\<localhost|computername\> \сервице\аус\кредссп** значение false.

Внимание! проверка подлинности CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.
Это повышает угрозу безопасности при работе в удаленном режиме.
Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.

## Примеры

### Пример 1. Отключение CredSSP на клиенте

```
PS C:\> Disable-WSManCredSSP -Role Client
```

Эта команда отключает CredSSP на стороне клиента, что препятствует делегированию на серверы.

### Пример 2. Отключение CredSSP на сервере

```
PS C:\> Disable-WSManCredSSP -Role Server
```

Эта команда отключает CredSSP на стороне сервера, что препятствует делегированию с клиентов.

## PARAMETERS

### -Role
Указывает, следует ли отключить CredSSP в качестве клиента или сервера.
Допустимые значения для этого параметра: Client и Server.

При указании клиента этот командлет выполняет следующие действия:

- Отключает CredSSP на клиенте. Этот командлет задает WS-Management параметру **\<localhost|computername\> \клиент\аус\кредссп** значение false.
- Удаляет все параметры WSMan/* из политики Windows CredSSP, **алловфрешкредентиалс** на клиенте.

При указании Server этот командлет выполняет следующее действие:

- Отключает CredSSP на сервере. Этот командлет задает для параметра WS-Management **\<localhost|computername\> \сервице\аус\кредссп** значение false.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None
Этот командлет не принимает никаких входных данных.

## Выходные данные

### None
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Чтобы включить аутентификацию CredSSP, воспользуйтесь командлетом Enable-WSManCredSSP.

*

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)

