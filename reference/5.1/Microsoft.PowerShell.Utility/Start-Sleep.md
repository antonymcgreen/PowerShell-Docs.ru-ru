---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 3/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4add39c09b6123aaf8c9302529346a6b1dec391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227497"
---
# Start-Sleep

## Краткий обзор
Приостанавливает действие в скрипте или сеансе на указанное время.

## SYNTAX

### Секунд (по умолчанию)

```
Start-Sleep [-Seconds] <Int32> [<CommonParameters>]
```

### Миллисекунды

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## DESCRIPTION

`Start-Sleep`Командлет приостанавливает действие в скрипте или сеансе за указанный период времени.
Его можно использовать для выполнения многих задач, например ожидания завершения операции или приостановки перед повторением операции.

## Примеры

### Пример 1. спящий режим для всех команд в течение 15 секунд

```powershell
Start-Sleep -s 15
```

Эта команда приостанавливает все команды в сеансе на 15 секунд.

### Пример 2. спящий режим всех команд

```powershell
Start-Sleep -m 500
```

Эта команда приостанавливает все команды в сеансе на полсекунды (500 мс).

## PARAMETERS

### – Миллисекунды

Указывает, на какое время ресурс приостанавливается, в миллисекундах.
Параметр можно сократить на **m** .

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Секунд

Указывает, на какое время ресурс приостанавливается, в секундах.
Имя параметра (в **секундах** ) можно опустить или сократить до **s** .

```yaml
Type: System.Int32
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Int32

Количество секунд можно передать в `Start-Sleep` .

## Выходные данные

### Нет

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

- Также можно ссылаться `Start-Sleep` по встроенному псевдониму `sleep` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Ctrl+C` разрыв из `Start-Sleep` .
  - `Ctrl+C` не нарушает работу `[Threading.Thread]::Sleep` . Дополнительные сведения см. в разделе [метод Thread. Sleep](/dotnet/api/system.threading.thread.sleep).

## Связанные ссылки
