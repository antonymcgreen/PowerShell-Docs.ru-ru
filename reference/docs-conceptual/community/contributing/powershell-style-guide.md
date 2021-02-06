---
title: Руководство по стилю для документации PowerShell
description: В этой статье приводятся стилевые рекомендации для написания документации по PowerShell.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 6f23f63cffc9fed9cbbcf84539875bfaf4247732
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "99601077"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="5e97c-103">Руководство по стилю для документации PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e97c-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="5e97c-104">В этой статье представлено руководство по стилю для документации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="5e97c-105">Он основан на информации, приведенной в [обзоре](overview.md#get-started-writing-docs).</span><span class="sxs-lookup"><span data-stu-id="5e97c-105">It builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="5e97c-106">Терминология продукта</span><span class="sxs-lookup"><span data-stu-id="5e97c-106">Product Terminology</span></span>

<span data-ttu-id="5e97c-107">Существует несколько вариантов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="5e97c-108">**PowerShell** — используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e97c-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="5e97c-109">Мы считаем, что PowerShell 7 и более поздние, — это один из них, PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-109">We consider PowerShell 7 and beyond to be the one, true PowerShell.</span></span>
- <span data-ttu-id="5e97c-110">**PowerShell Core** — PowerShell на основе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e97c-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="5e97c-111">Использование термина " **ядро** " должно быть ограничено вариантами, в которых необходимо отличать его от Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-111">Usage of the term **Core** should be limited to cases where it's necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="5e97c-112">**Windows PowerShell** — PowerShell на основе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e97c-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="5e97c-113">Windows PowerShell поставляется только в Windows, и для его работы требуется полная версия платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e97c-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="5e97c-114">Как правило, ссылки на "Windows PowerShell" в документации можно изменить на _PowerShell_.</span><span class="sxs-lookup"><span data-stu-id="5e97c-114">In general, references to "Windows PowerShell" in documentation can be changed to _PowerShell_.</span></span>
  <span data-ttu-id="5e97c-115">"Windows PowerShell" следует использовать при обсуждении поведения, характерного для _Windows PowerShell_.</span><span class="sxs-lookup"><span data-stu-id="5e97c-115">"Windows PowerShell" should be used when _Windows PowerShell_-specific behavior is being discussed.</span></span>

<span data-ttu-id="5e97c-116">Связанные продукты</span><span class="sxs-lookup"><span data-stu-id="5e97c-116">Related products</span></span>

- <span data-ttu-id="5e97c-117">**Visual Studio Code (VS Code)** — это бесплатный редактор с открытым исходным кодом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e97c-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open-source editor.</span></span> <span data-ttu-id="5e97c-118">При первом упоминании имя должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="5e97c-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="5e97c-119">Затем можно использовать **VS Code**.</span><span class="sxs-lookup"><span data-stu-id="5e97c-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="5e97c-120">Не используйте "VSCode".</span><span class="sxs-lookup"><span data-stu-id="5e97c-120">Don't use "VSCode".</span></span>
- <span data-ttu-id="5e97c-121">**Расширение PowerShell для Visual Studio Code** — это расширение делает VS Code предпочтительной интегрированной средой разработки для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="5e97c-122">При первом упоминании имя должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="5e97c-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="5e97c-123">Затем можно использовать термин **расширение PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5e97c-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="5e97c-124">**Azure PowerShell** — это коллекция модулей PowerShell, используемых для управления службами Azure.</span><span class="sxs-lookup"><span data-stu-id="5e97c-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="5e97c-125">**Azure Stack PowerShell** — это коллекция модулей PowerShell, используемых для управления гибридным облачным решением Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e97c-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="5e97c-126">Особенности Markdown</span><span class="sxs-lookup"><span data-stu-id="5e97c-126">Markdown specifics</span></span>

<span data-ttu-id="5e97c-127">В системе Microsoft Open Publishing System (OPS), лежащей в основе нашей документации, используется [markdig][] для обработки документов Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e97c-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="5e97c-128">Markdig анализирует документы на основе правил последней версии спецификации [CommonMark][].</span><span class="sxs-lookup"><span data-stu-id="5e97c-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="5e97c-129">Новая версия спецификации CommonMark является более строгой в отношении структуры некоторых элементов Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e97c-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="5e97c-130">Обратите особое внимание на сведения, приведенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="5e97c-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="5e97c-131">Пустые строки, пробелы и знаки табуляции</span><span class="sxs-lookup"><span data-stu-id="5e97c-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="5e97c-132">Пустые строки также обозначают конец блока в Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e97c-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="5e97c-133">Между блоками Markdown разных типов (например, между абзацем и списком или заголовком) должна быть одна пустая строка.</span><span class="sxs-lookup"><span data-stu-id="5e97c-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="5e97c-134">Несколько последовательных пустых строк отображаются в виде одной пустой строки в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="5e97c-134">Multiple consecutive blank lines render as a single blank line in HTML.</span></span> <span data-ttu-id="5e97c-135">Они не служат целью.</span><span class="sxs-lookup"><span data-stu-id="5e97c-135">They serve no purpose.</span></span>
<span data-ttu-id="5e97c-136">В блоке кода последовательные пустые строки нарушают блок кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-136">Within a code block, consecutive blank lines break the code block.</span></span>

<span data-ttu-id="5e97c-137">Удалите лишние пробелы в конце строк.</span><span class="sxs-lookup"><span data-stu-id="5e97c-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="5e97c-138">Промежутки очень важны в Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e97c-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="5e97c-139">Вместо символов табуляции всегда используйте пробелы.</span><span class="sxs-lookup"><span data-stu-id="5e97c-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="5e97c-140">Пробелы в конце могут изменить способ отображения Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e97c-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="5e97c-141">Заголовки</span><span class="sxs-lookup"><span data-stu-id="5e97c-141">Titles and headings</span></span>

<span data-ttu-id="5e97c-142">Используйте только [стиль заголовков с ATX][atx] (стиль #, а не стиль заголовков `=` или `-`).</span><span class="sxs-lookup"><span data-stu-id="5e97c-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="5e97c-143">Используйте регистр обычных предложений: начинать с заглавной буквы следует только определенные существительные и заголовки</span><span class="sxs-lookup"><span data-stu-id="5e97c-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="5e97c-144">Между `#` и первой буквой заголовка должен быть один пробел</span><span class="sxs-lookup"><span data-stu-id="5e97c-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="5e97c-145">До и после заголовка необходимо указать по одной пустой строке</span><span class="sxs-lookup"><span data-stu-id="5e97c-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="5e97c-146">В документе должен быть только один заголовок H1</span><span class="sxs-lookup"><span data-stu-id="5e97c-146">Only one H1 per document</span></span>
- <span data-ttu-id="5e97c-147">Уровни заголовков должны увеличиваться на единицу.</span><span class="sxs-lookup"><span data-stu-id="5e97c-147">Header levels should increment by one.</span></span> <span data-ttu-id="5e97c-148">Не пропускать уровни</span><span class="sxs-lookup"><span data-stu-id="5e97c-148">Don't skip levels</span></span>
- <span data-ttu-id="5e97c-149">Не используйте полужирный шрифт или другую разметку в заголовках</span><span class="sxs-lookup"><span data-stu-id="5e97c-149">Don't use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="5e97c-150">Ограничьте длину строки 100 символами</span><span class="sxs-lookup"><span data-stu-id="5e97c-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="5e97c-151">Это относится к концептуальным статьям и к справочнику по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5e97c-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="5e97c-152">Ограничение длины строки повышает удобочитаемость сравнения изменений и журнала Git.</span><span class="sxs-lookup"><span data-stu-id="5e97c-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="5e97c-153">Кроме того, это упрощает изменение содержимого для других авторов.</span><span class="sxs-lookup"><span data-stu-id="5e97c-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="5e97c-154">Используйте расширение [Reflow Markdown][reflow] в Visual Studio Code, чтобы легко переформатировать абзацы в соответствии с заданной длиной строки.</span><span class="sxs-lookup"><span data-stu-id="5e97c-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="5e97c-155">Разделы "about" ограничены 80 символами.</span><span class="sxs-lookup"><span data-stu-id="5e97c-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="5e97c-156">Дополнительные сведения см. в разделе [форматирование about_ файлов](#formatting-about_-files).</span><span class="sxs-lookup"><span data-stu-id="5e97c-156">For more specific information, see [Formatting About_ files](#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="5e97c-157">Списки</span><span class="sxs-lookup"><span data-stu-id="5e97c-157">Lists</span></span>

<span data-ttu-id="5e97c-158">Если список содержит несколько предложений или абзацев, рассмотрите возможность использования заголовка подуровне, а не списка.</span><span class="sxs-lookup"><span data-stu-id="5e97c-158">If your list contains multiple sentences or paragraphs, consider using a sublevel header rather than a list.</span></span>

<span data-ttu-id="5e97c-159">До и после списка необходимо указать по одной пустой строке.</span><span class="sxs-lookup"><span data-stu-id="5e97c-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="5e97c-160">Неупорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="5e97c-160">Unordered lists</span></span>

<span data-ttu-id="5e97c-161">Не завершайте элементы списка точкой, если они не содержат несколько предложений.</span><span class="sxs-lookup"><span data-stu-id="5e97c-161">Don't end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="5e97c-162">Используйте знак дефиса (`-`) для обозначения элементов списка.</span><span class="sxs-lookup"><span data-stu-id="5e97c-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="5e97c-163">Это позволяет избежать путаницы с полужирной или курсивной разметкой, в которой используется звездочка [`*`].</span><span class="sxs-lookup"><span data-stu-id="5e97c-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="5e97c-164">Чтобы включить абзац или другие элементы в элемент маркированного списка, вставьте разрыв строки и выровняйте отступы с первым символом после маркера.</span><span class="sxs-lookup"><span data-stu-id="5e97c-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="5e97c-165">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-165">For example:</span></span>

```markdown
This is a list that contain child elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Child bullet item

    Sentence explaining the child bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="5e97c-166">Это список, содержащий дочерние элементы под элементом маркированного списка.</span><span class="sxs-lookup"><span data-stu-id="5e97c-166">This is a list that contains child elements under a bullet item.</span></span>

- <span data-ttu-id="5e97c-167">Первый элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="5e97c-167">First bullet item</span></span>

  <span data-ttu-id="5e97c-168">Предложение, объясняющее первый маркер.</span><span class="sxs-lookup"><span data-stu-id="5e97c-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="5e97c-169">Дочерний элемент маркера</span><span class="sxs-lookup"><span data-stu-id="5e97c-169">Child bullet item</span></span>

    <span data-ttu-id="5e97c-170">Предложение, объясняющее дочерний маркер.</span><span class="sxs-lookup"><span data-stu-id="5e97c-170">Sentence explaining the child bullet.</span></span>

- <span data-ttu-id="5e97c-171">Второй элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="5e97c-171">Second bullet item</span></span>
- <span data-ttu-id="5e97c-172">Третий элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="5e97c-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="5e97c-173">Упорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="5e97c-173">Ordered lists</span></span>

<span data-ttu-id="5e97c-174">Чтобы включить абзац или другие элементы в элемент нумерованного списка, выровняйте отступы с первым символом после номера элемента.</span><span class="sxs-lookup"><span data-stu-id="5e97c-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="5e97c-175">Для всех элементов нумерованного списка необходимо указать число `1.` вместо того, чтобы увеличивать номер каждого элемента вручную.</span><span class="sxs-lookup"><span data-stu-id="5e97c-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="5e97c-176">Markdown увеличит значения автоматически при выводе.</span><span class="sxs-lookup"><span data-stu-id="5e97c-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="5e97c-177">Это упрощает изменение порядка элементов и стандартизирует отступы для вложенного содержимого.</span><span class="sxs-lookup"><span data-stu-id="5e97c-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="5e97c-178">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-178">For example:</span></span>

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

<span data-ttu-id="5e97c-179">Итоговый тест Markdown будет выведен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5e97c-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="5e97c-180">Для первого элемента добавьте один пробел после цифры 1.</span><span class="sxs-lookup"><span data-stu-id="5e97c-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="5e97c-181">Длинные предложения необходимо переносить на следующую строку и выравнивать по первому символу после маркера нумерованного списка.</span><span class="sxs-lookup"><span data-stu-id="5e97c-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="5e97c-182">Чтобы включить второй элемент (такой, как этот), вставьте разрыв строки после первого элемента и выровняйте отступы.</span><span class="sxs-lookup"><span data-stu-id="5e97c-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="5e97c-183">Отступ второго элемента необходимо выравнивать с первым символом после маркера нумерованного списка.</span><span class="sxs-lookup"><span data-stu-id="5e97c-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="5e97c-184">Для однозначных номеров элементов, таких как этот, необходимо осуществлять отступ по столбцу 4.</span><span class="sxs-lookup"><span data-stu-id="5e97c-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="5e97c-185">Для двузначных номеров элементов, например, для элемента № 10, необходимо осуществлять отступ по столбцу 5.</span><span class="sxs-lookup"><span data-stu-id="5e97c-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="5e97c-186">Следующий элемент нумерованного списка начинается здесь.</span><span class="sxs-lookup"><span data-stu-id="5e97c-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="5e97c-187">Изображения</span><span class="sxs-lookup"><span data-stu-id="5e97c-187">Images</span></span>

<span data-ttu-id="5e97c-188">Для включения изображения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5e97c-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="5e97c-189">Здесь `alt text` — краткое описание изображения, а `<folder path>` — относительный путь к изображению.</span><span class="sxs-lookup"><span data-stu-id="5e97c-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="5e97c-190">Необходимо указать дополнительный текст для средств чтения с экрана для лиц с ослабленным зрением.</span><span class="sxs-lookup"><span data-stu-id="5e97c-190">Alternate text is required for screen readers for the visually impaired.</span></span>

<span data-ttu-id="5e97c-191">Изображения должны храниться в `media/<article-name>` папке в папке, содержащей статью.</span><span class="sxs-lookup"><span data-stu-id="5e97c-191">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="5e97c-192">Не обменивайтесь образами между статьями.</span><span class="sxs-lookup"><span data-stu-id="5e97c-192">Don't share images between articles.</span></span> <span data-ttu-id="5e97c-193">В папке `media` создайте вложенную папку, имя которой совпадает с именем файла статьи.</span><span class="sxs-lookup"><span data-stu-id="5e97c-193">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="5e97c-194">Скопируйте изображения для статьи в эту новую папку.</span><span class="sxs-lookup"><span data-stu-id="5e97c-194">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="5e97c-195">Если изображение используется в нескольких статьях, его копия должна быть в папке с изображениями каждой из них.</span><span class="sxs-lookup"><span data-stu-id="5e97c-195">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="5e97c-196">Это нужно для того, чтобы при изменении изображения в одной статье в остальных оно не менялось.</span><span class="sxs-lookup"><span data-stu-id="5e97c-196">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="5e97c-197">Поддерживаются следующие типы файлов изображений: `*.png` , `*.gif` , `*.jpeg` , `*.jpg` , `*.svg`</span><span class="sxs-lookup"><span data-stu-id="5e97c-197">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="5e97c-198">Расширения Markdown, поддерживаемые в Open Publishing</span><span class="sxs-lookup"><span data-stu-id="5e97c-198">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="5e97c-199">[Пакет разработки документация Майкрософт](/contribute/how-to-write-docs-auth-pack) содержит средства, которые поддерживают функции, уникальные для нашей системы публикации.</span><span class="sxs-lookup"><span data-stu-id="5e97c-199">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="5e97c-200">Оповещения — это расширение Markdown для создания цитаты, отображаемых на docs.microsoft.com с цветами и значками, которые выделяют значимость содержимого.</span><span class="sxs-lookup"><span data-stu-id="5e97c-200">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="5e97c-201">Поддерживаются следующие типы оповещений:</span><span class="sxs-lookup"><span data-stu-id="5e97c-201">The following alert types are supported:</span></span>

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

<span data-ttu-id="5e97c-202">На сайте docs.microsoft.com эти оповещения отображаются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5e97c-202">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="5e97c-203">Блок заметок</span><span class="sxs-lookup"><span data-stu-id="5e97c-203">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="5e97c-204">Информация, которую пользователь должен заметить даже при беглом просмотре.</span><span class="sxs-lookup"><span data-stu-id="5e97c-204">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="5e97c-205">Блок TIP</span><span class="sxs-lookup"><span data-stu-id="5e97c-205">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="5e97c-206">Дополнительные сведения, помогающие пользователю лучше решить задачу.</span><span class="sxs-lookup"><span data-stu-id="5e97c-206">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="5e97c-207">Важный блок</span><span class="sxs-lookup"><span data-stu-id="5e97c-207">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e97c-208">Важные сведения для успешного решения задачи.</span><span class="sxs-lookup"><span data-stu-id="5e97c-208">Essential information required for user success.</span></span>

<span data-ttu-id="5e97c-209">Блок предостережения</span><span class="sxs-lookup"><span data-stu-id="5e97c-209">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="5e97c-210">Потенциальные негативные последствия действия.</span><span class="sxs-lookup"><span data-stu-id="5e97c-210">Negative potential consequences of an action.</span></span>

<span data-ttu-id="5e97c-211">Блок предупреждений</span><span class="sxs-lookup"><span data-stu-id="5e97c-211">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="5e97c-212">Опасные последствия действия.</span><span class="sxs-lookup"><span data-stu-id="5e97c-212">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="5e97c-213">Гиперссылки</span><span class="sxs-lookup"><span data-stu-id="5e97c-213">Hyperlinks</span></span>

- <span data-ttu-id="5e97c-214">Гиперссылки должны использовать синтаксис Markdown `[friendlyname](url-or-path)` .</span><span class="sxs-lookup"><span data-stu-id="5e97c-214">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`.</span></span> <span data-ttu-id="5e97c-215">Поддерживаются [ссылки на][linkref] ссылки.</span><span class="sxs-lookup"><span data-stu-id="5e97c-215">[Link references][linkref] are supported.</span></span>
- <span data-ttu-id="5e97c-216">Система публикации поддерживает три типа ссылок:</span><span class="sxs-lookup"><span data-stu-id="5e97c-216">The publishing system supports three types of links:</span></span>
  - <span data-ttu-id="5e97c-217">URL-ссылки</span><span class="sxs-lookup"><span data-stu-id="5e97c-217">URL links</span></span>
  - <span data-ttu-id="5e97c-218">Ссылки на файлы</span><span class="sxs-lookup"><span data-stu-id="5e97c-218">File links</span></span>
  - <span data-ttu-id="5e97c-219">Ссылки на перекрестные ссылки</span><span class="sxs-lookup"><span data-stu-id="5e97c-219">Cross-reference links</span></span>
- <span data-ttu-id="5e97c-220">Ссылки на другие статьи в docs.microsoft.com должны относиться к сайтам</span><span class="sxs-lookup"><span data-stu-id="5e97c-220">Links to other articles on docs.microsoft.com must be site-relative paths</span></span>
- <span data-ttu-id="5e97c-221">Для всех URL-адресов внешних веб-сайтов следует использовать протокол HTTPS, если он не является допустимым для целевого сайта.</span><span class="sxs-lookup"><span data-stu-id="5e97c-221">All URLs to external websites should use HTTPS unless that isn't valid for the target site.</span></span>
- <span data-ttu-id="5e97c-222">Ссылки должны иметь понятное имя, обычно название связанной статьи</span><span class="sxs-lookup"><span data-stu-id="5e97c-222">Links must have a friendly name, usually the title of the linked article</span></span>
- <span data-ttu-id="5e97c-223">Все элементы в разделе _связанных ссылок_ внизу должны быть гиперссылками</span><span class="sxs-lookup"><span data-stu-id="5e97c-223">All items in the _Related links_ section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="5e97c-224">Не используйте обратные импульсы, полужирное начертание или другую разметку в квадратных скобках гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="5e97c-224">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="5e97c-225">URL-адреса исходного кода могут использоваться при документировании определенного URI.</span><span class="sxs-lookup"><span data-stu-id="5e97c-225">Bare URLs may be used when you're documenting a specific URI.</span></span> <span data-ttu-id="5e97c-226">URI должен быть заключен в обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="5e97c-226">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="5e97c-227">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-227">For example:</span></span>

  ```markdown
  By default, if you don't specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content-on-docsmicrosoftcom"></a><span data-ttu-id="5e97c-228">Связывание с другим содержимым в docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5e97c-228">Linking to other content on docs.microsoft.com</span></span>

- <span data-ttu-id="5e97c-229">**URL-ссылки** на другие статьи в docs.Microsoft.com должны относиться к сайтам.</span><span class="sxs-lookup"><span data-stu-id="5e97c-229">**URL links** to other articles on docs.microsoft.com must be site-relative paths.</span></span> <span data-ttu-id="5e97c-230">Самый простой способ создать относительную ссылку — скопировать URL-адрес из браузера, а затем удалить `https://docs.microsoft.com/en-us` из значения, вставляемого в Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e97c-230">The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span> <span data-ttu-id="5e97c-231">Не включайте языковые стандарты в URL-адреса свойств Майкрософт (удаление `/en-us` с URL-адреса).</span><span class="sxs-lookup"><span data-stu-id="5e97c-231">Don't include locales in URLs on Microsoft properties (remove `/en-us` from URL).</span></span> <span data-ttu-id="5e97c-232">Удалите из URL-адреса все ненужные параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="5e97c-232">Remove any unnecessary query parameters from the URL.</span></span> <span data-ttu-id="5e97c-233">Примеры, которые следует удалить:</span><span class="sxs-lookup"><span data-stu-id="5e97c-233">Examples that should be removed:</span></span>

  - <span data-ttu-id="5e97c-234">`?view=powershell-5.1` — используется для связи с определенной версией PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e97c-234">`?view=powershell-5.1` - used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="5e97c-235">`?redirectedfrom=MSDN` — добавляется к URL-адресу при перенаправлении из старой статьи в новое расположение</span><span class="sxs-lookup"><span data-stu-id="5e97c-235">`?redirectedfrom=MSDN` - added to the URL when you get redirected from an old article to its new location</span></span>

  <span data-ttu-id="5e97c-236">Если необходимо связать с определенной версией документа, необходимо добавить `&preserve_view=true` параметр в строку запроса.</span><span class="sxs-lookup"><span data-stu-id="5e97c-236">If you need to link to a specific version of a document, then you need to add the `&preserve_view=true` parameter to the query string.</span></span> <span data-ttu-id="5e97c-237">Пример: `?view=powershell-5.1&preserve_view=true`</span><span class="sxs-lookup"><span data-stu-id="5e97c-237">For example: `?view=powershell-5.1&preserve_view=true`</span></span>

- <span data-ttu-id="5e97c-238">**Ссылка на файл** используется для связи одной справочной статьи с другой или из одной концептуальной статьи в другую.</span><span class="sxs-lookup"><span data-stu-id="5e97c-238">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="5e97c-239">Если необходимо создать ссылку на справочную статью для определенной версии PowerShell, необходимо использовать URL-ссылку.</span><span class="sxs-lookup"><span data-stu-id="5e97c-239">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

  - <span data-ttu-id="5e97c-240">Ссылки на файлы содержат относительный путь к файлу (например, `../folder/file.md` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-240">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
  - <span data-ttu-id="5e97c-241">Все пути к файлам используют символы прямой косой черты ( `/` )</span><span class="sxs-lookup"><span data-stu-id="5e97c-241">All file paths use forward-slash (`/`) characters</span></span>

- <span data-ttu-id="5e97c-242">**Ссылки на перекрестные ссылки** — это специальная функция, поддерживаемая системой публикации.</span><span class="sxs-lookup"><span data-stu-id="5e97c-242">**Cross-reference links** are a special feature supported by the publishing system.</span></span> <span data-ttu-id="5e97c-243">Ссылки на перекрестные ссылки в концептуальных статьях можно использовать для ссылки на API .NET или Справочник по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5e97c-243">You can use cross-reference links in conceptual articles to link to .NET API or cmdlet reference.</span></span>

  <span data-ttu-id="5e97c-244">Ссылки на справочник по API для .NET см. в разделе [Использование ссылок в документации](/contribute/how-to-write-links#xref-cross-reference-links) в центральном руководстве для участников.</span><span class="sxs-lookup"><span data-stu-id="5e97c-244">For links to .NET API reference, see [Use links in documentation](/contribute/how-to-write-links#xref-cross-reference-links) in the central Contributor Guide.</span></span>

  <span data-ttu-id="5e97c-245">Ссылки на ссылки на командлеты имеют следующий формат: `xref:<module-name>.<cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="5e97c-245">Links to cmdlet reference have the following format: `xref:<module-name>.<cmdlet-name>`.</span></span> <span data-ttu-id="5e97c-246">Например, чтобы создать ссылку на `Get-Content` командлет в модуле **Microsoft. PowerShell. Management** .</span><span class="sxs-lookup"><span data-stu-id="5e97c-246">For example, to link to the `Get-Content` cmdlet in the **Microsoft.PowerShell.Management** module.</span></span>

  `[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)`

<span data-ttu-id="5e97c-247">Глубокая компоновка разрешена как для URL-адресов, так и для ссылок на файлы.</span><span class="sxs-lookup"><span data-stu-id="5e97c-247">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="5e97c-248">Добавьте привязку к концу целевого пути.</span><span class="sxs-lookup"><span data-stu-id="5e97c-248">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="5e97c-249">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-249">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="5e97c-250">Дополнительные сведения см. [в разделе Использование ссылок в документации](/contribute/how-to-write-links).</span><span class="sxs-lookup"><span data-stu-id="5e97c-250">For more information, see [Use links in documentation](/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="5e97c-251">Форматирование элементов синтаксиса команд</span><span class="sxs-lookup"><span data-stu-id="5e97c-251">Formatting command syntax elements</span></span>

- <span data-ttu-id="5e97c-252">Всегда используйте полное имя для командлетов и параметров.</span><span class="sxs-lookup"><span data-stu-id="5e97c-252">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="5e97c-253">Старайтесь не использовать псевдонимы, если только вы не порабатываете псевдоним.</span><span class="sxs-lookup"><span data-stu-id="5e97c-253">Avoid using aliases unless you're specifically demonstrating the alias.</span></span>

- <span data-ttu-id="5e97c-254">Свойство, параметр, объект, имена типов, имена классов, методы класса должны быть **полужирным**.</span><span class="sxs-lookup"><span data-stu-id="5e97c-254">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="5e97c-255">Значения свойств и параметров должны быть заключены в обратные кавычки ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-255">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="5e97c-256">При ссылке на типы с помощью стиля в квадратных скобках используйте обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="5e97c-256">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="5e97c-257">Пример: `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="5e97c-257">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="5e97c-258">Ключевые слова языка, имена командлетов, функции, переменные, собственные исполняемые файлы, пути к файлам и встроенные примеры синтаксиса должны быть заключены в символы обратной кавычки ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-258">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="5e97c-259">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-259">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="5e97c-260">Если параметр указывается по имени, он должен быть выделен **полужирным шрифтом**.</span><span class="sxs-lookup"><span data-stu-id="5e97c-260">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="5e97c-261">Если иллюстрируется использование параметра с префиксом в виде дефиса, параметр должен быть заключен в грависы.</span><span class="sxs-lookup"><span data-stu-id="5e97c-261">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="5e97c-262">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-262">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it's typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="5e97c-263">Если приводится пример использования внешней команды, он должен быть заключен в грависы.</span><span class="sxs-lookup"><span data-stu-id="5e97c-263">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="5e97c-264">Всегда включайте расширение файла в собственную команду.</span><span class="sxs-lookup"><span data-stu-id="5e97c-264">Always include the file extension in the native command.</span></span> <span data-ttu-id="5e97c-265">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-265">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="5e97c-266">Включение расширения файла обеспечивает выполнение правильной команды в соответствии с приоритетом команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-266">Including the file extension ensures that the correct command is executed according to PowerShell's command precedence.</span></span>

- <span data-ttu-id="5e97c-267">При написании концептуальной статьи (а не справочного содержимого) первое упоминание имени командлета должно быть гиперссылкой на документацию по командлету.</span><span class="sxs-lookup"><span data-stu-id="5e97c-267">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="5e97c-268">Не используйте обратные импульсы, полужирное начертание или другую разметку в квадратных скобках гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="5e97c-268">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="5e97c-269">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-269">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="5e97c-270">Дополнительные сведения см. в разделе [гиперссылки](#hyperlinks) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="5e97c-270">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="5e97c-271">Markdown для примеров кода</span><span class="sxs-lookup"><span data-stu-id="5e97c-271">Markdown for code samples</span></span>

<span data-ttu-id="5e97c-272">Markdown поддерживает два разных стиля кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-272">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="5e97c-273">**Код охватывает фрагменты кода (встроенный)** , помеченный одним символом обратной кавычки ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-273">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="5e97c-274">Используется в абзаце, а не в виде автономного блока.</span><span class="sxs-lookup"><span data-stu-id="5e97c-274">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="5e97c-275">**Блоки кода** — многострочный блок, заключенный в строки тройного обратного деления ( `` ``` `` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-275">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="5e97c-276">Блоки кода также могут иметь метку языка после обратных импульсов.</span><span class="sxs-lookup"><span data-stu-id="5e97c-276">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="5e97c-277">Метка языка включает выделение синтаксиса для содержимого блока кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-277">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="5e97c-278">Блоки кода следует ограждать.</span><span class="sxs-lookup"><span data-stu-id="5e97c-278">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="5e97c-279">Никогда не используйте отступы для блоков кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-279">Never use indentation for code blocks.</span></span> <span data-ttu-id="5e97c-280">Markdown допускает этот шаблон, но это может быть проблематично, и его следует избегать.</span><span class="sxs-lookup"><span data-stu-id="5e97c-280">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="5e97c-281">Блок кода — одна или несколько строк кода, заключенных в границу кода Triple-обратных тактов ( `` ``` `` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-281">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="5e97c-282">Маркеры границ кода должны находиться в отдельных строках до и после примера кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-282">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="5e97c-283">Маркер в начале блока может иметь метку языка (необязательно).</span><span class="sxs-lookup"><span data-stu-id="5e97c-283">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="5e97c-284">Открытая система публикации Майкрософт (OPS) использует метку языка для поддержки функции выделения синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="5e97c-284">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="5e97c-285">Полный список поддерживаемых тегов языков см. в разделе [блоки кода с ограждением](/contribute/code-in-docs#fenced-code-blocks) в централизованном руководством для участников.</span><span class="sxs-lookup"><span data-stu-id="5e97c-285">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="5e97c-286">OPS также добавляет кнопку **Копировать**, при нажатии которой содержимое блока кода копируется в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5e97c-286">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="5e97c-287">Это позволяет быстро вставить код в скрипт для тестирования примера кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-287">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="5e97c-288">Однако не все примеры в нашей документации должны выполняться как есть.</span><span class="sxs-lookup"><span data-stu-id="5e97c-288">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="5e97c-289">Некоторые блоки кода являются простыми иллюстрациями концепции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-289">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="5e97c-290">В нашей документации используются три типа блоков кода:</span><span class="sxs-lookup"><span data-stu-id="5e97c-290">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="5e97c-291">Блоки синтаксиса</span><span class="sxs-lookup"><span data-stu-id="5e97c-291">Syntax blocks</span></span>
1. <span data-ttu-id="5e97c-292">Иллюстративные примеры</span><span class="sxs-lookup"><span data-stu-id="5e97c-292">Illustrative examples</span></span>
1. <span data-ttu-id="5e97c-293">исполняемые примеры.</span><span class="sxs-lookup"><span data-stu-id="5e97c-293">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="5e97c-294">Блоки кода синтаксиса</span><span class="sxs-lookup"><span data-stu-id="5e97c-294">Syntax code blocks</span></span>

<span data-ttu-id="5e97c-295">Блоки кода синтаксиса используются для описания синтаксической структуры команды.</span><span class="sxs-lookup"><span data-stu-id="5e97c-295">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="5e97c-296">Не используйте тег языка в границе кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-296">Don't use a language tag on the code fence.</span></span> <span data-ttu-id="5e97c-297">В этом примере представлены все возможные параметры командлета `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="5e97c-297">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="5e97c-298">В этом примере представлена общая форма оператора `for`:</span><span class="sxs-lookup"><span data-stu-id="5e97c-298">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="5e97c-299">пояснительные примеры;</span><span class="sxs-lookup"><span data-stu-id="5e97c-299">Illustrative examples</span></span>

<span data-ttu-id="5e97c-300">Пояснительные примеры служат для иллюстрации какого-либо аспекта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-300">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="5e97c-301">Они не предназначены для копирования в буфер обмена для выполнения.</span><span class="sxs-lookup"><span data-stu-id="5e97c-301">They aren't meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="5e97c-302">Они наиболее часто используются для простых примеров, которые легко вводить и легко понимать.</span><span class="sxs-lookup"><span data-stu-id="5e97c-302">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="5e97c-303">Блок кода может включать в себя командную строку PowerShell и выходные данные примера.</span><span class="sxs-lookup"><span data-stu-id="5e97c-303">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="5e97c-304">Ниже приведен простой пример, иллюстрирующий операторы сравнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-304">Here's a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="5e97c-305">Этот пример не предусматривает копирование и выполнение читателем.</span><span class="sxs-lookup"><span data-stu-id="5e97c-305">In this case, we don't intend the reader to copy and run this example.</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a><span data-ttu-id="5e97c-306">исполняемые примеры.</span><span class="sxs-lookup"><span data-stu-id="5e97c-306">Executable examples</span></span>

<span data-ttu-id="5e97c-307">Сложные примеры или примеры, предназначенные для копирования и выполнения, должны использовать следующую разметку в блок-стиле:</span><span class="sxs-lookup"><span data-stu-id="5e97c-307">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="5e97c-308">Выходные данные команд PowerShell должны выноситься в отдельные блоки кода с меткой **Output**, чтобы не происходило выделение синтаксических конструкций.</span><span class="sxs-lookup"><span data-stu-id="5e97c-308">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="5e97c-309">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-309">For example:</span></span>

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

<span data-ttu-id="5e97c-310">Метка " **выходной** код" не является официальным "языком", поддерживаемым системой выделения синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="5e97c-310">The **Output** code label isn't an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="5e97c-311">Однако эта метка полезна, поскольку OPS добавляет метку Output в рамку поля кода на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="5e97c-311">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="5e97c-312">В поле "вывод" отсутствует выделение синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="5e97c-312">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="5e97c-313">Правила в отношении стиля оформления кода</span><span class="sxs-lookup"><span data-stu-id="5e97c-313">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="5e97c-314">Избегайте продолжения строк в примерах кода</span><span class="sxs-lookup"><span data-stu-id="5e97c-314">Avoid line continuation in code samples</span></span>

<span data-ttu-id="5e97c-315">Старайтесь не использовать символы продолжения строки (`` ` ``) в примерах кода PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e97c-315">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="5e97c-316">Они малозаметны, а лишние пробелы в конце строки могут вызвать проблемы.</span><span class="sxs-lookup"><span data-stu-id="5e97c-316">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="5e97c-317">Используйте PowerShell Сплаттинг, чтобы уменьшить длину строки для командлетов, имеющих несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="5e97c-317">Use PowerShell splatting to reduce line length for cmdlets that have several parameters.</span></span>
- <span data-ttu-id="5e97c-318">Воспользуйтесь преимуществами естественных возможностей переноса строк в PowerShell, например после символов вертикальной черты ( `|` ), открывающих фигурных скобок ( `{` ), круглых скобок () `(` и квадратных скобок ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-318">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces (`{`), parentheses (`(`), and brackets (`[`).</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="5e97c-319">Избегайте использования приглашения командной строки PowerShell в примерах</span><span class="sxs-lookup"><span data-stu-id="5e97c-319">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="5e97c-320">Использование строки запроса не рекомендуется и должно быть ограничено сценариями, предназначенными для иллюстрации использования командной строки.</span><span class="sxs-lookup"><span data-stu-id="5e97c-320">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command-line usage.</span></span> <span data-ttu-id="5e97c-321">В большинстве этих примеров строка запроса должна иметь значение `PS>` .</span><span class="sxs-lookup"><span data-stu-id="5e97c-321">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="5e97c-322">Она не зависит от меток ОС.</span><span class="sxs-lookup"><span data-stu-id="5e97c-322">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="5e97c-323">В примерах требуются запросы для демонстрации команд, которые изменяют запрос, или если отображаемый путь важен для сценария.</span><span class="sxs-lookup"><span data-stu-id="5e97c-323">Prompts are required in examples to illustrate commands that alter the prompt or when the path displayed is significant to the scenario.</span></span> <span data-ttu-id="5e97c-324">В приведенном ниже примере демонстрируется, как меняется строка приглашения при использовании поставщика реестра.</span><span class="sxs-lookup"><span data-stu-id="5e97c-324">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

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

### <a name="dont-use-aliases-in-examples"></a><span data-ttu-id="5e97c-325">Не используйте псевдонимы в примерах</span><span class="sxs-lookup"><span data-stu-id="5e97c-325">Don't use aliases in examples</span></span>

<span data-ttu-id="5e97c-326">Используйте полное имя всех командлетов и параметров, если только не задокументирован псевдоним.</span><span class="sxs-lookup"><span data-stu-id="5e97c-326">Use the full name of all cmdlets and parameters unless you're specifically documenting the alias.</span></span>
<span data-ttu-id="5e97c-327">Имена командлетов и параметров должны использовать правильные имена в [стиле Pascal][] .</span><span class="sxs-lookup"><span data-stu-id="5e97c-327">Cmdlet and parameter names must use the proper [Pascal-cased][] names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="5e97c-328">Использование параметров в примерах</span><span class="sxs-lookup"><span data-stu-id="5e97c-328">Using parameters in examples</span></span>

<span data-ttu-id="5e97c-329">Избегайте использования позиционных параметров.</span><span class="sxs-lookup"><span data-stu-id="5e97c-329">Avoid using positional parameters.</span></span> <span data-ttu-id="5e97c-330">Как правило, в примере всегда следует включать имя параметра, даже если параметр является позиционированным.</span><span class="sxs-lookup"><span data-stu-id="5e97c-330">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="5e97c-331">Это снижает вероятность возникновения путаницы.</span><span class="sxs-lookup"><span data-stu-id="5e97c-331">This reduces the chance of confusion in your examples.</span></span>

## <a name="formatting-cmdlet-reference-articles"></a><span data-ttu-id="5e97c-332">Справочные статьи по командлетам форматирования</span><span class="sxs-lookup"><span data-stu-id="5e97c-332">Formatting cmdlet reference articles</span></span>

<span data-ttu-id="5e97c-333">Справочные статьи по командлетам имеют определенную структуру.</span><span class="sxs-lookup"><span data-stu-id="5e97c-333">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="5e97c-334">Она определяется модулем [PlatyPS][].</span><span class="sxs-lookup"><span data-stu-id="5e97c-334">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="5e97c-335">Платипс создает справку по командлетам для модулей PowerShell в Markdown.</span><span class="sxs-lookup"><span data-stu-id="5e97c-335">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="5e97c-336">После редактирования файлов Markdown с помощью PlatyPS создаются MAML-файлы справки, используемые командлетом `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="5e97c-336">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="5e97c-337">В коде PlatyPS жестко задана схема для справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="5e97c-337">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="5e97c-338">Ее описание можно найти в файле [platyPS.schema.md][].</span><span class="sxs-lookup"><span data-stu-id="5e97c-338">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="5e97c-339">Нарушения схемы приводят к ошибкам сборки, которые необходимо исправить, иначе ваше содержимое не будет принято.</span><span class="sxs-lookup"><span data-stu-id="5e97c-339">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

- <span data-ttu-id="5e97c-340">Не удаляйте ни одну из структур заголовка ATX.</span><span class="sxs-lookup"><span data-stu-id="5e97c-340">Don't remove any of the ATX header structures.</span></span> <span data-ttu-id="5e97c-341">PlatyPS требует определенного набора заголовков.</span><span class="sxs-lookup"><span data-stu-id="5e97c-341">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="5e97c-342">Под заголовками **Input type** (Тип входных данных) и **Output type** (Тип выходных данных) должен быть указан тип.</span><span class="sxs-lookup"><span data-stu-id="5e97c-342">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="5e97c-343">Если командлет не принимает входные данные или не возвращает значение, используйте значение `None` .</span><span class="sxs-lookup"><span data-stu-id="5e97c-343">If the cmdlet doesn't take input or return a value, then use the value `None`.</span></span>
- <span data-ttu-id="5e97c-344">Встроенные фрагменты кода можно использовать в любом абзаце.</span><span class="sxs-lookup"><span data-stu-id="5e97c-344">Inline code spans can be used in any paragraph.</span></span>
- <span data-ttu-id="5e97c-345">Блоки кода с ограждением разрешены только в разделе " **примеры** ".</span><span class="sxs-lookup"><span data-stu-id="5e97c-345">Fenced code blocks are only allowed in the **EXAMPLES** section.</span></span>

<span data-ttu-id="5e97c-346">В схеме Платипс в **качестве примера** используется заголовок H2.</span><span class="sxs-lookup"><span data-stu-id="5e97c-346">In the PlatyPS schema, **EXAMPLES** is an H2 header.</span></span> <span data-ttu-id="5e97c-347">Каждый пример является заголовком H3.</span><span class="sxs-lookup"><span data-stu-id="5e97c-347">Each example is an H3 header.</span></span> <span data-ttu-id="5e97c-348">В этом примере схема не позволяет разделять блоки кода абзацами.</span><span class="sxs-lookup"><span data-stu-id="5e97c-348">Within an example, the schema doesn't allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="5e97c-349">Схема позволяет выполнять следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="5e97c-349">The schema allows the following structure:</span></span>

```
### Example X - Title sentence

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="5e97c-350">Пронумеруйте все примеры и снабдите их краткими заголовками.</span><span class="sxs-lookup"><span data-stu-id="5e97c-350">Number each example and add a brief title.</span></span>

<span data-ttu-id="5e97c-351">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-351">For example:</span></span>

~~~markdown
### Example 1: Get cmdlets, functions, and aliases

This command gets the PowerShell cmdlets, functions, and aliases that are installed on the
computer.

```powershell
Get-Command
```

### Example 2: Get commands in the current session

```powershell
Get-Command -ListImported
```
~~~

## <a name="formatting-about_-files"></a><span data-ttu-id="5e97c-352">Форматирование файлов About_</span><span class="sxs-lookup"><span data-stu-id="5e97c-352">Formatting About_ files</span></span>

<span data-ttu-id="5e97c-353">`About_*` файлы записываются в Markdown, но поставляются в виде обычных текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="5e97c-353">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="5e97c-354">Мы используем [pandoc][] для преобразования Markdown в обычный текст.</span><span class="sxs-lookup"><span data-stu-id="5e97c-354">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="5e97c-355">`About_*` файлы форматируются для обеспечения лучшей совместимости во всех версиях PowerShell и с помощью средств публикации.</span><span class="sxs-lookup"><span data-stu-id="5e97c-355">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="5e97c-356">Основные рекомендации по форматированию:</span><span class="sxs-lookup"><span data-stu-id="5e97c-356">Basic formatting guidelines:</span></span>

- <span data-ttu-id="5e97c-357">Ограничить обычные строки до 80 символов</span><span class="sxs-lookup"><span data-stu-id="5e97c-357">Limit normal lines to 80 characters</span></span>
- <span data-ttu-id="5e97c-358">Длина блоков кода ограничена 76 символами</span><span class="sxs-lookup"><span data-stu-id="5e97c-358">Code blocks are limited to 76 characters</span></span>
- <span data-ttu-id="5e97c-359">Цитаты (и предупреждения) имеют ограниченный 78 символов</span><span class="sxs-lookup"><span data-stu-id="5e97c-359">Blockquotes (and Alerts) are limited 78 characters</span></span>
- <span data-ttu-id="5e97c-360">При использовании этих специальных мета-символов `\` , `$` и `<` :</span><span class="sxs-lookup"><span data-stu-id="5e97c-360">When using these special meta-characters `\`,`$`, and `<`:</span></span>
  - <span data-ttu-id="5e97c-361">В заголовке эти символы должны быть экранированы с помощью начального `\` символа или заключены в фрагменты кода с помощью обратных импульсов ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="5e97c-361">Within a header, these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="5e97c-362">В пределах абзаца эти символы должны быть помещается в фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="5e97c-362">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="5e97c-363">Пример:</span><span class="sxs-lookup"><span data-stu-id="5e97c-363">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="5e97c-364">Размер таблиц должен сопадать в 76 символов</span><span class="sxs-lookup"><span data-stu-id="5e97c-364">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="5e97c-365">Переносите содержимое ячеек по строкам вручную.</span><span class="sxs-lookup"><span data-stu-id="5e97c-365">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="5e97c-366">Используйте открывающие и закрывающие символы `|` в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="5e97c-366">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="5e97c-367">В следующем примере показано, как правильно создать таблицу, содержащую сведения, которые переносятся на несколько строк в ячейке.</span><span class="sxs-lookup"><span data-stu-id="5e97c-367">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > <span data-ttu-id="5e97c-368">Ограничение 76 — столбец относится только к `About_*` разделам.</span><span class="sxs-lookup"><span data-stu-id="5e97c-368">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="5e97c-369">Широкие столбцы можно использовать в концептуальной или справочной статье о командлетах.</span><span class="sxs-lookup"><span data-stu-id="5e97c-369">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e97c-370">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5e97c-370">Next steps</span></span>

[<span data-ttu-id="5e97c-371">Контрольный список редактора</span><span class="sxs-lookup"><span data-stu-id="5e97c-371">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[atx]: https://github.github.com/gfm/#atx-headings
[CommonMark]: https://spec.commonmark.org/
[маркдиг]: https://github.com/lunet-io/markdig
[markdig]: https://github.com/lunet-io/markdig
[Pandoc]: https://pandoc.org
[С учетом стиля Pascal]: https://en.wikipedia.org/wiki/PascalCase
[Pascal-cased]: https://en.wikipedia.org/wiki/PascalCase
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[PlatyPS]: https://github.com/powershell/platyps
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
[linkref]: https://spec.commonmark.org/0.29/#link-reference-definitions
