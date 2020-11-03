---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "93230681"
---
# Get-Clipboard

## Краткий обзор
Возвращает текущую запись в буфере обмена Windows.

## SYNTAX

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

`Get-Clipboard`Командлет возвращает текущую запись в буфере обмена Windows. Несколько строк текста возвращаются в виде массива строк, аналогичного `Get-Content` .

## Примеры

### Пример 1. получение содержимого буфера обмена и его отображение в командной строке

В этом примере мы щелкнули правой кнопкой мыши изображение в браузере и выбрали действие **копирования** . Следующая команда отображает ссылку в виде URL-адреса изображения, хранящегося в буфере обмена.

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### Пример 2. получение содержимого буфера обмена в определенном формате

В этом примере мы скопировали файлы в буфер обмена в Windows Експлорерби, выбрав их и нажав клавиши <kbd>CTRL + C</kbd>. С помощью следующей команды можно получить доступ к содержимому буфера обмена в виде списка файлов:

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## PARAMETERS

### -Format

Задает тип или формат буфера обмена. Допустимые значения для этого параметра:

- Текст
- филедроплист
- Образ —
- Аудио

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RAW

Возвращает все содержимое буфера обмена. Многострочный текст возвращается в виде одной многострочной строки, а не массива строк.

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

### -Текстформаттипе

Задает тип формата текстовых данных буфера обмена. Допустимые значения для этого параметра:

- Текст
- уникодетекст
- RTF
- Html
- коммасепаратедвалуе

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### System. String, System. IO. FileInfo, System. IO. Stream, System. Drawing. Image

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Set-Clipboard](Set-Clipboard.md)
