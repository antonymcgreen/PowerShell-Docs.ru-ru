---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228469"
---
# Checkpoint-Computer

## Краткий обзор
Создает точку восстановления системы на локальном компьютере.

## SYNTAX

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## DESCRIPTION

`Checkpoint-Computer`Командлет создает точку восстановления системы на локальном компьютере.

Точки восстановления системы и `Checkpoint-Computer` командлеты поддерживаются только в клиентских операционных системах, таких как Windows 8, Windows 7, Windows Vista и Windows XP.

Начиная с Windows 8, `Checkpoint-Computer` каждый день нельзя создавать более одной контрольной точки.

## Примеры

### Пример 1. Создание точки восстановления системы

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

Эта команда создает точку восстановления системы с именем Install MyApp.
Она использует тип точки восстановления APPLICATION_INSTALL по умолчанию.

### Пример 2. Создание точки восстановления системы MODIFY_SETTINGS

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

Эта команда создает точку восстановления системы MODIFY_SETTINGS с именем ChangeNetSettings.

## PARAMETERS

### -Description

Указывает описательное имя для точки восстановления.
Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ресторепоинттипе

Указывает тип точки восстановления.
Значение по умолчанию — APPLICATION_INSTALL.

Допустимые значения для этого параметра:

- APPLICATION_INSTALL
- APPLICATION_UNINSTALL
- DEVICE_DRIVER_INSTALL
- MODIFY_SETTINGS
- CANCELLED_OPERATION

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

Вы не можете передать объекты в `Checkpoint-Computer` .

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- Этот командлет использует метод **креатересторепоинт** класса **SystemRestore** с событием **BEGIN_SYSTEM_CHANGE** .
- Начиная с Windows 8, `Checkpoint-Computer` каждый день не может создавать более одной точки восстановления системы. При попытке создать новую точку восстановления до истечения 24-часового периода в Windows PowerShell возникнет следующая ошибка:

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## Связанные ссылки

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restore-Computer](Restore-Computer.md)
