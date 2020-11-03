---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227054"
---
# Remove-PSSnapin

## Краткий обзор
Удаляет оснастки Windows PowerShell из текущего сеанса.

## SYNTAX

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Remove-PSSnapin** удаляет оснастку Windows PowerShell из текущего сеанса.
Его можно использовать для удаления оснасток, добавленных в Windows PowerShell. Этот командлет нельзя использовать для удаления оснасток, установленных с помощью Windows PowerShell.

После удаления оснастки из текущего сеанса оснастка по-прежнему загружается, но командлеты и поставщики в оснастке больше не будут доступны в сеансе.

## Примеры

### Пример 1. удаление оснастки

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

Эта команда удаляет оснастку **Microsoft. Exchange** из текущего сеанса.
После выполнения команды командлеты и поставщики, поддерживаемые этой оснасткой, будут недоступны в данном сеансе.

### Пример 2. удаление оснасток с помощью имен в конвейере

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

Эта команда удаляет оснастки Windows PowerShell, имена которых начинаются с SMP, из текущего сеанса.

Команда использует командлет **Get-PSSnapin** для получения объектов, представляющих оснастки. Оператор конвейера (|) отправляет результаты в командлет **Remove-PSSnapin** , который удаляет их из сеанса.
При этом поддерживаемые оснасткой поставщики и командлеты становятся недоступными в этом сеансе.

При передаче объектов в командлет **Remove-PSSnapin** имена объектов связываются с параметром *Name* , который принимает объекты из конвейера, у которых есть свойство **Name** .

### Пример 3. удаление оснасток с помощью имен

```
PS C:\> Remove-PSSnapin -Name *event*
```

Эта команда удаляет все оснастки Windows PowerShell с именами, которые содержат событие.

## PARAMETERS

### -Name
Задает имена оснасток Windows PowerShell для удаления из текущего сеанса.
Допускается использование подстановочных знаков (*).

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

### -PassThru
Возвращает объект, представляющий оснастку.
По умолчанию этот командлет не создает выходные данные.

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
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. PSSnapInInfo
Объект оснастки можно передать в этот командлет по конвейеру.

## Выходные данные

### Нет, System. Management. Automation. PSSnapInInfo
Этот командлет создает объект **System. Management. Automation. PSSnapInInfo** , представляющий оснастку, если указан параметр *PassThru* .
По умолчанию **Remove-PSSnapin** не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

* Командлет **Remove-PSSnapin** не проверяет версию Windows PowerShell перед удалением оснастки из сеанса. Если удалить оснастку не удается, отображается предупреждение и команда не выполняется.
* **Remove-PSSnapin** влияет только на текущий сеанс. Если команда Add-PSSnapin добавлена в профиль Windows PowerShell, то для удаления оснастки из будущих сеансов эту команду следует удалить. Для получения инструкций введите `Get-Help about_Profiles` .

## Связанные ссылки

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)
