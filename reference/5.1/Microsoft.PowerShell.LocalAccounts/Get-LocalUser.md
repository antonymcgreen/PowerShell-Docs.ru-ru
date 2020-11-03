---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 34210145bcddc8d9420552d637a6cd6e5f8e61cc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226609"
---
# Get-LocalUser

## Краткий обзор
Возвращает учетные записи локальных пользователей.

## SYNTAX

### Default (по умолчанию)

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-LocalUser`Командлет получает локальные учетные записи пользователей. Этот командлет получает встроенные учетные записи пользователей по умолчанию, созданные локальные учетные записи пользователей и локальные учетные записи, подключенные к учетным записям Майкрософт.

> [!NOTE]
> Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.

## Примеры

### Пример 1. Получение учетной записи с помощью ее имени

В этом примере получается учетная запись пользователя с именем AdminContoso02.

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### Пример 2. Получение учетной записи, подключенной к учетная запись Майкрософт

В этом примере возвращается учетная запись пользователя, подключенная к учетная запись Майкрософт. В этом примере используется значение заполнителя для имени пользователя учетной записи в Outlook.com.

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### Пример 3. Получение учетной записи, подключенной к учетная запись Майкрософт

В этом примере возвращается локальная учетная запись пользователя с указанным идентификатором SID.

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## PARAMETERS

### -Name

Указывает массив имен учетных записей пользователей, которые получает этот командлет. Можно использовать подстановочный знак.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### ИД безопасности

Указывает массив идентификаторов безопасности (SID) учетных записей пользователей, которые получает этот командлет.

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

### System. Management. Automation. Секуритяккаунтсманажер. LocalUser []

Этот командлет возвращает локальные учетные записи пользователей.

## ПРИМЕЧАНИЯ

Свойство **принЦипалсаурце** объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** описывает источник объекта. Возможны следующие источники:

- Локальная
- Active Directory
- Группа Azure Active Directory
- Учетная запись Майкрософт

**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows. Для более ранних версий свойство остается пустым.

## Связанные ссылки

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[New-LocalUser](New-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
