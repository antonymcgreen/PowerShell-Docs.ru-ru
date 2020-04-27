---
title: Изменение справочных статей
description: В этой статье приводятся правила, касающиеся редактирования справки по командлетам и других справочных статей в документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: e135f6cc81ba7537a535a08421e1ca9b2b2af573
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624777"
---
# <a name="editing-reference-articles"></a><span data-ttu-id="1ddd1-103">Изменение справочных статей</span><span class="sxs-lookup"><span data-stu-id="1ddd1-103">Editing reference articles</span></span>

<span data-ttu-id="1ddd1-104">Справочные статьи по командлетам имеют определенную структуру.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="1ddd1-105">Она определяется модулем [PlatyPS][].</span><span class="sxs-lookup"><span data-stu-id="1ddd1-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="1ddd1-106">Средство PlatyPS создает справку по командлетам для модулей PowerShell в разметке Markdown.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="1ddd1-107">После редактирования файлов Markdown с помощью PlatyPS создаются MAML-файлы справки, используемые командлетом `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="1ddd1-108">В коде PlatyPS жестко задана схема для справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="1ddd1-109">Ее описание можно найти в документе [platyPS.schema.md][].</span><span class="sxs-lookup"><span data-stu-id="1ddd1-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="1ddd1-110">Нарушения схемы приводят к ошибкам сборки, которые необходимо исправить, иначе ваше содержимое не будет принято.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="1ddd1-111">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="1ddd1-111">General guidelines</span></span>

- <span data-ttu-id="1ddd1-112">Не удаляйте заголовки.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="1ddd1-113">PlatyPS требует определенного набора заголовков.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="1ddd1-114">Под заголовками **Input type** (Тип входных данных) и **Output type** (Тип выходных данных) должен быть указан тип.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="1ddd1-115">Если командлет не принимает входные данные или не возвращает значение, используйте значение `None` (Нет).</span><span class="sxs-lookup"><span data-stu-id="1ddd1-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="1ddd1-116">Огражденные блоки кода допускаются только в разделе [Examples](#structuring-examples) (Примеры).</span><span class="sxs-lookup"><span data-stu-id="1ddd1-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="1ddd1-117">Встроенные фрагменты кода можно использовать в любом абзаце.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="1ddd1-118">Форматирование файлов About_</span><span class="sxs-lookup"><span data-stu-id="1ddd1-118">Formatting About_ files</span></span>

<span data-ttu-id="1ddd1-119">Файлы `About_*` записываются в Markdown, но поставляются в виде обычных текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-119">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="1ddd1-120">Для преобразования Markdown в обычный текст используется [Pandoc][].</span><span class="sxs-lookup"><span data-stu-id="1ddd1-120">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="1ddd1-121">Файлы `About_*` форматируются так, чтобы они были максимально совместимы со всеми версиями PowerShell и средствами публикации.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-121">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="1ddd1-122">Основные рекомендации по форматированию.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-122">Basic formatting guidelines:</span></span>

- <span data-ttu-id="1ddd1-123">Ограничьте длину строк 80 символами.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-123">Limit lines to 80 characters.</span></span> <span data-ttu-id="1ddd1-124">Pandoc делает отступ для некоторых блоков Markdown, чтобы выровнять эти блоки.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-124">Pandoc indents some Markdown blocks so those block must be adjusted.</span></span>
  - <span data-ttu-id="1ddd1-125">Длина блоков кода ограничена 76 символами.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-125">Code blocks are limited to 76 characters</span></span>
  - <span data-ttu-id="1ddd1-126">Длина таблиц ограничена 76 символами.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-126">Tables are limited 76 characters</span></span>
  - <span data-ttu-id="1ddd1-127">Блоки цитирования (и оповещения) ограничены 78 символами.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-127">Blockquotes (and Alerts) are limited 78 characters</span></span>

- <span data-ttu-id="1ddd1-128">Используйте специальные символы Pandoc в заголовке: `\`, `$` и `<`.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-128">Using Pandoc's special meta-characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="1ddd1-129">Эти символы должны быть экранированы с помощью начального символа `\` или включены во встроенные фрагменты кода с помощью обратных апострофов (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="1ddd1-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="1ddd1-130">в абзаце эти символы должны включаться во фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="1ddd1-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="1ddd1-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="1ddd1-132">Ширина таблиц должна быть не более 76 символов.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-132">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="1ddd1-133">Переносите содержимое ячеек по строкам вручную.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-133">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="1ddd1-134">Используйте открывающие и закрывающие символы `|` в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-134">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="1ddd1-135">В следующем примере показано, как правильно создать таблицу со сведениями, которые переносятся на несколько строк в ячейке.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-135">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

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
    > <span data-ttu-id="1ddd1-136">Ограничение в 76 столбцов применяется только к разделам `About_*`.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-136">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="1ddd1-137">Широкие столбцы можно использовать в обзорной или справочной документации по командлетам.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-137">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="structuring-examples"></a><span data-ttu-id="1ddd1-138">Структурирование примеров</span><span class="sxs-lookup"><span data-stu-id="1ddd1-138">Structuring examples</span></span>

<span data-ttu-id="1ddd1-139">В схеме PlatyPS заголовок **EXAMPLES** (Примеры) имеет уровень H2, а заголовок каждого примера — уровень H3.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-139">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="1ddd1-140">Внутри примера схема не позволяет разделять блоки кода абзацами.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-140">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="1ddd1-141">Допустимая схема:</span><span class="sxs-lookup"><span data-stu-id="1ddd1-141">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="1ddd1-142">Пронумеруйте все примеры и снабдите их краткими заголовками.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-142">Number each example and add a brief title.</span></span>

<span data-ttu-id="1ddd1-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="1ddd1-143">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="1ddd1-144">Пример 1: Получение командлетов, функций и псевдонимов</span><span class="sxs-lookup"><span data-stu-id="1ddd1-144">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="1ddd1-145">Эта команда получает командлеты, функции и псевдонимы PowerShell, которые устанавливаются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1ddd1-145">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="1ddd1-146">Пример 2. Получение команд в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="1ddd1-146">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="1ddd1-147">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1ddd1-147">Next steps</span></span>

[<span data-ttu-id="1ddd1-148">Контрольный список для редактора</span><span class="sxs-lookup"><span data-stu-id="1ddd1-148">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
