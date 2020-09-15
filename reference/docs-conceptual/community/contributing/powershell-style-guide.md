---
title: Руководство по стилю для документации PowerShell
description: В этой статье приводятся стилевые рекомендации для написания документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 32df641f7cafa2a5bfcf1bcbf94be594aa77c7d0
ms.sourcegitcommit: 105c69ecedfe5180d8c12e8015d667c5f1a71579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85837449"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="8a4eb-103">Руководство по стилю для документации PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a4eb-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="8a4eb-104">В этой статье представлено руководство по стилю для документации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="8a4eb-105">Эта статья основана на сведениях, указанных в разделе [Обзор](overview.md#get-started-writing-docs).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-105">This builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="8a4eb-106">Терминология продукта</span><span class="sxs-lookup"><span data-stu-id="8a4eb-106">Product Terminology</span></span>

<span data-ttu-id="8a4eb-107">Существует несколько вариантов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="8a4eb-108">**PowerShell** — используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="8a4eb-109">Это понятие подразумевает PowerShell 7 и последующих версий.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-109">We consider PowerShell 7 and beyond to be the one, true PowerShell going forward.</span></span>
- <span data-ttu-id="8a4eb-110">**PowerShell Core** — PowerShell на основе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="8a4eb-111">Понятие **Core** должно использоваться только в тех ситуациях, когда необходимо отличить PowerShell Core от Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-111">Usage of the term **Core** should be limited to cases where it is necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="8a4eb-112">**Windows PowerShell** — PowerShell на основе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="8a4eb-113">Windows PowerShell поставляется только в Windows, и для его работы требуется полная версия платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="8a4eb-114">В общем случае ссылки на "Windows PowerShell" в документации можно изменить на "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="8a4eb-114">In general, references to "Windows PowerShell" in documentation can be changed to "PowerShell".</span></span>
  <span data-ttu-id="8a4eb-115">При обсуждении поведения, характерного для Windows PowerShell, нужно использовать термин "Windows PowerShell".</span><span class="sxs-lookup"><span data-stu-id="8a4eb-115">"Windows PowerShell" should be used when "Windows PowerShell"-specific behavior is being discussed.</span></span>

<span data-ttu-id="8a4eb-116">Связанные продукты</span><span class="sxs-lookup"><span data-stu-id="8a4eb-116">Related products</span></span>

- <span data-ttu-id="8a4eb-117">**Visual Studio Code (VS Code)**  — это бесплатный редактор от Майкрософт с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open source editor.</span></span> <span data-ttu-id="8a4eb-118">При первом упоминании имя должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="8a4eb-119">Затем можно использовать **VS Code**.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="8a4eb-120">Не используйте "VSCode".</span><span class="sxs-lookup"><span data-stu-id="8a4eb-120">Do not use "VSCode".</span></span>
- <span data-ttu-id="8a4eb-121">**Расширение PowerShell для Visual Studio Code** — это расширение делает VS Code предпочтительной интегрированной средой разработки для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="8a4eb-122">При первом упоминании имя должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="8a4eb-123">Затем можно использовать термин **расширение PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="8a4eb-124">**Azure PowerShell** — это коллекция модулей PowerShell, используемых для управления службами Azure.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="8a4eb-125">**Azure Stack PowerShell** — это коллекция модулей PowerShell, используемых для управления гибридным облачным решением Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="8a4eb-126">Особенности Markdown</span><span class="sxs-lookup"><span data-stu-id="8a4eb-126">Markdown specifics</span></span>

<span data-ttu-id="8a4eb-127">В системе Microsoft Open Publishing System (OPS), лежащей в основе нашей документации, используется [markdig][] для обработки документов Markdown.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="8a4eb-128">Markdig анализирует документы на основе правил последней версии спецификации [CommonMark][].</span><span class="sxs-lookup"><span data-stu-id="8a4eb-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="8a4eb-129">Новая версия спецификации CommonMark является более строгой в отношении структуры некоторых элементов Markdown.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="8a4eb-130">Обратите особое внимание на сведения, приведенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="8a4eb-131">Пустые строки, пробелы и знаки табуляции</span><span class="sxs-lookup"><span data-stu-id="8a4eb-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="8a4eb-132">Пустые строки также обозначают конец блока в Markdown.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="8a4eb-133">Между блоками Markdown разных типов (например, между абзацем и списком или заголовком) должна быть одна пустая строка.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="8a4eb-134">Удалите дублирующиеся пустые строки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-134">Remove duplicate blank lines.</span></span> <span data-ttu-id="8a4eb-135">Несколько пустых строк отображаются в виде одной пустой строки в формате HTML, поэтому указывать несколько пустых строк не требуется.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-135">Multiple blank lines render as a single blank line in HTML so there is no purpose for multiple blank lines.</span></span> <span data-ttu-id="8a4eb-136">Несколько пустых строк в блоке кода разбивают блок кода на фрагменты.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-136">Multiple blank lines within a code block break the code block.</span></span>

<span data-ttu-id="8a4eb-137">Удалите лишние пробелы в конце строк.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="8a4eb-138">Промежутки очень важны в Markdown.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="8a4eb-139">Вместо символов табуляции всегда используйте пробелы.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="8a4eb-140">Пробелы в конце могут изменить способ отображения Markdown.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="8a4eb-141">Заголовки</span><span class="sxs-lookup"><span data-stu-id="8a4eb-141">Titles and headings</span></span>

<span data-ttu-id="8a4eb-142">Используйте только [стиль заголовков с ATX][atx] (стиль #, а не стиль заголовков `=` или `-`).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="8a4eb-143">Используйте регистр обычных предложений: начинать с заглавной буквы следует только определенные существительные и заголовки</span><span class="sxs-lookup"><span data-stu-id="8a4eb-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="8a4eb-144">Между `#` и первой буквой заголовка должен быть один пробел</span><span class="sxs-lookup"><span data-stu-id="8a4eb-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="8a4eb-145">До и после заголовка необходимо указать по одной пустой строке</span><span class="sxs-lookup"><span data-stu-id="8a4eb-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="8a4eb-146">В документе должен быть только один заголовок H1</span><span class="sxs-lookup"><span data-stu-id="8a4eb-146">Only one H1 per document</span></span>
- <span data-ttu-id="8a4eb-147">Уровни заголовков должны увеличиваться на единицу.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-147">Header levels should increment by one.</span></span> <span data-ttu-id="8a4eb-148">Не пропускайте уровни</span><span class="sxs-lookup"><span data-stu-id="8a4eb-148">Do not skip levels</span></span>
- <span data-ttu-id="8a4eb-149">Не используйте полужирный шрифт и другую разметку в заголовках</span><span class="sxs-lookup"><span data-stu-id="8a4eb-149">Do not use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="8a4eb-150">Ограничьте длину строки 100 символами</span><span class="sxs-lookup"><span data-stu-id="8a4eb-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="8a4eb-151">Это относится к концептуальным статьям и к справочнику по командлетам.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="8a4eb-152">Ограничение длины строки повышает удобочитаемость сравнения изменений и журнала Git.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="8a4eb-153">Кроме того, это упрощает изменение содержимого для других авторов.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="8a4eb-154">Используйте расширение [Reflow Markdown][reflow] в Visual Studio Code, чтобы легко переформатировать абзацы в соответствии с заданной длиной строки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="8a4eb-155">Разделы "about" ограничены 80 символами.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="8a4eb-156">Дополнительные сведения см. в разделе [Форматирование файлов About_](./editing-cmdlet-ref.md#formatting-about_-files).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-156">For more specific information, see [Editing reference articles](./editing-cmdlet-ref.md#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="8a4eb-157">Списки</span><span class="sxs-lookup"><span data-stu-id="8a4eb-157">Lists</span></span>

<span data-ttu-id="8a4eb-158">Если список содержит несколько предложений или абзацев, используйте заголовки нижнего уровня, а не список.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-158">If your list contains multiple sentences or paragraphs, consider using a sub-level header rather than a list.</span></span>

<span data-ttu-id="8a4eb-159">До и после списка необходимо указать по одной пустой строке.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="8a4eb-160">Неупорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="8a4eb-160">Unordered lists</span></span>

<span data-ttu-id="8a4eb-161">Не ставьте в конце элементов списка точку (только если они не содержат несколько предложений).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-161">Do not end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="8a4eb-162">Используйте знак дефиса (`-`) для обозначения элементов списка.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="8a4eb-163">Это позволяет избежать путаницы с полужирной или курсивной разметкой, в которой используется звездочка [`*`].</span><span class="sxs-lookup"><span data-stu-id="8a4eb-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="8a4eb-164">Чтобы включить абзац или другие элементы в элемент маркированного списка, вставьте разрыв строки и выровняйте отступы с первым символом после маркера.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="8a4eb-165">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-165">For example:</span></span>

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="8a4eb-166">Это список, содержащий вложенные элементы в элементе маркированного списка.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-166">This is a list that contains sub-elements under a bullet item.</span></span>

- <span data-ttu-id="8a4eb-167">Первый элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="8a4eb-167">First bullet item</span></span>

  <span data-ttu-id="8a4eb-168">Предложение, объясняющее первый маркер.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="8a4eb-169">Вложенный элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="8a4eb-169">Sub-bullet item</span></span>

    <span data-ttu-id="8a4eb-170">Предложение, объясняющее вложенный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-170">Sentence explaining the sub-bullet.</span></span>

- <span data-ttu-id="8a4eb-171">Второй элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="8a4eb-171">Second bullet item</span></span>
- <span data-ttu-id="8a4eb-172">Третий элемент маркированного списка</span><span class="sxs-lookup"><span data-stu-id="8a4eb-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="8a4eb-173">Упорядоченные списки</span><span class="sxs-lookup"><span data-stu-id="8a4eb-173">Ordered lists</span></span>

<span data-ttu-id="8a4eb-174">Чтобы включить абзац или другие элементы в элемент нумерованного списка, выровняйте отступы с первым символом после номера элемента.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="8a4eb-175">Для всех элементов нумерованного списка необходимо указать число `1.` вместо того, чтобы увеличивать номер каждого элемента вручную.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="8a4eb-176">Markdown увеличит значения автоматически при выводе.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="8a4eb-177">Это упрощает изменение порядка элементов и стандартизирует отступы для вложенного содержимого.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="8a4eb-178">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-178">For example:</span></span>

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

<span data-ttu-id="8a4eb-179">Итоговый тест Markdown будет выведен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="8a4eb-180">Для первого элемента добавьте один пробел после цифры 1.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="8a4eb-181">Длинные предложения необходимо переносить на следующую строку и выравнивать по первому символу после маркера нумерованного списка.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="8a4eb-182">Чтобы включить второй элемент (такой, как этот), вставьте разрыв строки после первого элемента и выровняйте отступы.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="8a4eb-183">Отступ второго элемента необходимо выравнивать с первым символом после маркера нумерованного списка.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="8a4eb-184">Для однозначных номеров элементов, таких как этот, необходимо осуществлять отступ по столбцу 4.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="8a4eb-185">Для двузначных номеров элементов, например, для элемента № 10, необходимо осуществлять отступ по столбцу 5.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="8a4eb-186">Следующий элемент нумерованного списка начинается здесь.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="8a4eb-187">Изображения</span><span class="sxs-lookup"><span data-stu-id="8a4eb-187">Images</span></span>

<span data-ttu-id="8a4eb-188">Для включения изображения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="8a4eb-189">Здесь `alt text` — краткое описание изображения, а `<folder path>` — относительный путь к изображению.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="8a4eb-190">Необходимо указать дополнительный текст для средств чтения с экрана для лиц с ослабленным зрением.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-190">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="8a4eb-191">Этот текст также пригодится при возникновении ошибки на сайте, из-за которой изображение не будет отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-191">It is also useful in case there is a site bug where the image cannot be rendered.</span></span>

<span data-ttu-id="8a4eb-192">Изображения должны храниться в папке `media/<article-name>` в подпапке, содержащей статью.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-192">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="8a4eb-193">Изображения не должны одновременно использоваться в нескольких статьях.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-193">Images should not be shared between articles.</span></span> <span data-ttu-id="8a4eb-194">Создайте подпапку, соответствующую имени файла статьи, в папке `media`.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-194">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="8a4eb-195">Скопируйте изображения для этой статьи в созданную подпапку.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-195">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="8a4eb-196">Если изображение используется в нескольких статьях, необходимо скопировать это изображение в каждую подпапку с изображениями для соответствующей статьи.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-196">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="8a4eb-197">Это позволяет избежать ситуации, когда изменение изображения в одной статье влияет на другую статью.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-197">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="8a4eb-198">Поддерживаются следующие типы файлов изображений: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span><span class="sxs-lookup"><span data-stu-id="8a4eb-198">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="8a4eb-199">Расширения Markdown, поддерживаемые Open Publishing</span><span class="sxs-lookup"><span data-stu-id="8a4eb-199">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="8a4eb-200">[Пакет создания документации Майкрософт](/contribute/how-to-write-docs-auth-pack) содержит средства, которые поддерживают функции, уникальные для нашей системы публикации.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-200">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="8a4eb-201">Оповещения — это расширение Markdown для создания блочных цитат, которые отображаются на сайте docs.microsoft.com с цветовым оформлением и значками, указывающими на значимость содержимого.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-201">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="8a4eb-202">Поддерживаются следующие типы оповещений:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-202">The following alert types are supported:</span></span>

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

<span data-ttu-id="8a4eb-203">На сайте docs.microsoft.com эти оповещения выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-203">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="8a4eb-204">Блок примечаний</span><span class="sxs-lookup"><span data-stu-id="8a4eb-204">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="8a4eb-205">Информация, которую пользователь должен заметить даже при беглом чтении текста.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-205">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="8a4eb-206">Блок советов</span><span class="sxs-lookup"><span data-stu-id="8a4eb-206">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="8a4eb-207">Дополнительные сведения, которые могут пригодиться пользователю для успешного выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-207">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="8a4eb-208">Блок "Важно!"</span><span class="sxs-lookup"><span data-stu-id="8a4eb-208">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a4eb-209">Обязательные сведения, необходимые для успешного выполнения действия пользователем.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-209">Essential information required for user success.</span></span>

<span data-ttu-id="8a4eb-210">Блок "Внимание!"</span><span class="sxs-lookup"><span data-stu-id="8a4eb-210">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="8a4eb-211">Возможные отрицательные последствия действия.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-211">Negative potential consequences of an action.</span></span>

<span data-ttu-id="8a4eb-212">Блок "Предупреждение"</span><span class="sxs-lookup"><span data-stu-id="8a4eb-212">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="8a4eb-213">Определенные опасные последствия действия.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-213">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="8a4eb-214">Гиперссылки</span><span class="sxs-lookup"><span data-stu-id="8a4eb-214">Hyperlinks</span></span>

- <span data-ttu-id="8a4eb-215">Гиперссылки должны использовать синтаксис Markdown `[friendlyname](url-or-path)`.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-215">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`</span></span>
- <span data-ttu-id="8a4eb-216">По возможности следует использовать ссылки с HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-216">Links should be HTTPS when possible.</span></span>
- <span data-ttu-id="8a4eb-217">Ссылки должны иметь понятное имя (обычно это заголовок соответствующего раздела)</span><span class="sxs-lookup"><span data-stu-id="8a4eb-217">Links must have a friendly name, usually the title of the linked topic</span></span>
- <span data-ttu-id="8a4eb-218">Все элементы в разделе "Связанные ссылки" в нижней части страницы должны быть оформлены как гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-218">All items in the "related links" section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="8a4eb-219">Не используйте обратные кавычки, полужирный шрифт или другую разметку в квадратных скобках гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-219">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="8a4eb-220">Если речь идет о конкретном URI, можно использовать неоформленные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-220">Bare URLs may be used when you are talking about a specific URI.</span></span> <span data-ttu-id="8a4eb-221">URI должен быть заключен в обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-221">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="8a4eb-222">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-222">For example:</span></span>

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content"></a><span data-ttu-id="8a4eb-223">Ссылки на другое содержимое</span><span class="sxs-lookup"><span data-stu-id="8a4eb-223">Linking to other content</span></span>

<span data-ttu-id="8a4eb-224">Существует два типа гиперссылок, поддерживаемых системой публикации:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-224">There are two types of hyperlinks supported by the publishing system:</span></span>

<span data-ttu-id="8a4eb-225">В качестве **URL-адреса** можно указать путь URL-адреса, который является относительным к корню сайта docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-225">A **URL link** can be a URL path that is relative to the root of docs.microsoft.com.</span></span> <span data-ttu-id="8a4eb-226">Также можно указать абсолютный URL-адрес в соответствии с синтаксисом полного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-226">Or an absolute URL that include the full URL syntax.</span></span> <span data-ttu-id="8a4eb-227">Например: `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span><span class="sxs-lookup"><span data-stu-id="8a4eb-227">For example: `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span></span>

- <span data-ttu-id="8a4eb-228">Используйте URL-адреса для ссылки на содержимое, расположенное за пределами PowerShell, а также для ссылок между справкой по командлетам и абстрактными статьями в документации по PowerShell. Самый простой способ получить относительную ссылку — скопировать URL-адрес из браузера, а затем удалить `https://docs.microsoft.com/en-us` и вставить оставшуюся часть ссылки в Markdown.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-228">Use URL links when linking to content outside of PowerShell-Docs or between cmdlet reference and conceptual articles within PowerShell-docs. The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span>
- <span data-ttu-id="8a4eb-229">Не включайте языковой стандарт в URL-адреса страниц на сайтах Майкрософт (например,</span><span class="sxs-lookup"><span data-stu-id="8a4eb-229">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="8a4eb-230">удалите `/en-us` из URL-адреса).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-230">remove `/en-us` from URL).</span></span>
- <span data-ttu-id="8a4eb-231">Удалите ненужные параметры запроса из URL-адреса, если не требуется ссылка на определенную версию статьи.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-231">Remove any unnecessary query parameters from the URL unless you need to link to a specific version of an article.</span></span> <span data-ttu-id="8a4eb-232">Примеры:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-232">Examples:</span></span>
  - <span data-ttu-id="8a4eb-233">`?view=powershell-5.1` — используется для создания ссылки на определенную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-233">`?view=powershell-5.1` - this is used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="8a4eb-234">`?redirectedfrom=MSDN` — добавляется к URL-адресу при перенаправлении из старой статьи в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-234">`?redirectedfrom=MSDN` - this is added to the URL when you get redirected from an old article to its new location</span></span>
- <span data-ttu-id="8a4eb-235">Во всех URL-адресах, указывающих на внешние веб-сайты, должен использоваться префикс HTTPS, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-235">All URLs to external websites should use HTTPS unless that is not valid for the target site.</span></span>

<span data-ttu-id="8a4eb-236">**Ссылка на файл** используется для создания ссылки из одной справочной статьи на другую или из одной ознакомительной статьи на другую.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-236">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="8a4eb-237">Если необходимо создать ссылку на справочную статью для определенной версии PowerShell, используйте URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-237">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

- <span data-ttu-id="8a4eb-238">Ссылки на файлы содержат относительный путь к файлу (например, `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="8a4eb-238">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
- <span data-ttu-id="8a4eb-239">Во всех путях к файлам должна использоваться косая черта (`/`)</span><span class="sxs-lookup"><span data-stu-id="8a4eb-239">All file paths use forward-slash (`/`) characters</span></span>

<span data-ttu-id="8a4eb-240">Создание глубинных ссылок разрешено как для URL-адресов, так и для ссылок на файлы.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-240">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="8a4eb-241">Добавьте привязку в конец целевого пути.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-241">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="8a4eb-242">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-242">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="8a4eb-243">Дополнительные сведения см. в статье [Использование ссылок в документации](/contribute/how-to-write-links).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-243">For more information, see [Use links in documentation](/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="8a4eb-244">Элементы синтаксиса команды форматирования</span><span class="sxs-lookup"><span data-stu-id="8a4eb-244">Formatting command syntax elements</span></span>

- <span data-ttu-id="8a4eb-245">Всегда используйте полные имена командлетов и параметров.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-245">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="8a4eb-246">Старайтесь не использовать псевдонимы, если только вы не демонстрируете псевдоним специально.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-246">Avoid using aliases unless you are specifically demonstrating the alias.</span></span>

- <span data-ttu-id="8a4eb-247">Свойство, параметр, объект, имена типов, имена классов, методы класса должны быть выделены **полужирным** шрифтом.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-247">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="8a4eb-248">Значения свойств и параметров должны быть заключены в обратные кавычки (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-248">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="8a4eb-249">При указании типов в квадратных скобках используйте обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-249">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="8a4eb-250">Например: `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="8a4eb-250">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="8a4eb-251">Ключевые слова языка, имена командлетов, функции, переменные, собственные исполняемые файлы, пути к файлам и встроенные примеры синтаксиса должны быть заключены в символы обратных кавычек (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-251">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="8a4eb-252">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-252">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="8a4eb-253">При ссылке на параметр по имени его имя должно быть выделено **полужирным** шрифтом.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-253">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="8a4eb-254">При демонстрации использования параметра с префиксом дефиса параметр должен быть заключен в обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-254">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="8a4eb-255">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-255">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it is typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="8a4eb-256">При демонстрации примера использования внешней команды этот пример должен быть заключен в обратные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-256">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="8a4eb-257">Всегда включайте расширение файла в собственную команду.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-257">Always include the file extension in the native command.</span></span> <span data-ttu-id="8a4eb-258">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-258">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="8a4eb-259">Включение расширения файла гарантирует выполнение правильной команды в соответствии с очередностью команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-259">Including the file extension ensures that the correct command is executed according PowerShell's command precedence.</span></span>

- <span data-ttu-id="8a4eb-260">При оформлении абстрактной статьи (в отличие от справочных материалов) представляйте первый экземпляр имени командлета в виде гиперссылки на документацию по командлетам.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-260">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="8a4eb-261">Не используйте обратные кавычки, полужирный шрифт или другую разметку в квадратных скобках гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-261">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="8a4eb-262">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-262">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="8a4eb-263">Дополнительные сведения см. в разделе [Гиперссылки](#hyperlinks) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-263">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="8a4eb-264">Markdown для примеров кода</span><span class="sxs-lookup"><span data-stu-id="8a4eb-264">Markdown for code samples</span></span>

<span data-ttu-id="8a4eb-265">Markdown поддерживает два различных стиля кода:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-265">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="8a4eb-266">**Фрагменты кода (встроенный код)**  — помечаются символом обратных кавычек (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-266">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="8a4eb-267">Они используются внутри абзаца, а не в виде автономного блока.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-267">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="8a4eb-268">**Блоки кода** — это многострочный блок, заключенный в тройные обратные кавычки (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-268">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="8a4eb-269">В блоках кода после обратных кавычек также может быть указана метка языка.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-269">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="8a4eb-270">При указании метки языка включается подсветка синтаксиса для содержимого блока кода.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-270">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="8a4eb-271">Все блоки кода должны находиться в границах кода.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-271">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="8a4eb-272">Ни в коем случае не используйте отступы для блоков кода.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-272">Never use indentation for code blocks.</span></span> <span data-ttu-id="8a4eb-273">Markdown допускает использование такого шаблона, но это может вызвать проблемы, поэтому его следует избегать.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-273">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="8a4eb-274">Блок кода — это одна или несколько строк кода, заключенных в тройные обратные кавычки (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="8a4eb-274">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="8a4eb-275">Маркеры границ кода должны располагаться на отдельных строках до и после примера кода.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-275">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="8a4eb-276">Метка в начале блока кода может содержать метку языка.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-276">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="8a4eb-277">Система публикации Майкрософт Open Publishing System (OPS) использует метки языка для подсветки синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-277">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="8a4eb-278">Полный список поддерживаемых тегов языков см. в разделе [Огороженные блоки кода](/contribute/code-in-docs#fenced-code-blocks) централизованного руководства для участников.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-278">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="8a4eb-279">OPS также добавляет кнопку **Копировать**, которая копирует содержимое блока кода в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-279">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="8a4eb-280">Это позволяет быстро вставить код в скрипт для тестирования примера кода.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-280">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="8a4eb-281">Однако не все примеры в нашей документации предназначены для выполнения без модификации.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-281">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="8a4eb-282">Некоторые блоки кода просто иллюстрируют концепцию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-282">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="8a4eb-283">В нашей документации используются три типа блоков кода:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-283">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="8a4eb-284">Блоки синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-284">Syntax blocks</span></span>
1. <span data-ttu-id="8a4eb-285">Иллюстративные примеры</span><span class="sxs-lookup"><span data-stu-id="8a4eb-285">Illustrative examples</span></span>
1. <span data-ttu-id="8a4eb-286">Примеры для выполнения</span><span class="sxs-lookup"><span data-stu-id="8a4eb-286">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="8a4eb-287">Блоки кода синтаксиса</span><span class="sxs-lookup"><span data-stu-id="8a4eb-287">Syntax code blocks</span></span>

<span data-ttu-id="8a4eb-288">Блоки кода синтаксиса используются для описания синтаксической структуры команды.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-288">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="8a4eb-289">Не используйте тег языка в границе кода.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-289">Do not use a language tag on the code fence.</span></span> <span data-ttu-id="8a4eb-290">В этом примере показаны все возможные параметры командлета `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-290">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="8a4eb-291">В этом примере описана инструкция `for` с использованием обобщенных понятий:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-291">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="8a4eb-292">Иллюстративные примеры</span><span class="sxs-lookup"><span data-stu-id="8a4eb-292">Illustrative examples</span></span>

<span data-ttu-id="8a4eb-293">Иллюстративные примеры используются для объяснения концепции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-293">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="8a4eb-294">Они не предназначены для копирования в буфер обмена с целью последующего выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-294">They are not meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="8a4eb-295">Они чаще всего используются для простых примеров, код которых прост для понимания и который легко набрать.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-295">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="8a4eb-296">Блок кода может включать в себя командную строку PowerShell и выходные данные примера.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-296">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="8a4eb-297">Ниже приведен простой пример с операторами сравнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-297">Here is a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="8a4eb-298">В данном случае не предполагается, что читатель будет копировать и запускать этот пример.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-298">In this case, we don't intend the reader to copy and run this example.</span></span>

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

### <a name="executable-examples"></a><span data-ttu-id="8a4eb-299">Примеры для выполнения</span><span class="sxs-lookup"><span data-stu-id="8a4eb-299">Executable examples</span></span>

<span data-ttu-id="8a4eb-300">В сложных примерах и примерах, предназначенных для копирования и выполнения, должна использоваться следующая разметка с использованием обратных кавычек:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-300">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="8a4eb-301">Выходные данные команд PowerShell необходимо заключить в блок кода **Выходные данные**, чтобы для них не выполнялась подсветка синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-301">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="8a4eb-302">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a4eb-302">For example:</span></span>

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

<span data-ttu-id="8a4eb-303">Метка кода **Выходные данные** не является официальным "языком", поддерживаемым системой подсветки синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-303">The **Output** code label is not an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="8a4eb-304">Однако эта метка полезна, так как OPS добавляет метку "Выходные данные" в рамку блока кода на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-304">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="8a4eb-305">В блоке кода "Выходные данные" подсветка синтаксиса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-305">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="8a4eb-306">Стилевые правила оформления кода</span><span class="sxs-lookup"><span data-stu-id="8a4eb-306">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="8a4eb-307">Избегайте разрыва строк в примерах кода</span><span class="sxs-lookup"><span data-stu-id="8a4eb-307">Avoid line continuation in code samples</span></span>

<span data-ttu-id="8a4eb-308">Не используйте символы продолжения строки (`` ` ``) в примерах кода PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-308">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="8a4eb-309">Эти символы трудно увидеть и могут вызвать проблемы, если в конце строки есть лишние пробелы.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-309">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="8a4eb-310">Используйте сплаттинг PowerShell, чтобы сократить длину строки для командлетов с большим количеством параметров.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-310">Use PowerShell splatting to reduce line length for cmdlets that have a lot of parameters.</span></span>
- <span data-ttu-id="8a4eb-311">Используйте естественные возможности переноса строк в PowerShell, например, после символа вертикальной черты (`|`), открывающих фигурных скобок, круглых скобок и квадратных скобок.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-311">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces, parentheses, and brackets.</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="8a4eb-312">Избегайте использования командной строки PowerShell в примерах</span><span class="sxs-lookup"><span data-stu-id="8a4eb-312">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="8a4eb-313">Использование командной строки в примерах не рекомендуется и должно быть ограничено сценариями, предназначенными для иллюстрации использования командной строки.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-313">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command line usage.</span></span> <span data-ttu-id="8a4eb-314">В большинстве этих примеров командная строка должна иметь вид `PS>`.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-314">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="8a4eb-315">Такая командная строка не зависит от характеристик конкретной ОС.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-315">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="8a4eb-316">Командная строка требуется для примеров, иллюстрирующих команды, которые изменяют командную строку, или в тех случаях, когда отображаемый в командной строке путь важен для сценария, о котором идет речь.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-316">Prompts are required for examples that illustrate commands that alter the prompt or when the path displayed is significant to the scenario being illustrated.</span></span> <span data-ttu-id="8a4eb-317">В следующем примере показано изменение командной строки при использовании поставщика реестра.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-317">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

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

### <a name="do-not-use-aliases-in-examples"></a><span data-ttu-id="8a4eb-318">Не используйте псевдонимы в примерах</span><span class="sxs-lookup"><span data-stu-id="8a4eb-318">Do not use aliases in examples</span></span>

<span data-ttu-id="8a4eb-319">Следует всегда использовать полные имена командлетов и параметров, если только речь не идет именно об этом псевдониме.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-319">You should always use the full name of all cmdlets and parameters unless you are specifically talking about the alias.</span></span> <span data-ttu-id="8a4eb-320">При написании имен командлетов и параметров необходимо использовать нотацию в стиле Pascal.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-320">Cmdlet and parameter names must use the proper Pascal-cased names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="8a4eb-321">Использование параметров в примерах</span><span class="sxs-lookup"><span data-stu-id="8a4eb-321">Using parameters in examples</span></span>

<span data-ttu-id="8a4eb-322">Старайтесь не использовать позиционные параметры.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-322">Avoid using positional parameters.</span></span> <span data-ttu-id="8a4eb-323">В общем случае следует всегда включать в пример имя параметра, даже если параметр является позиционным.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-323">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="8a4eb-324">Это снижает вероятность путаницы в ваших примерах.</span><span class="sxs-lookup"><span data-stu-id="8a4eb-324">This reduces the chance of confusion in your examples.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a4eb-325">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8a4eb-325">Next steps</span></span>

[<span data-ttu-id="8a4eb-326">Редактирование справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="8a4eb-326">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
