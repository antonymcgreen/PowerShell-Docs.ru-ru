---
title: Создание справки на основе XML с помощью PlatyPS
description: Использование PlatyPS — это быстрый и эффективный способ создания справки на основе XML.
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972598"
---
# <a name="create-xml-based-help-using-platyps"></a><span data-ttu-id="02b67-103">Создание справки на основе XML с помощью PlatyPS</span><span class="sxs-lookup"><span data-stu-id="02b67-103">Create XML-based help using PlatyPS</span></span>

<span data-ttu-id="02b67-104">При создании модуля PowerShell всегда рекомендуется включать подробную справку по созданным командлетам.</span><span class="sxs-lookup"><span data-stu-id="02b67-104">When creating a PowerShell module, it is always recommended that you include detailed help for the cmdlets you create.</span></span> <span data-ttu-id="02b67-105">Если командлеты реализованы в компилированном коде, необходимо использовать справку на основе XML.</span><span class="sxs-lookup"><span data-stu-id="02b67-105">If your cmdlets are implemented in compiled code, you must use the XML-based help.</span></span> <span data-ttu-id="02b67-106">Этот формат XML известен как язык разметки Microsoft Assistance (MAML).</span><span class="sxs-lookup"><span data-stu-id="02b67-106">This XML format is known as the Microsoft Assistance Markup Language (MAML).</span></span>

<span data-ttu-id="02b67-107">В устаревшей документации по пакету SDK PowerShell содержатся сведения о создании справки по командлетам PowerShell, упакованным в модули.</span><span class="sxs-lookup"><span data-stu-id="02b67-107">The legacy PowerShell SDK documentation covers the details of creating help for PowerShell cmdlets packaged into modules.</span></span> <span data-ttu-id="02b67-108">Однако PowerShell не предоставляет средства для создания справки на основе XML.</span><span class="sxs-lookup"><span data-stu-id="02b67-108">However, PowerShell does not provide any tools for creating the XML-based help.</span></span> <span data-ttu-id="02b67-109">В документации по пакету SDK описывается структура справки MAML, но вы должны сами создать сложное содержимое MAML с множеством вложенных разделов.</span><span class="sxs-lookup"><span data-stu-id="02b67-109">The SDK documentation explains the structure of MAML help, but leaves you the task of creating the complex, and deeply nested, MAML content by hand.</span></span>

<span data-ttu-id="02b67-110">В этом вам поможет модуль [PlatyPS][].</span><span class="sxs-lookup"><span data-stu-id="02b67-110">This is where the [PlatyPS][] module can help.</span></span>

## <a name="what-is-platyps"></a><span data-ttu-id="02b67-111">Что такое PlatyPS?</span><span class="sxs-lookup"><span data-stu-id="02b67-111">What is PlatyPS?</span></span>

<span data-ttu-id="02b67-112">PlatyPS — это инструмент [с открытым кодом][platyps-repo], который был придуман в рамках _хакатона_, чтобы упростить создание и обслуживание MAML.</span><span class="sxs-lookup"><span data-stu-id="02b67-112">PlatyPS is an [open-source][platyps-repo] tool that started as a _hackathon_ project to make the creation and maintenance of MAML easier.</span></span> <span data-ttu-id="02b67-113">PlatyPS документирует синтаксис наборов параметров и отдельных параметров для каждого командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="02b67-113">PlatyPS documents the syntax of parameter sets and the individual parameters for each cmdlet in your module.</span></span> <span data-ttu-id="02b67-114">PlatyPS создает структурированные файлы [Markdown][], содержащие сведения о синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="02b67-114">PlatyPS creates structured [Markdown][] files that contain the syntax information.</span></span> <span data-ttu-id="02b67-115">Он не может создавать описания или предоставлять примеры,</span><span class="sxs-lookup"><span data-stu-id="02b67-115">It can't create descriptions or provide examples.</span></span>

<span data-ttu-id="02b67-116">зато создает заполнители для описаний и примеров.</span><span class="sxs-lookup"><span data-stu-id="02b67-116">PlatyPS creates placeholders for you to fill in descriptions and examples.</span></span> <span data-ttu-id="02b67-117">После добавления необходимой информации PlatyPS компилирует файлы Markdown в файлы MAML.</span><span class="sxs-lookup"><span data-stu-id="02b67-117">After adding the required information, PlatyPS compiles the Markdown files into MAML files.</span></span> <span data-ttu-id="02b67-118">Справочная система PowerShell также допускает файлы справки в виде обычного текста (разделы общих сведений).</span><span class="sxs-lookup"><span data-stu-id="02b67-118">PowerShell's help system also allows for plain-text conceptual help files (about topics).</span></span> <span data-ttu-id="02b67-119">В PlatyPS есть командлет для создания структурированного шаблона Markdown для нового файла _общих сведений_, но эти файлы `about_*.help.txt` необходимо обслуживать вручную.</span><span class="sxs-lookup"><span data-stu-id="02b67-119">PlatyPS has a cmdlet to create a structured Markdown template for a new _about_ file, but these `about_*.help.txt` files must be maintained manually.</span></span>

<span data-ttu-id="02b67-120">В модуль можно включить файлы справки MAML и текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="02b67-120">You can include the MAML and Text help files with your module.</span></span> <span data-ttu-id="02b67-121">Можно также использовать PlatyPS для компиляции файлов справки в пакет CAB, который можно разместить для реализации функции обновления.</span><span class="sxs-lookup"><span data-stu-id="02b67-121">You can also use PlatyPS to compile the help files into a CAB package that can be hosted for updateable help.</span></span>

## <a name="get-started-using-platyps"></a><span data-ttu-id="02b67-122">Начало работы с PlatyPS</span><span class="sxs-lookup"><span data-stu-id="02b67-122">Get started using PlatyPS</span></span>

<span data-ttu-id="02b67-123">Сначала необходимо установить PlatyPS из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02b67-123">First you must install PlatyPS from the PowerShell Gallery.</span></span>

```powershell
Install-Module platyps -Force
Import-Module platyps
```

<span data-ttu-id="02b67-124">В следующей блок-схеме описывается процесс создания или обновления справочного содержимого PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02b67-124">The following flowchart outlines the process for creating or updating PowerShell reference content.</span></span>

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="Рабочий процесс создания справки на основе XML с помощью PlatyPS":::

##  <a name="create-markdown-content-for-a-powershell-module"></a><span data-ttu-id="02b67-126">Создание содержимого Markdown для модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="02b67-126">Create Markdown content for a PowerShell module</span></span>

1. <span data-ttu-id="02b67-127">Импортируйте новый модуль в сеанс.</span><span class="sxs-lookup"><span data-stu-id="02b67-127">Import your new module into the session.</span></span> <span data-ttu-id="02b67-128">Повторите этот шаг для каждого модуля, который необходимо задокументировать.</span><span class="sxs-lookup"><span data-stu-id="02b67-128">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="02b67-129">Выполните следующую команду для импорта модулей.</span><span class="sxs-lookup"><span data-stu-id="02b67-129">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="02b67-130">Используйте PlatyPS для создания файлов Markdown для страницы модуля и всех связанных командлетов в модуле.</span><span class="sxs-lookup"><span data-stu-id="02b67-130">Use PlatyPS to generate Markdown files for your module page and all associated cmdlets within the module.</span></span> <span data-ttu-id="02b67-131">Повторите этот шаг для каждого модуля, который необходимо задокументировать.</span><span class="sxs-lookup"><span data-stu-id="02b67-131">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   <span data-ttu-id="02b67-132">Если папка выходных данных не существует, `New-MarkdownHelp` создаст ее.</span><span class="sxs-lookup"><span data-stu-id="02b67-132">If the output folder does not exist, `New-MarkdownHelp` creates it.</span></span> <span data-ttu-id="02b67-133">В этом примере `New-MarkdownHelp` создает файл Markdown для каждого командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="02b67-133">In this example, `New-MarkdownHelp` creates a Markdown file for each cmdlet in the module.</span></span> <span data-ttu-id="02b67-134">Он также создает _страницу модуля_ в файле с именем `<ModuleName>.md`.</span><span class="sxs-lookup"><span data-stu-id="02b67-134">It also creates the _module page_ in a file named `<ModuleName>.md`.</span></span> <span data-ttu-id="02b67-135">Эта страница модуля включает список командлетов, содержащихся в модуле, и заполнители для **краткого описания**.</span><span class="sxs-lookup"><span data-stu-id="02b67-135">This module page contains a list of the cmdlets contained in the module and placeholders for the **Synopsis** description.</span></span> <span data-ttu-id="02b67-136">Метаданные на странице модуля берутся из манифеста модуля и используются PlatyPS для создания XML-файла HelpInfo (как описано [ниже](#creating-an-updateable-help-package)).</span><span class="sxs-lookup"><span data-stu-id="02b67-136">The metadata in the module page comes from the module manifest and is used by PlatyPS to create the HelpInfo XML file (as explained [below](#creating-an-updateable-help-package)).</span></span>

   <span data-ttu-id="02b67-137">`New-MarkdownAboutHelp` создает новый файл _общих сведений_ с именем `about_topic_name.md`.</span><span class="sxs-lookup"><span data-stu-id="02b67-137">`New-MarkdownAboutHelp` creates a new _about_ file named `about_topic_name.md`.</span></span>

   <span data-ttu-id="02b67-138">Дополнительные сведения см. в статьях [New-MarkdownHelp][] и [New-MarkdownAboutHelp][].</span><span class="sxs-lookup"><span data-stu-id="02b67-138">For more information, see [New-MarkdownHelp][] and [New-MarkdownAboutHelp][].</span></span>

### <a name="update-existing-markdown-content-when-the-module-changes"></a><span data-ttu-id="02b67-139">Обновление существующего содержимого Markdown при изменении модуля</span><span class="sxs-lookup"><span data-stu-id="02b67-139">Update existing Markdown content when the module changes</span></span>

<span data-ttu-id="02b67-140">PlatyPS также может обновлять существующие файлы Markdown для модуля.</span><span class="sxs-lookup"><span data-stu-id="02b67-140">PlatyPS can also update existing Markdown files for a module.</span></span> <span data-ttu-id="02b67-141">Используйте этот шаг, чтобы обновить существующие модули с новыми командлетами, новыми параметрами или измененными параметрами.</span><span class="sxs-lookup"><span data-stu-id="02b67-141">Use this step to update existing modules that have new cmdlets, new parameters, or parameters that have changed.</span></span>

1. <span data-ttu-id="02b67-142">Импортируйте новый модуль в сеанс.</span><span class="sxs-lookup"><span data-stu-id="02b67-142">Import your new module into the session.</span></span> <span data-ttu-id="02b67-143">Повторите этот шаг для каждого модуля, который необходимо задокументировать.</span><span class="sxs-lookup"><span data-stu-id="02b67-143">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="02b67-144">Выполните следующую команду для импорта модулей.</span><span class="sxs-lookup"><span data-stu-id="02b67-144">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="02b67-145">Используйте PlatyPS для обновления файлов Markdown для целевой страницы модуля и всех связанных командлетов в модуле.</span><span class="sxs-lookup"><span data-stu-id="02b67-145">Use PlatyPS to update Markdown files for your module landing page and all associated cmdlets within the module.</span></span> <span data-ttu-id="02b67-146">Повторите этот шаг для каждого модуля, который необходимо задокументировать.</span><span class="sxs-lookup"><span data-stu-id="02b67-146">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   <span data-ttu-id="02b67-147">`Update-MarkdownHelpModule` обновляет командлет и файлы Markdown модуля в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="02b67-147">`Update-MarkdownHelpModule` updates the cmdlet and module Markdown files in the specified folder.</span></span>
   <span data-ttu-id="02b67-148">Файлы `about_*.md` не обновляются.</span><span class="sxs-lookup"><span data-stu-id="02b67-148">It does not update the `about_*.md` files.</span></span> <span data-ttu-id="02b67-149">Файл модуля (`ModuleName.md`) получает новый текст **краткого описания**, добавленный в файлы командлетов.</span><span class="sxs-lookup"><span data-stu-id="02b67-149">The module file (`ModuleName.md`) receives any new **Synopsis** text that has been added to the cmdlet files.</span></span> <span data-ttu-id="02b67-150">Обновления файлов командлетов включают следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="02b67-150">Updates to cmdlet files include the following change:</span></span>

   - <span data-ttu-id="02b67-151">Наборы новых параметров</span><span class="sxs-lookup"><span data-stu-id="02b67-151">New parameter sets</span></span>
   - <span data-ttu-id="02b67-152">Новые параметры</span><span class="sxs-lookup"><span data-stu-id="02b67-152">New parameters</span></span>
   - <span data-ttu-id="02b67-153">Обновленные метаданные параметра</span><span class="sxs-lookup"><span data-stu-id="02b67-153">Updated parameter metadata</span></span>
   - <span data-ttu-id="02b67-154">Обновленные сведения о типах входных и выходных данных</span><span class="sxs-lookup"><span data-stu-id="02b67-154">Updated input and output type information</span></span>

   <span data-ttu-id="02b67-155">Дополнительные сведения см. в разделе [Update-MarkdownHelpModule][].</span><span class="sxs-lookup"><span data-stu-id="02b67-155">For more information, see [Update-MarkdownHelpModule][].</span></span>

## <a name="edit-the-new-or-updated-markdown-files"></a><span data-ttu-id="02b67-156">Изменение новых или обновленных файлов Markdown</span><span class="sxs-lookup"><span data-stu-id="02b67-156">Edit the new or updated Markdown files</span></span>

<span data-ttu-id="02b67-157">PlatyPS документирует синтаксис наборов параметров и отдельных параметров.</span><span class="sxs-lookup"><span data-stu-id="02b67-157">PlatyPS documents the syntax of the parameter sets and the individual parameters.</span></span> <span data-ttu-id="02b67-158">Он не может создавать описания или предоставлять примеры,</span><span class="sxs-lookup"><span data-stu-id="02b67-158">It can't create descriptions or provide examples.</span></span> <span data-ttu-id="02b67-159">а конкретные области, в которых требуется содержимое, содержатся в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="02b67-159">The specific areas where content is needed are contained in curly braces.</span></span> <span data-ttu-id="02b67-160">Пример: `{{ Fill in the Description }}`</span><span class="sxs-lookup"><span data-stu-id="02b67-160">For example: `{{ Fill in the Description }}`</span></span>

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="Шаблон Markdown, отображающий заполнители в VS Code":::

<span data-ttu-id="02b67-162">Необходимо добавить краткое описание, описание командлета, описания для каждого параметра и хотя бы один пример.</span><span class="sxs-lookup"><span data-stu-id="02b67-162">You need to add a synopsis, a description of the cmdlet, descriptions for each parameter, and at least one example.</span></span>

<span data-ttu-id="02b67-163">Подробные сведения о записи содержимого PowerShell см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="02b67-163">For detailed information about writing PowerShell content, see the following articles:</span></span>

- [<span data-ttu-id="02b67-164">Руководство по стилю для PowerShell</span><span class="sxs-lookup"><span data-stu-id="02b67-164">PowerShell style guide</span></span>](/powershell/scripting/community/contributing/powershell-style-guide)
- [<span data-ttu-id="02b67-165">Изменение справочных статей</span><span class="sxs-lookup"><span data-stu-id="02b67-165">Editing reference articles</span></span>](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> <span data-ttu-id="02b67-166">В PlatyPS существует определенная схема, которая используется для ссылки на командлет.</span><span class="sxs-lookup"><span data-stu-id="02b67-166">PlatyPS has a specific schema that is uses for cmdlet reference.</span></span> <span data-ttu-id="02b67-167">Эта схема допускает только определенные блоки Markdown в определенных разделах документа.</span><span class="sxs-lookup"><span data-stu-id="02b67-167">That schema only allows certain Markdown blocks in specific sections of the document.</span></span> <span data-ttu-id="02b67-168">Если содержимое размещено в неправильном расположении, шаг сборки PlatyPS завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="02b67-168">If you put content in the wrong location, the PlatyPS build step fails.</span></span> <span data-ttu-id="02b67-169">Дополнительные сведения см. в документации по [схеме][] в репозитории PlatyPS.</span><span class="sxs-lookup"><span data-stu-id="02b67-169">For more information, see the [schema][] documentation in the PlatyPS repository.</span></span> <span data-ttu-id="02b67-170">Полный пример справки по командлетам с правильным форматом см. в разделе [Get-Item][].</span><span class="sxs-lookup"><span data-stu-id="02b67-170">For a complete example of well-formed cmdlet reference, see [Get-Item][].</span></span>

<span data-ttu-id="02b67-171">Предоставив необходимое содержимое для каждого командлета, необходимо обновить целевую страницу модуля.</span><span class="sxs-lookup"><span data-stu-id="02b67-171">After providing the required content for each of your cmdlets, you need to make sure that you update the module landing page.</span></span> <span data-ttu-id="02b67-172">Убедитесь, что модуль имеет правильные значения `Module Guid` и `Download Help Link` в метаданных YAML файла `<module-name>.md`.</span><span class="sxs-lookup"><span data-stu-id="02b67-172">Verify your module has the correct `Module Guid` and `Download Help Link` values in the YAML metadata of the `<module-name>.md` file.</span></span> <span data-ttu-id="02b67-173">Добавьте отсутствующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="02b67-173">Add any missing metadata.</span></span>

<span data-ttu-id="02b67-174">Кроме того, вы можете заметить, что у некоторых командлетов не хватает **краткого описания** (_синопсиса_).</span><span class="sxs-lookup"><span data-stu-id="02b67-174">Also, you may notice that some cmdlets may be missing a **Synopsis** (_short description_).</span></span> <span data-ttu-id="02b67-175">Следующая команда обновляет целевую страницу модуля, указав текст **краткого описания**.</span><span class="sxs-lookup"><span data-stu-id="02b67-175">The following command updates the module landing page with your **Synopsis** description text.</span></span> <span data-ttu-id="02b67-176">Откройте целевую страницу модуля, чтобы проверить описания.</span><span class="sxs-lookup"><span data-stu-id="02b67-176">Open the module landing page to verify the descriptions.</span></span>

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

<span data-ttu-id="02b67-177">Теперь, когда все содержимое введено, вы можете создать файлы справки MAML, отображаемые `Get-Help` в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02b67-177">Now that you have entered all the content, you can create the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

## <a name="create-the-external-help-files"></a><span data-ttu-id="02b67-178">Создание внешних файлов справки</span><span class="sxs-lookup"><span data-stu-id="02b67-178">Create the external help files</span></span>

<span data-ttu-id="02b67-179">На этом шаге создаются файлы справки MAML, которые отображаются `Get-Help` в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02b67-179">This step creates the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

<span data-ttu-id="02b67-180">Чтобы создать файлы MAML, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="02b67-180">To build the MAML files, run the following command:</span></span>

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

<span data-ttu-id="02b67-181">`New-ExternalHelp` преобразует все файлы Markdown командлета в один файл MAML (или несколько).</span><span class="sxs-lookup"><span data-stu-id="02b67-181">`New-ExternalHelp` converts all of the cmdlet Markdown files into one (or more) MAML files.</span></span> <span data-ttu-id="02b67-182">Файлы с общими сведениями преобразуются в обычные текстовые файлы со следующим форматом имени: `about_topic_name.help.txt`.</span><span class="sxs-lookup"><span data-stu-id="02b67-182">About files are converted to plain-text files with the following name format: `about_topic_name.help.txt`.</span></span>
<span data-ttu-id="02b67-183">Содержимое Markdown должно соответствовать требованию схемы PlatyPS.</span><span class="sxs-lookup"><span data-stu-id="02b67-183">The Markdown content must meet the requirement of the PlatyPS schema.</span></span> <span data-ttu-id="02b67-184">`New-ExternalHelp` завершается с ошибками, если содержимое не соответствует схеме.</span><span class="sxs-lookup"><span data-stu-id="02b67-184">`New-ExternalHelp` will exits with errors when the content does not follow the schema.</span></span> <span data-ttu-id="02b67-185">Чтобы устранить нарушения схемы, необходимо изменить файлы.</span><span class="sxs-lookup"><span data-stu-id="02b67-185">You must edit the files to fix the schema violations.</span></span>

> [!CAUTION]
> <span data-ttu-id="02b67-186">PlatyPS не очень хорошо преобразует файлы `about_*.md` в обычный текст.</span><span class="sxs-lookup"><span data-stu-id="02b67-186">PlatyPS does a poor job converting the `about_*.md` files to plain text.</span></span> <span data-ttu-id="02b67-187">Чтобы получить приемлемые результаты, используйте очень простой Markdown.</span><span class="sxs-lookup"><span data-stu-id="02b67-187">You must use very simple Markdown to get acceptable results.</span></span> <span data-ttu-id="02b67-188">Файлы можно хранить в обычном текстовом формате `about_topic_name.help.txt`, чтобы PlatyPS не пришлось их преобразовывать.</span><span class="sxs-lookup"><span data-stu-id="02b67-188">You may want to maintain the files in plain-text `about_topic_name.help.txt` format, rather than allowing PlatyPS to convert them.</span></span>

<span data-ttu-id="02b67-189">После завершения этого шага вы увидите файлы `*-help.xml` и `about_*.help.txt` в целевой выходной папке.</span><span class="sxs-lookup"><span data-stu-id="02b67-189">Once this step is complete, you will see `*-help.xml` and `about_*.help.txt` files in the target output folder.</span></span>

<span data-ttu-id="02b67-190">Дополнительные сведения см. в разделе [New-ExternalHelp][].</span><span class="sxs-lookup"><span data-stu-id="02b67-190">For more information, see [New-ExternalHelp][]</span></span>

### <a name="test-the-compiled-help-files"></a><span data-ttu-id="02b67-191">Тестирование скомпилированных файлов справки</span><span class="sxs-lookup"><span data-stu-id="02b67-191">Test the compiled help files</span></span>

<span data-ttu-id="02b67-192">Вы можете проверить содержимое с помощью командлета [Get-HelpPreview][].</span><span class="sxs-lookup"><span data-stu-id="02b67-192">You can verify the content with the [Get-HelpPreview][] cmdlet:</span></span>

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

<span data-ttu-id="02b67-193">Командлет считывает скомпилированный файл MAML и выводит содержимое в том же формате, что и `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="02b67-193">The cmdlet reads the compiled MAML file and outputs the content in the same format you would receive from `Get-Help`.</span></span> <span data-ttu-id="02b67-194">Это позволяет проверить результаты, чтобы убедиться, что файлы Markdown скомпилированы правильно и дают нужные результаты.</span><span class="sxs-lookup"><span data-stu-id="02b67-194">This allows you to inspect the results to verify that the Markdown files compiled correctly and produce the desired results.</span></span> <span data-ttu-id="02b67-195">Если обнаружена ошибка, снова измените файлы Markdown и перекомпилируйте MAML.</span><span class="sxs-lookup"><span data-stu-id="02b67-195">If you find an error, re-edit the Markdown files and recompile the MAML.</span></span>

<span data-ttu-id="02b67-196">Теперь все готово для публикации файлов справки.</span><span class="sxs-lookup"><span data-stu-id="02b67-196">Now you are ready to publish your help files.</span></span>

## <a name="publishing-your-help"></a><span data-ttu-id="02b67-197">Публикация справки</span><span class="sxs-lookup"><span data-stu-id="02b67-197">Publishing your help</span></span>

<span data-ttu-id="02b67-198">Теперь, когда файлы Markdown скомпилированы в файлы справки PowerShell, вы можете представить их пользователям.</span><span class="sxs-lookup"><span data-stu-id="02b67-198">Now that you have compiled the Markdown files into PowerShell help files, you are ready to make the files available to users.</span></span> <span data-ttu-id="02b67-199">Существует два варианта предоставления справки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02b67-199">There are two options for providing help in the PowerShell console.</span></span>

- <span data-ttu-id="02b67-200">Упаковка файлов справки с помощью модуля.</span><span class="sxs-lookup"><span data-stu-id="02b67-200">Package the help files with the module</span></span>
- <span data-ttu-id="02b67-201">Создание обновляемого пакета справки, который пользователи устанавливают с помощью командлета `Update-Help`.</span><span class="sxs-lookup"><span data-stu-id="02b67-201">Create an updateable help package that users install with the `Update-Help` cmdlet</span></span>

### <a name="packaging-help-with-the-module"></a><span data-ttu-id="02b67-202">Упаковка справки по модулю</span><span class="sxs-lookup"><span data-stu-id="02b67-202">Packaging help with the module</span></span>

<span data-ttu-id="02b67-203">Файлы справки можно упаковать в собственный модуль.</span><span class="sxs-lookup"><span data-stu-id="02b67-203">The help files can be packaged with your module.</span></span> <span data-ttu-id="02b67-204">Дополнительные сведения о структуре папок см. в разделе [Написание справки для модулей][].</span><span class="sxs-lookup"><span data-stu-id="02b67-204">See [Writing Help for Modules][] for details of the folder structure.</span></span> <span data-ttu-id="02b67-205">Необходимо включить список файлов справки в значение ключа **FileList** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="02b67-205">You should include the list of Help files in the value of the **FileList** key in the module manifest.</span></span>

### <a name="creating-an-updateable-help-package"></a><span data-ttu-id="02b67-206">Создание обновляемого пакета справки</span><span class="sxs-lookup"><span data-stu-id="02b67-206">Creating an updateable help package</span></span>

<span data-ttu-id="02b67-207">В общих чертах, необходимо выполнить следующие действия по созданию обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="02b67-207">At a high level, the steps to create updateable help include:</span></span>

1. <span data-ttu-id="02b67-208">Поиск веб-сайта для размещения файлов справки.</span><span class="sxs-lookup"><span data-stu-id="02b67-208">Find an internet site to host your help files</span></span>
1. <span data-ttu-id="02b67-209">Добавление ключа **HelpInfoURI** в манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="02b67-209">Add a **HelpInfoURI** key to your module manifest</span></span>
1. <span data-ttu-id="02b67-210">Создание XML-файла HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="02b67-210">Create a HelpInfo XML file</span></span>
1. <span data-ttu-id="02b67-211">Создание CAB-файлов.</span><span class="sxs-lookup"><span data-stu-id="02b67-211">Create CAB files</span></span>
1. <span data-ttu-id="02b67-212">Отправка файлов.</span><span class="sxs-lookup"><span data-stu-id="02b67-212">Upload your files</span></span>

<span data-ttu-id="02b67-213">Дополнительные сведения см. в разделе [Поддержка обновляемой справки: пошаговые инструкции][step-by-step].</span><span class="sxs-lookup"><span data-stu-id="02b67-213">For more information, see [Supporting Updateable Help: Step-by-step][step-by-step].</span></span>

<span data-ttu-id="02b67-214">PlatyPS помогает выполнить некоторые из этих действий.</span><span class="sxs-lookup"><span data-stu-id="02b67-214">PlatyPS assists you with  some of these steps.</span></span>

<span data-ttu-id="02b67-215">**HelpInfoURI** — это URL-адрес, указывающий на расположение, где файлы справки размещаются в Интернете.</span><span class="sxs-lookup"><span data-stu-id="02b67-215">The **HelpInfoURI** is a URL that points to location where your help files are hosted on the internet.</span></span> <span data-ttu-id="02b67-216">Это значение настраивается в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="02b67-216">This value is configured in the module manifest.</span></span> <span data-ttu-id="02b67-217">`Update-Help` считывает манифест модуля для получения этого URL-адреса и загрузки обновляемого содержимого справки.</span><span class="sxs-lookup"><span data-stu-id="02b67-217">`Update-Help` reads the module manifest to get this URL and download the updateable help content.</span></span> <span data-ttu-id="02b67-218">Этот URL-адрес должен указывать только на расположение папки, а не на отдельные файлы.</span><span class="sxs-lookup"><span data-stu-id="02b67-218">This URL should only point to the folder location and not to individual files.</span></span> <span data-ttu-id="02b67-219">`Update-Help` создает имена файлов для загрузки на основе других сведений из манифеста модуля и XML-файла HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="02b67-219">`Update-Help` constructs the filenames to download based on other information from the module manifest and the HelpInfo XML file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02b67-220">**HelpInfoURI** должен заканчиваться символом прямой косой черты (`/`).</span><span class="sxs-lookup"><span data-stu-id="02b67-220">The **HelpInfoURI** must end with a forward-slash character (`/`).</span></span> <span data-ttu-id="02b67-221">Без этого символа `Update-Help` не сможет создать правильные пути к файлам для скачивания содержимого.</span><span class="sxs-lookup"><span data-stu-id="02b67-221">Without that character, `Update-Help` cannot construct the correct file paths to download the content.</span></span> <span data-ttu-id="02b67-222">Кроме того, большинство файловых служб на основе HTTP учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="02b67-222">Also, most HTTP-based file services are case-sensitive.</span></span> <span data-ttu-id="02b67-223">Метаданные модуля в XML-файле HelpInfo должны содержать правильный регистр букв.</span><span class="sxs-lookup"><span data-stu-id="02b67-223">It is important that the module metadata in the HelpInfo XML file contains the proper letter case.</span></span>

<span data-ttu-id="02b67-224">Командлет `New-ExternalHelp` создает XML-файл HelpInfo в выходной папке.</span><span class="sxs-lookup"><span data-stu-id="02b67-224">The `New-ExternalHelp` cmdlet creates the HelpInfo XML file in the output folder.</span></span> <span data-ttu-id="02b67-225">XML-файл HelpInfo строится с помощью метаданных YAML, содержащихся в файлах Markdown модуля (`ModuleName.md`).</span><span class="sxs-lookup"><span data-stu-id="02b67-225">The HelpInfo XML file is built using YAML metadata contained in the module Markdown files (`ModuleName.md`).</span></span>

<span data-ttu-id="02b67-226">Командлет `New-ExternalHelpCab` создает ZIP- и CAB-файлы, содержащие скомпилированные файлы MAML и `about_*.help.txt`.</span><span class="sxs-lookup"><span data-stu-id="02b67-226">The `New-ExternalHelpCab` cmdlet creates ZIP and CAB files containing the MAML and `about_*.help.txt` files you compiled.</span></span> <span data-ttu-id="02b67-227">CAB-файлы совместимы со всеми версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02b67-227">CAB files are compatible with all versions of PowerShell.</span></span>
<span data-ttu-id="02b67-228">В PowerShell 6 и более поздних версий можно использовать ZIP-файлы.</span><span class="sxs-lookup"><span data-stu-id="02b67-228">PowerShell 6 and higher can use ZIP files.</span></span>

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

<span data-ttu-id="02b67-229">После создания ZIP- и CAB-файлов отправьте файлы ZIP, CAB и XML HelpInfo на файловый сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="02b67-229">After creating the ZIP and CAB files, upload the ZIP, CAB, and HelpInfo XML files to your HTTP file server.</span></span> <span data-ttu-id="02b67-230">Разместите файлы в расположении, указанном **HelpInfoURI**.</span><span class="sxs-lookup"><span data-stu-id="02b67-230">Put the files in the location indicated by the **HelpInfoURI**.</span></span>

<span data-ttu-id="02b67-231">Дополнительные сведения см. в разделе [New-ExternalHelpCab][].</span><span class="sxs-lookup"><span data-stu-id="02b67-231">For more information, see [New-ExternalHelpCab][].</span></span>

### <a name="other-publishing-options"></a><span data-ttu-id="02b67-232">Другие варианты публикации</span><span class="sxs-lookup"><span data-stu-id="02b67-232">Other publishing options</span></span>

<span data-ttu-id="02b67-233">Markdown — это универсальный формат, который легко преобразовать в другие форматы для публикации.</span><span class="sxs-lookup"><span data-stu-id="02b67-233">Markdown is a versatile format that is easy to transform to other formats for publishing.</span></span> <span data-ttu-id="02b67-234">С помощью такого средства, как [Pandoc][], можно преобразовать файлы справки Markdown в различные форматы документов, включая обычный текст, HTML, PDF и Office.</span><span class="sxs-lookup"><span data-stu-id="02b67-234">Using a tool like [Pandoc][], you can convert your Markdown help files to many different document formats, including plain text, HTML, PDF, and Office document formats.</span></span>

<span data-ttu-id="02b67-235">Кроме того, командлеты [ConvertFrom-Markdown][] и [Show-Markdown][] в PowerShell 6 и более поздних версий можно использовать для преобразования Markdown в HTML или создания цветового отображения в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02b67-235">Also, the cmdlets [ConvertFrom-Markdown][] and [Show-Markdown][] in PowerShell 6 and higher can be used to convert Markdown to HTML or create a colorful display in the PowerShell console.</span></span>

## <a name="known-issues"></a><span data-ttu-id="02b67-236">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="02b67-236">Known issues</span></span>

<span data-ttu-id="02b67-237">Для PlatyPS очень важна [схема][] структуры создаваемых и компилируемых файлов Markdown.</span><span class="sxs-lookup"><span data-stu-id="02b67-237">PlatyPS is very sensitive to the [schema][] for the structure of the Markdown files it creates and compiles.</span></span> <span data-ttu-id="02b67-238">Допустимый Markdown вполне может нарушать эту схему.</span><span class="sxs-lookup"><span data-stu-id="02b67-238">It is very easy write valid Markdown that violates this schema.</span></span> <span data-ttu-id="02b67-239">Дополнительные сведения см. в [руководстве по стилю PowerShell][] и разделе о [редактировании справочных статей][].</span><span class="sxs-lookup"><span data-stu-id="02b67-239">For more information, consult the [PowerShell style guide][] and [Editing reference articles][].</span></span>

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[Руководство по стилю для PowerShell]: /powershell/scripting/community/contributing/powershell-style-guide
[PowerShell style guide]: /powershell/scripting/community/contributing/powershell-style-guide
[Изменение справочных статей]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Editing reference articles]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Написание справки для модулей]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[Writing Help for Modules]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
