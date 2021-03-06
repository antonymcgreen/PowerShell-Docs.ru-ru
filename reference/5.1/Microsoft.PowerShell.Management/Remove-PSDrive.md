---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: 4b9b466be3d52877056b948e4cc373991784416a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227934"
---
# Remove-PSDrive

## Краткий обзор
Удаляет временные диски PowerShell и отключает сопоставленные сетевые диски.

## SYNTAX

### Имя (по умолчанию)

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### литералнаме

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

`Remove-PSDrive`Командлет удаляет временные диски PowerShell, созданные с помощью `New-PSDrive` командлета.

Начиная с Windows PowerShell 3,0, `Remove-PSDrive` также отключает подключенные сетевые диски, включая, но не ограниченные, дисками, созданными с помощью `Persist` параметра `New-PSDrive` .

`Remove-PSDrive` невозможно удалить физические или логические диски Windows.

Начиная с Windows PowerShell 3,0, когда к компьютеру подключен внешний диск, PowerShell автоматически добавляет PSDrive в файловую систему, представляющую новый диск.
Перезапускать PowerShell не требуется.
Аналогично, когда внешний диск отключается от компьютера, PowerShell автоматически удаляет PSDrive, представляющий удаленный диск.

## Примеры

### Пример 1. Удаление диска файловой системы

Эта команда удаляет временный диск файловой системы с именем smp.

```powershell
Remove-PSDrive -Name smp
```

### Пример 2. удаление сопоставленных сетевых дисков

Эта команда использует `Remove-PSDrive` для отключения подключенных сетевых дисков X: и S:.

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## PARAMETERS

### -Force

Удаляет текущий диск PowerShell.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Литералнаме

Задает имя диска.

Значение параметра **LiteralName** используется именно так, как оно введено.
Никакие символы не интерпретируются как знаки подстановки.
Если в имени есть escape-символы, заключите их в одиночные кавычки (').
Одинарные кавычки предписывает PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает имена дисков, которые нужно удалить.
Не ставьте двоеточие (:) после имени диска.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PSProvider

Указывает массив объектов **psprovider** .
Этот командлет удаляет и отключает все диски, связанные с указанным поставщиком PowerShell.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope

Указывает область для диска.
Допустимые значения для этого параметра: Global, Local и script или Number, относящихся к текущей области. Области с номером 0 по числу областей. Текущий номер области равен 0, а его родительский элемент — 1.
Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseTransaction

Включает команду в активную транзакцию.
Этот параметр доступен только при выполнении транзакции.
Дополнительные сведения см. в разделе about_Transactions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Management.Automation.PSDРивеинфо

Вы можете передать в командлет объект Drive, например один из `Get-PSDrive` командлетов `Remove-PSDrive` .

## Выходные данные

### Нет

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

- `Remove-PSDrive`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком PowerShell. Чтобы получить список поставщиков в сеансе, используйте `Get-PSProvider` командлет. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[Get-PSDrive](Get-PSDrive.md)

[New-PSDrive](New-PSDrive.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
