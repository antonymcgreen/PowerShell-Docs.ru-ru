---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: cac2c2bb8ce1f3a28c0d91c7503b3ac4d038ccad
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "99601093"
---
# <span data-ttu-id="ef9cd-102">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="ef9cd-102">Set-PSReadLineOption</span></span>

## <span data-ttu-id="ef9cd-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ef9cd-103">Synopsis</span></span>
<span data-ttu-id="ef9cd-104">Настройка поведения редактирования командной строки в **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-104">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

## <span data-ttu-id="ef9cd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef9cd-105">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func`2[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action`1[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-PredictionSource <PredictionSource>]
 [-PredictionViewStyle <PredictionViewStyle>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="ef9cd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ef9cd-106">Description</span></span>

<span data-ttu-id="ef9cd-107">`Set-PSReadLineOption`Командлет настраивает поведение модуля **PSReadLine** при редактировании командной строки.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-107">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="ef9cd-108">Чтобы просмотреть параметры **PSReadLine** , используйте `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-108">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="ef9cd-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="ef9cd-109">Examples</span></span>

### <span data-ttu-id="ef9cd-110">Пример 1. Задание цветов переднего плана и фона</span><span class="sxs-lookup"><span data-stu-id="ef9cd-110">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="ef9cd-111">В этом примере задается **PSReadLine** для вывода маркера **комментария** с зеленым текстом переднего плана на сером фоне.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-111">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="ef9cd-112">В escape-последовательности, используемой в примере, **32** представляет цвет переднего плана, а **47** — цвет фона.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-112">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

<span data-ttu-id="ef9cd-113">Можно выбрать только цвет текста переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-113">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="ef9cd-114">Например, светло-зеленый цвет текста для маркера **комментария** : ``"Comment"="`e[92m"`` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-114">For example, a bright green foreground text color for the **Comment** token: ``"Comment"="`e[92m"``.</span></span>

### <span data-ttu-id="ef9cd-115">Пример 2. Задание стиля колокольчика</span><span class="sxs-lookup"><span data-stu-id="ef9cd-115">Example 2: Set bell style</span></span>

<span data-ttu-id="ef9cd-116">В этом примере **PSReadLine** будет отвечать на ошибки или условия, требующие вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-116">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="ef9cd-117">**Беллстиле** настроен на вывод звукового сигнала с частотой 1221 гц для 60 мс.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-117">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="ef9cd-118">Эта функция может не работать на всех узлах на платформах.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-118">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="ef9cd-119">Пример 3. Настройка нескольких параметров</span><span class="sxs-lookup"><span data-stu-id="ef9cd-119">Example 3: Set multiple options</span></span>

<span data-ttu-id="ef9cd-120">`Set-PSReadLineOption` может задавать несколько параметров с помощью хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-120">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

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

<span data-ttu-id="ef9cd-121">`$PSReadLineOptions`Хэш-таблица задает ключи и значения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-121">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="ef9cd-122">`Set-PSReadLineOption` использует ключи и значения с `@PSReadLineOptions` для обновления параметров **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-122">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="ef9cd-123">Ключи и значения, введенные в поле Имя хэш-таблицы, можно просмотреть `$PSReadLineOptions` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-123">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="ef9cd-124">Пример 4. Задание нескольких параметров цвета</span><span class="sxs-lookup"><span data-stu-id="ef9cd-124">Example 4: Set multiple color options</span></span>

<span data-ttu-id="ef9cd-125">В этом примере показано, как задать более одного значения цвета в одной команде.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-125">This example shows how to set more than one color value in a single command.</span></span>

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

### <span data-ttu-id="ef9cd-126">Пример 5. Задание цветовых значений для нескольких типов</span><span class="sxs-lookup"><span data-stu-id="ef9cd-126">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="ef9cd-127">В этом примере показаны три разных метода настройки цвета маркеров, отображаемых в **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-127">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine**.</span></span>

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

### <span data-ttu-id="ef9cd-128">Пример 6. Использование Вимодечанжехандлер для вывода изменений в режиме VI</span><span class="sxs-lookup"><span data-stu-id="ef9cd-128">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="ef9cd-129">В этом примере выдается изменение курсора VT в ответ на изменение режима **VI** .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-129">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

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

<span data-ttu-id="ef9cd-130">Функция **онвимодечанже** задает параметры курсора для режимов **VI** : INSERT и Command.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-130">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="ef9cd-131">**Вимодечанжехандлер** использует `Function:` поставщик для ссылки на **онвимодечанже** в качестве объекта блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-131">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="ef9cd-132">Дополнительные сведения см. в разделе [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span><span class="sxs-lookup"><span data-stu-id="ef9cd-132">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="ef9cd-133">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef9cd-133">Parameters</span></span>

### <span data-ttu-id="ef9cd-134">-Аддтохисторихандлер</span><span class="sxs-lookup"><span data-stu-id="ef9cd-134">-AddToHistoryHandler</span></span>

<span data-ttu-id="ef9cd-135">Указывает блок **сценария** , который определяет, какие команды добавляются в журнал **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-135">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="ef9cd-136">**ScriptBlock** получает командную строку в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-136">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="ef9cd-137">Если блок **ScriptBlock** возвращает значение `$True` , Командная строка добавляется в журнал.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-137">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

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

### <span data-ttu-id="ef9cd-138">-Ансиескапетимеаут</span><span class="sxs-lookup"><span data-stu-id="ef9cd-138">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="ef9cd-139">Этот параметр характерен для Windows, если входные данные перенаправляются, например при выполнении в `tmux` или `screen` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-139">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="ef9cd-140">При использовании перенаправления входных данных в Windows многие ключи отправляются в виде последовательности символов, начиная с escape-символа.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-140">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="ef9cd-141">Невозможно отличить один escape-символ, за которым следует больше символов, и допустимую escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-141">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="ef9cd-142">Предполагается, что терминал может отправить символы быстрее, чем пользовательские типы.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-142">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="ef9cd-143">**PSReadLine** ждет этого времени ожидания, прежде чем завершать его получением полной escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-143">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="ef9cd-144">Если при вводе текста отображаются случайные или непредвиденные символы, можно настроить это время ожидания.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-144">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

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

### <span data-ttu-id="ef9cd-145">-Беллстиле</span><span class="sxs-lookup"><span data-stu-id="ef9cd-145">-BellStyle</span></span>

<span data-ttu-id="ef9cd-146">Указывает, как **PSReadLine** реагирует на различные ошибочные и неоднозначные условия.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-146">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="ef9cd-147">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-147">The valid values are as follows:</span></span>

- <span data-ttu-id="ef9cd-148">**Звук**: короткий звуковой сигнал.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-148">**Audible**: A short beep.</span></span>
- <span data-ttu-id="ef9cd-149">**Визуальный** элемент: краткие текстовые Flash.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-149">**Visual**: Text flashes briefly.</span></span>
- <span data-ttu-id="ef9cd-150">**Нет**: Отзывы отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-150">**None**: No feedback.</span></span>

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

### <span data-ttu-id="ef9cd-151">— Цвета</span><span class="sxs-lookup"><span data-stu-id="ef9cd-151">-Colors</span></span>

<span data-ttu-id="ef9cd-152">Параметр **Colors** указывает различные цвета, используемые **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-152">The **Colors** parameter specifies various colors used by **PSReadLine**.</span></span>

<span data-ttu-id="ef9cd-153">Аргумент — это хэш-таблица, в которой ключи указывают, какой элемент и какие значения определяют цвет.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-153">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="ef9cd-154">Дополнительные сведения см. в разделе [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="ef9cd-154">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="ef9cd-155">Цвета могут быть либо значением из **консолеколор**, `[ConsoleColor]::Red` либо допустимой escape-последовательностью ANSI.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-155">Colors can be either a value from **ConsoleColor**, for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="ef9cd-156">Допустимые escape-последовательности зависят от терминала.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-156">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="ef9cd-157">В PowerShell 5,0 пример escape-последовательности для красного текста — `$([char]0x1b)[91m` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-157">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="ef9cd-158">В PowerShell 6 и более поздних версиях одна и та же escape-последовательность имеет значение `` `e[91m`` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-158">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="ef9cd-159">Можно указать другие escape-последовательности, в том числе следующие типы:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-159">You can specify other escape sequences including the following types:</span></span>

<span data-ttu-id="ef9cd-160">Для поддержки настройки в PSReadLine 2.2.0 были добавлены два параметра цвета `ListView` :</span><span class="sxs-lookup"><span data-stu-id="ef9cd-160">Two color settings were added to support customization of the `ListView` in PSReadLine 2.2.0:</span></span>

- <span data-ttu-id="ef9cd-161">**Листпредиктионколор** — задает цвет начального `>` символа и конечного имени источника, например `[History]` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-161">**ListPredictionColor** - set color for the leading `>` character and the trailing source name, e.g. `[History]`.</span></span> <span data-ttu-id="ef9cd-162">По умолчанию используется в `DarkYellow` качестве цвета переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-162">By default, it uses `DarkYellow` as the foreground color.</span></span>
- <span data-ttu-id="ef9cd-163">**Листпредиктионселектедколор** — задает цвет, указывающий, что элемент списка выбран.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-163">**ListPredictionSelectedColor** - set color for indicating a list item is selected.</span></span> <span data-ttu-id="ef9cd-164">По умолчанию в `DarkBlack` качестве цвета фона используется.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-164">By default, it uses `DarkBlack` as the background color.</span></span>

- <span data-ttu-id="ef9cd-165">цвет 256</span><span class="sxs-lookup"><span data-stu-id="ef9cd-165">256 color</span></span>
- <span data-ttu-id="ef9cd-166">24-разрядный цвет</span><span class="sxs-lookup"><span data-stu-id="ef9cd-166">24-bit color</span></span>
- <span data-ttu-id="ef9cd-167">Передний план, фон или оба</span><span class="sxs-lookup"><span data-stu-id="ef9cd-167">Foreground, background, or both</span></span>
- <span data-ttu-id="ef9cd-168">Инверсия, полужирный</span><span class="sxs-lookup"><span data-stu-id="ef9cd-168">Inverse, bold</span></span>

<span data-ttu-id="ef9cd-169">Дополнительные сведения о кодах цветов ANSI см. в статье [escape-код ANSI](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-169">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="ef9cd-170">К допустимым ключам относятся:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-170">The valid keys include:</span></span>

- <span data-ttu-id="ef9cd-171">**Континуатионпромпт**: цвет запроса продолжения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-171">**ContinuationPrompt**: The color of the continuation prompt.</span></span>
- <span data-ttu-id="ef9cd-172">**Выделение**: цвет выделения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-172">**Emphasis**: The emphasis color.</span></span> <span data-ttu-id="ef9cd-173">Например, соответствующий текст при поиске в журнале.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-173">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="ef9cd-174">**Ошибка**: цвет ошибки.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-174">**Error**: The error color.</span></span> <span data-ttu-id="ef9cd-175">Например, в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-175">For example, in the prompt.</span></span>
- <span data-ttu-id="ef9cd-176">**Выделение**: цвет для выделения выбранного или выделенного текста в меню.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-176">**Selection**: The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="ef9cd-177">**По умолчанию**: цвет токена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-177">**Default**: The default token color.</span></span>
- <span data-ttu-id="ef9cd-178">**Комментарий**: цвет маркера комментария.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-178">**Comment**: The comment token color.</span></span>
- <span data-ttu-id="ef9cd-179">**Ключевое слово**: цвет маркера ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-179">**Keyword**: The keyword token color.</span></span>
- <span data-ttu-id="ef9cd-180">**String**: цвет маркера строки.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-180">**String**: The string token color.</span></span>
- <span data-ttu-id="ef9cd-181">**Оператор**: цвет маркера оператора.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-181">**Operator**: The operator token color.</span></span>
- <span data-ttu-id="ef9cd-182">**Переменная**: цвет маркера переменной.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-182">**Variable**: The variable token color.</span></span>
- <span data-ttu-id="ef9cd-183">**Команда**: цвет маркера команды.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-183">**Command**: The command token color.</span></span>
- <span data-ttu-id="ef9cd-184">**Параметр**: цвет маркера параметра.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-184">**Parameter**: The parameter token color.</span></span>
- <span data-ttu-id="ef9cd-185">**Тип**: цвет маркера типа.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-185">**Type**: The type token color.</span></span>
- <span data-ttu-id="ef9cd-186">**Число**: цвет маркера номера.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-186">**Number**: The number token color.</span></span>
- <span data-ttu-id="ef9cd-187">**Member**: цвет маркера имени элемента.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-187">**Member**: The member name token color.</span></span>
- <span data-ttu-id="ef9cd-188">**Инлинепредиктион**: цвет встроенного представления прогнозного предложения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-188">**InlinePrediction**: The color for the inline view of the predictive suggestion.</span></span>

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

### <span data-ttu-id="ef9cd-189">-Коммандвалидатионхандлер</span><span class="sxs-lookup"><span data-stu-id="ef9cd-189">-CommandValidationHandler</span></span>

<span data-ttu-id="ef9cd-190">Задает блок **ScriptBlock** , вызываемый из **валидатеандакцептлине**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-190">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine**.</span></span> <span data-ttu-id="ef9cd-191">При возникновении исключения проверка завершается неудачей и сообщается об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-191">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="ef9cd-192">Перед созданием исключения обработчик проверки может поместить курсор в точку ошибки, чтобы упростить ее исправление.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-192">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="ef9cd-193">Обработчик проверки может также изменить командную строку, например, чтобы исправить распространенные типографские ошибки.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-193">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="ef9cd-194">**Валидатеандакцептлине** используется, чтобы избежать переполнения журнала с помощью команд, которые не могут работать.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-194">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

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

### <span data-ttu-id="ef9cd-195">-Комплетионкуеритемс</span><span class="sxs-lookup"><span data-stu-id="ef9cd-195">-CompletionQueryItems</span></span>

<span data-ttu-id="ef9cd-196">Указывает максимальное количество элементов завершения, отображаемых без запроса.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-196">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="ef9cd-197">Если число отображаемых элементов больше этого значения, **PSReadLine** запрашивает **Да/нет** перед отображением элементов завершения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-197">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

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

### <span data-ttu-id="ef9cd-198">-Континуатионпромпт</span><span class="sxs-lookup"><span data-stu-id="ef9cd-198">-ContinuationPrompt</span></span>

<span data-ttu-id="ef9cd-199">Задает строку, отображаемую в начале последующих строк при вводе многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-199">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="ef9cd-200">По умолчанию это два знака «больше» ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="ef9cd-200">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="ef9cd-201">Допустима пустая строка.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-201">An empty string is valid.</span></span>

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

### <span data-ttu-id="ef9cd-202">-Дингдуратион</span><span class="sxs-lookup"><span data-stu-id="ef9cd-202">-DingDuration</span></span>

<span data-ttu-id="ef9cd-203">Указывает длительность звукового сигнала, когда для **беллстиле** задано значение " **звук**".</span><span class="sxs-lookup"><span data-stu-id="ef9cd-203">Specifies the duration of the beep when **BellStyle** is set to **Audible**.</span></span>

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

### <span data-ttu-id="ef9cd-204">-Дингтоне</span><span class="sxs-lookup"><span data-stu-id="ef9cd-204">-DingTone</span></span>

<span data-ttu-id="ef9cd-205">Задает тон в герцах (Гц) звукового сигнала, если для **беллстиле** задано значение " **звук**".</span><span class="sxs-lookup"><span data-stu-id="ef9cd-205">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible**.</span></span>

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

### <span data-ttu-id="ef9cd-206">-EditMode</span><span class="sxs-lookup"><span data-stu-id="ef9cd-206">-EditMode</span></span>

<span data-ttu-id="ef9cd-207">Задает режим редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-207">Specifies the command line editing mode.</span></span> <span data-ttu-id="ef9cd-208">Использование этого параметра приводит к сбросу всех привязок к ключам, установленных `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-208">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="ef9cd-209">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-209">The valid values are as follows:</span></span>

- <span data-ttu-id="ef9cd-210">**Windows**: привязки клавиш имитируют PowerShell, cmd и Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-210">**Windows**: Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="ef9cd-211">**Emacs**: привязки клавиш имитируют bash или Emacs.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-211">**Emacs**: Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="ef9cd-212">**VI**: привязки ключей имитируют VI.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-212">**Vi**: Key bindings emulate Vi.</span></span>

<span data-ttu-id="ef9cd-213">Используйте `Get-PSReadLineKeyHandler` , чтобы просмотреть сочетания клавиш для текущего настроенного **EditMode**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-213">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode**.</span></span>

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

### <span data-ttu-id="ef9cd-214">-Екстрапромптлинекаунт</span><span class="sxs-lookup"><span data-stu-id="ef9cd-214">-ExtraPromptLineCount</span></span>

<span data-ttu-id="ef9cd-215">Указывает количество дополнительных строк.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-215">Specifies the number of extra lines.</span></span>

<span data-ttu-id="ef9cd-216">Если запрос охватывает более одной строки, укажите значение для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-216">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="ef9cd-217">Используйте этот параметр, если требуется, чтобы дополнительные строки были доступны, когда **PSReadLine** отображает запрос после отображения некоторых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-217">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="ef9cd-218">Например, **PSReadLine** возвращает список завершений.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-218">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="ef9cd-219">Этот параметр требуется меньше, чем в предыдущих версиях **PSReadLine**, но полезен при `InvokePrompt` использовании функции.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-219">This option is needed less than in previous versions of **PSReadLine**, but is useful when the `InvokePrompt` function is used.</span></span>

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

### <span data-ttu-id="ef9cd-220">-Хисторинодупликатес</span><span class="sxs-lookup"><span data-stu-id="ef9cd-220">-HistoryNoDuplicates</span></span>

<span data-ttu-id="ef9cd-221">Этот параметр управляет поведением отзыва.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-221">This option controls the recall behavior.</span></span> <span data-ttu-id="ef9cd-222">Дубликаты команд по-прежнему добавляются в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-222">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="ef9cd-223">Если этот параметр задан, то при отзыве команд появляется только самый последний вызов.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-223">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="ef9cd-224">Повторяющиеся команды добавляются в журнал для сохранения порядка во время отзыва.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-224">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="ef9cd-225">Однако обычно не требуется, чтобы команда была встречаться несколько раз при отзыве или поиске по журналу.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-225">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="ef9cd-226">По умолчанию свойству **хисторинодупликатес** глобального объекта **псконсолереадлинеоптионс** присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-226">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="ef9cd-227">При использовании этого **переключатель** свойству присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-227">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="ef9cd-228">Чтобы изменить значение свойства, необходимо указать значение **переключатель** следующим образом: `-HistoryNoDuplicates:$False` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-228">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="ef9cd-229">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-229">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="ef9cd-230">-Хисторисавепас</span><span class="sxs-lookup"><span data-stu-id="ef9cd-230">-HistorySavePath</span></span>

<span data-ttu-id="ef9cd-231">Указывает путь к файлу, в котором сохранен журнал.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-231">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="ef9cd-232">Компьютеры под управлением Windows или платформы, отличной от Windows, сохраняют файл в разных расположениях.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-232">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="ef9cd-233">Имя файла хранится в переменной `$($host.Name)_history.txt` , например `ConsoleHost_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-233">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="ef9cd-234">Если этот параметр не используется, путь по умолчанию выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-234">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="ef9cd-235">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ef9cd-235">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="ef9cd-236">**не Windows**</span><span class="sxs-lookup"><span data-stu-id="ef9cd-236">**non-Windows**</span></span>

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

### <span data-ttu-id="ef9cd-237">-Хисторисавестиле</span><span class="sxs-lookup"><span data-stu-id="ef9cd-237">-HistorySaveStyle</span></span>

<span data-ttu-id="ef9cd-238">Указывает, как **PSReadLine** сохраняет журнал.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-238">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="ef9cd-239">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-239">Valid values are as follows:</span></span>

- <span data-ttu-id="ef9cd-240">**Савеинкременталли**: сохранение журнала после выполнения каждой команды и совместного использования нескольких экземпляров PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-240">**SaveIncrementally**: Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="ef9cd-241">**Савеатексит**: Добавление файла журнала при выходе из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-241">**SaveAtExit**: Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="ef9cd-242">**Савеносинг**: не используйте файл журнала.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-242">**SaveNothing**: Don't use a history file.</span></span>

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

### <span data-ttu-id="ef9cd-243">-Хисторисеарчкасесенситиве</span><span class="sxs-lookup"><span data-stu-id="ef9cd-243">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="ef9cd-244">Указывает, что при поиске в журнале учитывается регистр в таких функциях, как **реверсесеарчхистори** или **хисторисеарчбакквард**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-244">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward**.</span></span>

<span data-ttu-id="ef9cd-245">По умолчанию свойству **хисторисеарчкасесенситиве** глобального объекта **псконсолереадлинеоптионс** присваивается значение `False` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-245">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="ef9cd-246">При использовании этого **переключатель** свойству присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-246">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="ef9cd-247">Чтобы изменить значение свойства обратно, необходимо указать значение **переключатель** следующим образом: `-HistorySearchCaseSensitive:$False` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-247">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="ef9cd-248">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-248">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="ef9cd-249">-Хисторисеарчкурсормовестоенд</span><span class="sxs-lookup"><span data-stu-id="ef9cd-249">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="ef9cd-250">Указывает, что курсор перемещается в конец команд, загруженных из журнала с помощью поиска.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-250">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="ef9cd-251">Если для этого параметра задано значение `$False` , курсор остается в том положении, в котором он находился при нажатии стрелок вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-251">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="ef9cd-252">По умолчанию свойству **хисторисеарчкурсормовестоенд** глобального объекта **псконсолереадлинеоптионс** присваивается значение `False` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-252">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="ef9cd-253">Используя этот **переключатель** , задайте для свойства значение `True` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-253">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="ef9cd-254">Чтобы изменить значение свойства обратно, необходимо указать значение **переключатель** следующим образом: `-HistorySearchCursorMovesToEnd:$False` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-254">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="ef9cd-255">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-255">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="ef9cd-256">-Максимумхисторикаунт</span><span class="sxs-lookup"><span data-stu-id="ef9cd-256">-MaximumHistoryCount</span></span>

<span data-ttu-id="ef9cd-257">Указывает максимальное количество команд для сохранения в журнале **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-257">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="ef9cd-258">Журнал **PSReadLine** отличается от журнала PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-258">**PSReadLine** history is separate from PowerShell history.</span></span>

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

### <span data-ttu-id="ef9cd-259">-Максимумкиллрингкаунт</span><span class="sxs-lookup"><span data-stu-id="ef9cd-259">-MaximumKillRingCount</span></span>

<span data-ttu-id="ef9cd-260">Указывает максимальное число элементов, хранящихся в кольцевом буфере.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-260">Specifies the maximum number of items stored in the kill ring.</span></span>

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

### <span data-ttu-id="ef9cd-261">-Промпттекст</span><span class="sxs-lookup"><span data-stu-id="ef9cd-261">-PromptText</span></span>

<span data-ttu-id="ef9cd-262">При возникновении ошибки синтаксического анализа **PSReadLine** изменяет часть красной строки.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-262">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="ef9cd-263">**PSReadLine** анализирует функцию Prompt, чтобы определить, как изменить только цвет части запроса.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-263">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="ef9cd-264">Этот анализ не 100% надежности.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-264">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="ef9cd-265">Используйте этот параметр, если **PSReadLine** изменяет запрос непредвиденным образом.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-265">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="ef9cd-266">Включите все конечные пробелы.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-266">Include any trailing whitespace.</span></span>

<span data-ttu-id="ef9cd-267">Например, если функция Prompt выглядит как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-267">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="ef9cd-268">Затем задайте:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-268">Then set:</span></span>

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

### <span data-ttu-id="ef9cd-269">-Шовтултипс</span><span class="sxs-lookup"><span data-stu-id="ef9cd-269">-ShowToolTips</span></span>

<span data-ttu-id="ef9cd-270">При отображении возможных завершений подсказки отображаются в списке завершений.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-270">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="ef9cd-271">Этот параметр по умолчанию включен.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-271">This option is enabled by default.</span></span> <span data-ttu-id="ef9cd-272">Этот параметр не включен по умолчанию в предыдущих версиях **PSReadLine**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-272">This option wasn't enabled by default in prior versions of **PSReadLine**.</span></span> <span data-ttu-id="ef9cd-273">Чтобы отключить этот параметр, установите для этого параметра значение `$False` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-273">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="ef9cd-274">По умолчанию свойству **шовтултипс** глобального объекта **псконсолереадлинеоптионс** присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-274">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="ef9cd-275">При использовании этого **переключатель** свойству присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-275">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="ef9cd-276">Чтобы изменить значение свойства, необходимо указать значение **переключатель** следующим образом: `-ShowToolTips:$False` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-276">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="ef9cd-277">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-277">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="ef9cd-278">-Вимодечанжехандлер</span><span class="sxs-lookup"><span data-stu-id="ef9cd-278">-ViModeChangeHandler</span></span>

<span data-ttu-id="ef9cd-279">Если для **вимодеиндикатор** задано значение `Script` , то указанный блок скрипта будет вызываться каждый раз при изменении режима.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-279">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="ef9cd-280">Блок скрипта предоставляет один аргумент типа `ViMode` .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-280">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="ef9cd-281">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-281">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="ef9cd-282">-Вимодеиндикатор</span><span class="sxs-lookup"><span data-stu-id="ef9cd-282">-ViModeIndicator</span></span>

<span data-ttu-id="ef9cd-283">Этот параметр задает визуальное обозначение для текущего режима **VI** .</span><span class="sxs-lookup"><span data-stu-id="ef9cd-283">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="ef9cd-284">Режим вставки или режим команд.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-284">Either insert mode or command mode.</span></span>

<span data-ttu-id="ef9cd-285">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-285">The valid values are as follows:</span></span>

- <span data-ttu-id="ef9cd-286">**Нет**: нет никаких свидетельств.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-286">**None**: There's no indication.</span></span>
- <span data-ttu-id="ef9cd-287">**Prompt**: запрос изменит цвет.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-287">**Prompt**: The prompt changes color.</span></span>
- <span data-ttu-id="ef9cd-288">**Cursor**: размер курсора меняется.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-288">**Cursor**: The cursor changes size.</span></span>
- <span data-ttu-id="ef9cd-289">**Скрипт**: печатается указанный пользователем текст.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-289">**Script**: User-specified text is printed.</span></span>

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

### <span data-ttu-id="ef9cd-290">-Вордделимитерс</span><span class="sxs-lookup"><span data-stu-id="ef9cd-290">-WordDelimiters</span></span>

<span data-ttu-id="ef9cd-291">Задает символы, разделяющие слова для таких функций, как **форвардворд** или **киллворд**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-291">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"---
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef9cd-292">-Предиктионсаурце</span><span class="sxs-lookup"><span data-stu-id="ef9cd-292">-PredictionSource</span></span>

<span data-ttu-id="ef9cd-293">Указывает источник PSReadLine для получения прогнозных предложений.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-293">Specifies the source for PSReadLine to get predictive suggestions.</span></span>

<span data-ttu-id="ef9cd-294">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ef9cd-294">Valid values are:</span></span>

- <span data-ttu-id="ef9cd-295">**None** — отключить функцию прогнозной IntelliSense (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ef9cd-295">**None** - disable the predictive IntelliSense feature (default).</span></span>
<span data-ttu-id="ef9cd-296">-\`**Журнал** . Включите функцию прогнозной IntelliSense и используйте в качестве единственного источника журнал PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-296">-\`**History** - enable the predictive IntelliSense feature and use the PSReadLine history as the only source.</span></span>
- <span data-ttu-id="ef9cd-297">**Подключаемый модуль** . Включите функцию прогнозной IntelliSense и используйте подключаемые модули ( `CommandPrediction` ) в качестве единственного источника.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-297">**Plugin** - enable the predictive IntelliSense feature and use the plugins (`CommandPrediction`) as the only source.</span></span> <span data-ttu-id="ef9cd-298">Это значение было добавлено в PSReadLine 2.2.0</span><span class="sxs-lookup"><span data-stu-id="ef9cd-298">This value was added in PSReadLine 2.2.0</span></span>
- <span data-ttu-id="ef9cd-299">**Хисторяндплугин** . Включите функцию прогнозной IntelliSense и используйте в качестве источников как журнал, так и подключаемый модуль.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-299">**HistoryAndPlugin** - enable the predictive IntelliSense feature and use both history and plugin as the sources.</span></span> <span data-ttu-id="ef9cd-300">Это значение было добавлено в PSReadLine 2.2.0</span><span class="sxs-lookup"><span data-stu-id="ef9cd-300">This value was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionSource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef9cd-301">-Предиктионвиевстиле</span><span class="sxs-lookup"><span data-stu-id="ef9cd-301">-PredictionViewStyle</span></span>

<span data-ttu-id="ef9cd-302">Задает стиль для вывода прогнозного текста.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-302">Sets the style for the display of the predictive text.</span></span> <span data-ttu-id="ef9cd-303">Значение по умолчанию — **инлиневиев**.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-303">The default is **InlineView**.</span></span>

- <span data-ttu-id="ef9cd-304">**Инлиневиев** — стиль, существующий сегодня, как в оболочке рыбы и ЗШ.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-304">**InlineView** - the style as existing today, similar as in fish shell and zsh.</span></span> <span data-ttu-id="ef9cd-305">(по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ef9cd-305">(default)</span></span>
- <span data-ttu-id="ef9cd-306">**ListView** — предложения отображаются в раскрывающемся списке, а пользователи могут выбрать использование <kbd>стрелок</kbd> и <kbd>стрелка вниз</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-306">**ListView** - suggestions are rendered in a drop down list, and users can select using <kbd>UpArrow</kbd> and <kbd>DownArrow</kbd>.</span></span>

<span data-ttu-id="ef9cd-307">Этот параметр был добавлен в PSReadLine 2.2.0</span><span class="sxs-lookup"><span data-stu-id="ef9cd-307">This parameter was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionViewStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineView
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef9cd-308">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ef9cd-308">CommonParameters</span></span>

<span data-ttu-id="ef9cd-309">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-309">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef9cd-310">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ef9cd-310">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef9cd-311">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ef9cd-311">Inputs</span></span>

### <span data-ttu-id="ef9cd-312">None</span><span class="sxs-lookup"><span data-stu-id="ef9cd-312">None</span></span>

<span data-ttu-id="ef9cd-313">Вы не можете передать объекты в `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="ef9cd-313">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="ef9cd-314">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ef9cd-314">Outputs</span></span>

### <span data-ttu-id="ef9cd-315">None</span><span class="sxs-lookup"><span data-stu-id="ef9cd-315">None</span></span>

<span data-ttu-id="ef9cd-316">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ef9cd-316">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ef9cd-317">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef9cd-317">Notes</span></span>

## <span data-ttu-id="ef9cd-318">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ef9cd-318">Related links</span></span>

[<span data-ttu-id="ef9cd-319">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="ef9cd-319">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="ef9cd-320">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ef9cd-320">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="ef9cd-321">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="ef9cd-321">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="ef9cd-322">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ef9cd-322">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="ef9cd-323">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ef9cd-323">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
