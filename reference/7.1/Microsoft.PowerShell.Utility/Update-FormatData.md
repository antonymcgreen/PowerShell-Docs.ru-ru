---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-formatdata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-FormatData
ms.openlocfilehash: 8e4f9e82674baa90b8c7242921e4838f7470a85a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229442"
---
# Update-FormatData

## Краткий обзор
Обновляет данные форматирования в текущем сеансе.

## SYNTAX

```
Update-FormatData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Update-FormatData`Командлет перезагружает данные форматирования из файлов форматирования в текущий сеанс. Этот командлет позволяет обновлять данные форматирования без перезапуска PowerShell.

Без параметров `Update-FormatData` перегружает загруженные ранее файлы форматирования.
`Update-FormatData`Для добавления новых файлов форматирования в сеанс можно использовать параметры.

Файлы форматирования — это текстовые файлы в формате XML с `format.ps1xml` расширением имени файла. Данные форматирования в этих файлах определяют способ отображения объектов Microsoft .NET Framework в рамках сеанса.

При запуске PowerShell загружает данные формата из исходного кода PowerShell. Однако можно создать пользовательские format.ps1XML-файлы для обновления форматирования в текущем сеансе. Можно использовать `Update-FormatData` для повторной загрузки данных форматирования в текущий сеанс без перезапуска PowerShell. Это полезно в том случае, если вы добавили или изменили файл форматирования, но не хотите прерывать сеанс.

Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## Примеры

### Пример 1. Перезагрузка ранее загруженных файлов форматирования

```powershell
Update-FormatData
```

Эта команда перезагружает файлы форматирования, которые она ранее загрузила.

### Пример 2. Перезагрузка файлов форматирования и файлов форматирования трассировки и журнала

```powershell
Update-FormatData -AppendPath "trace.format.ps1xml, log.format.ps1xml"
```

Эта команда перезагружает в сеанс файлы форматирования, включая два новых файла: Trace.format.ps1xml и Log.format.ps1xml.

Поскольку в команде используется параметр **AppendPath** , данные форматирования в новых файлах загружаются после форматирования данных из встроенных файлов.

Используется параметр **AppendPath** , так как новые файлы содержат данные форматирования для объектов, на которые нет ссылок во встроенных файлах.

### Пример 3. изменение файла форматирования и его повторная загрузка

```powershell
Update-FormatData -PrependPath "c:\test\NewFiles.format.ps1xml"

# Edit the NewFiles.format.ps1 file.

Update-FormatData
```

В этом примере показано, как перезагрузить файл форматирования после его изменения.

Первая команда добавляет в сеанс файл NewFiles.format.ps1xml. Он использует параметр **препендпас** , поскольку файл содержит данные форматирования для объектов, на которые имеются ссылки во встроенных файлах.

После добавления XML-файла NewFiles.format.ps1и его тестирования в этих сеансах автор редактирует файл.

Вторая команда использует `Update-FormatData` командлет для повторной загрузки файлов форматирования. Так как XML-файл NewFiles.format.ps1был ранее загружен, `Update-FormatData` автоматически перезагружает его без использования параметров.

## PARAMETERS

### -AppendPath

Указывает файлы форматирования, которые этот командлет добавляет к сеансу. Файлы загружаются после того, как PowerShell загружает встроенные файлы форматирования.

При форматировании объектов .NET PowerShell использует первое определение форматирования, найденное для каждого типа .NET. При использовании параметра **AppendPath** PowerShell выполняет поиск данных из встроенных файлов до того, как он встречает добавляемые данные форматирования.

Используйте этот параметр для добавления файла, форматирующего объект .NET, на который нет ссылок во встроенных файлах форматирования.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrependPath

Указывает файлы форматирования, которые этот командлет добавляет к сеансу. Файлы загружаются перед тем, как PowerShell загружает встроенные файлы форматирования.

При форматировании объектов .NET PowerShell использует первое определение форматирования, найденное для каждого типа .NET. При использовании параметра **Препендпас** PowerShell ищет данные из добавляемых файлов перед тем, как обнаруживает данные форматирования из встроенных файлов.

Используйте этот параметр для добавления файла, форматирующего объект .NET, на который также есть ссылки во встроенных файлах форматирования.

```yaml
Type: System.String[]
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

### System.String

Строку, содержащую путь к добавлению, можно передать в `Update-FormatData` .

## Выходные данные

### Нет

Этот командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

- `Update-FormatData` также обновляет данные форматирования для команд в сеансе, импортированных из модулей. При изменении файла форматирования для модуля можно выполнить `Update-FormatData` команду, чтобы обновить данные форматирования для импортированных команд. Импортировать модуль снова не требуется.

## Связанные ссылки

[Get-FormatData;](Get-FormatData.md)

[Export-FormatData](Export-FormatData.md)
