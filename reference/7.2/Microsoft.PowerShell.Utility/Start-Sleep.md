---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4d06fdd1d5a616c24a4dd7bec10ea4dadea4062
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604650"
---
# Start-Sleep

## Краткий обзор
Приостанавливает действие в скрипте или сеансе на указанное время.

## SYNTAX

### Секунд (по умолчанию)

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### Миллисекунды

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## DESCRIPTION

`Start-Sleep`Командлет приостанавливает действие в скрипте или сеансе за указанный период времени. Его можно использовать для выполнения многих задач, например ожидания завершения операции или приостановки перед повторением операции.

## Примеры

### Пример 1. спящий режим для всех команд в течение 15 секунд

```powershell
Start-Sleep -s 15
```

### Пример 2. спящий режим для всех команд в течение 1,5 секунд

В этом примере все команды сеанса находятся в спящем режиме в течение одной и одной половины секунд.

```powershell
Start-Sleep -Seconds 1.5
```

## PARAMETERS

### – Миллисекунды

Указывает, на какое время ресурс приостанавливается, в миллисекундах. Параметр можно сократить на **m**.

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Секунд

Указывает, на какое время ресурс приостанавливается, в секундах. Имя параметра можно опустить или сократить до **s**. Начиная с PowerShell 6.2.0, этот параметр теперь принимает дробные значения.

```yaml
Type: System.Double
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

### None

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

- Также можно ссылаться `Start-Sleep` по встроенному псевдониму `sleep` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Ctrl+C` разрыв из `Start-Sleep` .
  - `Ctrl+C` не нарушает работу `[Threading.Thread]::Sleep` . Дополнительные сведения см. в разделе [метод Thread. Sleep](/dotnet/api/system.threading.thread.sleep).

## Связанные ссылки

