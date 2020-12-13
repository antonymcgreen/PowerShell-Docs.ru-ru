---
ms.date: 06/09/2020
ms.topic: reference
title: Ключевые слова справки на основе комментариев
description: Ключевые слова справки на основе комментариев
ms.openlocfilehash: d87dde8700813767f6c09cfce70ed06c7964ebc7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645475"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="ec4c9-103">Ключевые слова справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="ec4c9-103">Comment-Based Help Keywords</span></span>

<span data-ttu-id="ec4c9-104">В этом разделе перечислены и описаны ключевые слова в справке на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-104">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="ec4c9-105">Ключевые слова в справке Comment-Based</span><span class="sxs-lookup"><span data-stu-id="ec4c9-105">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="ec4c9-106">Ниже приведены допустимые ключевые слова справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-106">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="ec4c9-107">Они перечислены в том порядке, в котором они обычно отображаются в разделе справки, а также их предполагаемое использование.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-107">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="ec4c9-108">Эти ключевые слова могут отображаться в любом порядке в справке на основе комментариев и не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-108">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="ec4c9-109">Обратите внимание, что `.EXTERNALHELP` ключевое слово имеет приоритет над всеми остальными ключевыми словами справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-109">Note that the `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span>
<span data-ttu-id="ec4c9-110">Если `.EXTERNALHELP` параметр существует, командлет [Microsoft. PowerShell. Commands. жеселпкомманд](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) не отображает справку на основе комментариев, даже если ей не удается найти файл справки, соответствующий значению ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-110">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ec4c9-111">. Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ec4c9-111">.SYNOPSIS</span></span>

<span data-ttu-id="ec4c9-112">Краткое описание функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-112">A brief description of the function or script.</span></span> <span data-ttu-id="ec4c9-113">Это ключевое слово может использоваться только один раз в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-113">This keyword can be used only once in each topic.</span></span>

## <a name="description"></a><span data-ttu-id="ec4c9-114">. NОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ec4c9-114">.DESCRIPTION</span></span>

<span data-ttu-id="ec4c9-115">Подробное описание функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-115">A detailed description of the function or script.</span></span> <span data-ttu-id="ec4c9-116">Это ключевое слово может использоваться только один раз в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-116">This keyword can be used only once in each topic.</span></span>

## <a name="parameter-parameter-name"></a><span data-ttu-id="ec4c9-117">. ПАРАМЕТР \<Parameter-Name></span><span class="sxs-lookup"><span data-stu-id="ec4c9-117">.PARAMETER \<Parameter-Name></span></span>

<span data-ttu-id="ec4c9-118">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-118">The description of a parameter.</span></span> <span data-ttu-id="ec4c9-119">Можно включить `.PARAMETER` ключевое слово для каждого параметра в функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-119">You can include a `.PARAMETER` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="ec4c9-120">`.PARAMETER`Ключевые слова могут располагаться в любом порядке в блоке комментариев, но порядок, в котором параметры отображаются в `Param` инструкции или объявлении функции, определяет порядок, в котором параметры отображаются в разделе справки.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-120">The `.PARAMETER` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="ec4c9-121">Чтобы изменить порядок параметров в разделе справки, измените порядок параметров в `Param` объявлении оператора или функции.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-121">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="ec4c9-122">Можно также указать описание параметра, поместив комментарий в `Param` инструкцию непосредственно перед именем переменной параметра.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-122">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="ec4c9-123">Если используются как `Param` Комментарий оператора, так и `.PARAMETER` ключевое слово, то используется описание, связанное с `.PARAMETER` ключевым словом, и `Param` Комментарий оператора игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-123">If you use both a `Param` statement comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the `Param` statement comment is ignored.</span></span>

## <a name="example"></a><span data-ttu-id="ec4c9-124">. Например</span><span class="sxs-lookup"><span data-stu-id="ec4c9-124">.EXAMPLE</span></span>

<span data-ttu-id="ec4c9-125">Пример команды, которая использует функцию или скрипт, при необходимости за которой следует пример выходных данных и описание.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-125">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="ec4c9-126">Повторите это ключевое слово для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-126">Repeat this keyword for each example.</span></span>

## <a name="inputs"></a><span data-ttu-id="ec4c9-127">. ВХОДА</span><span class="sxs-lookup"><span data-stu-id="ec4c9-127">.INPUTS</span></span>

<span data-ttu-id="ec4c9-128">Microsoft .NET типы платформ объектов, которые можно передать в функцию или скрипт.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-128">The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="ec4c9-129">Можно также включить описание входных объектов.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-129">You can also include a description of the input objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="ec4c9-130">. ВЫХОДНЫЕ</span><span class="sxs-lookup"><span data-stu-id="ec4c9-130">.OUTPUTS</span></span>

<span data-ttu-id="ec4c9-131">Тип .NET Framework объектов, возвращаемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-131">The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="ec4c9-132">Можно также включить описание возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-132">You can also include a description of the returned objects.</span></span>

## <a name="notes"></a><span data-ttu-id="ec4c9-133">. Заметки О</span><span class="sxs-lookup"><span data-stu-id="ec4c9-133">.NOTES</span></span>

<span data-ttu-id="ec4c9-134">Дополнительные сведения о функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-134">Additional information about the function or script.</span></span>

## <a name="link"></a><span data-ttu-id="ec4c9-135">. ССЫЛКУ</span><span class="sxs-lookup"><span data-stu-id="ec4c9-135">.LINK</span></span>

<span data-ttu-id="ec4c9-136">Имя связанного раздела.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-136">The name of a related topic.</span></span> <span data-ttu-id="ec4c9-137">Повторите это ключевое слово для каждого связанного раздела.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-137">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="ec4c9-138">Это содержимое отображается в разделе "связанные ссылки" раздела справки.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-138">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="ec4c9-139">`.LINK`Содержимое ключевого слова может также включать универсальный код ресурса (URI) в Интернет-версию того же раздела справки.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-139">The `.LINK` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="ec4c9-140">Версия в Интернете открывается при использовании `Online` параметра `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="ec4c9-140">The online version opens when you use the `Online` parameter of `Get-Help`.</span></span> <span data-ttu-id="ec4c9-141">URI должен начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="ec4c9-141">The URI must begin with "http" or "https".</span></span>

## <a name="component"></a><span data-ttu-id="ec4c9-142">. СМ</span><span class="sxs-lookup"><span data-stu-id="ec4c9-142">.COMPONENT</span></span>

<span data-ttu-id="ec4c9-143">Имя технологии или компонента, используемых функцией или сценарием или с которым она связана.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-143">The name of the technology or feature that the function or script uses, or to which it is related.</span></span>
<span data-ttu-id="ec4c9-144">Параметр **компонента** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="ec4c9-144">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="role"></a><span data-ttu-id="ec4c9-145">. Role</span><span class="sxs-lookup"><span data-stu-id="ec4c9-145">.Role</span></span>

<span data-ttu-id="ec4c9-146">Имя роли пользователя для раздела справки.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-146">The name of the user role for the help topic.</span></span> <span data-ttu-id="ec4c9-147">Параметр **Role** объекта `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="ec4c9-147">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="functionality"></a><span data-ttu-id="ec4c9-148">. ВОЗМОЖНОСТИ</span><span class="sxs-lookup"><span data-stu-id="ec4c9-148">.FUNCTIONALITY</span></span>

<span data-ttu-id="ec4c9-149">Ключевые слова, описывающие предполагаемое использование функции.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-149">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="ec4c9-150">Параметр **функций функции** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="ec4c9-150">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="forwardhelptargetname-command-name"></a><span data-ttu-id="ec4c9-151">. форвардхелптаржетнаме \<Command-Name></span><span class="sxs-lookup"><span data-stu-id="ec4c9-151">.FORWARDHELPTARGETNAME \<Command-Name></span></span>

<span data-ttu-id="ec4c9-152">Выполняет перенаправление в раздел справки для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-152">Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="ec4c9-153">Вы можете перенаправить пользователей в любой раздел справки, включая разделы справки для функции, скрипта, командлета или поставщика.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-153">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

## <a name="forwardhelpcategory-category"></a><span data-ttu-id="ec4c9-154">. форвардхелпкатегори \<Category></span><span class="sxs-lookup"><span data-stu-id="ec4c9-154">.FORWARDHELPCATEGORY \<Category></span></span>

<span data-ttu-id="ec4c9-155">Указывает категорию справки для элемента в `.FORWARDHELPTARGETNAME` .</span><span class="sxs-lookup"><span data-stu-id="ec4c9-155">Specifies the Help category of the item in `.FORWARDHELPTARGETNAME`.</span></span> <span data-ttu-id="ec4c9-156">Используйте это ключевое слово, чтобы избежать конфликтов при наличии команд с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-156">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="ec4c9-157">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ec4c9-157">Valid values are:</span></span>

- <span data-ttu-id="ec4c9-158">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="ec4c9-158">Alias</span></span>
- <span data-ttu-id="ec4c9-159">Командлет</span><span class="sxs-lookup"><span data-stu-id="ec4c9-159">Cmdlet</span></span>
- <span data-ttu-id="ec4c9-160">HelpFile</span><span class="sxs-lookup"><span data-stu-id="ec4c9-160">HelpFile</span></span>
- <span data-ttu-id="ec4c9-161">Функция</span><span class="sxs-lookup"><span data-stu-id="ec4c9-161">Function</span></span>
- <span data-ttu-id="ec4c9-162">Поставщик</span><span class="sxs-lookup"><span data-stu-id="ec4c9-162">Provider</span></span>
- <span data-ttu-id="ec4c9-163">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="ec4c9-163">General</span></span>
- <span data-ttu-id="ec4c9-164">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="ec4c9-164">FAQ</span></span>
- <span data-ttu-id="ec4c9-165">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="ec4c9-165">Glossary</span></span>
- <span data-ttu-id="ec4c9-166">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="ec4c9-166">ScriptCommand</span></span>
- <span data-ttu-id="ec4c9-167">екстерналскрипт</span><span class="sxs-lookup"><span data-stu-id="ec4c9-167">ExternalScript</span></span>
- <span data-ttu-id="ec4c9-168">Фильтр</span><span class="sxs-lookup"><span data-stu-id="ec4c9-168">Filter</span></span>
- <span data-ttu-id="ec4c9-169">Все</span><span class="sxs-lookup"><span data-stu-id="ec4c9-169">All</span></span>

## <a name="remotehelprunspace-pssession-variable"></a><span data-ttu-id="ec4c9-170">. ремотехелпрунспаце \<PSSession-variable></span><span class="sxs-lookup"><span data-stu-id="ec4c9-170">.REMOTEHELPRUNSPACE \<PSSession-variable></span></span>

<span data-ttu-id="ec4c9-171">Указывает сеанс, содержащий раздел справки.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-171">Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="ec4c9-172">Введите переменную, содержащую сеанс PSSession.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-172">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="ec4c9-173">Это ключевое слово используется `Export-PSSession` командлетом для поиска разделов справки для экспортированных команд.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-173">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

## <a name="externalhelp-xml-help-file"></a><span data-ttu-id="ec4c9-174">. екстерналхелп \<XML Help File></span><span class="sxs-lookup"><span data-stu-id="ec4c9-174">.EXTERNALHELP \<XML Help File></span></span>

<span data-ttu-id="ec4c9-175">Указывает путь и (или) имя файла справки на основе XML для скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-175">Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="ec4c9-176">`.EXTERNALHELP`Ключевое слово сообщает командлету [Microsoft. PowerShell. Commands. жеселпкомманд](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) о получении справки для скрипта или функции в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-176">The `.EXTERNALHELP` keyword tells the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="ec4c9-177">`.EXTERNALHELP`Ключевое слово требуется при использовании файла справки на основе XML для скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-177">The `.EXTERNALHELP` keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="ec4c9-178">Без него `Get-Help` файл справки для функции или скрипта не будет найден.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-178">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="ec4c9-179">`.EXTERNALHELP`Ключевое слово имеет приоритет над всеми остальными ключевыми словами справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-179">The `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="ec4c9-180">Если `.EXTERNALHELP` параметр существует, командлет [Microsoft. PowerShell. Commands. жеселпкомманд](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) не отображает справку на основе комментариев, даже если ей не удается найти файл справки, соответствующий значению ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-180">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="ec4c9-181">При экспорте функции модулем скрипта значение `.EXTERNALHELP` должно быть именем файла без пути.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-181">When the function is exported by a script module, the value of `.EXTERNALHELP` should be a filename without a path.</span></span> <span data-ttu-id="ec4c9-182">`Get-Help` ищет файл в подкаталоге, зависящем от языкового стандарта, в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-182">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="ec4c9-183">Требования к имени файла отсутствуют, но рекомендуется использовать следующий формат имени файла: `<ScriptModule>.psm1-help.xml` .</span><span class="sxs-lookup"><span data-stu-id="ec4c9-183">There are no requirements for the filename, but a best practice is to use the following filename format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="ec4c9-184">Если функция не связана с модулем, укажите путь и имя файла в значении `.EXTERNALHELP` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-184">When the function is not associated with a module, include a path and filename in the value of the `.EXTERNALHELP` keyword.</span></span> <span data-ttu-id="ec4c9-185">Если указанный путь к XML-файлу содержит подкаталоги, относящиеся к пользовательскому интерфейсу, `Get-Help` то поиск в подкаталогах выполняется рекурсивно для XML-файла с именем сценария или функции в соответствии со стандартами переключения языка, установленными для Windows, так же, как и для всех разделов справки на основе XML.</span><span class="sxs-lookup"><span data-stu-id="ec4c9-185">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="ec4c9-186">Дополнительные сведения о формате файла справки на основе XML для командлета см. в разделе [Создание справки по командлетам Windows PowerShell](./writing-help-for-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="ec4c9-186">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>
