---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226610"
---
# Get-LocalGroupMember

## Краткий обзор
Возвращает элементы из локальной группы.

## SYNTAX

### Default (по умолчанию)

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### Group

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-локалграупмембер** получает элементы из локальной группы.

> [!NOTE]
> Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.

## Примеры

### Пример 1. получение всех членов группы "Администраторы"

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

Эта команда возвращает всех членов локальной группы администраторов.

## PARAMETERS

### -Group
Указывает группу безопасности, из которой этот командлет получает элементы.

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Member
Указывает пользователя или группу, которую этот командлет получает из группы безопасности.
Можно указать пользователей или группы по имени или ИДЕНТИФИКАТОРу безопасности (SID).
Укажите строки SID в S-R-I-S-S.
. .
ЧЧ:ММ:СС...
Можно использовать подстановочные знаки.
Если этот параметр не указан, командлет получает все члены группы.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Указывает имя группы безопасности, из которой этот командлет получает элементы.

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### ИД безопасности
Указывает идентификатор безопасности группы безопасности, из которой этот командлет получает элементы.

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. Секуритяккаунтсманажер. LocalGroup, System. String, System. Security. Principal. SecurityIdentifier
К этому командлету можно передать по конвейеру локальную группу, строку или идентификатор безопасности.

## Выходные данные

### Microsoft. Секуритяккаунтсманажер. ЛокалпринЦипал
Этот командлет возвращает локальных участников.

## ПРИМЕЧАНИЯ

* Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта. Возможны следующие источники:

- Локальная
- Active Directory
- Группа Azure Active Directory
- Учетная запись Майкрософт

**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows. Для более ранних версий свойство остается пустым.

## Связанные ссылки

[Add-LocalGroupMember](Add-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
