---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226629"
---
# Add-LocalGroupMember

## Краткий обзор
Добавляет элементы в локальную группу.

## SYNTAX

### Group

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### По умолчанию

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Add-LocalGroupMember`Командлет добавляет пользователей или группы в локальную группу безопасности. Все права и разрешения, присвоенные группе, действительны для всех членов данной группы.

Члены группы "Администраторы" на локальном компьютере имеют разрешения полного доступа на данном компьютере. Ограничьте число пользователей в группе "Администраторы".

Если компьютер подключен к домену, в локальную группу можно добавлять учетные записи пользователей, компьютеров и групп из этого домена и из доверенных доменов.

> [!NOTE]
> Если компьютер присоединен к домену и вы пытаетесь добавить локального пользователя с тем же именем, что и член домена, он добавляет член домена.

## Примеры

### Пример 1. Добавление членов в группу "Администраторы"

Эта команда добавляет несколько членов в локальную группу администраторов. Новые члены включают учетную запись локального пользователя, учетная запись Майкрософт, учетную запись Azure Active Directory и группу домена. В этом примере используется значение заполнителя для имени пользователя учетной записи в Outlook.com.

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## PARAMETERS

### -Group

Указывает группу безопасности, в которую этот командлет добавляет члены.

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Member

Указывает массив пользователей или групп, которые этот командлет добавляет в группу безопасности. Можно указать пользователей или группы по имени, ИДЕНТИФИКАТОРу безопасности (SID) или объектам **локалпринЦипал** .

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имя группы безопасности, в которую этот командлет добавляет члены.

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### ИД безопасности

Указывает идентификатор безопасности группы безопасности, в которую этот командлет добавляет члены.

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

### System. Management. Automation. Секуритяккаунтсманажер. LocalGroup, System. String, System. Security. Principal. SecurityIdentifier

Этому командлету можно передать по конвейеру локальный субъект, строку или идентификатор безопасности.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Модуль Microsoft. PowerShell. LocalAccounts недоступен в 32-разрядной версии PowerShell в 64-разрядной системе.

Свойство **принЦипалсаурце** является свойством для объектов **LocalUser** , **LocalGroup** и **локалпринЦипал** , описывающих источник объекта. Возможны следующие источники:

- Локальная
- Active Directory
- Группа Azure Active Directory
- Учетная запись Майкрософт

**ПринЦипалсаурце** поддерживается только в Windows 10, windows Server 2016 и более поздних версиях операционной системы Windows. Для более ранних версий свойство остается пустым.

## Связанные ссылки

[Get-LocalGroupMember](Get-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
