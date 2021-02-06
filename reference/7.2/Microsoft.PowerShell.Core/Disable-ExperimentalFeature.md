---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ExperimentalFeature
ms.openlocfilehash: e35e164f3116304efd52c71c1715ba70711f6253
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601499"
---
# Disable-ExperimentalFeature

## Краткий обзор
Отключите экспериментальную функцию при запуске нового экземпляра PowerShell.

## SYNTAX

```
Disable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Disable-ExperimentalFeature`Командлет отключает экспериментальные функции, удаляя именованные экспериментальные функции из `powershell.config.json` файла параметров, считанного при запуске PowerShell.

Этот командлет появился в PowerShell 6,2.

> [!NOTE]
> Любые изменения в экспериментальном состоянии вступают в силу только при перезапуске PowerShell

## Примеры

### Пример 1. Отключение экспериментальной функции

В этом примере, если эта экспериментальная функция была включена ранее, `powershell.config.json` файл будет обновлен, чтобы пользователь не включил эту функцию после перезапуска PowerShell.
При успешном выполнении в конвейер ничего не выводится, и отображается только предупреждающее сообщение.

```powershell
PS C:\> Disable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## PARAMETERS

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Имя или имена экспериментальных функций для отключения.

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

### -Scope

Определяет, какие `powershell.config.json` обновления влияют на все пользователи или только на текущего пользователя.

```yaml
Type: System.Management.Automation.Configuration.ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: AllUsers, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### експерименталфеатуре

Для отключения необходимо передать экземпляры Експерименталфеатуре из `Get-ExperimentalFeature` командлета.

## Выходные данные

### None

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

Изменения в состоянии экспериментальной функции вступают в силу только при перезапуске PowerShell.

## Связанные ссылки

[Enable-ExperimentalFeature](Enable-ExperimentalFeature.md)

[Get-ExperimentalFeature](Get-ExperimentalFeature.md)

