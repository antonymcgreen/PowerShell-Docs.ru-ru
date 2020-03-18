---
title: Руководство по стилю для документации PowerShell
description: В этой статье приводятся стилевые рекомендации для написания документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 964536c5195c3bb8abd98b5996a96fc7b9362489
ms.sourcegitcommit: c97dcf1e00ef540e7464c36c88f841474060044c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402581"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="a66e9-103">Руководство по стилю для документации PowerShell</span><span class="sxs-lookup"><span data-stu-id="a66e9-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="a66e9-104">В этой статье представлено руководство по стилю для документации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="a66e9-105">Эта статья основана на сведениях, указанных в разделе [Обзор](overview.md#get-started-writing-docs).</span><span class="sxs-lookup"><span data-stu-id="a66e9-105">This builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="a66e9-106">Терминология продукта</span><span class="sxs-lookup"><span data-stu-id="a66e9-106">Product Terminology</span></span>

<span data-ttu-id="a66e9-107">Существует несколько вариантов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-107">There are several variants of PowerShell.</span></span>
<span data-ttu-id="a66e9-108">В этой таблице определены некоторые из различных терминов, используемых для обсуждения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-108">This table defines some of the different terms used to discuss PowerShell.</span></span>

- <span data-ttu-id="a66e9-109">**PowerShell** — используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a66e9-109">**PowerShell** - This is the default.</span></span> <span data-ttu-id="a66e9-110">Это понятие подразумевает PowerShell 7 и последующих версий.</span><span class="sxs-lookup"><span data-stu-id="a66e9-110">We consider PowerShell 7 and beyond to be the one, true PowerShell going forward.</span></span>

- <span data-ttu-id="a66e9-111">**PowerShell Core** — PowerShell на основе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a66e9-111">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="a66e9-112">Понятие **Core** должно использоваться только в тех ситуациях, когда необходимо отличить PowerShell Core от Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-112">Usage of the term **Core** should be limited to cases where it is necessary to differentiate it from Windows PowerShell.</span></span>

- <span data-ttu-id="a66e9-113">**Windows PowerShell** — PowerShell на основе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a66e9-113">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="a66e9-114">Windows PowerShell поставляется только в Windows, и для его работы требуется полная версия платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a66e9-114">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

<span data-ttu-id="a66e9-115">В общем случае ссылки на "Windows PowerShell" в документации можно изменить на "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="a66e9-115">In general, references to "Windows PowerShell" in documentation can be changed to "PowerShell".</span></span>
<span data-ttu-id="a66e9-116">"Windows PowerShell" **не следует** изменять на "PowerShell" при обсуждении технологии, специфичной для Windows.</span><span class="sxs-lookup"><span data-stu-id="a66e9-116">"Windows PowerShell" should **not** be changed when Windows-specific technology is being discussed.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="a66e9-117">Особенности Markdown</span><span class="sxs-lookup"><span data-stu-id="a66e9-117">Markdown specifics</span></span>

<span data-ttu-id="a66e9-118">В системе Microsoft Open Publishing System (OPS), лежащей в основе нашей документации, используется [markdig][] для обработки документов Markdown.</span><span class="sxs-lookup"><span data-stu-id="a66e9-118">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="a66e9-119">Markdig анализирует документы на основе правил последней версии спецификации [CommonMark][].</span><span class="sxs-lookup"><span data-stu-id="a66e9-119">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="a66e9-120">Новая версия спецификации CommonMark является более строгой в отношении структуры некоторых элементов Markdown.</span><span class="sxs-lookup"><span data-stu-id="a66e9-120">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="a66e9-121">Обратите особое внимание на сведения, приведенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="a66e9-121">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="a66e9-122">Пустые строки, пробелы и знаки табуляции</span><span class="sxs-lookup"><span data-stu-id="a66e9-122">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="a66e9-123">Удалите дублирующиеся пустые строки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-123">Remove duplicate blank lines.</span></span> <span data-ttu-id="a66e9-124">Несколько пустых строк отображаются в виде одной пустой строки в формате HTML, поэтому указывать несколько пустых строк не требуется.</span><span class="sxs-lookup"><span data-stu-id="a66e9-124">Multiple blank lines render as a single blank line in HTML so there is not purpose for multiple blank lines.</span></span>

<span data-ttu-id="a66e9-125">Пустые строки также обозначают конец блока в Markdown.</span><span class="sxs-lookup"><span data-stu-id="a66e9-125">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="a66e9-126">Между блоками Markdown разных типов (например, между абзацем и списком или заголовком) должна быть одна пустая строка.</span><span class="sxs-lookup"><span data-stu-id="a66e9-126">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

> [!NOTE]
> <span data-ttu-id="a66e9-127">Промежутки очень важны в Markdown.</span><span class="sxs-lookup"><span data-stu-id="a66e9-127">Spacing is significant in Markdown.</span></span> <span data-ttu-id="a66e9-128">Вместо символов табуляции всегда используйте пробелы.</span><span class="sxs-lookup"><span data-stu-id="a66e9-128">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="a66e9-129">Удалите лишние пробелы в конце строк.</span><span class="sxs-lookup"><span data-stu-id="a66e9-129">Remove extra spaces at the end of lines.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="a66e9-130">Заголовки</span><span class="sxs-lookup"><span data-stu-id="a66e9-130">Titles and headings</span></span>

<span data-ttu-id="a66e9-131">Используйте только [стиль заголовков с ATX][atx] (стиль #, а не стиль заголовков `=` или `-`).</span><span class="sxs-lookup"><span data-stu-id="a66e9-131">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="a66e9-132">Используйте регистр обычных предложений: начинать с заглавной буквы следует только определенные существительные и заголовки</span><span class="sxs-lookup"><span data-stu-id="a66e9-132">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="a66e9-133">Между `#` и первой буквой заголовка должен быть один пробел</span><span class="sxs-lookup"><span data-stu-id="a66e9-133">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="a66e9-134">До и после заголовка необходимо указать по одной пустой строке</span><span class="sxs-lookup"><span data-stu-id="a66e9-134">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="a66e9-135">В документе должен быть только один заголовок H1</span><span class="sxs-lookup"><span data-stu-id="a66e9-135">Only one H1 per document</span></span>
- <span data-ttu-id="a66e9-136">Уровни заголовков должны увеличиваться на единицу.</span><span class="sxs-lookup"><span data-stu-id="a66e9-136">Header levels should increment by one.</span></span> <span data-ttu-id="a66e9-137">Не пропускайте уровни</span><span class="sxs-lookup"><span data-stu-id="a66e9-137">Do not skip levels</span></span>
- <span data-ttu-id="a66e9-138">Не используйте полужирный шрифт и другую разметку в заголовках</span><span class="sxs-lookup"><span data-stu-id="a66e9-138">Do not use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="a66e9-139">Ограничьте длину строки 100 символами</span><span class="sxs-lookup"><span data-stu-id="a66e9-139">Limit line length to 100 characters</span></span>

<span data-ttu-id="a66e9-140">Это относится к концептуальным статьям и к справочнику по командлетам.</span><span class="sxs-lookup"><span data-stu-id="a66e9-140">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="a66e9-141">Разделы "about" ограничены 80 символами.</span><span class="sxs-lookup"><span data-stu-id="a66e9-141">About_topics are limited to 80 characters.</span></span>
<span data-ttu-id="a66e9-142">Ограничение длины строки повышает удобочитаемость разностных сравнений и журнала Git.</span><span class="sxs-lookup"><span data-stu-id="a66e9-142">Limiting the line length improves the readability git diffs and history.</span></span> <span data-ttu-id="a66e9-143">Кроме того, это упрощает изменение содержимого для других авторов.</span><span class="sxs-lookup"><span data-stu-id="a66e9-143">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="a66e9-144">Используйте расширение [Reflow Markdown][reflow] в Visual Studio Code, чтобы легко переформатировать абзацы в соответствии с заданной длиной строки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-144">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

### <a name="lists"></a><span data-ttu-id="a66e9-145">Списки</span><span class="sxs-lookup"><span data-stu-id="a66e9-145">Lists</span></span>

<span data-ttu-id="a66e9-146">Если список содержит несколько предложений или абзацев, используйте заголовки нижнего уровня, а не список.</span><span class="sxs-lookup"><span data-stu-id="a66e9-146">If your list contains multiple sentences or paragraphs, consider using a sub-level header rather than a list.</span></span>

<span data-ttu-id="a66e9-147">До и после списка необходимо указать по одной пустой строке.</span><span class="sxs-lookup"><span data-stu-id="a66e9-147">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="a66e9-148">Неупорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="a66e9-148">Unordered lists</span></span>

<span data-ttu-id="a66e9-149">Не ставьте в конце элементов списка точку (только если они не содержат несколько предложений).</span><span class="sxs-lookup"><span data-stu-id="a66e9-149">Do not end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="a66e9-150">Используйте знак дефиса (`-`) для обозначения элементов списка.</span><span class="sxs-lookup"><span data-stu-id="a66e9-150">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="a66e9-151">Это позволяет избежать путаницы с полужирной или курсивной разметкой, в которой используется звездочка [`*`].</span><span class="sxs-lookup"><span data-stu-id="a66e9-151">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="a66e9-152">Чтобы включить абзац или другие элементы в элемент маркированного списка, вставьте разрыв строки и выровняйте отступы с первым символом после маркера.</span><span class="sxs-lookup"><span data-stu-id="a66e9-152">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="a66e9-153">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-153">For example:</span></span>

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="a66e9-154">Это список, содержащий вложенные элементы в элементе маркированного списка.</span><span class="sxs-lookup"><span data-stu-id="a66e9-154">This is a list that contains sub-elements under a bullet item.</span></span>

- <span data-ttu-id="a66e9-155">Первый элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="a66e9-155">First bullet item</span></span>

  <span data-ttu-id="a66e9-156">Предложение, объясняющее первый маркер.</span><span class="sxs-lookup"><span data-stu-id="a66e9-156">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="a66e9-157">Вложенный элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="a66e9-157">Sub-bullet item</span></span>

    <span data-ttu-id="a66e9-158">Предложение, объясняющее вложенный элемент.</span><span class="sxs-lookup"><span data-stu-id="a66e9-158">Sentence explaining the sub-bullet.</span></span>

- <span data-ttu-id="a66e9-159">Второй элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="a66e9-159">Second bullet item</span></span>
- <span data-ttu-id="a66e9-160">Третий элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="a66e9-160">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="a66e9-161">Упорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="a66e9-161">Ordered lists</span></span>

<span data-ttu-id="a66e9-162">Чтобы включить абзац или другие элементы в элемент нумерованного списка, выровняйте отступы с первым символом после номера элемента.</span><span class="sxs-lookup"><span data-stu-id="a66e9-162">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="a66e9-163">Для всех элементов нумерованного списка необходимо указать число `1.` вместо того, чтобы увеличивать номер каждого элемента вручную.</span><span class="sxs-lookup"><span data-stu-id="a66e9-163">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="a66e9-164">Markdown увеличит значения автоматически при выводе.</span><span class="sxs-lookup"><span data-stu-id="a66e9-164">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="a66e9-165">Это упрощает изменение порядка элементов и стандартизирует отступы для вложенного содержимого.</span><span class="sxs-lookup"><span data-stu-id="a66e9-165">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="a66e9-166">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-166">For example:</span></span>

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

<span data-ttu-id="a66e9-167">Итоговый тест Markdown будет выведен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a66e9-167">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="a66e9-168">Для первого элемента добавьте один пробел после цифры 1.</span><span class="sxs-lookup"><span data-stu-id="a66e9-168">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="a66e9-169">Длинные предложения необходимо переносить на следующую строку и выравнивать по первому символу после маркера нумерованного списка.</span><span class="sxs-lookup"><span data-stu-id="a66e9-169">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="a66e9-170">Чтобы включить второй элемент (такой, как этот), вставьте разрыв строки после первого элемента и выровняйте отступы.</span><span class="sxs-lookup"><span data-stu-id="a66e9-170">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="a66e9-171">Отступ второго элемента необходимо выравнивать с первым символом после маркера нумерованного списка.</span><span class="sxs-lookup"><span data-stu-id="a66e9-171">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="a66e9-172">Для однозначных номеров элементов, таких как этот, необходимо осуществлять отступ по столбцу 4.</span><span class="sxs-lookup"><span data-stu-id="a66e9-172">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="a66e9-173">Для двузначных номеров элементов, например, для элемента № 10, необходимо осуществлять отступ по столбцу 5.</span><span class="sxs-lookup"><span data-stu-id="a66e9-173">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="a66e9-174">Следующий элемент нумерованного списка начинается здесь.</span><span class="sxs-lookup"><span data-stu-id="a66e9-174">The next numbered item starts here.</span></span>

### <a name="formatting-command-syntax-elements"></a><span data-ttu-id="a66e9-175">Элементы синтаксиса команды форматирования</span><span class="sxs-lookup"><span data-stu-id="a66e9-175">Formatting command syntax elements</span></span>

- <span data-ttu-id="a66e9-176">Всегда используйте полные имена командлетов и параметров.</span><span class="sxs-lookup"><span data-stu-id="a66e9-176">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="a66e9-177">Старайтесь не использовать псевдонимы, если только вы не демонстрируете псевдоним специально.</span><span class="sxs-lookup"><span data-stu-id="a66e9-177">Avoid using aliases unless you are specifically demonstrating the alias.</span></span>

- <span data-ttu-id="a66e9-178">В абзацах ключевые слова языка, имена командлетов, переменные и пути к файлам должны быть заключены в обратные кавычки (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="a66e9-178">Within a paragraph, language keywords, cmdlet names, variables, and file paths should be wrapped in backtick (`` ` ``) characters.</span></span> <span data-ttu-id="a66e9-179">Имена свойств, параметров и классов должны быть выделены **полужирным** шрифтом.</span><span class="sxs-lookup"><span data-stu-id="a66e9-179">Property, parameter, and class names should be **bold**.</span></span>

  <span data-ttu-id="a66e9-180">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-180">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

- <span data-ttu-id="a66e9-181">При ссылке на параметр по имени его имя должно быть выделено **полужирным** шрифтом.</span><span class="sxs-lookup"><span data-stu-id="a66e9-181">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="a66e9-182">При демонстрации использования параметра с префиксом дефиса параметр должен быть заключен в обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-182">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="a66e9-183">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-183">For example:</span></span>

  ```markdown
  The parameter's name is **Name**, but it is typed as `-Name` when used on the command
  line as a parameter.
  ```

- <span data-ttu-id="a66e9-184">При ссылке на внешние команды (exe-файлы, сценарии и т. д.) имя команды должно быть выделено полужирным шрифтом и указано прописными буквами (или начинаться с заглавной буквы, если оно идет в начале предложения). Имя команды также должно включать соответствующее расширение файла.</span><span class="sxs-lookup"><span data-stu-id="a66e9-184">When referring to external commands (EXEs, scripts, etc.), the command name should be bold, all lowercase (or capitalized if at the beginning of a sentence), and include the appropriate file extension.</span></span> <span data-ttu-id="a66e9-185">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-185">For example:</span></span>

  ```markdown
  For example, on Windows systems, you can use the `net start` and `net stop` commands
  to start and stop a service. **Sc.exe** is another service control tool for Windows.
  That name does not fit into the naming pattern for the **net.exe** service commands.
  ```

- <span data-ttu-id="a66e9-186">При демонстрации примера использования внешней команды этот пример должен быть заключен в обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-186">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
  <span data-ttu-id="a66e9-187">При конфликте имен с псевдонимом необходимо включить расширение файла в пример команды.</span><span class="sxs-lookup"><span data-stu-id="a66e9-187">When there is a name collisions with an alias you must include the file extension in the command example.</span></span> <span data-ttu-id="a66e9-188">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-188">For example:</span></span>

  ```markdown
  To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
  ```

- <span data-ttu-id="a66e9-189">При оформлении абстрактной статьи (в отличие от справочных материалов) представляйте первый экземпляр имени командлета в виде гиперссылки на документацию по командлетам.</span><span class="sxs-lookup"><span data-stu-id="a66e9-189">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="a66e9-190">Не используйте обратные кавычки, полужирный шрифт или другую разметку в квадратных скобках гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-190">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="a66e9-191">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-191">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="a66e9-192">Дополнительные сведения см. в разделе [Гиперссылки](#hyperlinks) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a66e9-192">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

### <a name="images"></a><span data-ttu-id="a66e9-193">Изображения</span><span class="sxs-lookup"><span data-stu-id="a66e9-193">Images</span></span>

<span data-ttu-id="a66e9-194">Для включения изображения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a66e9-194">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="a66e9-195">Здесь `alt text` — краткое описание изображения, а `<folder path>` — относительный путь к изображению.</span><span class="sxs-lookup"><span data-stu-id="a66e9-195">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="a66e9-196">Необходимо указать дополнительный текст для средств чтения с экрана для лиц с ослабленным зрением.</span><span class="sxs-lookup"><span data-stu-id="a66e9-196">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="a66e9-197">Этот текст также пригодится при возникновении ошибки на сайте, из-за которой изображение не будет отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="a66e9-197">It is also useful in case there is a site bug where the image cannot be rendered.</span></span>

<span data-ttu-id="a66e9-198">Изображения должны храниться в папке `media/<article-name>` в подпапке, содержащей статью.</span><span class="sxs-lookup"><span data-stu-id="a66e9-198">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="a66e9-199">Изображения не должны одновременно использоваться в нескольких статьях.</span><span class="sxs-lookup"><span data-stu-id="a66e9-199">Images should not be shared between articles.</span></span> <span data-ttu-id="a66e9-200">Создайте подпапку, соответствующую имени файла статьи, в папке `media`.</span><span class="sxs-lookup"><span data-stu-id="a66e9-200">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="a66e9-201">Скопируйте изображения для этой статьи в созданную подпапку.</span><span class="sxs-lookup"><span data-stu-id="a66e9-201">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="a66e9-202">Если изображение используется в нескольких статьях, необходимо скопировать это изображение в каждую подпапку с изображениями для соответствующей статьи.</span><span class="sxs-lookup"><span data-stu-id="a66e9-202">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="a66e9-203">Это позволяет избежать ситуации, когда изменение изображения в одной статье влияет на другую статью.</span><span class="sxs-lookup"><span data-stu-id="a66e9-203">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="a66e9-204">Поддерживаются следующие типы файлов изображений: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span><span class="sxs-lookup"><span data-stu-id="a66e9-204">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="a66e9-205">Расширения Markdown, поддерживаемые Open Publishing</span><span class="sxs-lookup"><span data-stu-id="a66e9-205">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="a66e9-206">[Пакет создания документации Майкрософт](/contribute/how-to-write-docs-auth-pack) содержит средства, которые поддерживают функции, уникальные для нашей системы публикации.</span><span class="sxs-lookup"><span data-stu-id="a66e9-206">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="a66e9-207">Оповещения — это расширение Markdown для создания блочных цитат, которые отображаются на сайте docs.microsoft.com с цветовым оформлением и значками, указывающими на значимость содержимого.</span><span class="sxs-lookup"><span data-stu-id="a66e9-207">Alerts are a Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="a66e9-208">Поддерживаются следующие типы оповещений:</span><span class="sxs-lookup"><span data-stu-id="a66e9-208">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="a66e9-209">На сайте docs.microsoft.com эти оповещения выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a66e9-209">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="a66e9-210">Информация, которую пользователь должен заметить даже при беглом чтении текста.</span><span class="sxs-lookup"><span data-stu-id="a66e9-210">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="a66e9-211">Дополнительные сведения, которые могут пригодиться пользователю для успешного выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="a66e9-211">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a66e9-212">Обязательные сведения, необходимые для успешного выполнения действия пользователем.</span><span class="sxs-lookup"><span data-stu-id="a66e9-212">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="a66e9-213">Возможные отрицательные последствия действия.</span><span class="sxs-lookup"><span data-stu-id="a66e9-213">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="a66e9-214">Определенные опасные последствия действия.</span><span class="sxs-lookup"><span data-stu-id="a66e9-214">Dangerous certain consequences of an action.</span></span>

## <a name="hyperlinks"></a><span data-ttu-id="a66e9-215">Гиперссылки</span><span class="sxs-lookup"><span data-stu-id="a66e9-215">Hyperlinks</span></span>

- <span data-ttu-id="a66e9-216">Старайтесь не указывать обыкновенные URL-адреса в тексте.</span><span class="sxs-lookup"><span data-stu-id="a66e9-216">Avoid using bare URLs.</span></span> <span data-ttu-id="a66e9-217">Для ссылок необходимо использовать синтаксис Markdown `[friendlyname](url-or-path)`</span><span class="sxs-lookup"><span data-stu-id="a66e9-217">Links should use Markdown syntax `[friendlyname](url-or-path)`</span></span>
- <span data-ttu-id="a66e9-218">Обыкновенные URL-адреса могут использоваться в тексте при необходимости, но они должны быть заключены в обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-218">Bare URLs may be used when necessary, but should be enclosed in backticks.</span></span> <span data-ttu-id="a66e9-219">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-219">For example:</span></span>

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

- <span data-ttu-id="a66e9-220">По возможности следует использовать URL-адреса HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a66e9-220">URL links should be HTTPS when possible.</span></span>
- <span data-ttu-id="a66e9-221">Ссылки должны иметь понятное имя (обычно это заголовок соответствующего раздела)</span><span class="sxs-lookup"><span data-stu-id="a66e9-221">Links must have a friendly name, usually the title of the linked topic</span></span>
- <span data-ttu-id="a66e9-222">Все элементы в разделе "Связанные ссылки" в нижней части страницы должны быть оформлены как гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-222">All items in the "related links" section at the bottom should be hyperlinked.</span></span>
- <span data-ttu-id="a66e9-223">Не используйте обратные кавычки, полужирный шрифт или другую разметку в квадратных скобках гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-223">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

### <a name="linking-to-other-content"></a><span data-ttu-id="a66e9-224">Ссылки на другое содержимое</span><span class="sxs-lookup"><span data-stu-id="a66e9-224">Linking to other content</span></span>

<span data-ttu-id="a66e9-225">Существует два типа гиперссылок, поддерживаемых системой публикации: URL-адреса и ссылки на файлы.</span><span class="sxs-lookup"><span data-stu-id="a66e9-225">There are two types of hyperlinks supported by the publishing system: URLs and file links.</span></span>

<span data-ttu-id="a66e9-226">В качестве URL-адреса можно указать путь URL-адреса по отношению к корню сайта docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a66e9-226">A URL link can be a URL path that is relative to the root of docs.microsoft.com.</span></span> <span data-ttu-id="a66e9-227">Также можно указать абсолютный URL-адрес в соответствии с синтаксисом полного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="a66e9-227">Or an absolute URL that include the full URL syntax.</span></span> <span data-ttu-id="a66e9-228">(Например, `https:/github.com/MicrosoftDocs/PowerShell-Docs`)</span><span class="sxs-lookup"><span data-stu-id="a66e9-228">(For example: `https:/github.com/MicrosoftDocs/PowerShell-Docs`)</span></span>

- <span data-ttu-id="a66e9-229">Используйте URL-адреса для ссылки на содержимое, расположенное за пределами PowerShell, а также для ссылок между справкой по командлетам и абстрактными статьями в документации по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-229">Use URL links when linking to content outside of PowerShell-Docs or between cmdlet reference and conceptual articles within PowerShell-docs.</span></span>
- <span data-ttu-id="a66e9-230">Самый простой способ получить относительную ссылку — скопировать URL-адрес из браузера, а затем удалить `https://docs.microsoft.com/en-us` и вставить оставшуюся часть ссылки в Markdown.</span><span class="sxs-lookup"><span data-stu-id="a66e9-230">The simplest way to link create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span>
   - <span data-ttu-id="a66e9-231">Не включайте языковой стандарт в URL-адреса страниц на сайтах Майкрософт (например,</span><span class="sxs-lookup"><span data-stu-id="a66e9-231">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="a66e9-232">удалите из URL-адреса "/en-us").</span><span class="sxs-lookup"><span data-stu-id="a66e9-232">remove "/en-us" from URL).</span></span>
- <span data-ttu-id="a66e9-233">Во всех URL-адресах, указывающих на внешние веб-сайты, должен использоваться префикс HTTPS, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="a66e9-233">All URLs to external websites should use HTTPS unless that is not valid for the target site.</span></span>

<span data-ttu-id="a66e9-234">Ссылка на файл используется для связи одной справочной статьи с другой или одной абстрактной статьи с другой.</span><span class="sxs-lookup"><span data-stu-id="a66e9-234">A file link is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="a66e9-235">Если необходимо создать ссылку на справочную статью для определенной версии PowerShell, используйте URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="a66e9-235">If you need to link to a reference article for a specific version of PowerShell, then you need to use a URL link.</span></span>

- <span data-ttu-id="a66e9-236">Ссылки на файлы содержат относительный путь к файлу (например, `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="a66e9-236">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
- <span data-ttu-id="a66e9-237">Во всех путях к файлам должна использоваться косая черта (`/`)</span><span class="sxs-lookup"><span data-stu-id="a66e9-237">All file paths use forward-slash (`/`) characters</span></span>

## <a name="formatting-code-samples"></a><span data-ttu-id="a66e9-238">Форматирование блоков кода</span><span class="sxs-lookup"><span data-stu-id="a66e9-238">Formatting code samples</span></span>

<span data-ttu-id="a66e9-239">Markdown поддерживает два различных стиля кода:</span><span class="sxs-lookup"><span data-stu-id="a66e9-239">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="a66e9-240">Фрагменты кода (встроенный код) — помечаются одной обратной кавычкой (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="a66e9-240">Code spans (inline) - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="a66e9-241">Они используются внутри абзаца, а не в виде автономного блока.</span><span class="sxs-lookup"><span data-stu-id="a66e9-241">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="a66e9-242">Блоки кода — многострочный блок, окруженный тройными обратными кавычками (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="a66e9-242">Code blocks - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="a66e9-243">В блоках кода после обратных кавычек также может быть указана метка языка.</span><span class="sxs-lookup"><span data-stu-id="a66e9-243">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="a66e9-244">При указании метки языка включается подсветка синтаксиса для содержимого блока кода.</span><span class="sxs-lookup"><span data-stu-id="a66e9-244">The language label enables syntax highlighting for the contents of the code block.</span></span>

### <a name="using-code-blocks"></a><span data-ttu-id="a66e9-245">Использование блоков кода</span><span class="sxs-lookup"><span data-stu-id="a66e9-245">Using code blocks</span></span>

<span data-ttu-id="a66e9-246">Markdown позволяет обозначать блоки кода с помощью отступов, но такой способ может вызвать проблемы, и его следует избегать.</span><span class="sxs-lookup"><span data-stu-id="a66e9-246">Markdown allows for indentation to signify a code block, but this pattern can be problematic and should be avoided.</span></span> <span data-ttu-id="a66e9-247">Все блоки кода должны находиться в границах кода.</span><span class="sxs-lookup"><span data-stu-id="a66e9-247">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="a66e9-248">Граница кода — это блок кода, заключенный в строки с тройными обратными кавычками (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="a66e9-248">A code fence is a block of code surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="a66e9-249">Маркеры границ кода должны располагаться на отдельных строках до и после примера кода.</span><span class="sxs-lookup"><span data-stu-id="a66e9-249">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="a66e9-250">Метка в начале блока кода может содержать метку языка.</span><span class="sxs-lookup"><span data-stu-id="a66e9-250">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="a66e9-251">Система публикации Майкрософт Open Publishing System (OPS) использует метки языка для подсветки синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="a66e9-251">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="a66e9-252">OPS также добавляет кнопку **Копировать**, которая копирует содержимое блока кода в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="a66e9-252">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="a66e9-253">Это позволяет быстро вставить код в сценарий для тестирования примера кода.</span><span class="sxs-lookup"><span data-stu-id="a66e9-253">This allows you to quickly paste the code into a script for testing the code example.</span></span> <span data-ttu-id="a66e9-254">Однако не все примеры в нашей документации предназначены для выполнения.</span><span class="sxs-lookup"><span data-stu-id="a66e9-254">However, not all examples in our documentation are intended to be run.</span></span> <span data-ttu-id="a66e9-255">Некоторые блоки кода просто иллюстрируют концепцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-255">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="a66e9-256">В нашей документации используются два типа блоков кода:</span><span class="sxs-lookup"><span data-stu-id="a66e9-256">There are two types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="a66e9-257">Иллюстративные примеры</span><span class="sxs-lookup"><span data-stu-id="a66e9-257">Illustrative examples</span></span>
2. <span data-ttu-id="a66e9-258">Примеры для выполнения</span><span class="sxs-lookup"><span data-stu-id="a66e9-258">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="a66e9-259">Блоки кода синтаксиса</span><span class="sxs-lookup"><span data-stu-id="a66e9-259">Syntax code blocks</span></span>

<span data-ttu-id="a66e9-260">В этом примере показаны все возможные параметры командлета `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="a66e9-260">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
  [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
  [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="a66e9-261">В этом примере описана инструкция `for` с использованием обобщенных понятий:</span><span class="sxs-lookup"><span data-stu-id="a66e9-261">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="a66e9-262">Иллюстративные примеры</span><span class="sxs-lookup"><span data-stu-id="a66e9-262">Illustrative examples</span></span>

<span data-ttu-id="a66e9-263">Иллюстративные примеры используются для объяснения концепции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-263">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="a66e9-264">Они не предназначены для копирования в буфер обмена с целью последующего выполнения.</span><span class="sxs-lookup"><span data-stu-id="a66e9-264">They are not meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="a66e9-265">Они чаще всего используются для простых примеров, код которых легко набрать.</span><span class="sxs-lookup"><span data-stu-id="a66e9-265">These are most commonly used for simple examples that are easy to type.</span></span>
<span data-ttu-id="a66e9-266">Они также используются для примеров синтаксиса, в которых демонстрируется синтаксис команды.</span><span class="sxs-lookup"><span data-stu-id="a66e9-266">They are also used for syntax examples where you are illustrating the syntax of a command.</span></span> <span data-ttu-id="a66e9-267">Блок кода может содержать пример выходных данных команды, о которой идет речь.</span><span class="sxs-lookup"><span data-stu-id="a66e9-267">The code block may contain example output from the command being illustrated.</span></span>

<span data-ttu-id="a66e9-268">Ниже приведен простой пример, иллюстрирующий операторы сравнения PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a66e9-268">Here is a simple example illustrating a PowerShell comparison operators:</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS>  1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

<span data-ttu-id="a66e9-269">Обратите внимание, что в этом примере используется упрощенная командная строка PowerShell и отображаются полученные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a66e9-269">Note that this example has the simplified PowerShell prompt and shows the resulting output.</span></span> <span data-ttu-id="a66e9-270">В данном случае не предполагается, что читатель будет копировать и запускать этот пример.</span><span class="sxs-lookup"><span data-stu-id="a66e9-270">In this case, we don't intend the reader to copy and run this example.</span></span>

### <a name="executable-examples"></a><span data-ttu-id="a66e9-271">Примеры для выполнения</span><span class="sxs-lookup"><span data-stu-id="a66e9-271">Executable examples</span></span>

<span data-ttu-id="a66e9-272">В более сложных примерах и примерах, предназначенных для копирования и выполнения, должна использоваться следующая разметка с применением обратных кавычек:</span><span class="sxs-lookup"><span data-stu-id="a66e9-272">More complex examples or examples that are intended to be useful to copy and execute should use the following block-style markup:</span></span>

~~~markdown
```powershell
<PowerShell code goes here>
```
~~~

<span data-ttu-id="a66e9-273">Выходные данные команд PowerShell необходимо заключить в блок кода **Выходные данные**, чтобы для них не выполнялась подсветка синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="a66e9-273">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="a66e9-274">Пример:</span><span class="sxs-lookup"><span data-stu-id="a66e9-274">For example:</span></span>

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

<span data-ttu-id="a66e9-275">Метка кода **Выходные данные** не является официальным "языком", поддерживаемым системой подсветки синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="a66e9-275">The **Output** code label is not an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="a66e9-276">Однако эта метка полезна, так как OPS добавляет метку "Выходные данные" в рамку блока кода на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="a66e9-276">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="a66e9-277">В блоке кода "Выходные данные" подсветка синтаксиса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a66e9-277">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="a66e9-278">Стилевые правила оформления кода</span><span class="sxs-lookup"><span data-stu-id="a66e9-278">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="a66e9-279">Избегайте разрыва строк в примерах кода</span><span class="sxs-lookup"><span data-stu-id="a66e9-279">Avoid line continuation in code samples</span></span>

<span data-ttu-id="a66e9-280">Не используйте символы продолжения строки (`` ` ``) в примерах кода PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a66e9-280">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="a66e9-281">Эти символы трудно увидеть и могут вызвать проблемы, если в конце строки есть лишние пробелы.</span><span class="sxs-lookup"><span data-stu-id="a66e9-281">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="a66e9-282">Используйте сплаттинг PowerShell, чтобы сократить длину строки для командлетов с большим количеством параметров.</span><span class="sxs-lookup"><span data-stu-id="a66e9-282">Use PowerShell splatting to reduce line length for cmdlets that have a lot of parameters.</span></span>
- <span data-ttu-id="a66e9-283">Используйте естественные возможности переноса строк в PowerShell, например, после символа вертикальной черты (`|`), открывающих фигурных скобок, круглых скобок и квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="a66e9-283">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces, parentheses, and brackets.</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="a66e9-284">Избегайте использования командной строки PowerShell в примерах</span><span class="sxs-lookup"><span data-stu-id="a66e9-284">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="a66e9-285">Использование командной строки в примерах не рекомендуется и должно быть ограничено сценариями, предназначенными для иллюстрации использования командной строки.</span><span class="sxs-lookup"><span data-stu-id="a66e9-285">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command line usage.</span></span> <span data-ttu-id="a66e9-286">В большинстве этих примеров командная строка должна иметь вид `PS>`.</span><span class="sxs-lookup"><span data-stu-id="a66e9-286">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="a66e9-287">Такая командная строка не зависит от характеристик конкретной ОС.</span><span class="sxs-lookup"><span data-stu-id="a66e9-287">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="a66e9-288">Командная строка требуется для примеров, иллюстрирующих команды, которые изменяют командную строку, или в тех случаях, когда отображаемый в командной строке путь важен для сценария, о котором идет речь.</span><span class="sxs-lookup"><span data-stu-id="a66e9-288">Prompts are required for examples that illustrate commands that alter the prompt or when the path displayed is significant to the scenario being illustrated.</span></span> <span data-ttu-id="a66e9-289">В следующем примере показано изменение командной строки при использовании поставщика реестра.</span><span class="sxs-lookup"><span data-stu-id="a66e9-289">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="do-not-use-aliases-in-examples"></a><span data-ttu-id="a66e9-290">Не используйте псевдонимы в примерах</span><span class="sxs-lookup"><span data-stu-id="a66e9-290">Do not use aliases in examples</span></span>

<span data-ttu-id="a66e9-291">Следует всегда использовать полные имена командлетов и параметров, если только речь не идет именно об этом псевдониме.</span><span class="sxs-lookup"><span data-stu-id="a66e9-291">You should always use the full name of all cmdlets and parameters unless you are specifically talking about the alias.</span></span> <span data-ttu-id="a66e9-292">Написание имен командлетов и параметров должно соответствовать стандартам кода.</span><span class="sxs-lookup"><span data-stu-id="a66e9-292">Cmdlet and parameter names must use the proper spelling defined in the code.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="a66e9-293">Использование параметров в примерах</span><span class="sxs-lookup"><span data-stu-id="a66e9-293">Using parameters in examples</span></span>

<span data-ttu-id="a66e9-294">Старайтесь не использовать позиционные параметры.</span><span class="sxs-lookup"><span data-stu-id="a66e9-294">Avoid using positional parameters.</span></span> <span data-ttu-id="a66e9-295">В общем случае следует всегда включать в пример имя параметра, даже если параметр является позиционным.</span><span class="sxs-lookup"><span data-stu-id="a66e9-295">In general, you should use always include the parameter name in an example, even if the parameter positional.</span></span> <span data-ttu-id="a66e9-296">Это снижает вероятность путаницы в ваших примерах.</span><span class="sxs-lookup"><span data-stu-id="a66e9-296">This reduces the chance of confusion in your examples.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a66e9-297">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a66e9-297">Next steps</span></span>

[<span data-ttu-id="a66e9-298">Редактирование справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="a66e9-298">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
