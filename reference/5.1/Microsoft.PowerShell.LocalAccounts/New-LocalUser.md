---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228001"
---
# New-LocalUser

## Краткий обзор

Создает локальную учетную запись пользователя.

## SYNTAX

### Пароль (по умолчанию)

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Не заменять пароль

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`New-LocalUser`Командлет создает локальную учетную запись пользователя. Этот командлет создает локальную учетную запись пользователя или локальную учетную запись пользователя, подключенную к учетная запись Майкрософт.

> [!NOTE]
> Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.

## Примеры

### Пример 1. Создание учетной записи пользователя

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

Эта команда создает локальную учетную запись пользователя и не указывает параметры **AccountExpires** или **Password** . Поэтому срок действия учетной записи не истекает или пароль по умолчанию не используется.

### Пример 2. Создание учетной записи пользователя с паролем

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

Первая команда запрашивает пароль с помощью `Read-Host` командлета. Команда сохраняет пароль в виде защищенной строки в `$Password` переменной.

Вторая команда создает локальную учетную запись пользователя, используя пароль, хранящийся в `$Password` . Команда задает имя пользователя, полное имя и описание учетной записи пользователя.

## PARAMETERS

### -AccountExpires

Указывает, когда истекает срок действия учетной записи пользователя. Чтобы получить объект **DateTime** , используйте `Get-Date` командлет.
Если этот параметр не указан, срок действия учетной записи не истечет.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Аккаунтневерекспирес

Указывает, что срок действия учетной записи не истекает.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description

Указывает комментарий для учетной записи пользователя.
Максимальная длина — 48 символов.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — Отключено

Указывает, что этот командлет создает учетную запись пользователя как отключенную.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullName

Указывает полное имя учетной записи пользователя. Полное имя отличается от имени пользователя учетной записи пользователя.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает имя пользователя для учетной записи пользователя.

Если вы создаете локальную учетную запись пользователя для локальной системы, имя пользователя может содержать до 20 символов верхнего регистра или строчных символов. Имя пользователя не может содержать следующие символы:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

Имя пользователя не может состоять только из точек `.` или пробелов.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Непарольный

Указывает, что у учетной записи пользователя нет пароля.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password

Указывает пароль для учетной записи пользователя. Для `Read-Host -GetCredential` `Get-Credential` `ConvertTo-SecureString` создания объекта **SecureString** для пароля можно использовать, или.

Если вы не пропускаете параметры **Password** **и Password,** `New-LocalUser` запрашивает пароль нового пользователя.

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Пассвордневерекспирес

Указывает, истечет ли срок действия пароля.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Усермайнотчанжепассворд

Указывает, что пользователь не может изменить пароль для учетной записи пользователя.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System. String, System. DateTime, System. Boolean, System. Security. SecureString

В этот командлет можно передать по конвейеру строку, объект **DateTime** , логическое значение или безопасную строку.

## Выходные данные

### System. Management. Automation. Секуритяккаунтсманажер. LocalUser

Этот командлет возвращает объект **LocalUser** .
Этот объект предоставляет сведения об учетной записи пользователя.

## ПРИМЕЧАНИЯ

- Имя пользователя не может совпадать с любым другим именем пользователя или группы на компьютере. Имя пользователя не может состоять только из точек `.` или пробелов. Имя пользователя может содержать до 20 символов верхнего регистра или строчных символов. Имя пользователя не может содержать следующие символы:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

- Пароль может содержать до 127 символов.
- Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта. Возможны следующие источники:

  - Локальная
  - Active Directory
  - Группа Azure Active Directory
  - Учетная запись Майкрософт

> [!NOTE]
> **ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows. Для более ранних версий свойство остается пустым.

## Связанные ссылки

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[Get-LocalUser](Get-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
