---
title: Изменение справочных статей
description: В этой статье приводятся правила, касающиеся редактирования справки по командлетам и других справочных статей в документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 3aed1c14429310c57681397d4877a3a6f48400fd
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500973"
---
# <a name="editing-reference-articles"></a><span data-ttu-id="f8345-103">Изменение справочных статей</span><span class="sxs-lookup"><span data-stu-id="f8345-103">Editing reference articles</span></span>

<span data-ttu-id="f8345-104">Справочные статьи по командлетам имеют определенную структуру.</span><span class="sxs-lookup"><span data-stu-id="f8345-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="f8345-105">Она определяется модулем [PlatyPS][].</span><span class="sxs-lookup"><span data-stu-id="f8345-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="f8345-106">Средство PlatyPS создает справку по командлетам для модулей PowerShell в разметке Markdown.</span><span class="sxs-lookup"><span data-stu-id="f8345-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="f8345-107">После редактирования файлов Markdown с помощью PlatyPS создаются MAML-файлы справки, используемые командлетом `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="f8345-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="f8345-108">В коде PlatyPS жестко задана схема для справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="f8345-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="f8345-109">Ее описание можно найти в документе [platyPS.schema.md][].</span><span class="sxs-lookup"><span data-stu-id="f8345-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="f8345-110">Нарушения схемы приводят к ошибкам сборки, которые необходимо исправить, иначе ваше содержимое не будет принято.</span><span class="sxs-lookup"><span data-stu-id="f8345-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="f8345-111">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="f8345-111">General guidelines</span></span>

- <span data-ttu-id="f8345-112">Не удаляйте заголовки.</span><span class="sxs-lookup"><span data-stu-id="f8345-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="f8345-113">PlatyPS требует определенного набора заголовков.</span><span class="sxs-lookup"><span data-stu-id="f8345-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="f8345-114">Под заголовками **Input type** (Тип входных данных) и **Output type** (Тип выходных данных) должен быть указан тип.</span><span class="sxs-lookup"><span data-stu-id="f8345-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="f8345-115">Если командлет не принимает входные данные или не возвращает значение, используйте значение `None` (Нет).</span><span class="sxs-lookup"><span data-stu-id="f8345-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="f8345-116">Огражденные блоки кода допускаются только в разделе [Examples](#structuring-examples) (Примеры).</span><span class="sxs-lookup"><span data-stu-id="f8345-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="f8345-117">Встроенные фрагменты кода можно использовать в любом абзаце.</span><span class="sxs-lookup"><span data-stu-id="f8345-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="f8345-118">Форматирование файлов About_</span><span class="sxs-lookup"><span data-stu-id="f8345-118">Formatting About_ files</span></span>

<span data-ttu-id="f8345-119">Файлы `About_*` теперь обрабатываются средством [Pandoc][], а не PlatyPS.</span><span class="sxs-lookup"><span data-stu-id="f8345-119">`About_*` files are now processed by [Pandoc][], instead of PlatyPS.</span></span> <span data-ttu-id="f8345-120">Файлы `About_*` форматируются так, чтобы они были максимально совместимы со всеми версиями PowerShell и средствами публикации.</span><span class="sxs-lookup"><span data-stu-id="f8345-120">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="f8345-121">Основные рекомендации по форматированию.</span><span class="sxs-lookup"><span data-stu-id="f8345-121">Basic formatting guidelines:</span></span>

- <span data-ttu-id="f8345-122">Ограничьте длину строк 80 символами.</span><span class="sxs-lookup"><span data-stu-id="f8345-122">Limit lines to 80 characters</span></span>
- <span data-ttu-id="f8345-123">Длина строк в блоках кода и таблицах ограничена 76 символами, так как при преобразовании средством Pandoc в обычный текст они получают отступ в четыре пробела.</span><span class="sxs-lookup"><span data-stu-id="f8345-123">Code blocks and tables are limited to 76 characters because Pandoc indents these by four spaces during conversion to plain text</span></span>
- <span data-ttu-id="f8345-124">Ширина таблиц должна быть не более 76 символов.</span><span class="sxs-lookup"><span data-stu-id="f8345-124">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="f8345-125">Переносите содержимое ячеек по строкам вручную.</span><span class="sxs-lookup"><span data-stu-id="f8345-125">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="f8345-126">Используйте открывающие и закрывающие символы `|` в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="f8345-126">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="f8345-127">Рабочий пример см. в разделе [about_Comparison_Operators][about-example].</span><span class="sxs-lookup"><span data-stu-id="f8345-127">See a working example in [about_Comparison_Operators][about-example]</span></span>
- <span data-ttu-id="f8345-128">Использование специальных символов Pandoc `\`, `$` и `<`:</span><span class="sxs-lookup"><span data-stu-id="f8345-128">Using Pandoc special characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="f8345-129">в заголовке эти символы должны быть экранированы с помощью начального символа `\` или заключены в обратные апострофы (`` ` ``);</span><span class="sxs-lookup"><span data-stu-id="f8345-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in backticks (`` ` ``)</span></span>
  - <span data-ttu-id="f8345-130">в абзаце эти символы должны включаться во фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="f8345-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="f8345-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8345-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

## <a name="structuring-examples"></a><span data-ttu-id="f8345-132">Структурирование примеров</span><span class="sxs-lookup"><span data-stu-id="f8345-132">Structuring examples</span></span>

<span data-ttu-id="f8345-133">В схеме PlatyPS заголовок **EXAMPLES** (Примеры) имеет уровень H2, а заголовок каждого примера — уровень H3.</span><span class="sxs-lookup"><span data-stu-id="f8345-133">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="f8345-134">Внутри примера схема не позволяет разделять блоки кода абзацами.</span><span class="sxs-lookup"><span data-stu-id="f8345-134">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="f8345-135">Допустимая схема:</span><span class="sxs-lookup"><span data-stu-id="f8345-135">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="f8345-136">Пронумеруйте все примеры и снабдите их краткими заголовками.</span><span class="sxs-lookup"><span data-stu-id="f8345-136">Number each example and add a brief title.</span></span>

<span data-ttu-id="f8345-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8345-137">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="f8345-138">Пример 1: Получение командлетов, функций и псевдонимов</span><span class="sxs-lookup"><span data-stu-id="f8345-138">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="f8345-139">Эта команда получает командлеты, функции и псевдонимы PowerShell, которые устанавливаются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f8345-139">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="f8345-140">Пример 2. Получение команд в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="f8345-140">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="f8345-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f8345-141">Next steps</span></span>

[<span data-ttu-id="f8345-142">Контрольный список для редактора</span><span class="sxs-lookup"><span data-stu-id="f8345-142">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
