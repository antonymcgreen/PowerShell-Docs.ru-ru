---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: 09e962d96bffc1c890a4532502e1f3461180caae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229054"
---
# ConvertTo-Xml

## Краткий обзор
Создает XML-представление объекта.

## SYNTAX

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## DESCRIPTION

`ConvertTo-Xml`Командлет создает [основанное на XML](/dotnet/api/system.xml.xmldocument) представление одного или нескольких объектов .NET. Чтобы использовать этот командлет, необходимо передать один или несколько объектов в командлет или использовать параметр **InputObject** для указания объекта.

При передаче нескольких объектов `ConvertTo-Xml` или использовании параметра **InputObject** для отправки нескольких объектов `ConvertTo-Xml` возвращает отдельный XML-документ в памяти, включающий представления всех объектов.

Этот командлет аналогичен [Export-Clixml](./Export-Clixml.md) , за исключением того, что `Export-Clixml` сохраняет результирующий XML-файл в [Common Language Infrastructureном XML-файле (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) , который может быть повторно импортирован как объекты с помощью командлета [Import-Clixml](./Import-Clixml.md). `ConvertTo-Xml` Возвращает представление XML-документа в памяти, поэтому вы можете продолжить его обработку в PowerShell. `ConvertTo-Xml` не имеет параметра для преобразования объектов в XML CLI.

## Примеры

### Пример 1. Преобразование даты в XML

```
PS C:\> Get-Date | ConvertTo-Xml
```

Эта команда преобразует текущую дату (объект **DateTime** ) в XML.

### Пример 2. Преобразование процессов в XML

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

Эта команда преобразует объекты процессов, представляющие все процессы на компьютере, в XML-документ. Объекты расширяются до трех уровней.

## PARAMETERS

### — Как

Определяет формат вывода.
Допустимые значения для этого параметра:

- Строка.
возвращает отдельную строку;
- Поток.
возвращает массив строк;
- Документ.
Возвращает объект **XmlDocument** .

Значение по умолчанию — Document.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Depth

Указывает, сколько уровней вложенных объектов включается в XML-представление. Значение по умолчанию — 1.

Например, если свойства объекта также содержат объекты, то для сохранения XML-представления свойств этих вложенных объектов необходимо указать глубину, равную 2.

Значение по умолчанию можно переопределить для типа объекта в файлах Types.ps1xml. Дополнительные сведения см. в разделе about_Types.ps1xml.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает объект для преобразования. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты. Также можно передать объекты в **ConvertTo-XML** .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoTypeInformation

Исключает атрибут Type из узлов объектов.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Любой объект можно передать по конвейеру в **ConvertTo-XML** .

## Выходные данные

### System. String или System.Xml.Xmlдокумент

Значение параметра *as* определяет тип объекта, возвращаемого **ConvertTo-XML** .

## ПРИМЕЧАНИЯ

## Связанные ссылки

[ConvertTo-Csv](ConvertTo-Csv.md)

[ConvertTo-Html](ConvertTo-Html.md)

[Export-Clixml](Export-Clixml.md)

[Get-Дата](Get-Date.md)

[Import-Clixml](Import-Clixml.md)
