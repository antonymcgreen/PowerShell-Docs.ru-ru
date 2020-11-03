---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226617"
---
# Get-LocalGroup

## Краткий обзор
Возвращает локальные группы безопасности.

## SYNTAX

### Default (по умолчанию)

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-LocalGroup** получает локальные группы безопасности в диспетчере учетных записей безопасности.
Этот командлет получает встроенные группы по умолчанию и локальные группы безопасности, которые вы создаете.

> [!NOTE]
> Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.

## Примеры

### Пример 1. Получение группы администраторов

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

Эта команда возвращает локальную группу администраторов.
Команда отображает свойства группы в консоли.

## PARAMETERS

### -Name
Указывает массив имен групп безопасности, которые получает этот командлет.
Можно использовать подстановочный знак.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### ИД безопасности
Указывает массив идентификаторов безопасности (SID) групп безопасности, которые получает этот командлет.

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. String, System. Security. Principal. SecurityIdentifier
В этот командлет можно передать строку или идентификатор безопасности.

## Выходные данные

### System. Management. Automation. Секуритяккаунтсманажер. LocalGroup
Этот командлет возвращает локальную группу.

## ПРИМЕЧАНИЯ

* Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта. Возможны следующие источники:

- Локальная
- Active Directory
- Группа Azure Active Directory
- Учетная запись Майкрософт

**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows. Для более ранних версий свойство остается пустым.

## Связанные ссылки

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroup](Remove-LocalGroup.md)

[Rename-LocalGroup](Rename-LocalGroup.md)

[Set-LocalGroup](Set-LocalGroup.md)
