---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: 4c1c6712966d78f9af4f0c1ff181bf1869c01eea
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233150"
---
# Set-PSReadLineOption

## Краткий обзор
Настройка поведения редактирования командной строки в **PSReadLine** .

## Синтаксис

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-Colors <Hashtable>] [-PredictionSource <PredictionSource>]
 [<CommonParameters>]
```

## Описание

`Set-PSReadLineOption`Командлет настраивает поведение модуля **PSReadLine** при редактировании командной строки. Чтобы просмотреть параметры **PSReadLine** , используйте `Get-PSReadLineOption` .

## Примеры

### Пример 1. Задание цветов переднего плана и фона

В этом примере задается **PSReadLine** для вывода маркера **комментария** с зеленым текстом переднего плана на сером фоне. В escape-последовательности, используемой в примере, **32** представляет цвет переднего плана, а **47** — цвет фона.

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

Можно выбрать только цвет текста переднего плана. Например, светло-зеленый цвет текста для маркера **комментария** : ``"Comment"="`e[92m"`` .

### Пример 2. Задание стиля колокольчика

В этом примере **PSReadLine** будет отвечать на ошибки или условия, требующие вмешательства пользователя.
**Беллстиле** настроен на вывод звукового сигнала с частотой 1221 гц для 60 мс.

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> Эта функция может не работать на всех узлах на платформах.

### Пример 3. Настройка нескольких параметров

`Set-PSReadLineOption` может задавать несколько параметров с помощью хэш-таблицы.

```powershell
$PSReadLineOptions = @{
    EditMode = "Emacs"
    HistoryNoDuplicates = $true
    HistorySearchCursorMovesToEnd = $true
    Colors = @{
        "Command" = "#8181f7"
    }
}
Set-PSReadLineOption @PSReadLineOptions
```

`$PSReadLineOptions`Хэш-таблица задает ключи и значения. `Set-PSReadLineOption` использует ключи и значения с `@PSReadLineOptions` для обновления параметров **PSReadLine** .

Ключи и значения, введенные в поле Имя хэш-таблицы, можно просмотреть `$PSReadLineOptions` в командной строке PowerShell.

### Пример 4. Задание нескольких параметров цвета

В этом примере показано, как задать более одного значения цвета в одной команде.

```powershell
Set-PSReadLineOption -Colors @{
  Command            = 'Magenta'
  Number             = 'DarkGray'
  Member             = 'DarkGray'
  Operator           = 'DarkGray'
  Type               = 'DarkGray'
  Variable           = 'DarkGreen'
  Parameter          = 'DarkGreen'
  ContinuationPrompt = 'DarkGray'
  Default            = 'DarkGray'
}
```

### Пример 5. Задание цветовых значений для нескольких типов

В этом примере показаны три разных метода настройки цвета маркеров, отображаемых в **PSReadLine** .

```powershell
Set-PSReadLineOption -Colors @{
 # Use a ConsoleColor enum
 "Error" = [ConsoleColor]::DarkRed

 # 24 bit color escape sequence
 "String" = "$([char]0x1b)[38;5;100m"

 # RGB value
 "Command" = "#8181f7"
}
```

### Пример 6. Использование Вимодечанжехандлер для вывода изменений в режиме VI

В этом примере выдается изменение курсора VT в ответ на изменение режима **VI** .

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "`e[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "`e[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

Функция **онвимодечанже** задает параметры курсора для режимов **VI** : INSERT и Command.
**Вимодечанжехандлер** использует `Function:` поставщик для ссылки на **онвимодечанже** в качестве объекта блока скрипта.

Дополнительные сведения см. в разделе [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).

## Параметры

### -Аддтохисторихандлер

Указывает блок **сценария** , который определяет, какие команды добавляются в журнал **PSReadLine** .

**ScriptBlock** получает командную строку в качестве входных данных. Если блок **ScriptBlock** возвращает значение `$True` , Командная строка добавляется в журнал.

```yaml
Type: System.Func`2[System.String,System.Object]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ансиескапетимеаут

Этот параметр характерен для Windows, если входные данные перенаправляются, например при выполнении в `tmux` или `screen` .

При использовании перенаправления входных данных в Windows многие ключи отправляются в виде последовательности символов, начиная с escape-символа. Невозможно отличить один escape-символ, за которым следует больше символов, и допустимую escape-последовательность.

Предполагается, что терминал может отправить символы быстрее, чем пользовательские типы. **PSReadLine** ждет этого времени ожидания, прежде чем завершать его получением полной escape-последовательности.

Если при вводе текста отображаются случайные или непредвиденные символы, можно настроить это время ожидания.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Беллстиле

Указывает, как **PSReadLine** реагирует на различные ошибочные и неоднозначные условия.

Допустимы следующие значения.

- **Звук** : короткий звуковой сигнал.
- **Визуальный** элемент: краткие текстовые Flash.
- **Нет** : Отзывы отсутствуют.

```yaml
Type: Microsoft.PowerShell.BellStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Audible
Accept pipeline input: False
Accept wildcard characters: False
```

### — Цвета

Параметр **Colors** указывает различные цвета, используемые **PSReadLine** .

Аргумент — это хэш-таблица, в которой ключи указывают, какой элемент и какие значения определяют цвет.
Дополнительные сведения см. в разделе [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).

Цвета могут быть либо значением из **консолеколор** , `[ConsoleColor]::Red` либо допустимой escape-последовательностью ANSI. Допустимые escape-последовательности зависят от терминала. В PowerShell 5,0 пример escape-последовательности для красного текста — `$([char]0x1b)[91m` . В PowerShell 6 и более поздних версиях одна и та же escape-последовательность имеет значение `` `e[91m`` . Можно указать другие escape-последовательности, в том числе следующие типы:

- цвет 256
- 24-разрядный цвет
- Передний план, фон или оба
- Инверсия, полужирный

Дополнительные сведения о кодах цветов ANSI см. в статье [escape-код ANSI](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) в Википедии.

К допустимым ключам относятся:

- **Континуатионпромпт** : цвет запроса продолжения.
- **Выделение** : цвет выделения. Например, соответствующий текст при поиске в журнале.
- **Ошибка** : цвет ошибки. Например, в командной строке.
- **Выделение** : цвет для выделения выбранного или выделенного текста в меню.
- **По умолчанию** : цвет токена по умолчанию.
- **Комментарий** : цвет маркера комментария.
- **Ключевое слово** : цвет маркера ключевого слова.
- **String** : цвет маркера строки.
- **Оператор** : цвет маркера оператора.
- **Переменная** : цвет маркера переменной.
- **Команда** : цвет маркера команды.
- **Параметр** : цвет маркера параметра.
- **Тип** : цвет маркера типа.
- **Число** : цвет маркера номера.
- **Member** : цвет маркера имени элемента.
- **Инлинепредиктион** : цвет встроенного представления прогнозного предложения.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Коммандвалидатионхандлер

Задает блок **ScriptBlock** , вызываемый из **валидатеандакцептлине** . При возникновении исключения проверка завершается неудачей и сообщается об ошибке.

Перед созданием исключения обработчик проверки может поместить курсор в точку ошибки, чтобы упростить ее исправление. Обработчик проверки может также изменить командную строку, например, чтобы исправить распространенные типографские ошибки.

**Валидатеандакцептлине** используется, чтобы избежать переполнения журнала с помощью команд, которые не могут работать.

```yaml
Type: System.Action`1[System.Management.Automation.Language.CommandAst]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Комплетионкуеритемс

Указывает максимальное количество элементов завершения, отображаемых без запроса.

Если число отображаемых элементов больше этого значения, **PSReadLine** запрашивает **Да/нет** перед отображением элементов завершения.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Континуатионпромпт

Задает строку, отображаемую в начале последующих строк при вводе многострочного ввода. По умолчанию это два знака «больше» ( `>>` ). Допустима пустая строка.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >>
Accept pipeline input: False
Accept wildcard characters: False
```

### -Дингдуратион

Указывает длительность звукового сигнала, когда для **беллстиле** задано значение " **звук** ".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50ms
Accept pipeline input: False
Accept wildcard characters: False
```

### -Дингтоне

Задает тон в герцах (Гц) звукового сигнала, если для **беллстиле** задано значение " **звук** ".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1221
Accept pipeline input: False
Accept wildcard characters: False
```

### -EditMode

Задает режим редактирования командной строки. Использование этого параметра приводит к сбросу всех привязок к ключам, установленных `Set-PSReadLineKeyHandler` .

Допустимы следующие значения.

- **Windows** : привязки клавиш имитируют PowerShell, cmd и Visual Studio.
- **Emacs** : привязки клавиш имитируют bash или Emacs.
- **VI** : привязки ключей имитируют VI.

Используйте `Get-PSReadLineKeyHandler` , чтобы просмотреть сочетания клавиш для текущего настроенного **EditMode** .

```yaml
Type: Microsoft.PowerShell.EditMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### -Екстрапромптлинекаунт

Указывает количество дополнительных строк.

Если запрос охватывает более одной строки, укажите значение для этого параметра. Используйте этот параметр, если требуется, чтобы дополнительные строки были доступны, когда **PSReadLine** отображает запрос после отображения некоторых выходных данных. Например, **PSReadLine** возвращает список завершений.

Этот параметр требуется меньше, чем в предыдущих версиях **PSReadLine** , но полезен при `InvokePrompt` использовании функции.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Хисторинодупликатес

Этот параметр управляет поведением отзыва. Дубликаты команд по-прежнему добавляются в файл журнала.
Если этот параметр задан, то при отзыве команд появляется только самый последний вызов. Повторяющиеся команды добавляются в журнал для сохранения порядка во время отзыва. Однако обычно не требуется, чтобы команда была встречаться несколько раз при отзыве или поиске по журналу.

По умолчанию свойству **хисторинодупликатес** глобального объекта **псконсолереадлинеоптионс** присваивается значение `True` . При использовании этого **переключатель** свойству присваивается значение `True` . Чтобы изменить значение свойства, необходимо указать значение **переключатель** следующим образом: `-HistoryNoDuplicates:$False` .

С помощью следующей команды можно задать значение свойства напрямую:

`(Get-PSReadLineOption).HistoryNoDuplicates = $False`

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

### -Хисторисавепас

Указывает путь к файлу, в котором сохранен журнал. Компьютеры под управлением Windows или платформы, отличной от Windows, сохраняют файл в разных расположениях. Имя файла хранится в переменной `$($host.Name)_history.txt` , например `ConsoleHost_history.txt` .

Если этот параметр не используется, путь по умолчанию выглядит следующим образом:

**Windows**

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

**не Windows**

`$env:XDG_DATA_HOME/powershell/PSReadLine\$($host.Name)_history.txt`

`$env:HOME/.local/share/powershell/PSReadLine\$($host.Name)_history.txt`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A file named $($host.Name)_history.txt in $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine on Windows and $env:XDG_DATA_HOME/powershell/PSReadLine or $env:HOME/.local/share/powershell/PSReadLine on non-Windows platforms
Accept pipeline input: False
Accept wildcard characters: False
```

### -Хисторисавестиле

Указывает, как **PSReadLine** сохраняет журнал.

Допустимы следующие значения:

- **Савеинкременталли** : сохранение журнала после выполнения каждой команды и совместного использования нескольких экземпляров PowerShell.
- **Савеатексит** : Добавление файла журнала при выходе из PowerShell.
- **Савеносинг** : не используйте файл журнала.

```yaml
Type: Microsoft.PowerShell.HistorySaveStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SaveIncrementally
Accept pipeline input: False
Accept wildcard characters: False
```

### -Хисторисеарчкасесенситиве

Указывает, что при поиске в журнале учитывается регистр в таких функциях, как **реверсесеарчхистори** или **хисторисеарчбакквард** .

По умолчанию свойству **хисторисеарчкасесенситиве** глобального объекта **псконсолереадлинеоптионс** присваивается значение `False` . При использовании этого **переключатель** свойству присваивается значение `True` . Чтобы изменить значение свойства обратно, необходимо указать значение **переключатель** следующим образом: `-HistorySearchCaseSensitive:$False` .

С помощью следующей команды можно задать значение свойства напрямую:

`(Get-PSReadLineOption).HistorySearchCaseSensitive = $False`

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

### -Хисторисеарчкурсормовестоенд

Указывает, что курсор перемещается в конец команд, загруженных из журнала с помощью поиска.
Если для этого параметра задано значение `$False` , курсор остается в том положении, в котором он находился при нажатии стрелок вверх или вниз.

По умолчанию свойству **хисторисеарчкурсормовестоенд** глобального объекта **псконсолереадлинеоптионс** присваивается значение `False` . Используя этот **переключатель** , задайте для свойства значение `True` . Чтобы изменить значение свойства обратно, необходимо указать значение **переключатель** следующим образом: `-HistorySearchCursorMovesToEnd:$False` .

С помощью следующей команды можно задать значение свойства напрямую:

`(Get-PSReadLineOption).HistorySearchCursorMovesToEnd = $False`

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

### -Максимумхисторикаунт

Указывает максимальное количество команд для сохранения в журнале **PSReadLine** .

Журнал **PSReadLine** отличается от журнала PowerShell.

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

### -Максимумкиллрингкаунт

Указывает максимальное число элементов, хранящихся в кольцевом буфере.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Предиктионсаурце

Указывает источник PSReadLine для получения прогнозных предложений.

Допустимые значения:

- **Нет** : отключить функцию прогнозного предложения
- **Журнал** : получение прогнозных предложений только из журнала

```yaml
Type: PredictionSource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Промпттекст

При возникновении ошибки синтаксического анализа **PSReadLine** изменяет часть красной строки. **PSReadLine** анализирует функцию Prompt, чтобы определить, как изменить только цвет части запроса. Этот анализ не 100% надежности.

Используйте этот параметр, если **PSReadLine** изменяет запрос непредвиденным образом. Включите все конечные пробелы.

Например, если функция Prompt выглядит как в следующем примере:

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

Затем задайте:

`Set-PSReadLineOption -PromptText "# "`

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >
Accept pipeline input: False
Accept wildcard characters: False
```

### -Шовтултипс

При отображении возможных завершений подсказки отображаются в списке завершений.

Этот параметр по умолчанию включен. Этот параметр не включен по умолчанию в предыдущих версиях **PSReadLine** . Чтобы отключить этот параметр, установите для этого параметра значение `$False` .

По умолчанию свойству **шовтултипс** глобального объекта **псконсолереадлинеоптионс** присваивается значение `True` . При использовании этого **переключатель** свойству присваивается значение `True` . Чтобы изменить значение свойства, необходимо указать значение **переключатель** следующим образом: `-ShowToolTips:$False` .

С помощью следующей команды можно задать значение свойства напрямую:

`(Get-PSReadLineOption).ShowToolTips = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Вимодечанжехандлер

Если для **вимодеиндикатор** задано значение `Script` , то указанный блок скрипта будет вызываться каждый раз при изменении режима. Блок скрипта предоставляет один аргумент типа `ViMode` .

Этот параметр появился в PowerShell 7.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Вимодеиндикатор

Этот параметр задает визуальное обозначение для текущего режима **VI** . Режим вставки или режим команд.

Допустимы следующие значения.

- **Нет** : нет никаких свидетельств.
- **Prompt** : запрос изменит цвет.
- **Cursor** : размер курсора меняется.
- **Скрипт** : печатается указанный пользователем текст.

```yaml
Type: Microsoft.PowerShell.ViModeStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Вордделимитерс

Задает символы, разделяющие слова для таких функций, как **форвардворд** или **киллворд** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"–—―
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

Вы не можете передать объекты в `Set-PSReadLineOption.`

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## Примечания

## Связанные ссылки

[about_PSReadLine](./About/about_PSReadLine.md)

[Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)

[Get-PSReadLineOption](Get-PSReadLineOption.md)

[Remove-PSReadLineKeyHandler](Remove-PSReadLineKeyHandler.md)

[Set-PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)
