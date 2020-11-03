---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: d3e3ee1dcde36ac09f8441aff7ce48797cf48b5f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228113"
---
# <span data-ttu-id="d4039-103">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="d4039-103">Set-PSReadLineOption</span></span>

## <span data-ttu-id="d4039-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d4039-104">Synopsis</span></span>
<span data-ttu-id="d4039-105">Настройка поведения редактирования командной строки в **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d4039-105">Customizes the behavior of command line editing in **PSReadLine** .</span></span>

## <span data-ttu-id="d4039-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4039-106">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="d4039-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d4039-107">Description</span></span>

<span data-ttu-id="d4039-108">`Set-PSReadLineOption`Командлет настраивает поведение модуля **PSReadLine** при редактировании командной строки.</span><span class="sxs-lookup"><span data-stu-id="d4039-108">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="d4039-109">Чтобы просмотреть параметры **PSReadLine** , используйте `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="d4039-109">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="d4039-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="d4039-110">Examples</span></span>

### <span data-ttu-id="d4039-111">Пример 1. Задание цветов переднего плана и фона</span><span class="sxs-lookup"><span data-stu-id="d4039-111">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="d4039-112">В этом примере задается **PSReadLine** для вывода маркера **комментария** с зеленым текстом переднего плана на сером фоне.</span><span class="sxs-lookup"><span data-stu-id="d4039-112">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="d4039-113">В escape-последовательности, используемой в примере, **32** представляет цвет переднего плана, а **47** — цвет фона.</span><span class="sxs-lookup"><span data-stu-id="d4039-113">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

<span data-ttu-id="d4039-114">Можно выбрать только цвет текста переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d4039-114">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="d4039-115">Например, светло-зеленый цвет текста для маркера **комментария** : ``"Comment"="`e[92m"`` .</span><span class="sxs-lookup"><span data-stu-id="d4039-115">For example, a bright green foreground text color for the **Comment** token: ``"Comment"="`e[92m"``.</span></span>

### <span data-ttu-id="d4039-116">Пример 2. Задание стиля колокольчика</span><span class="sxs-lookup"><span data-stu-id="d4039-116">Example 2: Set bell style</span></span>

<span data-ttu-id="d4039-117">В этом примере **PSReadLine** будет отвечать на ошибки или условия, требующие вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4039-117">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="d4039-118">**Беллстиле** настроен на вывод звукового сигнала с частотой 1221 гц для 60 мс.</span><span class="sxs-lookup"><span data-stu-id="d4039-118">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="d4039-119">Эта функция может не работать на всех узлах на платформах.</span><span class="sxs-lookup"><span data-stu-id="d4039-119">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="d4039-120">Пример 3. Настройка нескольких параметров</span><span class="sxs-lookup"><span data-stu-id="d4039-120">Example 3: Set multiple options</span></span>

<span data-ttu-id="d4039-121">`Set-PSReadLineOption` может задавать несколько параметров с помощью хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="d4039-121">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

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

<span data-ttu-id="d4039-122">`$PSReadLineOptions`Хэш-таблица задает ключи и значения.</span><span class="sxs-lookup"><span data-stu-id="d4039-122">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="d4039-123">`Set-PSReadLineOption` использует ключи и значения с `@PSReadLineOptions` для обновления параметров **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d4039-123">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="d4039-124">Ключи и значения, введенные в поле Имя хэш-таблицы, можно просмотреть `$PSReadLineOptions` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4039-124">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="d4039-125">Пример 4. Задание нескольких параметров цвета</span><span class="sxs-lookup"><span data-stu-id="d4039-125">Example 4: Set multiple color options</span></span>

<span data-ttu-id="d4039-126">В этом примере показано, как задать более одного значения цвета в одной команде.</span><span class="sxs-lookup"><span data-stu-id="d4039-126">This example shows how to set more than one color value in a single command.</span></span>

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

### <span data-ttu-id="d4039-127">Пример 5. Задание цветовых значений для нескольких типов</span><span class="sxs-lookup"><span data-stu-id="d4039-127">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="d4039-128">В этом примере показаны три разных метода настройки цвета маркеров, отображаемых в **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d4039-128">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine** .</span></span>

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

### <span data-ttu-id="d4039-129">Пример 6. Использование Вимодечанжехандлер для вывода изменений в режиме VI</span><span class="sxs-lookup"><span data-stu-id="d4039-129">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="d4039-130">В этом примере выдается изменение курсора VT в ответ на изменение режима **VI** .</span><span class="sxs-lookup"><span data-stu-id="d4039-130">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

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

<span data-ttu-id="d4039-131">Функция **онвимодечанже** задает параметры курсора для режимов **VI** : INSERT и Command.</span><span class="sxs-lookup"><span data-stu-id="d4039-131">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="d4039-132">**Вимодечанжехандлер** использует `Function:` поставщик для ссылки на **онвимодечанже** в качестве объекта блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="d4039-132">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="d4039-133">Дополнительные сведения см. в разделе [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span><span class="sxs-lookup"><span data-stu-id="d4039-133">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="d4039-134">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4039-134">Parameters</span></span>

### <span data-ttu-id="d4039-135">-Аддтохисторихандлер</span><span class="sxs-lookup"><span data-stu-id="d4039-135">-AddToHistoryHandler</span></span>

<span data-ttu-id="d4039-136">Указывает блок **сценария** , который определяет, какие команды добавляются в журнал **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d4039-136">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="d4039-137">**ScriptBlock** получает командную строку в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="d4039-137">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="d4039-138">Если блок **ScriptBlock** возвращает значение `$True` , Командная строка добавляется в журнал.</span><span class="sxs-lookup"><span data-stu-id="d4039-138">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

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

### <span data-ttu-id="d4039-139">-Ансиескапетимеаут</span><span class="sxs-lookup"><span data-stu-id="d4039-139">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="d4039-140">Этот параметр характерен для Windows, если входные данные перенаправляются, например при выполнении в `tmux` или `screen` .</span><span class="sxs-lookup"><span data-stu-id="d4039-140">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="d4039-141">При использовании перенаправления входных данных в Windows многие ключи отправляются в виде последовательности символов, начиная с escape-символа.</span><span class="sxs-lookup"><span data-stu-id="d4039-141">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="d4039-142">Невозможно отличить один escape-символ, за которым следует больше символов, и допустимую escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="d4039-142">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="d4039-143">Предполагается, что терминал может отправить символы быстрее, чем пользовательские типы.</span><span class="sxs-lookup"><span data-stu-id="d4039-143">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="d4039-144">**PSReadLine** ждет этого времени ожидания, прежде чем завершать его получением полной escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="d4039-144">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="d4039-145">Если при вводе текста отображаются случайные или непредвиденные символы, можно настроить это время ожидания.</span><span class="sxs-lookup"><span data-stu-id="d4039-145">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

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

### <span data-ttu-id="d4039-146">-Беллстиле</span><span class="sxs-lookup"><span data-stu-id="d4039-146">-BellStyle</span></span>

<span data-ttu-id="d4039-147">Указывает, как **PSReadLine** реагирует на различные ошибочные и неоднозначные условия.</span><span class="sxs-lookup"><span data-stu-id="d4039-147">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="d4039-148">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="d4039-148">The valid values are as follows:</span></span>

- <span data-ttu-id="d4039-149">**Звук** : короткий звуковой сигнал.</span><span class="sxs-lookup"><span data-stu-id="d4039-149">**Audible** : A short beep.</span></span>
- <span data-ttu-id="d4039-150">**Визуальный** элемент: краткие текстовые Flash.</span><span class="sxs-lookup"><span data-stu-id="d4039-150">**Visual** : Text flashes briefly.</span></span>
- <span data-ttu-id="d4039-151">**Нет** : Отзывы отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="d4039-151">**None** : No feedback.</span></span>

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

### <span data-ttu-id="d4039-152">— Цвета</span><span class="sxs-lookup"><span data-stu-id="d4039-152">-Colors</span></span>

<span data-ttu-id="d4039-153">Параметр **Colors** указывает различные цвета, используемые **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d4039-153">The **Colors** parameter specifies various colors used by **PSReadLine** .</span></span>

<span data-ttu-id="d4039-154">Аргумент — это хэш-таблица, в которой ключи указывают, какой элемент и какие значения определяют цвет.</span><span class="sxs-lookup"><span data-stu-id="d4039-154">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="d4039-155">Дополнительные сведения см. в разделе [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="d4039-155">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="d4039-156">Цвета могут быть либо значением из **консолеколор** , `[ConsoleColor]::Red` либо допустимой escape-последовательностью ANSI.</span><span class="sxs-lookup"><span data-stu-id="d4039-156">Colors can be either a value from **ConsoleColor** , for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="d4039-157">Допустимые escape-последовательности зависят от терминала.</span><span class="sxs-lookup"><span data-stu-id="d4039-157">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="d4039-158">В PowerShell 5,0 пример escape-последовательности для красного текста — `$([char]0x1b)[91m` .</span><span class="sxs-lookup"><span data-stu-id="d4039-158">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="d4039-159">В PowerShell 6 и более поздних версиях одна и та же escape-последовательность имеет значение `` `e[91m`` .</span><span class="sxs-lookup"><span data-stu-id="d4039-159">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="d4039-160">Можно указать другие escape-последовательности, в том числе следующие типы:</span><span class="sxs-lookup"><span data-stu-id="d4039-160">You can specify other escape sequences including the following types:</span></span>

- <span data-ttu-id="d4039-161">цвет 256</span><span class="sxs-lookup"><span data-stu-id="d4039-161">256 color</span></span>
- <span data-ttu-id="d4039-162">24-разрядный цвет</span><span class="sxs-lookup"><span data-stu-id="d4039-162">24-bit color</span></span>
- <span data-ttu-id="d4039-163">Передний план, фон или оба</span><span class="sxs-lookup"><span data-stu-id="d4039-163">Foreground, background, or both</span></span>
- <span data-ttu-id="d4039-164">Инверсия, полужирный</span><span class="sxs-lookup"><span data-stu-id="d4039-164">Inverse, bold</span></span>

<span data-ttu-id="d4039-165">Дополнительные сведения о кодах цветов ANSI см. в статье [escape-код ANSI](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="d4039-165">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="d4039-166">К допустимым ключам относятся:</span><span class="sxs-lookup"><span data-stu-id="d4039-166">The valid keys include:</span></span>

- <span data-ttu-id="d4039-167">**Континуатионпромпт** : цвет запроса продолжения.</span><span class="sxs-lookup"><span data-stu-id="d4039-167">**ContinuationPrompt** : The color of the continuation prompt.</span></span>
- <span data-ttu-id="d4039-168">**Выделение** : цвет выделения.</span><span class="sxs-lookup"><span data-stu-id="d4039-168">**Emphasis** : The emphasis color.</span></span> <span data-ttu-id="d4039-169">Например, соответствующий текст при поиске в журнале.</span><span class="sxs-lookup"><span data-stu-id="d4039-169">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="d4039-170">**Ошибка** : цвет ошибки.</span><span class="sxs-lookup"><span data-stu-id="d4039-170">**Error** : The error color.</span></span> <span data-ttu-id="d4039-171">Например, в командной строке.</span><span class="sxs-lookup"><span data-stu-id="d4039-171">For example, in the prompt.</span></span>
- <span data-ttu-id="d4039-172">**Выделение** : цвет для выделения выбранного или выделенного текста в меню.</span><span class="sxs-lookup"><span data-stu-id="d4039-172">**Selection** : The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="d4039-173">**По умолчанию** : цвет токена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d4039-173">**Default** : The default token color.</span></span>
- <span data-ttu-id="d4039-174">**Комментарий** : цвет маркера комментария.</span><span class="sxs-lookup"><span data-stu-id="d4039-174">**Comment** : The comment token color.</span></span>
- <span data-ttu-id="d4039-175">**Ключевое слово** : цвет маркера ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="d4039-175">**Keyword** : The keyword token color.</span></span>
- <span data-ttu-id="d4039-176">**String** : цвет маркера строки.</span><span class="sxs-lookup"><span data-stu-id="d4039-176">**String** : The string token color.</span></span>
- <span data-ttu-id="d4039-177">**Оператор** : цвет маркера оператора.</span><span class="sxs-lookup"><span data-stu-id="d4039-177">**Operator** : The operator token color.</span></span>
- <span data-ttu-id="d4039-178">**Переменная** : цвет маркера переменной.</span><span class="sxs-lookup"><span data-stu-id="d4039-178">**Variable** : The variable token color.</span></span>
- <span data-ttu-id="d4039-179">**Команда** : цвет маркера команды.</span><span class="sxs-lookup"><span data-stu-id="d4039-179">**Command** : The command token color.</span></span>
- <span data-ttu-id="d4039-180">**Параметр** : цвет маркера параметра.</span><span class="sxs-lookup"><span data-stu-id="d4039-180">**Parameter** : The parameter token color.</span></span>
- <span data-ttu-id="d4039-181">**Тип** : цвет маркера типа.</span><span class="sxs-lookup"><span data-stu-id="d4039-181">**Type** : The type token color.</span></span>
- <span data-ttu-id="d4039-182">**Число** : цвет маркера номера.</span><span class="sxs-lookup"><span data-stu-id="d4039-182">**Number** : The number token color.</span></span>
- <span data-ttu-id="d4039-183">**Member** : цвет маркера имени элемента.</span><span class="sxs-lookup"><span data-stu-id="d4039-183">**Member** : The member name token color.</span></span>

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

### <span data-ttu-id="d4039-184">-Коммандвалидатионхандлер</span><span class="sxs-lookup"><span data-stu-id="d4039-184">-CommandValidationHandler</span></span>

<span data-ttu-id="d4039-185">Задает блок **ScriptBlock** , вызываемый из **валидатеандакцептлине** .</span><span class="sxs-lookup"><span data-stu-id="d4039-185">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine** .</span></span> <span data-ttu-id="d4039-186">При возникновении исключения проверка завершается неудачей и сообщается об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d4039-186">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="d4039-187">Перед созданием исключения обработчик проверки может поместить курсор в точку ошибки, чтобы упростить ее исправление.</span><span class="sxs-lookup"><span data-stu-id="d4039-187">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="d4039-188">Обработчик проверки может также изменить командную строку, например, чтобы исправить распространенные типографские ошибки.</span><span class="sxs-lookup"><span data-stu-id="d4039-188">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="d4039-189">**Валидатеандакцептлине** используется, чтобы избежать переполнения журнала с помощью команд, которые не могут работать.</span><span class="sxs-lookup"><span data-stu-id="d4039-189">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

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

### <span data-ttu-id="d4039-190">-Комплетионкуеритемс</span><span class="sxs-lookup"><span data-stu-id="d4039-190">-CompletionQueryItems</span></span>

<span data-ttu-id="d4039-191">Указывает максимальное количество элементов завершения, отображаемых без запроса.</span><span class="sxs-lookup"><span data-stu-id="d4039-191">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="d4039-192">Если число отображаемых элементов больше этого значения, **PSReadLine** запрашивает **Да/нет** перед отображением элементов завершения.</span><span class="sxs-lookup"><span data-stu-id="d4039-192">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

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

### <span data-ttu-id="d4039-193">-Континуатионпромпт</span><span class="sxs-lookup"><span data-stu-id="d4039-193">-ContinuationPrompt</span></span>

<span data-ttu-id="d4039-194">Задает строку, отображаемую в начале последующих строк при вводе многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="d4039-194">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="d4039-195">По умолчанию это два знака «больше» ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="d4039-195">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="d4039-196">Допустима пустая строка.</span><span class="sxs-lookup"><span data-stu-id="d4039-196">An empty string is valid.</span></span>

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

### <span data-ttu-id="d4039-197">-Дингдуратион</span><span class="sxs-lookup"><span data-stu-id="d4039-197">-DingDuration</span></span>

<span data-ttu-id="d4039-198">Указывает длительность звукового сигнала, когда для **беллстиле** задано значение " **звук** ".</span><span class="sxs-lookup"><span data-stu-id="d4039-198">Specifies the duration of the beep when **BellStyle** is set to **Audible** .</span></span>

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

### <span data-ttu-id="d4039-199">-Дингтоне</span><span class="sxs-lookup"><span data-stu-id="d4039-199">-DingTone</span></span>

<span data-ttu-id="d4039-200">Задает тон в герцах (Гц) звукового сигнала, если для **беллстиле** задано значение " **звук** ".</span><span class="sxs-lookup"><span data-stu-id="d4039-200">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible** .</span></span>

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

### <span data-ttu-id="d4039-201">-EditMode</span><span class="sxs-lookup"><span data-stu-id="d4039-201">-EditMode</span></span>

<span data-ttu-id="d4039-202">Задает режим редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="d4039-202">Specifies the command line editing mode.</span></span> <span data-ttu-id="d4039-203">Использование этого параметра приводит к сбросу всех привязок к ключам, установленных `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="d4039-203">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="d4039-204">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="d4039-204">The valid values are as follows:</span></span>

- <span data-ttu-id="d4039-205">**Windows** : привязки клавиш имитируют PowerShell, cmd и Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d4039-205">**Windows** : Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="d4039-206">**Emacs** : привязки клавиш имитируют bash или Emacs.</span><span class="sxs-lookup"><span data-stu-id="d4039-206">**Emacs** : Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="d4039-207">**VI** : привязки ключей имитируют VI.</span><span class="sxs-lookup"><span data-stu-id="d4039-207">**Vi** : Key bindings emulate Vi.</span></span>

<span data-ttu-id="d4039-208">Используйте `Get-PSReadLineKeyHandler` , чтобы просмотреть сочетания клавиш для текущего настроенного **EditMode** .</span><span class="sxs-lookup"><span data-stu-id="d4039-208">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode** .</span></span>

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

### <span data-ttu-id="d4039-209">-Екстрапромптлинекаунт</span><span class="sxs-lookup"><span data-stu-id="d4039-209">-ExtraPromptLineCount</span></span>

<span data-ttu-id="d4039-210">Указывает количество дополнительных строк.</span><span class="sxs-lookup"><span data-stu-id="d4039-210">Specifies the number of extra lines.</span></span>

<span data-ttu-id="d4039-211">Если запрос охватывает более одной строки, укажите значение для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="d4039-211">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="d4039-212">Используйте этот параметр, если требуется, чтобы дополнительные строки были доступны, когда **PSReadLine** отображает запрос после отображения некоторых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d4039-212">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="d4039-213">Например, **PSReadLine** возвращает список завершений.</span><span class="sxs-lookup"><span data-stu-id="d4039-213">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="d4039-214">Этот параметр требуется меньше, чем в предыдущих версиях **PSReadLine** , но полезен при `InvokePrompt` использовании функции.</span><span class="sxs-lookup"><span data-stu-id="d4039-214">This option is needed less than in previous versions of **PSReadLine** , but is useful when the `InvokePrompt` function is used.</span></span>

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

### <span data-ttu-id="d4039-215">-Хисторинодупликатес</span><span class="sxs-lookup"><span data-stu-id="d4039-215">-HistoryNoDuplicates</span></span>

<span data-ttu-id="d4039-216">Этот параметр управляет поведением отзыва.</span><span class="sxs-lookup"><span data-stu-id="d4039-216">This option controls the recall behavior.</span></span> <span data-ttu-id="d4039-217">Дубликаты команд по-прежнему добавляются в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="d4039-217">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="d4039-218">Если этот параметр задан, то при отзыве команд появляется только самый последний вызов.</span><span class="sxs-lookup"><span data-stu-id="d4039-218">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="d4039-219">Повторяющиеся команды добавляются в журнал для сохранения порядка во время отзыва.</span><span class="sxs-lookup"><span data-stu-id="d4039-219">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="d4039-220">Однако обычно не требуется, чтобы команда была встречаться несколько раз при отзыве или поиске по журналу.</span><span class="sxs-lookup"><span data-stu-id="d4039-220">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="d4039-221">По умолчанию свойству **хисторинодупликатес** глобального объекта **псконсолереадлинеоптионс** присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="d4039-221">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="d4039-222">При использовании этого **переключатель** свойству присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="d4039-222">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="d4039-223">Чтобы изменить значение свойства, необходимо указать значение **переключатель** следующим образом: `-HistoryNoDuplicates:$False` .</span><span class="sxs-lookup"><span data-stu-id="d4039-223">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="d4039-224">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="d4039-224">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="d4039-225">-Хисторисавепас</span><span class="sxs-lookup"><span data-stu-id="d4039-225">-HistorySavePath</span></span>

<span data-ttu-id="d4039-226">Указывает путь к файлу, в котором сохранен журнал.</span><span class="sxs-lookup"><span data-stu-id="d4039-226">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="d4039-227">Компьютеры под управлением Windows или платформы, отличной от Windows, сохраняют файл в разных расположениях.</span><span class="sxs-lookup"><span data-stu-id="d4039-227">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="d4039-228">Имя файла хранится в переменной `$($host.Name)_history.txt` , например `ConsoleHost_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="d4039-228">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="d4039-229">Если этот параметр не используется, путь по умолчанию выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4039-229">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="d4039-230">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d4039-230">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="d4039-231">**не Windows**</span><span class="sxs-lookup"><span data-stu-id="d4039-231">**non-Windows**</span></span>

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

### <span data-ttu-id="d4039-232">-Хисторисавестиле</span><span class="sxs-lookup"><span data-stu-id="d4039-232">-HistorySaveStyle</span></span>

<span data-ttu-id="d4039-233">Указывает, как **PSReadLine** сохраняет журнал.</span><span class="sxs-lookup"><span data-stu-id="d4039-233">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="d4039-234">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d4039-234">Valid values are as follows:</span></span>

- <span data-ttu-id="d4039-235">**Савеинкременталли** : сохранение журнала после выполнения каждой команды и совместного использования нескольких экземпляров PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4039-235">**SaveIncrementally** : Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="d4039-236">**Савеатексит** : Добавление файла журнала при выходе из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4039-236">**SaveAtExit** : Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="d4039-237">**Савеносинг** : не используйте файл журнала.</span><span class="sxs-lookup"><span data-stu-id="d4039-237">**SaveNothing** : Don't use a history file.</span></span>

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

### <span data-ttu-id="d4039-238">-Хисторисеарчкасесенситиве</span><span class="sxs-lookup"><span data-stu-id="d4039-238">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="d4039-239">Указывает, что при поиске в журнале учитывается регистр в таких функциях, как **реверсесеарчхистори** или **хисторисеарчбакквард** .</span><span class="sxs-lookup"><span data-stu-id="d4039-239">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward** .</span></span>

<span data-ttu-id="d4039-240">По умолчанию свойству **хисторисеарчкасесенситиве** глобального объекта **псконсолереадлинеоптионс** присваивается значение `False` .</span><span class="sxs-lookup"><span data-stu-id="d4039-240">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="d4039-241">При использовании этого **переключатель** свойству присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="d4039-241">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="d4039-242">Чтобы изменить значение свойства обратно, необходимо указать значение **переключатель** следующим образом: `-HistorySearchCaseSensitive:$False` .</span><span class="sxs-lookup"><span data-stu-id="d4039-242">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="d4039-243">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="d4039-243">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="d4039-244">-Хисторисеарчкурсормовестоенд</span><span class="sxs-lookup"><span data-stu-id="d4039-244">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="d4039-245">Указывает, что курсор перемещается в конец команд, загруженных из журнала с помощью поиска.</span><span class="sxs-lookup"><span data-stu-id="d4039-245">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="d4039-246">Если для этого параметра задано значение `$False` , курсор остается в том положении, в котором он находился при нажатии стрелок вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="d4039-246">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="d4039-247">По умолчанию свойству **хисторисеарчкурсормовестоенд** глобального объекта **псконсолереадлинеоптионс** присваивается значение `False` .</span><span class="sxs-lookup"><span data-stu-id="d4039-247">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="d4039-248">Используя этот **переключатель** , задайте для свойства значение `True` .</span><span class="sxs-lookup"><span data-stu-id="d4039-248">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="d4039-249">Чтобы изменить значение свойства обратно, необходимо указать значение **переключатель** следующим образом: `-HistorySearchCursorMovesToEnd:$False` .</span><span class="sxs-lookup"><span data-stu-id="d4039-249">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="d4039-250">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="d4039-250">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="d4039-251">-Максимумхисторикаунт</span><span class="sxs-lookup"><span data-stu-id="d4039-251">-MaximumHistoryCount</span></span>

<span data-ttu-id="d4039-252">Указывает максимальное количество команд для сохранения в журнале **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d4039-252">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="d4039-253">Журнал **PSReadLine** отличается от журнала PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4039-253">**PSReadLine** history is separate from PowerShell history.</span></span>

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

### <span data-ttu-id="d4039-254">-Максимумкиллрингкаунт</span><span class="sxs-lookup"><span data-stu-id="d4039-254">-MaximumKillRingCount</span></span>

<span data-ttu-id="d4039-255">Указывает максимальное число элементов, хранящихся в кольцевом буфере.</span><span class="sxs-lookup"><span data-stu-id="d4039-255">Specifies the maximum number of items stored in the kill ring.</span></span>

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

### <span data-ttu-id="d4039-256">-Промпттекст</span><span class="sxs-lookup"><span data-stu-id="d4039-256">-PromptText</span></span>

<span data-ttu-id="d4039-257">При возникновении ошибки синтаксического анализа **PSReadLine** изменяет часть красной строки.</span><span class="sxs-lookup"><span data-stu-id="d4039-257">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="d4039-258">**PSReadLine** анализирует функцию Prompt, чтобы определить, как изменить только цвет части запроса.</span><span class="sxs-lookup"><span data-stu-id="d4039-258">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="d4039-259">Этот анализ не 100% надежности.</span><span class="sxs-lookup"><span data-stu-id="d4039-259">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="d4039-260">Используйте этот параметр, если **PSReadLine** изменяет запрос непредвиденным образом.</span><span class="sxs-lookup"><span data-stu-id="d4039-260">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="d4039-261">Включите все конечные пробелы.</span><span class="sxs-lookup"><span data-stu-id="d4039-261">Include any trailing whitespace.</span></span>

<span data-ttu-id="d4039-262">Например, если функция Prompt выглядит как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d4039-262">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="d4039-263">Затем задайте:</span><span class="sxs-lookup"><span data-stu-id="d4039-263">Then set:</span></span>

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

### <span data-ttu-id="d4039-264">-Шовтултипс</span><span class="sxs-lookup"><span data-stu-id="d4039-264">-ShowToolTips</span></span>

<span data-ttu-id="d4039-265">При отображении возможных завершений подсказки отображаются в списке завершений.</span><span class="sxs-lookup"><span data-stu-id="d4039-265">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="d4039-266">Этот параметр по умолчанию включен.</span><span class="sxs-lookup"><span data-stu-id="d4039-266">This option is enabled by default.</span></span> <span data-ttu-id="d4039-267">Этот параметр не включен по умолчанию в предыдущих версиях **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d4039-267">This option wasn't enabled by default in prior versions of **PSReadLine** .</span></span> <span data-ttu-id="d4039-268">Чтобы отключить этот параметр, установите для этого параметра значение `$False` .</span><span class="sxs-lookup"><span data-stu-id="d4039-268">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="d4039-269">По умолчанию свойству **шовтултипс** глобального объекта **псконсолереадлинеоптионс** присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="d4039-269">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="d4039-270">При использовании этого **переключатель** свойству присваивается значение `True` .</span><span class="sxs-lookup"><span data-stu-id="d4039-270">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="d4039-271">Чтобы изменить значение свойства, необходимо указать значение **переключатель** следующим образом: `-ShowToolTips:$False` .</span><span class="sxs-lookup"><span data-stu-id="d4039-271">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="d4039-272">С помощью следующей команды можно задать значение свойства напрямую:</span><span class="sxs-lookup"><span data-stu-id="d4039-272">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="d4039-273">-Вимодечанжехандлер</span><span class="sxs-lookup"><span data-stu-id="d4039-273">-ViModeChangeHandler</span></span>

<span data-ttu-id="d4039-274">Если для **вимодеиндикатор** задано значение `Script` , то указанный блок скрипта будет вызываться каждый раз при изменении режима.</span><span class="sxs-lookup"><span data-stu-id="d4039-274">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="d4039-275">Блок скрипта предоставляет один аргумент типа `ViMode` .</span><span class="sxs-lookup"><span data-stu-id="d4039-275">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="d4039-276">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="d4039-276">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="d4039-277">-Вимодеиндикатор</span><span class="sxs-lookup"><span data-stu-id="d4039-277">-ViModeIndicator</span></span>

<span data-ttu-id="d4039-278">Этот параметр задает визуальное обозначение для текущего режима **VI** .</span><span class="sxs-lookup"><span data-stu-id="d4039-278">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="d4039-279">Режим вставки или режим команд.</span><span class="sxs-lookup"><span data-stu-id="d4039-279">Either insert mode or command mode.</span></span>

<span data-ttu-id="d4039-280">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="d4039-280">The valid values are as follows:</span></span>

- <span data-ttu-id="d4039-281">**Нет** : нет никаких свидетельств.</span><span class="sxs-lookup"><span data-stu-id="d4039-281">**None** : There's no indication.</span></span>
- <span data-ttu-id="d4039-282">**Prompt** : запрос изменит цвет.</span><span class="sxs-lookup"><span data-stu-id="d4039-282">**Prompt** : The prompt changes color.</span></span>
- <span data-ttu-id="d4039-283">**Cursor** : размер курсора меняется.</span><span class="sxs-lookup"><span data-stu-id="d4039-283">**Cursor** : The cursor changes size.</span></span>
- <span data-ttu-id="d4039-284">**Скрипт** : печатается указанный пользователем текст.</span><span class="sxs-lookup"><span data-stu-id="d4039-284">**Script** : User-specified text is printed.</span></span>

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

### <span data-ttu-id="d4039-285">-Вордделимитерс</span><span class="sxs-lookup"><span data-stu-id="d4039-285">-WordDelimiters</span></span>

<span data-ttu-id="d4039-286">Задает символы, разделяющие слова для таких функций, как **форвардворд** или **киллворд** .</span><span class="sxs-lookup"><span data-stu-id="d4039-286">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord** .</span></span>

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

### <span data-ttu-id="d4039-287">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d4039-287">CommonParameters</span></span>

<span data-ttu-id="d4039-288">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d4039-288">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d4039-289">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d4039-289">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d4039-290">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d4039-290">Inputs</span></span>

### <span data-ttu-id="d4039-291">None</span><span class="sxs-lookup"><span data-stu-id="d4039-291">None</span></span>

<span data-ttu-id="d4039-292">Вы не можете передать объекты в `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="d4039-292">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="d4039-293">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d4039-293">Outputs</span></span>

### <span data-ttu-id="d4039-294">Нет</span><span class="sxs-lookup"><span data-stu-id="d4039-294">None</span></span>

<span data-ttu-id="d4039-295">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d4039-295">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d4039-296">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4039-296">Notes</span></span>

## <span data-ttu-id="d4039-297">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d4039-297">Related links</span></span>

[<span data-ttu-id="d4039-298">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d4039-298">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="d4039-299">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d4039-299">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="d4039-300">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="d4039-300">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="d4039-301">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d4039-301">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="d4039-302">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d4039-302">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
