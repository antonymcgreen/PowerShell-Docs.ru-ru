---
ms.date: 12/31/2019
keywords: powershell,командлет
title: Объект ISEEditor
ms.openlocfilehash: cb63acebc1a8bb9fa6cc07199088ae0d5441bc91
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736195"
---
# <a name="the-iseeditor-object"></a><span data-ttu-id="09b34-103">Объект ISEEditor</span><span class="sxs-lookup"><span data-stu-id="09b34-103">The ISEEditor Object</span></span>

<span data-ttu-id="09b34-104">Объект **ISEEditor** является экземпляром класса Microsoft.PowerShell.Host.ISE.ISEEditor.</span><span class="sxs-lookup"><span data-stu-id="09b34-104">An **ISEEditor** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEEditor class.</span></span> <span data-ttu-id="09b34-105">Область консоли — это объект **ISEEditor**.</span><span class="sxs-lookup"><span data-stu-id="09b34-105">The Console pane is an **ISEEditor** object.</span></span> <span data-ttu-id="09b34-106">Каждый объект [ISEFile](The-ISEFile-Object.md) имеет связанный объект **ISEEditor**.</span><span class="sxs-lookup"><span data-stu-id="09b34-106">Each [ISEFile](The-ISEFile-Object.md) object has an associated **ISEEditor** object.</span></span> <span data-ttu-id="09b34-107">В следующих разделах перечислены методы и свойства объекта **ISEEditor**.</span><span class="sxs-lookup"><span data-stu-id="09b34-107">The following sections list the methods and properties of an **ISEEditor** object.</span></span>

## <a name="methods"></a><span data-ttu-id="09b34-108">Методы</span><span class="sxs-lookup"><span data-stu-id="09b34-108">Methods</span></span>

### <a name="clear"></a><span data-ttu-id="09b34-109">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="09b34-109">Clear\(\)</span></span>

<span data-ttu-id="09b34-110">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-111">Удаляет текст в редакторе.</span><span class="sxs-lookup"><span data-stu-id="09b34-111">Clears the text in the editor.</span></span>

```powershell
# Clears the text in the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Clear()
```

### <a name="ensurevisibleint-linenumber"></a><span data-ttu-id="09b34-112">EnsureVisible\(int lineNumber\)</span><span class="sxs-lookup"><span data-stu-id="09b34-112">EnsureVisible\(int lineNumber\)</span></span>

<span data-ttu-id="09b34-113">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-113">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-114">Прокручивает редактор таким образом, чтобы отображалась строка, соответствующая значению параметра **lineNumber**.</span><span class="sxs-lookup"><span data-stu-id="09b34-114">Scrolls the editor so that the line that corresponds to the specified **lineNumber** parameter value is visible.</span></span> <span data-ttu-id="09b34-115">Метод создает исключение, если указанный номер строки находится за пределами диапазона 1, последнего номера строки, который определяет допустимые номера строк.</span><span class="sxs-lookup"><span data-stu-id="09b34-115">It throws an exception if the specified line number is outside the range of 1,last line number, which defines the valid line numbers.</span></span>

<span data-ttu-id="09b34-116">**lineNumber** — номер строки, которая будет отображена.</span><span class="sxs-lookup"><span data-stu-id="09b34-116">**lineNumber** The number of the line that is to be made visible.</span></span>

```powershell
# Scrolls the text in the Script pane so that the fifth line is in view.
$psISE.CurrentFile.Editor.EnsureVisible(5)
```

### <a name="focus"></a><span data-ttu-id="09b34-117">Focus\(\)</span><span class="sxs-lookup"><span data-stu-id="09b34-117">Focus\(\)</span></span>

<span data-ttu-id="09b34-118">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-119">Помещает редактор в фокус.</span><span class="sxs-lookup"><span data-stu-id="09b34-119">Sets the focus to the editor.</span></span>

```powershell
# Sets focus to the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### <a name="getlinelengthint-linenumber-"></a><span data-ttu-id="09b34-120">GetLineLength\(int lineNumber \)</span><span class="sxs-lookup"><span data-stu-id="09b34-120">GetLineLength\(int lineNumber \)</span></span>

<span data-ttu-id="09b34-121">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-121">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-122">Получает длину строки (в виде целого числа) по указанному номеру строки.</span><span class="sxs-lookup"><span data-stu-id="09b34-122">Gets the line length as an integer for the line that is specified by the line number.</span></span>

<span data-ttu-id="09b34-123">**lineNumber** — номер строки, длину которой необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="09b34-123">**lineNumber** The number of the line of which to get the length.</span></span>

<span data-ttu-id="09b34-124">**Возвращаемое значение** — длина строки с указанным номером.</span><span class="sxs-lookup"><span data-stu-id="09b34-124">**Returns** The line length for the line at the specified line number.</span></span>

```powershell
# Gets the length of the first line in the text of the Command pane.
$psISE.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### <a name="gotomatch"></a><span data-ttu-id="09b34-125">GoToMatch\(\)</span><span class="sxs-lookup"><span data-stu-id="09b34-125">GoToMatch\(\)</span></span>

<span data-ttu-id="09b34-126">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="09b34-126">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="09b34-127">Перемещает курсор в соответствующий знак, если свойству **CanGoToMatch** объекта редактора присвоено значение `$true`, которое присваивается, когда курсор находится непосредственно перед открывающей круглой, квадратной или фигурной скобкой (т. е. `(`,`[`,`{`) или сразу после закрывающей круглой, квадратной или фигурной скобки (т. е. `)`,`]`,`}`).</span><span class="sxs-lookup"><span data-stu-id="09b34-127">Moves the caret to the matching character if the **CanGoToMatch** property of the editor object is `$true`, which occurs when the caret is immediately before an opening parenthesis, bracket, or brace - `(`,`[`,`{` - or immediately after a closing parenthesis, bracket, or brace - `)`,`]`,`}`.</span></span> <span data-ttu-id="09b34-128">Курсор помещается перед открывающим символом или после закрывающего символа.</span><span class="sxs-lookup"><span data-stu-id="09b34-128">The caret is placed before an opening character or after a closing character.</span></span> <span data-ttu-id="09b34-129">Если свойство **CanGoToMatch** имеет значение `$false`, этот метод не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="09b34-129">If the **CanGoToMatch** property is `$false`, then this method does nothing.</span></span>

```powershell
# Goes to the matching character if CanGoToMatch() is $true
$psISE.CurrentPowerShellTab.ConsolePane.GoToMatch()
```

### <a name="inserttext-text-"></a><span data-ttu-id="09b34-130">InsertText\( text \)</span><span class="sxs-lookup"><span data-stu-id="09b34-130">InsertText\( text \)</span></span>

<span data-ttu-id="09b34-131">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-131">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-132">Заменяет выделенную область текстом или вставляет текст в текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="09b34-132">Replaces the selection with text or inserts text at the current caret position.</span></span>

<span data-ttu-id="09b34-133">**text** — строка. Вставляемый текст.</span><span class="sxs-lookup"><span data-stu-id="09b34-133">**text** - String The text to insert.</span></span>

<span data-ttu-id="09b34-134">См. [пример сценария](#scripting-example) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="09b34-134">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="select-startline-startcolumn-endline-endcolumn-"></a><span data-ttu-id="09b34-135">Select\( startLine, startColumn, endLine, endColumn \)</span><span class="sxs-lookup"><span data-stu-id="09b34-135">Select\( startLine, startColumn, endLine, endColumn \)</span></span>

<span data-ttu-id="09b34-136">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-137">Выделяет текст в области, определяемой параметрами **startLine**, **startColumn**, **endLine** и **endColumn**.</span><span class="sxs-lookup"><span data-stu-id="09b34-137">Selects the text from the **startLine**, **startColumn**, **endLine**, and **endColumn** parameters.</span></span>

<span data-ttu-id="09b34-138">**startLine** — целое число. Строка, в которой начинается выделение.</span><span class="sxs-lookup"><span data-stu-id="09b34-138">**startLine** - Integer The line where the selection starts.</span></span>

<span data-ttu-id="09b34-139">**startColumn** — целое число. Столбец в строке, в которой начинается выделение.</span><span class="sxs-lookup"><span data-stu-id="09b34-139">**startColumn** - Integer The column within the start line where the selection starts.</span></span>

<span data-ttu-id="09b34-140">**endLine** — целое число. Строка, в которой заканчивается выделение.</span><span class="sxs-lookup"><span data-stu-id="09b34-140">**endLine** - Integer The line where the selection ends.</span></span>

<span data-ttu-id="09b34-141">**endColumn** — целое число. Столбец в строке, в которой заканчивается выделение.</span><span class="sxs-lookup"><span data-stu-id="09b34-141">**endColumn** - Integer The column within the end line where the selection ends.</span></span>

<span data-ttu-id="09b34-142">См. [пример сценария](#scripting-example) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="09b34-142">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="selectcaretline"></a><span data-ttu-id="09b34-143">SelectCaretLine\(\)</span><span class="sxs-lookup"><span data-stu-id="09b34-143">SelectCaretLine\(\)</span></span>

<span data-ttu-id="09b34-144">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-144">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-145">Выделяет всю строку текста, в которой в данный момент находится курсор.</span><span class="sxs-lookup"><span data-stu-id="09b34-145">Selects the entire line of text that currently contains the caret.</span></span>

```powershell
# First, set the caret position on line 5.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
# Now select that entire line of text
$psISE.CurrentFile.Editor.SelectCaretLine()
```

### <a name="setcaretposition-linenumber-columnnumber-"></a><span data-ttu-id="09b34-146">SetCaretPosition\( lineNumber, columnNumber \)</span><span class="sxs-lookup"><span data-stu-id="09b34-146">SetCaretPosition\( lineNumber, columnNumber \)</span></span>

<span data-ttu-id="09b34-147">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-147">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-148">Задает положение курсора по номеру строки и номеру столбца.</span><span class="sxs-lookup"><span data-stu-id="09b34-148">Sets the caret position at the line number and the column number.</span></span> <span data-ttu-id="09b34-149">Метод создает исключение, если номер строки или номер столбца курсора находятся вне соответствующих допустимых диапазонов.</span><span class="sxs-lookup"><span data-stu-id="09b34-149">It throws an exception if either the caret line number or the caret column number are out of their respective valid ranges.</span></span>

<span data-ttu-id="09b34-150">**lineNumber** — целое число. Номер строки курсора.</span><span class="sxs-lookup"><span data-stu-id="09b34-150">**lineNumber** - Integer The caret line number.</span></span>

<span data-ttu-id="09b34-151">**columnNumber** — целое число. Номер столбца курсора.</span><span class="sxs-lookup"><span data-stu-id="09b34-151">**columnNumber** - Integer The caret column number.</span></span>

```powershell
# Set the CaretPosition.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
```

### <a name="toggleoutliningexpansion"></a><span data-ttu-id="09b34-152">ToggleOutliningExpansion\(\)</span><span class="sxs-lookup"><span data-stu-id="09b34-152">ToggleOutliningExpansion\(\)</span></span>

<span data-ttu-id="09b34-153">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="09b34-153">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="09b34-154">Выполняет свертывание или развертывание всех разделов структуры.</span><span class="sxs-lookup"><span data-stu-id="09b34-154">Causes all the outline sections to expand or collapse.</span></span>

```powershell
# Toggle the outlining expansion
$psISE.CurrentFile.Editor.ToggleOutliningExpansion()
```

## <a name="properties"></a><span data-ttu-id="09b34-155">Свойства</span><span class="sxs-lookup"><span data-stu-id="09b34-155">Properties</span></span>

### <a name="cangotomatch"></a><span data-ttu-id="09b34-156">CanGoToMatch</span><span class="sxs-lookup"><span data-stu-id="09b34-156">CanGoToMatch</span></span>

<span data-ttu-id="09b34-157">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="09b34-157">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="09b34-158">Логическое свойство, доступное только для чтения, которое указывает, находится ли курсор рядом с круглой, квадратной или фигурной скобкой — `()`, `[]`, `{}`.</span><span class="sxs-lookup"><span data-stu-id="09b34-158">The read-only Boolean property to indicate whether the caret is next to a parenthesis, bracket, or brace - `()`, `[]`, `{}`.</span></span> <span data-ttu-id="09b34-159">Если курсор находится непосредственно перед открывающим символом или сразу после парного закрывающего символа, то это свойство имеет значение `$true`.</span><span class="sxs-lookup"><span data-stu-id="09b34-159">If the caret is immediately before the opening character or immediately after the closing character of a pair, then this property value is `$true`.</span></span> <span data-ttu-id="09b34-160">В противном случае значение равно `$false`.</span><span class="sxs-lookup"><span data-stu-id="09b34-160">Otherwise, it is `$false`.</span></span>

```powershell
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psISE.CurrentFile.Editor.CanGoToMatch
```

### <a name="caretcolumn"></a><span data-ttu-id="09b34-161">CaretColumn</span><span class="sxs-lookup"><span data-stu-id="09b34-161">CaretColumn</span></span>

<span data-ttu-id="09b34-162">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-162">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-163">Свойство только для чтения, которое получает номер столбца, соответствующего позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="09b34-163">The read-only property that gets the column number that corresponds to the position of the caret.</span></span>

```powershell
# Get the CaretColumn.
$psISE.CurrentFile.Editor.CaretColumn
```

### <a name="caretline"></a><span data-ttu-id="09b34-164">CaretLine</span><span class="sxs-lookup"><span data-stu-id="09b34-164">CaretLine</span></span>

<span data-ttu-id="09b34-165">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-165">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-166">Свойство только для чтения, которое получает номер строки, содержащей курсор.</span><span class="sxs-lookup"><span data-stu-id="09b34-166">The read-only property that gets the number of the line that contains the caret.</span></span>

```powershell
# Get the CaretLine.
$psISE.CurrentFile.Editor.CaretLine
```

### <a name="caretlinetext"></a><span data-ttu-id="09b34-167">CaretLineText</span><span class="sxs-lookup"><span data-stu-id="09b34-167">CaretLineText</span></span>

<span data-ttu-id="09b34-168">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-168">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-169">Свойство только для чтения, которое получает полную строку текста, содержащую курсор.</span><span class="sxs-lookup"><span data-stu-id="09b34-169">The read-only property that gets the complete line of text that contains the caret.</span></span>

```powershell
# Get all of the text on the line that contains the caret.
$psISE.CurrentFile.Editor.CaretLineText
```

### <a name="linecount"></a><span data-ttu-id="09b34-170">LineCount</span><span class="sxs-lookup"><span data-stu-id="09b34-170">LineCount</span></span>

<span data-ttu-id="09b34-171">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-171">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-172">Свойство только для чтения, которое получает число строк из редактора.</span><span class="sxs-lookup"><span data-stu-id="09b34-172">The read-only property that gets the line count from the editor.</span></span>

```powershell
# Get the LineCount.
$psISE.CurrentFile.Editor.LineCount
```

### <a name="selectedtext"></a><span data-ttu-id="09b34-173">SelectedText</span><span class="sxs-lookup"><span data-stu-id="09b34-173">SelectedText</span></span>

<span data-ttu-id="09b34-174">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-174">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-175">Свойство только для чтения, которое получает выделенный текст из редактора.</span><span class="sxs-lookup"><span data-stu-id="09b34-175">The read-only property that gets the selected text from the editor.</span></span>

<span data-ttu-id="09b34-176">См. [пример сценария](#scripting-example) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="09b34-176">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="text"></a><span data-ttu-id="09b34-177">текст</span><span class="sxs-lookup"><span data-stu-id="09b34-177">Text</span></span>

<span data-ttu-id="09b34-178">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="09b34-178">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="09b34-179">Свойство для чтения и записи, которое получает или задает текст в редакторе.</span><span class="sxs-lookup"><span data-stu-id="09b34-179">The read/write property that gets or sets the text in the editor.</span></span>

<span data-ttu-id="09b34-180">См. [пример сценария](#scripting-example) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="09b34-180">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

## <a name="scripting-example"></a><span data-ttu-id="09b34-181">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="09b34-181">Scripting Example</span></span>

```powershell
# This illustrates how you can use the length of a line to
# select the entire line and shows how you can make it lowercase.
# You must run this in the Console pane. It will not run in the Script pane.
# Begin by getting a variable that points to the editor.
$myEditor = $psISE.CurrentFile.Editor
# Clear the text in the current file editor.
$myEditor.Clear()

# Make sure the file has five lines of text.
$myEditor.InsertText("LINE1 `n")
$myEditor.InsertText("LINE2 `n")
$myEditor.InsertText("LINE3 `n")
$myEditor.InsertText("LINE4 `n")
$myEditor.InsertText("LINE5 `n")

# Use the GetLineLength method to get the length of the third line.
$endColumn = $myEditor.GetLineLength(3)
# Select the text in the first three lines.
$myEditor.Select(1, 1, 3, $endColumn + 1)
$selection = $myEditor.SelectedText
# Clear all the text in the editor.
$myEditor.Clear()
# Add the selected text back, but in lower case.
$myEditor.InsertText($selection.ToLower())
```

## <a name="see-also"></a><span data-ttu-id="09b34-182">См. также:</span><span class="sxs-lookup"><span data-stu-id="09b34-182">See Also</span></span>

- [<span data-ttu-id="09b34-183">Объект ISEFile</span><span class="sxs-lookup"><span data-stu-id="09b34-183">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="09b34-184">Объект PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="09b34-184">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="09b34-185">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09b34-185">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="09b34-186">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="09b34-186">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
