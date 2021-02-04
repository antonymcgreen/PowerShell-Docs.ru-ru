---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 6ac35c698cc1b4f2571becdee48b1f73f21249e7
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098726"
---
# Clear-RecycleBin

## Краткий обзор
Очищает содержимое корзины.

## SYNTAX

### Все

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Clear-RecycleBin`Командлет удаляет содержимое корзины компьютера. Это действие аналогично использованию **пустой корзины** Windows.

Этот командлет был добавлен снова в PowerShell 7.

## Примеры

### 1: очистить все корзины

В этом примере очищаются все корзины локального компьютера.

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

`Clear-RecycleBin` запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.

### 2: Очистка указанной корзины

В этом примере очищается корзина для указанной буквы диска.

```powershell
Clear-RecycleBin -DriveLetter C
```

`Clear-RecycleBin` использует параметр **буква_диска** для указания корзины на томе **C** . Пользователю будет предложено подтвердить выполнение команды.

### 3: очистить все корзины без подтверждения

В этом примере не запрашивается подтверждение очистки корзины локального компьютера.

```powershell
Clear-RecycleBin -Force
```

`Clear-RecycleBin` использует параметр **Force** и не запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.

Альтернативой является замена на `-Force` `-Confirm:$false` .

## PARAMETERS

### -Буква_диска

Задает очистку корзины для одного диска или массива букв диска.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Указывает, что пользователю не предлагается подтверждение очистки корзины. Параметр **Force** также переопределяет параметры **WhatIf** и **Confirm** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение пользователя перед запуском командлета. Пользователю предлагается подтверждение, даже если параметр **Confirm** не указан.

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

Показывает, что произойдет при `Clear-RecycleBin` запуске. Командлет не выполняется.

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

## Выходные данные

### Нет

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

## Связанные ссылки
