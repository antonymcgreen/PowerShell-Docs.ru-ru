---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Set-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: e7e70637afcf53f84c719b489575f5267f9048b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226573"
---
# Set-MarkdownOption

## Краткий обзор
Задает цвета и стили, используемые для отрисовки содержимого Markdown в консоли.

## SYNTAX

### Индивидуалсеттинг (по умолчанию)

```
Set-MarkdownOption [-Header1Color <String>] [-Header2Color <String>] [-Header3Color <String>]
 [-Header4Color <String>] [-Header5Color <String>] [-Header6Color <String>] [-Code <String>]
 [-ImageAltTextForegroundColor <String>] [-LinkForegroundColor <String>]
 [-ItalicsForegroundColor <String>] [-BoldForegroundColor <String>] [-PassThru]
 [<CommonParameters>]
```

### Тема

```
Set-MarkdownOption [-PassThru] -Theme <String> [<CommonParameters>]
```

### InputObject

```
Set-MarkdownOption [-PassThru] [-InputObject] <PSObject> [<CommonParameters>]
```

## DESCRIPTION

Задает цвета и стили, используемые для отрисовки содержимого Markdown в консоли. Эти стили определяются с помощью escape-кодов ANSI, которые изменяют цвет и стиль отображаемого текста Markdown.

Дополнительные сведения о Markdown см. на веб-сайте [коммонмарк](https://commonmark.org/) .

> [!NOTE]
> Строковые значения, используемые в параметрах, — это символы, которые следуют за **escape** -символом ( `[char]0x1B` ) для управляющей последовательности ANSI. Не включайте **escape** -символ в строку. Дополнительные сведения о работе с управляющими escape-кодами ANSI см. в разделе [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).

## Примеры

### Пример 1. Переход к светлой теме

В этом примере выбирается **светло** -тема и отображается новая конфигурация с помощью параметра **PassThru** .

```powershell
Set-MarkdownOption -Theme Light -PassThru
```

```Output
Header1         : [7m
Header2         : [4;33m
Header3         : [4;34m
Header4         : [4;35m
Header5         : [4;36m
Header6         : [4;30m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

### Пример 2. Настройка параметров цвета и стиля

В этом примере изменяется escape-код для заголовков Markdown. Конфигурация по умолчанию для заголовков отображает их в виде подчеркнутого текста различных цветов. Это изменение приводит к удалению стиля подчеркивания.

```powershell
$mdOptions = Get-MarkdownOption
$mdOptions.Header2 = '[93m'
$mdOptions.Header3 = '[94m'
$mdOptions.Header4 = '[95m'
$mdOptions.Header5 = '[96m'
$mdOptions.Header6 = '[97m'
Set-MarkdownOption -InputObject $mdOptions -PassThru
```

```Output
Header1         : [7m
Header2         : [93m
Header3         : [94m
Header4         : [95m
Header5         : [96m
Header6         : [97m
Code            : [48;2;155;155;155;38;2;30;30;31m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

## PARAMETERS

### -Болдфореграундколор

Задает цвет переднего плана для отрисовки полужирного Markdown текста.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Code

Задает цвет для отрисовки блоков кода и диапазонов в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header1Color

Задает цвет для отрисовки блоков Header1 в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header2Color

Задает цвет для отрисовки блоков Header2 в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header3Color

Задает цвет для отрисовки блоков Header3 в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header4Color

Задает цвет для отрисовки блоков Header4 в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header5Color

Задает цвет для отрисовки блоков Header5 в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header6Color

Задает цвет для отрисовки блоков Header6 в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Имажеалттекстфореграундколор

Задает цвет переднего плана для отрисовки альтернативного текста элемента изображения в Markdown тексте.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Объект **псмаркдовноптионинфо** , содержащий конфигурацию, которую необходимо задать.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Италиксфореграундколор

Задает цвет переднего плана для отрисовки курсивного начертания в тексте Markdown.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Линкфореграундколор

Задает цвет переднего плана для отрисовки гиперссылок в Markdown тексте.

```yaml
Type: System.String
Parameter Sets: IndividualSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Приводит к тому, что командлет выводит объект **псмаркдовноптионинфо** , содержащий новую конфигурацию.

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

### -Theme

Выбирает тему, содержащую предопределенные параметры цвета. Возможные значения: **темный** и **светлый**.

```yaml
Type: System.String
Parameter Sets: Theme
Aliases:
Accepted values: Dark, Light

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

## Выходные данные

### Microsoft. PowerShell. Маркдовнрендер. Псмаркдовноптионинфо

## ПРИМЕЧАНИЯ

Строковые значения, используемые для определения цвета и стиля, должны соответствовать регулярному выражению `^\[*[0-9;]*?m{1}` .

## Связанные ссылки

[Get-MarkdownOption](Get-MarkdownOption.md)

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

[Show-Markdown](Show-Markdown.md)

[ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)

[CommonMark](https://commonmark.org/)

