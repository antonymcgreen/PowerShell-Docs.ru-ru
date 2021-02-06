---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: aad634bb0a917d418aa9c7fa295a53fda280b8a3
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "99604569"
---
# Get-ExperimentalFeature

## Краткий обзор
Получает экспериментальные функции.

## SYNTAX

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ExperimentalFeature`Командлет возвращает все экспериментальные функции, обнаруженные PowerShell.
Экспериментальные функции могут поступать из модулей или механизма PowerShell. Экспериментальные функции позволяют пользователям безопасно тестировать новые функции и предоставлять отзывы (обычно через GitHub), прежде чем проект считается завершенным, и любые изменения могут стать критическим изменением.

## Примеры

### Пример 1

Возвращает список зарегистрированных в настоящее время экспериментальных функций и их текущего состояния.

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## PARAMETERS

### -Name

Имя или имена конкретных экспериментальных функций, которые нужно вернуть.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String[]

Имя или имена экспериментальных функций, которые нужно вернуть.

## Выходные данные

### System. Management. Automation. Експерименталфеатуре

Возвращает экземпляры, соответствующие запрошенным именам, или все экспериментальные функции, если имя не указано.

## Связанные ссылки

[Disable-ExperimentalFeature](Disable-ExperimentalFeature.md)

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)
