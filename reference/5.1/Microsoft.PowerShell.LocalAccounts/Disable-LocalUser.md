---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/disable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-LocalUser
ms.openlocfilehash: a62242251da00688d3299c60e4cdae7aae6f581a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226626"
---
# Disable-LocalUser

## Краткий обзор
Отключает локальную учетную запись пользователя.

## SYNTAX

### InputObject

```
Disable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### По умолчанию

```
Disable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Disable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Disable-LocalUser** отключает локальные учетные записи пользователей.
Если учетная запись пользователя отключена, пользователь не может войти в систему.
Если учетная запись пользователя включена, пользователь может войти в систему.

> [!NOTE]
> Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.

## Примеры

### Пример 1. Отключение учетной записи путем указания имени

```
PS C:\> Disable-LocalUser -Name "Admin02"
```

Эта команда отключает учетную запись пользователя с именем Admin02.

### Пример 2. Отключение учетной записи с помощью конвейера

```
PS C:\> Get-LocalUser Guest | Disable-LocalUser
```

Эта команда получает встроенную учетную запись гостя с помощью командлета **Get-LocalUser** , а затем передает ее в текущий командлет с помощью конвейерного оператора.
Этот командлет отключает эту учетную запись.

## PARAMETERS

### -InputObject
Указывает массив учетных записей пользователей, которые отключает этот командлет.
Чтобы получить учетную запись пользователя, используйте командлет Get-LocalUser.

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Указывает массив имен учетных записей пользователей, которые отключает этот командлет.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### ИД безопасности
Указывает массив учетных записей пользователей, которые отключает этот командлет.

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. Секуритяккаунтсманажер. LocalUser, System. String, System. Security. Principal. SecurityIdentifier
Этот командлет можно передать по конвейеру локальному пользователю, строке или идентификатору безопасности.

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта. Возможны следующие источники:

- Локальная
- Active Directory
- Группа Azure Active Directory
- Учетная запись Майкрософт

**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows. Для более ранних версий свойство остается пустым.

## Связанные ссылки

[Enable-LocalUser](Enable-LocalUser.md)

[Get-LocalUser](Get-LocalUser.md)

[New-LocalUser](New-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
