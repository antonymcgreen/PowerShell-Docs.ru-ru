---
ms.date: 12/14/2020
title: Использование экспериментальных функций в PowerShell
description: Список доступных в настоящее время экспериментальных функций и их использование.
ms.openlocfilehash: 556ae8d877b670b119b7b5b958a52488aad16241
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500129"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="484ce-103">Использование экспериментальных функций в PowerShell</span><span class="sxs-lookup"><span data-stu-id="484ce-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="484ce-104">Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="484ce-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="484ce-105">Экспериментальной функцией называется та, которая находится на этапе проектирования.</span><span class="sxs-lookup"><span data-stu-id="484ce-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="484ce-106">Эта функция доступна пользователям для тестирования и предоставления отзывов о ней.</span><span class="sxs-lookup"><span data-stu-id="484ce-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="484ce-107">Как только процесс разработки экспериментальной функции будет завершен, изменения на этапе проектирования станут критическими.</span><span class="sxs-lookup"><span data-stu-id="484ce-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="484ce-108">Экспериментальные функции не предназначены для использования в рабочей среде, так как изменения могут привести к нарушению работы.</span><span class="sxs-lookup"><span data-stu-id="484ce-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="484ce-109">Экспериментальные функции официально не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="484ce-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="484ce-110">Тем не менее мы будем признательны вам за любые отзывы и отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="484ce-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="484ce-111">Сообщить о проблеме можно в [исходном репозитории GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).</span><span class="sxs-lookup"><span data-stu-id="484ce-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="484ce-112">Дополнительные сведения о включении или отключении этих функций см. в статье [Экспериментальные функции](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span><span class="sxs-lookup"><span data-stu-id="484ce-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="484ce-113">Доступные функции</span><span class="sxs-lookup"><span data-stu-id="484ce-113">Available features</span></span>

<span data-ttu-id="484ce-114">В этой статье описываются доступные экспериментальные функции и сведения об их использовании.</span><span class="sxs-lookup"><span data-stu-id="484ce-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="484ce-115">Имя</span><span class="sxs-lookup"><span data-stu-id="484ce-115">Name</span></span>                            |   <span data-ttu-id="484ce-116">6.2</span><span class="sxs-lookup"><span data-stu-id="484ce-116">6.2</span></span>   |   <span data-ttu-id="484ce-117">7.0</span><span class="sxs-lookup"><span data-stu-id="484ce-117">7.0</span></span>   |   <span data-ttu-id="484ce-118">7.1</span><span class="sxs-lookup"><span data-stu-id="484ce-118">7.1</span></span>   |   <span data-ttu-id="484ce-119">7.2</span><span class="sxs-lookup"><span data-stu-id="484ce-119">7.2</span></span>   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: | :-----: |
| <span data-ttu-id="484ce-120">PSTempDrive (основная фаза в PS 7.0 и выше)</span><span class="sxs-lookup"><span data-stu-id="484ce-120">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |         |         |
| <span data-ttu-id="484ce-121">PSUseAbbreviationExpansion (основная фаза в PS 7.0 и выше)</span><span class="sxs-lookup"><span data-stu-id="484ce-121">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |         |         |
| <span data-ttu-id="484ce-122">PSNullConditionalOperators (основная функция в версии PS 7.1 и более поздней)</span><span class="sxs-lookup"><span data-stu-id="484ce-122">PSNullConditionalOperators (mainstream in PS 7.1+)</span></span>         |         | &check; |         |         |
| <span data-ttu-id="484ce-123">PSUnixFileStat (только не на базе Windows, общедоступная функция в PS 7.1 и выше)</span><span class="sxs-lookup"><span data-stu-id="484ce-123">PSUnixFileStat (non-Windows only - mainstream in PS 7.1+)</span></span>  |         | &check; |         |         |
| <span data-ttu-id="484ce-124">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="484ce-124">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; | &check; | &check; |
| <span data-ttu-id="484ce-125">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="484ce-125">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; | &check; | &check; |
| <span data-ttu-id="484ce-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="484ce-126">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; | &check; | &check; |
| <span data-ttu-id="484ce-127">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="484ce-127">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; | &check; | &check; |
| <span data-ttu-id="484ce-128">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="484ce-128">PSNativePSPathResolution</span></span>                                   |         |         | &check; | &check; |
| <span data-ttu-id="484ce-129">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="484ce-129">PSCultureInvariantReplaceOperator</span></span>                          |         |         | &check; | &check; |
| <span data-ttu-id="484ce-130">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="484ce-130">PSNotApplyErrorActionToStderr</span></span>                              |         |         | &check; | &check; |
| <span data-ttu-id="484ce-131">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="484ce-131">PSSubsystemPluginModel</span></span>                                     |         |         | &check; | &check; |
| <span data-ttu-id="484ce-132">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="484ce-132">PSAnsiProgress</span></span>                                             |         |         |         | &check; |
| <span data-ttu-id="484ce-133">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="484ce-133">PSAnsiRendering</span></span>                                            |         |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="484ce-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="484ce-134">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="484ce-135">В PowerShell 7.0 эксперимент включает параметр **BreakAll** в командлетах `Debug-Runspace` и `Debug-Job`, чтобы пользователи могли решить, будет ли работа PowerShell в текущем расположении немедленно прервана при подключении отладчика.</span><span class="sxs-lookup"><span data-stu-id="484ce-135">In PowerShell 7.0, the experiment enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

<span data-ttu-id="484ce-136">В PowerShell 7.1 этот эксперимент также добавляет параметр **Runspace** к командлетам `*-PSBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="484ce-136">In PowerShell 7.1, this experiment also adds the **Runspace** parameter to the `*-PSBreakpoint` cmdlets.</span></span>

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

<span data-ttu-id="484ce-137">Параметр **Runspace** указывает объекту **Runspace** взаимодействовать с точками останова в указанном пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="484ce-137">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

<span data-ttu-id="484ce-138">В этом примере задание запускается с точкой останова, для которой настроена прерывание при выполнении `Set-PSBreakPoint`.</span><span class="sxs-lookup"><span data-stu-id="484ce-138">In this example, a job is started and a breakpoint is set to break when the `Set-PSBreakPoint` is run.</span></span> <span data-ttu-id="484ce-139">Пространство выполнения хранится в переменной и передается команде `Get-PSBreakPoint` с параметром **Runspace**.</span><span class="sxs-lookup"><span data-stu-id="484ce-139">The runspace is stored in a variable and passed to the `Get-PSBreakPoint` command with the **Runspace** parameter.</span></span> <span data-ttu-id="484ce-140">Затем вы можете просмотреть точку останова в переменной `$breakpoint`.</span><span class="sxs-lookup"><span data-stu-id="484ce-140">You can then inspect the breakpoint in the `$breakpoint` variable.</span></span>

## <a name="psansirendering"></a><span data-ttu-id="484ce-141">PSAnsiRendering</span><span class="sxs-lookup"><span data-stu-id="484ce-141">PSAnsiRendering</span></span>

<span data-ttu-id="484ce-142">Эта экспериментальная функция добавлена в PowerShell 7.2.</span><span class="sxs-lookup"><span data-stu-id="484ce-142">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="484ce-143">Она позволяет изменять способ вывода текста обработчиком PowerShell и добавлять автоматическую переменную `$PSStyle` для управления отрисовкой строковых выходных данных в ANSI.</span><span class="sxs-lookup"><span data-stu-id="484ce-143">The feature enables changes how the PowerShell engine outputs text and add the `$PSStyle` automatic variable to control ANSI rendering of string output.</span></span>

```powershell
PS> $PSStyle

Name            MemberType Definition
----            ---------- ----------
Reset           Property   string AttributesOff {get;set;}
Background      Property   System.Management.Automation.PSStyle+BackgroundColor Background {get;set;}
Blink           Property   string Blink {get;set;}
BlinkOff        Property   string BlinkOff {get;set;}
Bold            Property   string Bold {get;set;}
BoldOff         Property   string BoldOff {get;set;}
Foreground      Property   System.Management.Automation.PSStyle+ForegroundColor Foreground {get;set;}
Formatting      Property   System.Management.Automation.PSStyle+FormattingData Formatting {get;set;}
Hidden          Property   string Hidden {get;set;}
HiddenOff       Property   string HiddenOff {get;set;}
OutputRendering Property   System.Management.Automation.OutputRendering OutputRendering {get;set;}
Reverse         Property   string Reverse {get;set;}
ReverseOff      Property   string ReverseOff {get;set;}
Italic          Property   string Standout {get;set;}
ItalicOff       Property   string StandoutOff {get;set;}
Underline       Property   string Underlined {get;set;}
Underline Off   Property   string UnderlinedOff {get;set;}
```

<span data-ttu-id="484ce-144">Базовые элементы возвращают строки escape-последовательностей ANSI, сопоставленные с их именами.</span><span class="sxs-lookup"><span data-stu-id="484ce-144">The base members return strings of ANSI escape sequences mapped to their names.</span></span> <span data-ttu-id="484ce-145">Значения можно настраивать.</span><span class="sxs-lookup"><span data-stu-id="484ce-145">The values are settable to allow customization.</span></span>

<span data-ttu-id="484ce-146">Дополнительные сведения см. в статье [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="484ce-146">For more information, see [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)</span></span>

> [!NOTE]
> <span data-ttu-id="484ce-147">Разработчики C# могут получать доступ к `PSStyle` как к одиночному элементу.</span><span class="sxs-lookup"><span data-stu-id="484ce-147">For C# developers, you can access `PSStyle` as a singleton.</span></span> <span data-ttu-id="484ce-148">Использование будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="484ce-148">Usage will look like this:</span></span>
>
> ```csharp
> string output = $"{PSStyle.Instance.Foreground.Red}{PSStyle.Instance.Bold}Hello{PSStyle.Instance.Reset}";
> ```
>
> <span data-ttu-id="484ce-149">`PSStyle` существует в пространстве имен System.Management.Automation.</span><span class="sxs-lookup"><span data-stu-id="484ce-149">`PSStyle` exists in the System.Management.Automation namespace.</span></span>

<span data-ttu-id="484ce-150">Наряду с доступом к `$PSStyle`, появляются изменения в обработчике PowerShell.</span><span class="sxs-lookup"><span data-stu-id="484ce-150">Along with access to `$PSStyle`, this introduces changes to the PowerShell engine.</span></span> <span data-ttu-id="484ce-151">Система форматирования PowerShell обновляется в соответствии с `$PSStyle.OutputRendering`.</span><span class="sxs-lookup"><span data-stu-id="484ce-151">The PowerShell formatting system is updated to respect `$PSStyle.OutputRendering`.</span></span>

- <span data-ttu-id="484ce-152">Добавляется тип `StringDecorated` для обработки экранированных строк ANSI.</span><span class="sxs-lookup"><span data-stu-id="484ce-152">`StringDecorated` type is added to handle ANSI escaped strings.</span></span>
- <span data-ttu-id="484ce-153">В возвращаемые данные добавляется логическое свойство `string IsDecorated`, если строка содержит escape-последовательности ANSI при наличии в ней ESC или C1 CSI.</span><span class="sxs-lookup"><span data-stu-id="484ce-153">`string IsDecorated` boolean property is added to return if the string contains ANSI escape sequences based on if the string contains ESC or C1 CSI.</span></span>
- <span data-ttu-id="484ce-154">Свойство `Length` возвращает _только_ длину текста без escape-последовательностей ANSI.</span><span class="sxs-lookup"><span data-stu-id="484ce-154">The `Length` property returns _only_ the length for the text without the ANSI escape sequences.</span></span>
- <span data-ttu-id="484ce-155">Метод `StringDecorated Substring(int contentLength)` возвращает подстроку, начинающуюся с индекса 0 вплоть до длины содержимого, которое не является частью escape-последовательностей ANSI.</span><span class="sxs-lookup"><span data-stu-id="484ce-155">`StringDecorated Substring(int contentLength)` method returns a substring starting at index 0 up to the content length that is not a part of ANSI escape sequences.</span></span> <span data-ttu-id="484ce-156">Это необходимо для усечения строк и сохранения escape-последовательностей ANSI, которые не занимают место печатаемых символов, при форматировании таблицы.</span><span class="sxs-lookup"><span data-stu-id="484ce-156">This is needed for table formatting to truncate strings and preserve ANSI escape sequences that don't take up printable character space.</span></span>
- <span data-ttu-id="484ce-157">Метод `string ToString()` остается без изменений и возвращает версию строки в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="484ce-157">`string ToString()` method stays the same and returns the plaintext version of the string.</span></span>
- <span data-ttu-id="484ce-158">Метод `string ToString(bool Ansi)` возвращает необработанную встроенную строку ANSI, если параметр `Ansi` имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="484ce-158">`string ToString(bool Ansi)` method returns the raw ANSI embedded string if the `Ansi` parameter is true.</span></span> <span data-ttu-id="484ce-159">В противном случае возвращается версия с открытым текстом с удаленными escape-последовательностями ANSI.</span><span class="sxs-lookup"><span data-stu-id="484ce-159">Otherwise, a plaintext version with ANSI escape sequences removed is returned.</span></span>

## <a name="psansiprogress"></a><span data-ttu-id="484ce-160">PSAnsiProgress</span><span class="sxs-lookup"><span data-stu-id="484ce-160">PSAnsiProgress</span></span>

<span data-ttu-id="484ce-161">Эта экспериментальная функция добавлена в PowerShell 7.2.</span><span class="sxs-lookup"><span data-stu-id="484ce-161">This experiment was added in PowerShell 7.2.</span></span> <span data-ttu-id="484ce-162">Эта функция добавляет элемент `$PSStyle.Progress` и позволяет управлять рендерингом панели просмотра хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="484ce-162">The feature adds the `$PSStyle.Progress` member and allows you to control progress view bar rendering.</span></span>

- <span data-ttu-id="484ce-163">`$PSStyle.Progress.Style` — строка ANSI, задающая стиль рендеринга.</span><span class="sxs-lookup"><span data-stu-id="484ce-163">`$PSStyle.Progress.Style` - An ANSI string setting the rendering style.</span></span>
- <span data-ttu-id="484ce-164">`$PSStyle.Progress.MaxWidth` — задает максимальную ширину представления.</span><span class="sxs-lookup"><span data-stu-id="484ce-164">`$PSStyle.Progress.MaxWidth` - Sets the max width of the view.</span></span> <span data-ttu-id="484ce-165">Задайте для ширины консоли значение `0`.</span><span class="sxs-lookup"><span data-stu-id="484ce-165">Set to `0` for console width.</span></span>
  <span data-ttu-id="484ce-166">Значение по умолчанию — `120`</span><span class="sxs-lookup"><span data-stu-id="484ce-166">Defaults to `120`</span></span>
- <span data-ttu-id="484ce-167">`$PSStyle.Progress.View` — перечисление со значениями `Minimal` и `Classic`.</span><span class="sxs-lookup"><span data-stu-id="484ce-167">`$PSStyle.Progress.View` - An enum with values, `Minimal` and `Classic`.</span></span> <span data-ttu-id="484ce-168">`Classic` — существующий рендеринг без изменений.</span><span class="sxs-lookup"><span data-stu-id="484ce-168">`Classic` is the existing rendering with no changes.</span></span> <span data-ttu-id="484ce-169">`Minimal` — минимальный рендеринг одной строки.</span><span class="sxs-lookup"><span data-stu-id="484ce-169">`Minimal` is a single line minimal rendering.</span></span> <span data-ttu-id="484ce-170">Значение по умолчанию — `Minimal`.</span><span class="sxs-lookup"><span data-stu-id="484ce-170">`Minimal` is the default.</span></span>

<span data-ttu-id="484ce-171">В следующем примере стиль рендеринга обновляется для отображения минимального индикатора хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="484ce-171">The following example updates the rendering style to a minimal progress bar.</span></span>

```powershell
$PSStyle.Progress.View.Minimal
```

> [!NOTE]
> <span data-ttu-id="484ce-172">Для использования этой функции необходимо включить экспериментальную функцию **PSAnsiRendering**.</span><span class="sxs-lookup"><span data-stu-id="484ce-172">You must have the **PSAnsiRendering** experimental feature enabled to use this feature.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="484ce-173">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="484ce-173">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="484ce-174">Рекомендует потенциальные команды на основе поиска нечетких соответствий после **CommandNotFoundException**.</span><span class="sxs-lookup"><span data-stu-id="484ce-174">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="484ce-175">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="484ce-175">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="484ce-176">Когда левый операнд в инструкции оператора `-replace` не является строкой, он преобразуется в строку.</span><span class="sxs-lookup"><span data-stu-id="484ce-176">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="484ce-177">Когда эта функция отключена, оператор `-replace` выполняет преобразование строк с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="484ce-177">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="484ce-178">Например, если для языка и региональных параметров настроен французский язык (fr), значение `1.2` преобразуется в строку `1,2`.</span><span class="sxs-lookup"><span data-stu-id="484ce-178">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="484ce-179">С включенной функцией:</span><span class="sxs-lookup"><span data-stu-id="484ce-179">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="484ce-180">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="484ce-180">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="484ce-181">Эта функция включает компиляцию в MOF в системах, отличных от Windows, и позволяет использовать `Invoke-DSCResource` без LCM.</span><span class="sxs-lookup"><span data-stu-id="484ce-181">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="484ce-182">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="484ce-182">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="484ce-183">Эта функция проверяет команду, введенную в оболочке. Если все команды являются командами прокси-сервера неявного удаленного взаимодействия, которые образуют простой конвейер, то эти команды объединяются и вызываются как один удаленный конвейер.</span><span class="sxs-lookup"><span data-stu-id="484ce-183">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="484ce-184">Пример</span><span class="sxs-lookup"><span data-stu-id="484ce-184">Example:</span></span>

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

<span data-ttu-id="484ce-185">Как показано выше, при включенной функции пакетирования все три команды прокси-сервера неявного удаленного доступа (`Get-AllProcesses`, `Select-Custom`, `Group-Stuff`) выполняются в удаленном сеансе, а результат из конвейера — это единственные данные, которые возвращаются клиенту.</span><span class="sxs-lookup"><span data-stu-id="484ce-185">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="484ce-186">Это приводит к уменьшению объема данных, передаваемых между клиентом и удаленным сеансом. Это также уменьшает количество процессов сериализации и десериализации объекта.</span><span class="sxs-lookup"><span data-stu-id="484ce-186">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="484ce-187">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="484ce-187">PSNativePSPathResolution</span></span>

<span data-ttu-id="484ce-188">Если путь PSDrive, использующий поставщик FileSystem, передается собственной команде, то и разрешенный путь к файлу передается собственной команде.</span><span class="sxs-lookup"><span data-stu-id="484ce-188">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="484ce-189">Это означает, что такая команда, как `code temp:/test.txt`, сейчас работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="484ce-189">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="484ce-190">Кроме того, если в Windows путь начинается с `~`, он преобразуется в полный путь и передается собственной команде.</span><span class="sxs-lookup"><span data-stu-id="484ce-190">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="484ce-191">В обоих случаях путь нормализуется к разделителям каталогов для соответствующей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="484ce-191">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="484ce-192">Если путь не является PSDrive или `~` (в Windows), то нормализация пути не происходит.</span><span class="sxs-lookup"><span data-stu-id="484ce-192">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="484ce-193">Если путь указан в одинарных кавычках, он не разрешается и рассматривается в качестве литерала.</span><span class="sxs-lookup"><span data-stu-id="484ce-193">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnotapplyerroractiontostderr"></a><span data-ttu-id="484ce-194">PSNotApplyErrorActionToStderr</span><span class="sxs-lookup"><span data-stu-id="484ce-194">PSNotApplyErrorActionToStderr</span></span>

<span data-ttu-id="484ce-195">Если эта экспериментальная функция включена, записи ошибок, перенаправленные из собственных команд (например, при использовании операторов перенаправления, таких как `2>&1`), не записываются в переменную `$Error`, а привилегированная переменная `$ErrorActionPreference` не влияет на перенаправленные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="484ce-195">When this experimental feature is enabled, error records redirected from native commands, like when using redirection operators (`2>&1`), are not written to the `$Error` variable and the preference variable `$ErrorActionPreference` does not affect the redirected output.</span></span>

<span data-ttu-id="484ce-196">Многие собственные команды выполняют запись в `stderr` в качестве альтернативного потока для сохранения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="484ce-196">Many native commands write to `stderr` as an alternative stream for additional information.</span></span> <span data-ttu-id="484ce-197">Такое поведение может запутать пользователя при просмотре ошибок или же дополнительная выходная информация может быть утрачена для пользователя, если для `$ErrorActionPreference` настроено состояние, блокирующее вывод данных.</span><span class="sxs-lookup"><span data-stu-id="484ce-197">This behavior can cause confusion when looking through errors or the additional output information can be lost to the user if `$ErrorActionPreference` is set to a state that mutes the output.</span></span>

<span data-ttu-id="484ce-198">Если собственная команда имеет ненулевой код завершения, для `$?` задается значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="484ce-198">When a native command has a non-zero exit code, `$?` is set to `$false`.</span></span> <span data-ttu-id="484ce-199">Если код завершения равен нулю, для `$?` задается значение `$true`.</span><span class="sxs-lookup"><span data-stu-id="484ce-199">If the exit code is zero, `$?` is set to `$true`.</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="484ce-200">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="484ce-200">PSNullConditionalOperators</span></span>

<span data-ttu-id="484ce-201">Эта функция вводит новые операторы для операторов доступа к членам, определяемого условием NULL: `?.` и `?[]`.</span><span class="sxs-lookup"><span data-stu-id="484ce-201">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="484ce-202">Операторы доступа к элементам со значением NULL могут использоваться для скалярных типов и типов массивов.</span><span class="sxs-lookup"><span data-stu-id="484ce-202">Null member access operators can be used on scalar types and array types.</span></span> <span data-ttu-id="484ce-203">Возвращает значение члена, к которому был получен доступ, если переменная не равна значению NULL.</span><span class="sxs-lookup"><span data-stu-id="484ce-203">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="484ce-204">Если значение переменной равно значению NULL, тогда возвращается NULL.</span><span class="sxs-lookup"><span data-stu-id="484ce-204">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="484ce-205">Доступ к свойству `propname` и его значение возвращаются, только если `$x` не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="484ce-205">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="484ce-206">Аналогичным образом индексатор используется, только если `$x` не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="484ce-206">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="484ce-207">Если `$x` равно NULL, то возвращается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="484ce-207">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="484ce-208">Операторы `?.` и `?[]` являются операторами доступа к членам и не допускают пробела между именем переменной и оператором.</span><span class="sxs-lookup"><span data-stu-id="484ce-208">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="484ce-209">Так как PowerShell допускает `?` в качестве части имени переменной, когда операторы используются без пробела между именем переменной и оператором, требуется устранение неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="484ce-209">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="484ce-210">Чтобы устранить неоднозначность, переменные должны заключить имя переменной в скобки `{}`, например: `${x?}?.propertyName` или `${y}?[0]`.</span><span class="sxs-lookup"><span data-stu-id="484ce-210">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

> [!NOTE]
> <span data-ttu-id="484ce-211">Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7.1 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="484ce-211">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="484ce-212">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="484ce-212">PSTempDrive</span></span>

<span data-ttu-id="484ce-213">Создает `TEMP:` PSDrive, сопоставленный с временным каталогом пользователя.</span><span class="sxs-lookup"><span data-stu-id="484ce-213">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="484ce-214">Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="484ce-214">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="484ce-215">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="484ce-215">PSUnixFileStat</span></span>

<span data-ttu-id="484ce-216">Эта функция обеспечивает новые возможности для включения данных из API функции **stat** Unix в выходные данные поставщика файловой системы, чтобы упростить более похожий на Unix список файлов.</span><span class="sxs-lookup"><span data-stu-id="484ce-216">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="484ce-217">Она добавляет новое свойство примечания в поставщик файловой системы с именем **UnixStat**, которое включает в себя общее выражение API `stat(2)` из базовой системы типов Unix.</span><span class="sxs-lookup"><span data-stu-id="484ce-217">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="484ce-218">Результат `Get-ChildItem` должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="484ce-218">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

> [!NOTE]
> <span data-ttu-id="484ce-219">Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7.1 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="484ce-219">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7.1 and higher.</span></span>

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="484ce-220">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="484ce-220">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="484ce-221">Эта функция позволяет выполнять заполнение сокращенных командлетов и функций нажатием клавиши TAB:</span><span class="sxs-lookup"><span data-stu-id="484ce-221">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="484ce-222">Пример:</span><span class="sxs-lookup"><span data-stu-id="484ce-222">For example:</span></span>

- <span data-ttu-id="484ce-223">`i-psdf<tab>` возвращает `Import-PowerShellDataFile`.</span><span class="sxs-lookup"><span data-stu-id="484ce-223">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="484ce-224">`u-akvmssdr<tab>` возвращает `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span><span class="sxs-lookup"><span data-stu-id="484ce-224">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="484ce-225">Эта функция работает только для заполнения нажатием клавиши TAB (интерактивное использование), поэтому `i-psdf` — недопустимое имя командлета в скрипте.</span><span class="sxs-lookup"><span data-stu-id="484ce-225">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="484ce-226">Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="484ce-226">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="pssubsystempluginmodel"></a><span data-ttu-id="484ce-227">PSSubsystemPluginModel</span><span class="sxs-lookup"><span data-stu-id="484ce-227">PSSubsystemPluginModel</span></span>

<span data-ttu-id="484ce-228">Эта функция включает модель подключаемого модуля подсистемы в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="484ce-228">This feature enables the subsystem plugin model in PowerShell.</span></span> <span data-ttu-id="484ce-229">Эта функция позволяет разделять компоненты `System.Management.Automation.dll` в отдельные подсистемы, находящиеся в их собственной сборке.</span><span class="sxs-lookup"><span data-stu-id="484ce-229">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="484ce-230">Такое разделение сокращает объем дискового пространства ядра PowerShell и позволяет этим компонентам стать необязательными для минимальной установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="484ce-230">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="484ce-231">В настоящее время поддерживается только подсистема **CommandPredictor**.</span><span class="sxs-lookup"><span data-stu-id="484ce-231">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="484ce-232">Эта подсистема используется вместе с модулем PSReadLine для предоставления настраиваемых подключаемых модулей прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="484ce-232">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="484ce-233">В будущем **задание**, **CommandCompleter**, **удаленное взаимодействие** и другие компоненты можно будет разделить на сборки подсистемы за пределами `System.Management.Automation.dll`.</span><span class="sxs-lookup"><span data-stu-id="484ce-233">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

<span data-ttu-id="484ce-234">Экспериментальная функция содержит новый командлет [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span><span class="sxs-lookup"><span data-stu-id="484ce-234">The experimental feature includes a new cmdlet, [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem).</span></span> <span data-ttu-id="484ce-235">Этот командлет доступен, только если функция включена.</span><span class="sxs-lookup"><span data-stu-id="484ce-235">This cmdlet is only available when the feature is enabled.</span></span> <span data-ttu-id="484ce-236">Этот командлет возвращает сведения о подсистемах, доступных в системе.</span><span class="sxs-lookup"><span data-stu-id="484ce-236">This cmdlet returns information about the subsystems that are available on the system.</span></span>
