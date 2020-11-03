---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: PowerShell, командлет, Markdown
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: 9f070819491b87b02868dffdfbe25bf5d72ecab8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229142"
---
# ConvertFrom-Markdown

## Краткий обзор
Преобразование содержимого строки или файла в объект **маркдовнинфо** .

## SYNTAX

### Паспарамсет (по умолчанию)

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### литералпарамсет

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### инпутобжпарамсет

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## DESCRIPTION

Этот командлет Преобразует указанное содержимое в **маркдовнинфо**. При указании пути к файлу для параметра **path** содержимое файла преобразуется. Выходной объект имеет три свойства:

- Свойство **Token** имеет дерево абстрактного синтаксиса (AST) преобразованного объекта
- Свойство **HTML** имеет преобразование HTML для указанных входных данных
- Свойство **VT100EncodedString** имеет преобразованную строку с escape-последовательностями ANSI (VT100), если был указан параметр **AsVT100EncodedString**

Этот командлет появился в PowerShell 6,1.

## Примеры

### Пример 1. Преобразование файла, содержащего Markdown-содержимое, в HTML

```powershell
ConvertFrom-Markdown -Path .\README.md
```

Возвращается объект **маркдовнинфо** . Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла. Свойство **HTML** имеет преобразованное в HTML содержимое `README.md` файла.

### Пример 2. Преобразование файла, содержащего содержимое Markdown, в строку в кодировке VT100

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

Возвращается объект **маркдовнинфо** . Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла. Свойство **VT100EncodedString** содержит преобразованное в кодировку VT100 строковое содержимое `README.md` файла.

### Пример 3. преобразование входного объекта, содержащего Markdown содержимое, в строку в кодировке VT100

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

Возвращается объект **маркдовнинфо** . Объект **FileInfo** из `Get-Item` преобразуется в строку в кодировке VT100. Свойство **tokens** содержит AST преобразованного содержимого `README.md` файла. Свойство **VT100EncodedString** содержит преобразованное в кодировку VT100 строковое содержимое `README.md` файла.

### Пример 4. Преобразование строки, содержащей содержимое Markdown, в строку в кодировке VT100

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

Возвращается объект **маркдовнинфо** . Указанная строка `**Bold text**` преобразуется в строку в кодировке VT100 и доступна в свойстве **VT100EncodedString** .

## PARAMETERS

### -AsVT100EncodedString

Указывает, следует ли кодировать выходные данные как строку с escape-кодами VT100.

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

### -InputObject

Задает объект для преобразования. Если объект типа **System. String** указан, строка преобразуется. При указании объекта типа **System. IO. FileInfo** содержимое файла, указанного в объекте, преобразуется. Объекты любого другого типа приводят к ошибке.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к файлу для преобразования.

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к файлу для преобразования.

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

## Выходные данные

### Microsoft. PowerShell. Маркдовнрендер. Маркдовнинфо

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Средство синтаксического анализа Markdown](https://github.com/lunet-io/markdig)

[Escape-код ANSI](https://wikipedia.org/wiki/ANSI_escape_code)

