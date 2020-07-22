---
title: Ключевые слова справки на основе комментариев
ms.date: 06/09/2020
ms.openlocfilehash: fb737c19d7b7f4d003af3ba36bb396bac52d94e7
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893158"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="4b74e-102">Ключевые слова справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="4b74e-102">Comment-Based Help Keywords</span></span>

<span data-ttu-id="4b74e-103">В этом разделе перечислены и описаны ключевые слова в справке на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="4b74e-103">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="4b74e-104">Ключевые слова в справке на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="4b74e-104">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="4b74e-105">Ниже приведены допустимые ключевые слова справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="4b74e-105">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="4b74e-106">Они перечислены в том порядке, в котором они обычно отображаются в разделе справки, а также их предполагаемое использование.</span><span class="sxs-lookup"><span data-stu-id="4b74e-106">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="4b74e-107">Эти ключевые слова могут отображаться в любом порядке в справке на основе комментариев и не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="4b74e-107">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="4b74e-108">Обратите внимание, что `.EXTERNALHELP` ключевое слово имеет приоритет над всеми остальными ключевыми словами справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="4b74e-108">Note that the `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span>
<span data-ttu-id="4b74e-109">Если `.EXTERNALHELP` параметр существует, командлет [Microsoft. PowerShell. Commands. жеселпкомманд](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) не отображает справку на основе комментариев, даже если ей не удается найти файл справки, соответствующий значению ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="4b74e-109">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4b74e-110">. Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b74e-110">.SYNOPSIS</span></span>

<span data-ttu-id="4b74e-111">Краткое описание функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="4b74e-111">A brief description of the function or script.</span></span> <span data-ttu-id="4b74e-112">Это ключевое слово может использоваться только один раз в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="4b74e-112">This keyword can be used only once in each topic.</span></span>

## <a name="description"></a><span data-ttu-id="4b74e-113">. NОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="4b74e-113">.DESCRIPTION</span></span>

<span data-ttu-id="4b74e-114">Подробное описание функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="4b74e-114">A detailed description of the function or script.</span></span> <span data-ttu-id="4b74e-115">Это ключевое слово может использоваться только один раз в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="4b74e-115">This keyword can be used only once in each topic.</span></span>

## <a name="parameter-parameter-name"></a><span data-ttu-id="4b74e-116">. ПАРАМЕТР\<Parameter-Name></span><span class="sxs-lookup"><span data-stu-id="4b74e-116">.PARAMETER \<Parameter-Name></span></span>

<span data-ttu-id="4b74e-117">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="4b74e-117">The description of a parameter.</span></span> <span data-ttu-id="4b74e-118">Можно включить `.PARAMETER` ключевое слово для каждого параметра в функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="4b74e-118">You can include a `.PARAMETER` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="4b74e-119">`.PARAMETER`Ключевые слова могут располагаться в любом порядке в блоке комментариев, но порядок, в котором параметры отображаются в `Param` инструкции или объявлении функции, определяет порядок, в котором параметры отображаются в разделе справки.</span><span class="sxs-lookup"><span data-stu-id="4b74e-119">The `.PARAMETER` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="4b74e-120">Чтобы изменить порядок параметров в разделе справки, измените порядок параметров в `Param` объявлении оператора или функции.</span><span class="sxs-lookup"><span data-stu-id="4b74e-120">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="4b74e-121">Можно также указать описание параметра, поместив комментарий в `Param` инструкцию непосредственно перед именем переменной параметра.</span><span class="sxs-lookup"><span data-stu-id="4b74e-121">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="4b74e-122">Если используются как `Param` Комментарий оператора, так и `.PARAMETER` ключевое слово, то используется описание, связанное с `.PARAMETER` ключевым словом, и `Param` Комментарий оператора игнорируется.</span><span class="sxs-lookup"><span data-stu-id="4b74e-122">If you use both a `Param` statement comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the `Param` statement comment is ignored.</span></span>

## <a name="example"></a><span data-ttu-id="4b74e-123">. Например</span><span class="sxs-lookup"><span data-stu-id="4b74e-123">.EXAMPLE</span></span>

<span data-ttu-id="4b74e-124">Пример команды, которая использует функцию или скрипт, при необходимости за которой следует пример выходных данных и описание.</span><span class="sxs-lookup"><span data-stu-id="4b74e-124">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="4b74e-125">Повторите это ключевое слово для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="4b74e-125">Repeat this keyword for each example.</span></span>

## <a name="inputs"></a><span data-ttu-id="4b74e-126">. ВХОДА</span><span class="sxs-lookup"><span data-stu-id="4b74e-126">.INPUTS</span></span>

<span data-ttu-id="4b74e-127">Microsoft .NET типы платформ объектов, которые можно передать в функцию или скрипт.</span><span class="sxs-lookup"><span data-stu-id="4b74e-127">The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="4b74e-128">Можно также включить описание входных объектов.</span><span class="sxs-lookup"><span data-stu-id="4b74e-128">You can also include a description of the input objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="4b74e-129">. ВЫХОДНЫЕ</span><span class="sxs-lookup"><span data-stu-id="4b74e-129">.OUTPUTS</span></span>

<span data-ttu-id="4b74e-130">Тип .NET Framework объектов, возвращаемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="4b74e-130">The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="4b74e-131">Можно также включить описание возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="4b74e-131">You can also include a description of the returned objects.</span></span>

## <a name="notes"></a><span data-ttu-id="4b74e-132">. Заметки О</span><span class="sxs-lookup"><span data-stu-id="4b74e-132">.NOTES</span></span>

<span data-ttu-id="4b74e-133">Дополнительные сведения о функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="4b74e-133">Additional information about the function or script.</span></span>

## <a name="link"></a><span data-ttu-id="4b74e-134">. ССЫЛКУ</span><span class="sxs-lookup"><span data-stu-id="4b74e-134">.LINK</span></span>

<span data-ttu-id="4b74e-135">Имя связанного раздела.</span><span class="sxs-lookup"><span data-stu-id="4b74e-135">The name of a related topic.</span></span> <span data-ttu-id="4b74e-136">Повторите это ключевое слово для каждого связанного раздела.</span><span class="sxs-lookup"><span data-stu-id="4b74e-136">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="4b74e-137">Это содержимое отображается в разделе "связанные ссылки" раздела справки.</span><span class="sxs-lookup"><span data-stu-id="4b74e-137">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="4b74e-138">`.LINK`Содержимое ключевого слова может также включать универсальный код ресурса (URI) в Интернет-версию того же раздела справки.</span><span class="sxs-lookup"><span data-stu-id="4b74e-138">The `.LINK` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="4b74e-139">Версия в Интернете открывается при использовании `Online` параметра `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="4b74e-139">The online version opens when you use the `Online` parameter of `Get-Help`.</span></span> <span data-ttu-id="4b74e-140">URI должен начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="4b74e-140">The URI must begin with "http" or "https".</span></span>

## <a name="component"></a><span data-ttu-id="4b74e-141">. СМ</span><span class="sxs-lookup"><span data-stu-id="4b74e-141">.COMPONENT</span></span>

<span data-ttu-id="4b74e-142">Имя технологии или компонента, используемых функцией или сценарием или с которым она связана.</span><span class="sxs-lookup"><span data-stu-id="4b74e-142">The name of the technology or feature that the function or script uses, or to which it is related.</span></span>
<span data-ttu-id="4b74e-143">Параметр **компонента** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="4b74e-143">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="role"></a><span data-ttu-id="4b74e-144">. Role</span><span class="sxs-lookup"><span data-stu-id="4b74e-144">.Role</span></span>

<span data-ttu-id="4b74e-145">Имя роли пользователя для раздела справки.</span><span class="sxs-lookup"><span data-stu-id="4b74e-145">The name of the user role for the help topic.</span></span> <span data-ttu-id="4b74e-146">Параметр **Role** объекта `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="4b74e-146">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="functionality"></a><span data-ttu-id="4b74e-147">. ВОЗМОЖНОСТИ</span><span class="sxs-lookup"><span data-stu-id="4b74e-147">.FUNCTIONALITY</span></span>

<span data-ttu-id="4b74e-148">Ключевые слова, описывающие предполагаемое использование функции.</span><span class="sxs-lookup"><span data-stu-id="4b74e-148">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="4b74e-149">Параметр **функций функции** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="4b74e-149">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="forwardhelptargetname-command-name"></a><span data-ttu-id="4b74e-150">. форвардхелптаржетнаме\<Command-Name></span><span class="sxs-lookup"><span data-stu-id="4b74e-150">.FORWARDHELPTARGETNAME \<Command-Name></span></span>

<span data-ttu-id="4b74e-151">Выполняет перенаправление в раздел справки для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="4b74e-151">Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="4b74e-152">Вы можете перенаправить пользователей в любой раздел справки, включая разделы справки для функции, скрипта, командлета или поставщика.</span><span class="sxs-lookup"><span data-stu-id="4b74e-152">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

## <a name="forwardhelpcategory-category"></a><span data-ttu-id="4b74e-153">. форвардхелпкатегори\<Category></span><span class="sxs-lookup"><span data-stu-id="4b74e-153">.FORWARDHELPCATEGORY \<Category></span></span>

<span data-ttu-id="4b74e-154">Указывает категорию справки для элемента в `.FORWARDHELPTARGETNAME` .</span><span class="sxs-lookup"><span data-stu-id="4b74e-154">Specifies the Help category of the item in `.FORWARDHELPTARGETNAME`.</span></span> <span data-ttu-id="4b74e-155">Используйте это ключевое слово, чтобы избежать конфликтов при наличии команд с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="4b74e-155">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="4b74e-156">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4b74e-156">Valid values are:</span></span>

- <span data-ttu-id="4b74e-157">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="4b74e-157">Alias</span></span>
- <span data-ttu-id="4b74e-158">Командлет</span><span class="sxs-lookup"><span data-stu-id="4b74e-158">Cmdlet</span></span>
- <span data-ttu-id="4b74e-159">HelpFile</span><span class="sxs-lookup"><span data-stu-id="4b74e-159">HelpFile</span></span>
- <span data-ttu-id="4b74e-160">Функция</span><span class="sxs-lookup"><span data-stu-id="4b74e-160">Function</span></span>
- <span data-ttu-id="4b74e-161">Поставщик</span><span class="sxs-lookup"><span data-stu-id="4b74e-161">Provider</span></span>
- <span data-ttu-id="4b74e-162">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="4b74e-162">General</span></span>
- <span data-ttu-id="4b74e-163">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="4b74e-163">FAQ</span></span>
- <span data-ttu-id="4b74e-164">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="4b74e-164">Glossary</span></span>
- <span data-ttu-id="4b74e-165">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="4b74e-165">ScriptCommand</span></span>
- <span data-ttu-id="4b74e-166">екстерналскрипт</span><span class="sxs-lookup"><span data-stu-id="4b74e-166">ExternalScript</span></span>
- <span data-ttu-id="4b74e-167">Filter</span><span class="sxs-lookup"><span data-stu-id="4b74e-167">Filter</span></span>
- <span data-ttu-id="4b74e-168">Все</span><span class="sxs-lookup"><span data-stu-id="4b74e-168">All</span></span>

## <a name="remotehelprunspace-pssession-variable"></a><span data-ttu-id="4b74e-169">. ремотехелпрунспаце\<PSSession-variable></span><span class="sxs-lookup"><span data-stu-id="4b74e-169">.REMOTEHELPRUNSPACE \<PSSession-variable></span></span>

<span data-ttu-id="4b74e-170">Указывает сеанс, содержащий раздел справки.</span><span class="sxs-lookup"><span data-stu-id="4b74e-170">Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="4b74e-171">Введите переменную, содержащую сеанс PSSession.</span><span class="sxs-lookup"><span data-stu-id="4b74e-171">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="4b74e-172">Это ключевое слово используется `Export-PSSession` командлетом для поиска разделов справки для экспортированных команд.</span><span class="sxs-lookup"><span data-stu-id="4b74e-172">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

## <a name="externalhelp-xml-help-file"></a><span data-ttu-id="4b74e-173">. екстерналхелп\<XML Help File></span><span class="sxs-lookup"><span data-stu-id="4b74e-173">.EXTERNALHELP \<XML Help File></span></span>

<span data-ttu-id="4b74e-174">Указывает путь и (или) имя файла справки на основе XML для скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="4b74e-174">Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="4b74e-175">`.EXTERNALHELP`Ключевое слово сообщает командлету [Microsoft. PowerShell. Commands. жеселпкомманд](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) о получении справки для скрипта или функции в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="4b74e-175">The `.EXTERNALHELP` keyword tells the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="4b74e-176">`.EXTERNALHELP`Ключевое слово требуется при использовании файла справки на основе XML для скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="4b74e-176">The `.EXTERNALHELP` keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="4b74e-177">Без него `Get-Help` файл справки для функции или скрипта не будет найден.</span><span class="sxs-lookup"><span data-stu-id="4b74e-177">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="4b74e-178">`.EXTERNALHELP`Ключевое слово имеет приоритет над всеми остальными ключевыми словами справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="4b74e-178">The `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="4b74e-179">Если `.EXTERNALHELP` параметр существует, командлет [Microsoft. PowerShell. Commands. жеселпкомманд](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) не отображает справку на основе комментариев, даже если ей не удается найти файл справки, соответствующий значению ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="4b74e-179">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="4b74e-180">При экспорте функции модулем скрипта значение `.EXTERNALHELP` должно быть именем файла без пути.</span><span class="sxs-lookup"><span data-stu-id="4b74e-180">When the function is exported by a script module, the value of `.EXTERNALHELP` should be a filename without a path.</span></span> <span data-ttu-id="4b74e-181">`Get-Help`ищет файл в подкаталоге, зависящем от языкового стандарта, в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="4b74e-181">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="4b74e-182">Требования к имени файла отсутствуют, но рекомендуется использовать следующий формат имени файла: `<ScriptModule>.psm1-help.xml` .</span><span class="sxs-lookup"><span data-stu-id="4b74e-182">There are no requirements for the filename, but a best practice is to use the following filename format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="4b74e-183">Если функция не связана с модулем, укажите путь и имя файла в значении `.EXTERNALHELP` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="4b74e-183">When the function is not associated with a module, include a path and filename in the value of the `.EXTERNALHELP` keyword.</span></span> <span data-ttu-id="4b74e-184">Если указанный путь к XML-файлу содержит подкаталоги, относящиеся к пользовательскому интерфейсу, `Get-Help` то поиск в подкаталогах выполняется рекурсивно для XML-файла с именем сценария или функции в соответствии со стандартами переключения языка, установленными для Windows, так же, как и для всех разделов справки на основе XML.</span><span class="sxs-lookup"><span data-stu-id="4b74e-184">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="4b74e-185">Дополнительные сведения о формате файла справки на основе XML для командлета см. в разделе [Создание справки по командлетам Windows PowerShell](./writing-help-for-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="4b74e-185">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>
