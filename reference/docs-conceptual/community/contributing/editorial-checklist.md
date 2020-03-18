---
title: Контрольный список для редактора
description: Это сводный список правил по редактированию документации PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 511e0c323e1a3256039e819d06f32f6e1ac42767
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060339"
---
# <a name="editors-checklist"></a><span data-ttu-id="347c9-103">Контрольный список для редактора</span><span class="sxs-lookup"><span data-stu-id="347c9-103">Editor's checklist</span></span>

<span data-ttu-id="347c9-104">Это сводный список правил, которыми следует руководствоваться при написании новых или изменении существующих статей.</span><span class="sxs-lookup"><span data-stu-id="347c9-104">This is a summary of rules to apply when writing new or updating existing articles.</span></span> <span data-ttu-id="347c9-105">Подробные пояснения и примеры применения этих правил см. в других статьях в руководстве для участников.</span><span class="sxs-lookup"><span data-stu-id="347c9-105">See other articles in the Contributor's Guide for detailed explanations and examples of these rules.</span></span>

## <a name="metadata"></a><span data-ttu-id="347c9-106">Метаданные</span><span class="sxs-lookup"><span data-stu-id="347c9-106">Metadata</span></span>

- <span data-ttu-id="347c9-107">`ms.date`: требуется формат **ММ/ДД/ГГГГ**.</span><span class="sxs-lookup"><span data-stu-id="347c9-107">`ms.date`: must be in the format **MM/DD/YYYY**</span></span>
  - <span data-ttu-id="347c9-108">Измените дату при внесении значительного или фактического изменения:</span><span class="sxs-lookup"><span data-stu-id="347c9-108">Change the date when there is a significant or factual update</span></span>
    - <span data-ttu-id="347c9-109">реорганизации статьи;</span><span class="sxs-lookup"><span data-stu-id="347c9-109">Reorganizing the article</span></span>
    - <span data-ttu-id="347c9-110">исправлении фактических ошибок;</span><span class="sxs-lookup"><span data-stu-id="347c9-110">Fixing factual errors</span></span>
    - <span data-ttu-id="347c9-111">добавлении новой информации.</span><span class="sxs-lookup"><span data-stu-id="347c9-111">Adding new information</span></span>
  - <span data-ttu-id="347c9-112">Не изменяйте дату при внесении незначительного изменения:</span><span class="sxs-lookup"><span data-stu-id="347c9-112">Do not change the date if the update is insignificant</span></span>
    - <span data-ttu-id="347c9-113">исправлении опечаток или форматирования.</span><span class="sxs-lookup"><span data-stu-id="347c9-113">Fixing typos and formatting</span></span>
- <span data-ttu-id="347c9-114">`title`: уникальная строка длиной от 43 до 59 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="347c9-114">`title`: unique string of 43-59 chars including spaces</span></span>
  - <span data-ttu-id="347c9-115">Не включайте идентификатор сайта (он генерируется автоматически).</span><span class="sxs-lookup"><span data-stu-id="347c9-115">Do not include site identifier (it is auto-generated)</span></span>
  - <span data-ttu-id="347c9-116">Используйте регистр как в предложениях — с прописной буквы следует писать только первое слово и имена собственные.</span><span class="sxs-lookup"><span data-stu-id="347c9-116">Use sentence case - capitalize only the first word and any proper nouns</span></span>
- <span data-ttu-id="347c9-117">`description`: 115–145 символов, включая пробелы. Эта аннотация отображается в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="347c9-117">`description`: 115-145 characters including spaces - this abstract displays in the search result</span></span>

## <a name="formatting"></a><span data-ttu-id="347c9-118">Форматирование</span><span class="sxs-lookup"><span data-stu-id="347c9-118">Formatting</span></span>

- <span data-ttu-id="347c9-119">Элементы, встречающиеся в тексте абзаца, следует заключать в обратные апострофы:</span><span class="sxs-lookup"><span data-stu-id="347c9-119">Backtick syntax elements that appear, inline, within a paragraph</span></span>
  - <span data-ttu-id="347c9-120">имена командлетов (`Verb-Noun`);</span><span class="sxs-lookup"><span data-stu-id="347c9-120">Cmdlet names `Verb-Noun`</span></span>
  - <span data-ttu-id="347c9-121">переменные (`$counter`);</span><span class="sxs-lookup"><span data-stu-id="347c9-121">Variable `$counter`</span></span>
  - <span data-ttu-id="347c9-122">примеры синтаксиса (`Verb-Noun -Parameter`);</span><span class="sxs-lookup"><span data-stu-id="347c9-122">Syntactic examples `Verb-Noun -Parameter`</span></span>
  - <span data-ttu-id="347c9-123">пути к файлам (`C:\Program Files\PowerShell`, `/usr/bin/pwsh`);</span><span class="sxs-lookup"><span data-stu-id="347c9-123">File paths `C:\Program Files\PowerShell`, `/usr/bin/pwsh`</span></span>
  - <span data-ttu-id="347c9-124">URL-адреса, по которым нельзя перейти из документа.</span><span class="sxs-lookup"><span data-stu-id="347c9-124">URLs that are not meant to be clickable in the document</span></span>
- <span data-ttu-id="347c9-125">Используйте полужирный шрифт для имен свойств, значений параметров, имен параметров, имен классов, имен модулей, имен сущностей, имен объектов или типов.</span><span class="sxs-lookup"><span data-stu-id="347c9-125">Use bold for property names, parameter values, parameter names, class names, module names, entity names, object or type names</span></span>
  - <span data-ttu-id="347c9-126">Полужирный шрифт используется для семантической разметки, а не для выделения.</span><span class="sxs-lookup"><span data-stu-id="347c9-126">Bold is used for semantic markup, not emphasis</span></span>
  - <span data-ttu-id="347c9-127">Для выделения полужирным шрифтом используйте звездочки (`**`).</span><span class="sxs-lookup"><span data-stu-id="347c9-127">Bold - use asterisks `**`</span></span>
- <span data-ttu-id="347c9-128">Для выделения курсивным начертанием используйте символ подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="347c9-128">Italic - use underscore `_`</span></span>
  - <span data-ttu-id="347c9-129">Используется только для выделения, но не для семантической разметки.</span><span class="sxs-lookup"><span data-stu-id="347c9-129">Only used for emphasis, not for semantic markup</span></span>
- <span data-ttu-id="347c9-130">Используйте разрывы строк через 100 столбцов (или 80 для **about_Topics**).</span><span class="sxs-lookup"><span data-stu-id="347c9-130">Line breaks at 100 columns (or at 80 for **about_Topics**)</span></span>
- <span data-ttu-id="347c9-131">Не используйте жесткую табуляцию — только пробелы.</span><span class="sxs-lookup"><span data-stu-id="347c9-131">No hard tabs - use spaces only</span></span>
- <span data-ttu-id="347c9-132">В конце строк не должно быть пробелов.</span><span class="sxs-lookup"><span data-stu-id="347c9-132">No trailing spaces on lines</span></span>

### <a name="headers"></a><span data-ttu-id="347c9-133">Заголовки</span><span class="sxs-lookup"><span data-stu-id="347c9-133">Headers</span></span>

- <span data-ttu-id="347c9-134">Первый уровень — H1. В статье должен быть только один заголовок уровня H1.</span><span class="sxs-lookup"><span data-stu-id="347c9-134">H1 is first - only one H1 per article</span></span>
- <span data-ttu-id="347c9-135">Используйте только [заголовки ATX](https://github.github.com/gfm/#atx-headings).</span><span class="sxs-lookup"><span data-stu-id="347c9-135">Use [ATX Headers](https://github.github.com/gfm/#atx-headings) only</span></span>
- <span data-ttu-id="347c9-136">Используйте регистр как в предложениях для всех заголовков.</span><span class="sxs-lookup"><span data-stu-id="347c9-136">Use sentence case for all headers</span></span>
- <span data-ttu-id="347c9-137">Не пропускайте уровни — нельзя использовать уровень H3, если нет заголовка уровня H2.</span><span class="sxs-lookup"><span data-stu-id="347c9-137">Do not skip levels - no H3 without an H2</span></span>
- <span data-ttu-id="347c9-138">Максимальная глубина вложения — H3 или H4.</span><span class="sxs-lookup"><span data-stu-id="347c9-138">Max depth of H3 or H4</span></span>
- <span data-ttu-id="347c9-139">Перед заголовком и после него должна быть пустая строка.</span><span class="sxs-lookup"><span data-stu-id="347c9-139">Blank line before and after</span></span>
- <span data-ttu-id="347c9-140">В схеме PlatyPS применяются специальные заголовки — не добавляйте и не удаляйте их.</span><span class="sxs-lookup"><span data-stu-id="347c9-140">PlatyPS enforces specific headers in its schema - do not add or remove headers</span></span>

### <a name="code-blocks"></a><span data-ttu-id="347c9-141">Блоки кода</span><span class="sxs-lookup"><span data-stu-id="347c9-141">Code blocks</span></span>

- <span data-ttu-id="347c9-142">Перед заголовком и после него должна быть пустая строка.</span><span class="sxs-lookup"><span data-stu-id="347c9-142">Blank line before and after</span></span>
- <span data-ttu-id="347c9-143">Используйте ограждение кода с пометками — **powershell**, **Output** (Выходные данные) или иной идентификатор языка.</span><span class="sxs-lookup"><span data-stu-id="347c9-143">Use tagged code fences - **powershell**, **Output**, or other appropriate language ID</span></span>
- <span data-ttu-id="347c9-144">Используйте непомеченное ограждение для блоков синтаксиса или других оболочек.</span><span class="sxs-lookup"><span data-stu-id="347c9-144">Untagged fence - syntax blocks or other shells</span></span>
- <span data-ttu-id="347c9-145">**Выходные данные** следует выносить в отдельный блок кода, кроме простых примеров, которые не предполагают использования кнопки **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="347c9-145">Put **Output** in separate code block except for simple examples where you don't intend the for the reader to use the **Copy** button</span></span>
- <span data-ttu-id="347c9-146">См. список [поддерживаемых языков](/contribute/code-in-docs#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="347c9-146">See list of [supported languages](/contribute/code-in-docs#supported-languages)</span></span>

### <a name="lists"></a><span data-ttu-id="347c9-147">Списки</span><span class="sxs-lookup"><span data-stu-id="347c9-147">Lists</span></span>

- <span data-ttu-id="347c9-148">Правильные отступы.</span><span class="sxs-lookup"><span data-stu-id="347c9-148">Indented properly</span></span>
- <span data-ttu-id="347c9-149">Пустая строка перед первым элементом и после последнего элемента.</span><span class="sxs-lookup"><span data-stu-id="347c9-149">Blank line before first item and after last item</span></span>
- <span data-ttu-id="347c9-150">В качестве маркеров используйте дефисы (`-`), а не звездочки (`*`), которые легко спутать с символами выделения.</span><span class="sxs-lookup"><span data-stu-id="347c9-150">Bullet - use hyphen (`-`) not asterisk (`*`) - too easy to confuse with emphasis</span></span>
- <span data-ttu-id="347c9-151">В нумерованных списках используется формат нумерации "1."</span><span class="sxs-lookup"><span data-stu-id="347c9-151">For numbered lists, all numbers are "1."</span></span>

## <a name="terminology"></a><span data-ttu-id="347c9-152">Терминология</span><span class="sxs-lookup"><span data-stu-id="347c9-152">Terminology</span></span>

- <span data-ttu-id="347c9-153">PowerShell, Windows PowerShell и PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="347c9-153">PowerShell vs. Windows PowerShell vs. PowerShell Core</span></span>
- <span data-ttu-id="347c9-154">См. [терминологию продукта](powershell-style-guide.md#product-terminology).</span><span class="sxs-lookup"><span data-stu-id="347c9-154">See [Product Terminology](powershell-style-guide.md#product-terminology)</span></span>

## <a name="cmdlet-reference-examples"></a><span data-ttu-id="347c9-155">Примеры в справке по командлету</span><span class="sxs-lookup"><span data-stu-id="347c9-155">Cmdlet reference examples</span></span>

- <span data-ttu-id="347c9-156">В справке по командлету должен быть по крайней мере один пример.</span><span class="sxs-lookup"><span data-stu-id="347c9-156">Must have at least one example in cmdlet reference</span></span>
- <span data-ttu-id="347c9-157">Пример должен содержать ровно столько кода, сколько нужно для демонстрации использования.</span><span class="sxs-lookup"><span data-stu-id="347c9-157">Examples should be just enough code to demonstrate the usage</span></span>
- <span data-ttu-id="347c9-158">Синтаксис PowerShell</span><span class="sxs-lookup"><span data-stu-id="347c9-158">PowerShell syntax</span></span>
  - <span data-ttu-id="347c9-159">Используйте полные имена командлетов и параметров, а не псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="347c9-159">Use full names of cmdlets and parameters - no aliases</span></span>
  - <span data-ttu-id="347c9-160">Если командная строка слишком длинная, используйте сплаттинг для параметров.</span><span class="sxs-lookup"><span data-stu-id="347c9-160">Use splatting for parameters when the command line gets too long</span></span>
  - <span data-ttu-id="347c9-161">Избегайте использования обратных апострофов для продолжения строки — прибегайте к ним только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="347c9-161">Avoid using line continuation backticks - only use when necessary</span></span>
- <span data-ttu-id="347c9-162">Удаляйте или сокращайте приглашение командной строки PowerShell (`PS>`), за исключением случаев, когда оно необходимо для примера.</span><span class="sxs-lookup"><span data-stu-id="347c9-162">Remove or simplify the PowerShell prompt (`PS>`) except where required for the example</span></span>
- <span data-ttu-id="347c9-163">Пример в справке по командлету должен соответствовать следующей схеме PlatyPS:</span><span class="sxs-lookup"><span data-stu-id="347c9-163">Cmdlet reference example must follow the following PlatyPS schema</span></span>

  ~~~Markdown
  ### Example 1 - Descriptive title

  Zero or more short descriptive paragraphs explaining the context of the example followed by one or
  more code blocks. Recommend at least one and no more than two.

  ```powershell
  ... one or more PowerShell code statements ...
  ```

  ```Output
  Example output of the code above.
  ```

  Zero or more optional follow up paragraphs that explain the details of the code and output.
  ~~~

- <span data-ttu-id="347c9-164">Не помещайте абзацы между блоками кода.</span><span class="sxs-lookup"><span data-stu-id="347c9-164">Do not put paragraphs between the code blocks.</span></span> <span data-ttu-id="347c9-165">Весь текст с описанием должен располагаться до или после блоков кода.</span><span class="sxs-lookup"><span data-stu-id="347c9-165">All descriptive content must come before or after the code blocks.</span></span>

## <a name="linking-to-other-documents"></a><span data-ttu-id="347c9-166">Ссылки на другие документы</span><span class="sxs-lookup"><span data-stu-id="347c9-166">Linking to other documents</span></span>

- <span data-ttu-id="347c9-167">Ссылки на материалы за пределами набора документов или между справкой по командлетам и концептуальными статьями</span><span class="sxs-lookup"><span data-stu-id="347c9-167">Linking outside the docset or between cmdlet reference and conceptual</span></span>
  - <span data-ttu-id="347c9-168">Для ссылок на сайт docs.microsoft.com используйте относительные URL-адреса (убирайте `https://docs.microsoft.com/en-us`).</span><span class="sxs-lookup"><span data-stu-id="347c9-168">Use relative URLs when linking to docs.microsoft.com (remove `https://docs.microsoft.com/en-us`)</span></span>
  - <span data-ttu-id="347c9-169">Не включайте языковой стандарт в URL-адреса страниц на сайтах Майкрософт (например,</span><span class="sxs-lookup"><span data-stu-id="347c9-169">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="347c9-170">удалите `/en-us` из URL-адреса).</span><span class="sxs-lookup"><span data-stu-id="347c9-170">remove `/en-us` from URL)</span></span>
  - <span data-ttu-id="347c9-171">Во всех URL-адресах, указывающих на внешние веб-сайты, должен использоваться префикс HTTPS, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="347c9-171">All URLs to external websites should use HTTPS unless that is not valid for the target site</span></span>
- <span data-ttu-id="347c9-172">Ссылки в пределах набора документов:</span><span class="sxs-lookup"><span data-stu-id="347c9-172">Within docset</span></span>
  - <span data-ttu-id="347c9-173">используйте пути к файлам (например, `../folder/file.md`);</span><span class="sxs-lookup"><span data-stu-id="347c9-173">Link to file path (e.g. `../folder/file.md`)</span></span>
  - <span data-ttu-id="347c9-174">во всех путях к файлам должна использоваться косая черта (`/`).</span><span class="sxs-lookup"><span data-stu-id="347c9-174">All file paths use forward-slash (`/`) characters</span></span>
- <span data-ttu-id="347c9-175">Ссылки на изображения должны иметь уникальный замещающий текст.</span><span class="sxs-lookup"><span data-stu-id="347c9-175">Image links should have unique alt text</span></span>
