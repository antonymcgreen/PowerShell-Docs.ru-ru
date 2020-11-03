---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 769d1ac91cbbc580b3488ba84d14a759b6ef65d4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228006"
---
# Unregister-PSRepository

## Краткий обзор
Отмена регистрации репозитория.

## SYNTAX

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION

`Unregister-PSRepository`Командлет отменяет регистрацию репозитория для текущего пользователя.

## Примеры

### Пример 1. Отмена регистрации репозитория

В этом примере отменяется регистрация репозитория с именем Минужетсаурце.

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### Пример 2. Отмена регистрации всех репозиториев

В этом примере используется `Get-PSRepository` для получения всех зарегистрированных репозиториев и используется оператор конвейера, чтобы передать их для `Unregister-PSRepository` отмены регистрации.

```powershell
Get-PSRepository | Unregister-PSRepository
```

## PARAMETERS

### -Name

Указывает массив имен удаляемых репозиториев.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String[]

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-PSRepository](Get-PSRepository.md)

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)
