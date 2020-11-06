---
description: Описание процесса написания разделов справки на основе комментариев для функций и скриптов.
keywords: powershell,командлет
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: cb7ac6e7b4ec3afb95c9864665490633fdad6c5c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232229"
---
# <a name="about-comment-based-help"></a><span data-ttu-id="52258-104">Сведения о справке на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="52258-104">About Comment-based Help</span></span>

## <a name="short-description"></a><span data-ttu-id="52258-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="52258-105">Short description</span></span>
<span data-ttu-id="52258-106">Описание процесса написания разделов справки на основе комментариев для функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="52258-106">Describes how to write comment-based help topics for functions and scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="52258-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="52258-107">Long description</span></span>

<span data-ttu-id="52258-108">Разделы справки на основе комментариев можно писать для функций и скриптов с помощью специальных ключевых слов комментария справки.</span><span class="sxs-lookup"><span data-stu-id="52258-108">You can write comment-based help topics for functions and scripts by using special help comment keywords.</span></span>

<span data-ttu-id="52258-109">Командлет [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) отображает справку на основе комментариев в том же формате, в котором отображаются разделы справки по командлетам, созданные на основе XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="52258-109">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) cmdlet displays comment-based help in the same format in which it displays the cmdlet help topics that are generated from XML files.</span></span> <span data-ttu-id="52258-110">Пользователи могут использовать все параметры `Get-Help` , такие как **Detailed** , **Full** , **examples** и **Online** , для просмотра содержимого справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-110">Users can use all of the parameters of `Get-Help`, such as **Detailed** , **Full** , **Examples** , and **Online** , to display the contents of comment-based help.</span></span>

<span data-ttu-id="52258-111">Также можно создавать файлы справки на основе XML для функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="52258-111">You can also write XML-based help files for functions and scripts.</span></span> <span data-ttu-id="52258-112">Чтобы разрешить `Get-Help` командлету найти файл справки на основе XML для функции или скрипта, используйте `.ExternalHelp` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="52258-112">To enable the `Get-Help` cmdlet to find the XML-based help file for a function or script, use the `.ExternalHelp` keyword.</span></span> <span data-ttu-id="52258-113">Без этого ключевого слова `Get-Help` не удается найти разделы справки на основе XML для функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="52258-113">Without this keyword, `Get-Help` cannot find XML-based help topics for functions or scripts.</span></span>

<span data-ttu-id="52258-114">В этом разделе объясняется, как создавать разделы справки для функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="52258-114">This topic explains how to write help topics for functions and scripts.</span></span> <span data-ttu-id="52258-115">Сведения о том, как отображать разделы справки для функций и скриптов, см. в разделе [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span><span class="sxs-lookup"><span data-stu-id="52258-115">For information about how to display help topics for functions and scripts, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span></span>

<span data-ttu-id="52258-116">Командлеты [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) и [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) работают только с файлами XML.</span><span class="sxs-lookup"><span data-stu-id="52258-116">The [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) and [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) cmdlets work only on XML files.</span></span> <span data-ttu-id="52258-117">Обновляемая Справка не поддерживает разделы справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-117">Updatable Help does not support comment-based help topics.</span></span>

## <a name="syntax-for-comment-based-help"></a><span data-ttu-id="52258-118">Синтаксис для справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="52258-118">Syntax for comment-based help</span></span>

<span data-ttu-id="52258-119">Синтаксис для справки на основе комментариев выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="52258-119">The syntax for comment-based help is as follows:</span></span>

```
# .<help keyword>
# <help content>
```

<span data-ttu-id="52258-120">or</span><span class="sxs-lookup"><span data-stu-id="52258-120">or</span></span>

```
<#
.<help keyword>
<help content>
#>
```

<span data-ttu-id="52258-121">Справка на основе комментариев записывается в виде набора комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-121">Comment-based help is written as a series of comments.</span></span> <span data-ttu-id="52258-122">Символ комментария можно ввести `#` перед каждой строкой комментариев или использовать `<#` `#>` символы и для создания блока комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-122">You can type a comment symbol `#` before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="52258-123">Все строки внутри блока комментариев обрабатываются как комментарии.</span><span class="sxs-lookup"><span data-stu-id="52258-123">All the lines within the comment block are interpreted as comments.</span></span>

<span data-ttu-id="52258-124">Все строки в разделе справки на основе комментариев должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="52258-124">All of the lines in a comment-based help topic must be contiguous.</span></span> <span data-ttu-id="52258-125">Если раздел справки на основе комментариев следует за комментарием, который не является частью раздела справки, должна существовать хотя бы одна пустая строка между последней строкой комментария, отличной от справки, и началом справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-125">If a comment-based help topic follows a comment that is not part of the help topic, there must be at least one blank line between the last non-help comment line and the beginning of the comment-based help.</span></span>

<span data-ttu-id="52258-126">Ключевые слова определяют каждый раздел справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-126">Keywords define each section of comment-based help.</span></span> <span data-ttu-id="52258-127">Каждому ключевому слову справки на основе комментариев предшествует точка `.` .</span><span class="sxs-lookup"><span data-stu-id="52258-127">Each comment-based help keyword is preceded by a dot `.`.</span></span> <span data-ttu-id="52258-128">Ключевые слова могут отображаться в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="52258-128">The keywords can appear in any order.</span></span> <span data-ttu-id="52258-129">Имена ключевых слов не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="52258-129">The keyword names are not case-sensitive.</span></span>

<span data-ttu-id="52258-130">Например, `.Description` ключевое слово предшествует описанию функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-130">For example, the `.Description` keyword precedes a description of a function or script.</span></span>

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

<span data-ttu-id="52258-131">Блок комментариев должен содержать по крайней мере одно ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="52258-131">The comment block must contain at least one keyword.</span></span> <span data-ttu-id="52258-132">Некоторые ключевые слова, такие как `.EXAMPLE` , могут встречаться много раз в одном блоке комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-132">Some of the keywords, such as `.EXAMPLE`, can appear many times in the same comment block.</span></span> <span data-ttu-id="52258-133">Содержимое справки для каждого ключевого слова начинается в строке после ключевого слова и может охватывать несколько строк.</span><span class="sxs-lookup"><span data-stu-id="52258-133">The help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

## <a name="syntax-for-comment-based-help-in-functions"></a><span data-ttu-id="52258-134">Синтаксис для справки на основе комментариев в функциях</span><span class="sxs-lookup"><span data-stu-id="52258-134">Syntax for comment-based help in functions</span></span>

<span data-ttu-id="52258-135">Справка на основе комментариев для функции может находиться в одном из трех расположений:</span><span class="sxs-lookup"><span data-stu-id="52258-135">Comment-based help for a function can appear in one of three locations:</span></span>

- <span data-ttu-id="52258-136">В начале тела функции.</span><span class="sxs-lookup"><span data-stu-id="52258-136">At the beginning of the function body.</span></span>
- <span data-ttu-id="52258-137">В конце тела функции.</span><span class="sxs-lookup"><span data-stu-id="52258-137">At the end of the function body.</span></span>
- <span data-ttu-id="52258-138">Перед `function` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="52258-138">Before the `function` keyword.</span></span> <span data-ttu-id="52258-139">Между последней строкой справки функции и ключевым словом не может быть больше одной пустой строки `function` .</span><span class="sxs-lookup"><span data-stu-id="52258-139">There cannot be more than one blank line between the last line of the function help and the `function` keyword.</span></span>

<span data-ttu-id="52258-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="52258-140">For example:</span></span>

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

<span data-ttu-id="52258-141">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="52258-141">or</span></span>

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

<span data-ttu-id="52258-142">or</span><span class="sxs-lookup"><span data-stu-id="52258-142">or</span></span>

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a><span data-ttu-id="52258-143">Синтаксис для справки на основе комментариев в скриптах</span><span class="sxs-lookup"><span data-stu-id="52258-143">Syntax for comment-based help in scripts</span></span>

<span data-ttu-id="52258-144">Справка на основе комментариев для сценария может находиться в одном из двух расположений в скрипте.</span><span class="sxs-lookup"><span data-stu-id="52258-144">Comment-based help for a script can appear in one of the following two locations in the script.</span></span>

- <span data-ttu-id="52258-145">В начале файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-145">At the beginning of the script file.</span></span> <span data-ttu-id="52258-146">Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.</span><span class="sxs-lookup"><span data-stu-id="52258-146">Script help can be preceded in the script only by comments and blank lines.</span></span>

  <span data-ttu-id="52258-147">Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки.</span><span class="sxs-lookup"><span data-stu-id="52258-147">If the first item in the script body (after the help) is a function declaration, there must be at least two blank lines between the end of the script help and the function declaration.</span></span> <span data-ttu-id="52258-148">В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.</span><span class="sxs-lookup"><span data-stu-id="52258-148">Otherwise, the help is interpreted as being help for the function, not help for the script.</span></span>

- <span data-ttu-id="52258-149">В конце файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-149">At the end of the script file.</span></span> <span data-ttu-id="52258-150">Однако если сценарий подписан, поместите справку на основе комментариев в начало файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-150">However, if the script is signed, place Comment-based help at the beginning of the script file.</span></span> <span data-ttu-id="52258-151">Конец скрипта занят блоком сигнатур.</span><span class="sxs-lookup"><span data-stu-id="52258-151">The end of the script is occupied by the signature block.</span></span>

<span data-ttu-id="52258-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="52258-152">For example:</span></span>

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

<span data-ttu-id="52258-153">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="52258-153">or</span></span>

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a><span data-ttu-id="52258-154">Синтаксис для справки на основе комментариев в модулях скриптов</span><span class="sxs-lookup"><span data-stu-id="52258-154">Syntax for comment-based help in script modules</span></span>

<span data-ttu-id="52258-155">В модуле скрипта `.psm1` Справка на основе комментариев использует синтаксис для функций, а не синтаксис скриптов.</span><span class="sxs-lookup"><span data-stu-id="52258-155">In a script module `.psm1`, comment-based help uses the syntax for functions, not the syntax for scripts.</span></span> <span data-ttu-id="52258-156">Синтаксис скрипта нельзя использовать для предоставления справки для всех функций, определенных в модуле скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-156">You cannot use the script syntax to provide help for all functions defined in a script module.</span></span>

<span data-ttu-id="52258-157">Например, если вы используете `.ExternalHelp` ключевое слово для выявления файлов справки на основе XML для функций в модуле скрипта, необходимо добавить `.ExternalHelp` комментарий к каждой функции.</span><span class="sxs-lookup"><span data-stu-id="52258-157">For example, if you are using the `.ExternalHelp` keyword to identify the XML-based help files for the functions in a script module, you must add an `.ExternalHelp` comment to each function.</span></span>

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a><span data-ttu-id="52258-158">Ключевые слова справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="52258-158">Comment-based help keywords</span></span>

<span data-ttu-id="52258-159">Ниже приведены допустимые ключевые слова справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-159">The following are valid comment-based help keywords.</span></span> <span data-ttu-id="52258-160">Они перечислены в том порядке, в котором они обычно отображаются в разделе справки, а также их предполагаемое использование.</span><span class="sxs-lookup"><span data-stu-id="52258-160">They are listed in the order in which they typically appear in a help topic along with their intended use.</span></span> <span data-ttu-id="52258-161">Эти ключевые слова могут отображаться в любом порядке в справке на основе комментариев и не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="52258-161">These keywords can appear in any order in the comment-based help, and they are not case-sensitive.</span></span>

### <a name="synopsis"></a><span data-ttu-id="52258-162">. Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="52258-162">.SYNOPSIS</span></span>

<span data-ttu-id="52258-163">Краткое описание функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-163">A brief description of the function or script.</span></span> <span data-ttu-id="52258-164">Это ключевое слово может использоваться только один раз в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="52258-164">This keyword can be used only once in each topic.</span></span>

### <a name="description"></a><span data-ttu-id="52258-165">. NОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="52258-165">.DESCRIPTION</span></span>

<span data-ttu-id="52258-166">Подробное описание функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-166">A detailed description of the function or script.</span></span> <span data-ttu-id="52258-167">Это ключевое слово может использоваться только один раз в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="52258-167">This keyword can be used only once in each topic.</span></span>

### <a name="parameter"></a><span data-ttu-id="52258-168">. ПАРАМЕТР</span><span class="sxs-lookup"><span data-stu-id="52258-168">.PARAMETER</span></span>

<span data-ttu-id="52258-169">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="52258-169">The description of a parameter.</span></span> <span data-ttu-id="52258-170">Добавьте `.PARAMETER` ключевое слово для каждого параметра в синтаксисе функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-170">Add a `.PARAMETER` keyword for each parameter in the function or script syntax.</span></span>

<span data-ttu-id="52258-171">Введите имя параметра в той же строке, что и `.PARAMETER` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="52258-171">Type the parameter name on the same line as the `.PARAMETER` keyword.</span></span> <span data-ttu-id="52258-172">Введите описание параметра в строки после `.PARAMETER` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="52258-172">Type the parameter description on the lines following the `.PARAMETER` keyword.</span></span> <span data-ttu-id="52258-173">Windows PowerShell интерпретирует весь текст между `.PARAMETER` строками, а также ключевое слово Next или конец блока комментариев как часть описания параметра.</span><span class="sxs-lookup"><span data-stu-id="52258-173">Windows PowerShell interprets all text between the `.PARAMETER` line and the next keyword or the end of the comment block as part of the parameter description.</span></span>
<span data-ttu-id="52258-174">Описание может включать разрывы абзацев.</span><span class="sxs-lookup"><span data-stu-id="52258-174">The description can include paragraph breaks.</span></span>

```
.PARAMETER  <Parameter-Name>
```

<span data-ttu-id="52258-175">Ключевые слова параметров могут использоваться в любом порядке в блоке комментариев, но синтаксис функции или скрипта определяет порядок, в котором параметры (и их описания) отображаются в разделе справки.</span><span class="sxs-lookup"><span data-stu-id="52258-175">The Parameter keywords can appear in any order in the comment block, but the function or script syntax determines the order in which the parameters (and their descriptions) appear in help topic.</span></span> <span data-ttu-id="52258-176">Чтобы изменить порядок, измените синтаксис.</span><span class="sxs-lookup"><span data-stu-id="52258-176">To change the order, change the syntax.</span></span>

<span data-ttu-id="52258-177">Можно также указать описание параметра, разместив комментарий в функции или синтаксисе скрипта непосредственно перед именем переменной параметра.</span><span class="sxs-lookup"><span data-stu-id="52258-177">You can also specify a parameter description by placing a comment in the function or script syntax immediately before the parameter variable name.</span></span> <span data-ttu-id="52258-178">Чтобы это работало, необходимо также иметь блок комментариев, содержащий по крайней мере одно ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="52258-178">For this to work, you must also have a comment block with at least one keyword.</span></span>

<span data-ttu-id="52258-179">Если используются как комментарий синтаксиса, так и `.PARAMETER` ключевое слово, используется описание, связанное с `.PARAMETER` ключевым словом, и комментарий синтаксиса игнорируется.</span><span class="sxs-lookup"><span data-stu-id="52258-179">If you use both a syntax comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the syntax comment is ignored.</span></span>

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a><span data-ttu-id="52258-180">. Например</span><span class="sxs-lookup"><span data-stu-id="52258-180">.EXAMPLE</span></span>

<span data-ttu-id="52258-181">Пример команды, которая использует функцию или скрипт, при необходимости за которой следует пример выходных данных и описание.</span><span class="sxs-lookup"><span data-stu-id="52258-181">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="52258-182">Повторите это ключевое слово для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="52258-182">Repeat this keyword for each example.</span></span>

### <a name="inputs"></a><span data-ttu-id="52258-183">. ВХОДА</span><span class="sxs-lookup"><span data-stu-id="52258-183">.INPUTS</span></span>

<span data-ttu-id="52258-184">Типы объектов .NET, которые можно передать в функцию или скрипт.</span><span class="sxs-lookup"><span data-stu-id="52258-184">The .NET types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="52258-185">Можно также включить описание входных объектов.</span><span class="sxs-lookup"><span data-stu-id="52258-185">You can also include a description of the input objects.</span></span>

### <a name="outputs"></a><span data-ttu-id="52258-186">. ВЫХОДНЫЕ</span><span class="sxs-lookup"><span data-stu-id="52258-186">.OUTPUTS</span></span>

<span data-ttu-id="52258-187">Тип .NET объектов, возвращаемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="52258-187">The .NET type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="52258-188">Можно также включить описание возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="52258-188">You can also include a description of the returned objects.</span></span>

### <a name="notes"></a><span data-ttu-id="52258-189">. Заметки О</span><span class="sxs-lookup"><span data-stu-id="52258-189">.NOTES</span></span>

<span data-ttu-id="52258-190">Дополнительные сведения о функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="52258-190">Additional information about the function or script.</span></span>

### <a name="link"></a><span data-ttu-id="52258-191">. ССЫЛКУ</span><span class="sxs-lookup"><span data-stu-id="52258-191">.LINK</span></span>

<span data-ttu-id="52258-192">Имя связанного раздела.</span><span class="sxs-lookup"><span data-stu-id="52258-192">The name of a related topic.</span></span> <span data-ttu-id="52258-193">Значение отображается в строке под запятыми. LINK "и должен предшествовать символом комментария `#` или включаться в блок комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-193">The value appears on the line below the ".LINK" keyword and must be preceded by a comment symbol `#` or included in the comment block.</span></span>

<span data-ttu-id="52258-194">Повторите `.LINK` ключевое слово для каждого связанного раздела.</span><span class="sxs-lookup"><span data-stu-id="52258-194">Repeat the `.LINK` keyword for each related topic.</span></span>

<span data-ttu-id="52258-195">Это содержимое отображается в разделе "связанные ссылки" раздела справки.</span><span class="sxs-lookup"><span data-stu-id="52258-195">This content appears in the Related Links section of the help topic.</span></span>

<span data-ttu-id="52258-196">`.Link`Содержимое ключевого слова может также включать универсальный код ресурса (URI) в Интернет-версию того же раздела справки.</span><span class="sxs-lookup"><span data-stu-id="52258-196">The `.Link` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same help topic.</span></span> <span data-ttu-id="52258-197">Версия в Интернете открывается при использовании параметра **Online** для `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="52258-197">The online version opens when you use the **Online** parameter of `Get-Help`.</span></span> <span data-ttu-id="52258-198">URI должен начинаться с "http" или "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="52258-198">The URI must begin with "http" or "https".</span></span>

### <a name="component"></a><span data-ttu-id="52258-199">. СМ</span><span class="sxs-lookup"><span data-stu-id="52258-199">.COMPONENT</span></span>

<span data-ttu-id="52258-200">Имя технологии или компонента, используемых функцией или сценарием или с которым она связана.</span><span class="sxs-lookup"><span data-stu-id="52258-200">The name of the technology or feature that the function or script uses, or to which it is related.</span></span> <span data-ttu-id="52258-201">Параметр **компонента** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="52258-201">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="role"></a><span data-ttu-id="52258-202">. ROLE</span><span class="sxs-lookup"><span data-stu-id="52258-202">.ROLE</span></span>

<span data-ttu-id="52258-203">Имя роли пользователя для раздела справки.</span><span class="sxs-lookup"><span data-stu-id="52258-203">The name of the user role for the help topic.</span></span> <span data-ttu-id="52258-204">Параметр **Role** объекта `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="52258-204">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="functionality"></a><span data-ttu-id="52258-205">. ВОЗМОЖНОСТИ</span><span class="sxs-lookup"><span data-stu-id="52258-205">.FUNCTIONALITY</span></span>

<span data-ttu-id="52258-206">Ключевые слова, описывающие предполагаемое использование функции.</span><span class="sxs-lookup"><span data-stu-id="52258-206">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="52258-207">Параметр **функций функции** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="52258-207">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="forwardhelptargetname"></a><span data-ttu-id="52258-208">. форвардхелптаржетнаме</span><span class="sxs-lookup"><span data-stu-id="52258-208">.FORWARDHELPTARGETNAME</span></span>

<span data-ttu-id="52258-209">Выполняет перенаправление в раздел справки для указанной команды.</span><span class="sxs-lookup"><span data-stu-id="52258-209">Redirects to the help topic for the specified command.</span></span> <span data-ttu-id="52258-210">Вы можете перенаправить пользователей в любой раздел справки, включая разделы справки для функции, скрипта, командлета или поставщика.</span><span class="sxs-lookup"><span data-stu-id="52258-210">You can redirect users to any help topic, including help topics for a function, script, cmdlet, or provider.</span></span>

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a><span data-ttu-id="52258-211">. форвардхелпкатегори</span><span class="sxs-lookup"><span data-stu-id="52258-211">.FORWARDHELPCATEGORY</span></span>

<span data-ttu-id="52258-212">Указывает категорию справки для элемента в `.ForwardHelpTargetName` .</span><span class="sxs-lookup"><span data-stu-id="52258-212">Specifies the help category of the item in `.ForwardHelpTargetName`.</span></span> <span data-ttu-id="52258-213">Допустимые значения: `Alias` , `Cmdlet` , `HelpFile` , `Function` , `Provider` , `General` , `FAQ` , `Glossary` ,,, `ScriptCommand` `ExternalScript` `Filter` или `All` .</span><span class="sxs-lookup"><span data-stu-id="52258-213">Valid values are `Alias`, `Cmdlet`, `HelpFile`, `Function`, `Provider`, `General`, `FAQ`, `Glossary`, `ScriptCommand`, `ExternalScript`, `Filter`, or `All`.</span></span> <span data-ttu-id="52258-214">Используйте это ключевое слово, чтобы избежать конфликтов при наличии команд с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="52258-214">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a><span data-ttu-id="52258-215">. ремотехелпрунспаце</span><span class="sxs-lookup"><span data-stu-id="52258-215">.REMOTEHELPRUNSPACE</span></span>

<span data-ttu-id="52258-216">Указывает сеанс, содержащий раздел справки.</span><span class="sxs-lookup"><span data-stu-id="52258-216">Specifies a session that contains the help topic.</span></span> <span data-ttu-id="52258-217">Введите переменную, содержащую объект **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="52258-217">Enter a variable that contains a **PSSession** object.</span></span> <span data-ttu-id="52258-218">Это ключевое слово используется командлетом [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) для поиска разделов справки для экспортированных команд.</span><span class="sxs-lookup"><span data-stu-id="52258-218">This keyword is used by the [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) cmdlet to find the help topics for the exported commands.</span></span>

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a><span data-ttu-id="52258-219">. екстерналхелп</span><span class="sxs-lookup"><span data-stu-id="52258-219">.EXTERNALHELP</span></span>

<span data-ttu-id="52258-220">Указывает файл справки на основе XML для скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="52258-220">Specifies an XML-based help file for the script or function.</span></span>

```powershell
# .EXTERNALHELP <XML Help File>
```

<span data-ttu-id="52258-221">`.ExternalHelp`Ключевое слово требуется при документировании функции или скрипта в XML-файлах.</span><span class="sxs-lookup"><span data-stu-id="52258-221">The `.ExternalHelp` keyword is required when a function or script is documented in XML files.</span></span> <span data-ttu-id="52258-222">Без этого ключевого слова `Get-Help` не удается найти файл справки на основе XML для функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-222">Without this keyword, `Get-Help` cannot find the XML-based help file for the function or script.</span></span>

<span data-ttu-id="52258-223">`.ExternalHelp`Ключевое слово имеет приоритет над другими ключевыми словами справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-223">The `.ExternalHelp` keyword takes precedence over other comment-based help keywords.</span></span> <span data-ttu-id="52258-224">Если `.ExternalHelp` параметр существует, не `Get-Help` отображает справку на основе комментариев, даже если не удается найти раздел справки, соответствующий значению `.ExternalHelp` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="52258-224">If `.ExternalHelp` is present, `Get-Help` does not display comment-based help, even if it cannot find a help topic that matches the value of the `.ExternalHelp` keyword.</span></span>

<span data-ttu-id="52258-225">Если функция экспортируется модулем, в качестве значения `.ExternalHelp` ключевого слова необходимо указать имя файла без пути.</span><span class="sxs-lookup"><span data-stu-id="52258-225">If the function is exported by a module, set the value of the `.ExternalHelp` keyword to a filename without a path.</span></span> <span data-ttu-id="52258-226">`Get-Help` ищет указанное имя файла в подкаталоге, зависящем от языка, в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="52258-226">`Get-Help` looks for the specified file name in a language-specific subdirectory of the module directory.</span></span> <span data-ttu-id="52258-227">Нет никаких требований к имени файла справки на основе XML для функции, но рекомендуется использовать следующий формат:</span><span class="sxs-lookup"><span data-stu-id="52258-227">There are no requirements for the name of the XML-based help file for a function, but a best practice is to use the following format:</span></span>

```
<ScriptModule.psm1>-help.xml
```

<span data-ttu-id="52258-228">Если функция не включена в модуль, включите путь к файлу справки на основе XML.</span><span class="sxs-lookup"><span data-stu-id="52258-228">If the function is not included in a module, include a path to the XML-based help file.</span></span> <span data-ttu-id="52258-229">Если значение содержит путь и путь содержит подкаталоги, относящиеся к пользовательскому интерфейсу, то `Get-Help` Поиск в подкаталогах выполняется рекурсивно для XML-файла с именем скрипта или функции в соответствии со стандартами переключения языка, установленными для Windows, так же, как и в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="52258-229">If the value includes a path and the path contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does in a module directory.</span></span>

<span data-ttu-id="52258-230">Дополнительные сведения о формате файла справки на основе XML см. в статье Создание [справки по командлетам](https://go.microsoft.com/fwlink/?LinkID=123415) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="52258-230">For more information about the cmdlet help XML-based help file format, see [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>

## <a name="autogenerated-content"></a><span data-ttu-id="52258-231">Автоматически созданное содержимое</span><span class="sxs-lookup"><span data-stu-id="52258-231">Autogenerated content</span></span>

<span data-ttu-id="52258-232">Командлет автоматически создает имя, синтаксис, список параметров, таблицу атрибутов параметров, общие параметры и примечания `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="52258-232">The name, syntax, parameter list, parameter attribute table, common parameters, and remarks are automatically generated by the `Get-Help` cmdlet.</span></span>

### <a name="name"></a><span data-ttu-id="52258-233">name</span><span class="sxs-lookup"><span data-stu-id="52258-233">Name</span></span>

<span data-ttu-id="52258-234">Раздел **имени** раздела справки по функции берется из имени функции в синтаксисе функции.</span><span class="sxs-lookup"><span data-stu-id="52258-234">The **Name** section of a function help topic is taken from the function name in the function syntax.</span></span> <span data-ttu-id="52258-235">**Имя** раздела справки по скрипту берется из имени файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-235">The **Name** of a script help topic is taken from the script filename.</span></span> <span data-ttu-id="52258-236">Чтобы изменить имя или его регистр букв, измените синтаксис функции или имя файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-236">To change the name or its capitalization, change the function syntax or the script filename.</span></span>

### <a name="syntax"></a><span data-ttu-id="52258-237">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52258-237">Syntax</span></span>

<span data-ttu-id="52258-238">Раздел **синтаксиса** раздела справки создается на основе синтаксиса функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-238">The **Syntax** section of the help topic is generated from the function or script syntax.</span></span> <span data-ttu-id="52258-239">Чтобы добавить подробные сведения в синтаксис раздела справки, например тип .NET параметра, добавьте подробные сведения в синтаксис.</span><span class="sxs-lookup"><span data-stu-id="52258-239">To add detail to the help topic syntax, such as the .NET type of a parameter, add the detail to the syntax.</span></span> <span data-ttu-id="52258-240">Если не указать тип параметра, тип **объекта** будет вставлен в качестве значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52258-240">If you do not specify a parameter type, the **Object** type is inserted as the default value.</span></span>

### <a name="parameter-list"></a><span data-ttu-id="52258-241">Список параметров</span><span class="sxs-lookup"><span data-stu-id="52258-241">Parameter List</span></span>

<span data-ttu-id="52258-242">Список параметров в разделе справки создается на основе синтаксиса функции или скрипта, а также из описаний, добавленных с помощью `.Parameter` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="52258-242">The parameter list in the help topic is generated from the function or script syntax and from the descriptions that you add by using the `.Parameter` keyword.</span></span> <span data-ttu-id="52258-243">Параметры функции отображаются в разделе **Parameters** раздела справки в том же порядке, в котором они отображаются в синтаксисе функции или сценария.</span><span class="sxs-lookup"><span data-stu-id="52258-243">The function parameters appear in the **Parameters** section of the help topic in the same order that they appear in the function or script syntax.</span></span> <span data-ttu-id="52258-244">В синтаксисе также берется написание и капитализация имен параметров.</span><span class="sxs-lookup"><span data-stu-id="52258-244">The spelling and capitalization of parameter names is also taken from the syntax.</span></span> <span data-ttu-id="52258-245">На него не влияет имя параметра, заданное `.Parameter` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="52258-245">It is not affected by the parameter name specified by the `.Parameter` keyword.</span></span>

### <a name="common-parameters"></a><span data-ttu-id="52258-246">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="52258-246">Common Parameters</span></span>

<span data-ttu-id="52258-247">**Общие параметры** добавляются к синтаксису и списку параметров раздела справки, даже если они не оказывают никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="52258-247">The **Common parameters** are added to the syntax and parameter list of the help topic, even if they have no effect.</span></span> <span data-ttu-id="52258-248">Дополнительные сведения об общих параметрах см. в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="52258-248">For more information about the common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="52258-249">Таблица атрибутов параметра</span><span class="sxs-lookup"><span data-stu-id="52258-249">Parameter Attribute Table</span></span>

<span data-ttu-id="52258-250">`Get-Help` формирует таблицу атрибутов параметров, которые отображаются при использовании параметра **Full** или **параметра** `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="52258-250">`Get-Help` generates the table of parameter attributes that appears when you use the **Full** or **Parameter** parameter of `Get-Help`.</span></span> <span data-ttu-id="52258-251">Значения атрибутов **Required** , **позицией** и значения **по умолчанию** берутся из синтаксиса функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-251">The value of the **Required** , **Position** , and **Default** value attributes is taken from the function or script syntax.</span></span>

<span data-ttu-id="52258-252">Значения по умолчанию и значение для **Accept подстановочных знаков** не отображаются в таблице атрибутов параметров, даже если они определены в функции или скрипте.</span><span class="sxs-lookup"><span data-stu-id="52258-252">Default values and a value for **Accept Wildcard characters** do not appear in the parameter attribute table even when they are defined in the function or script.</span></span> <span data-ttu-id="52258-253">Чтобы помочь пользователям, укажите эти сведения в описании параметра.</span><span class="sxs-lookup"><span data-stu-id="52258-253">To help users, provide this information in the parameter description.</span></span>

### <a name="remarks"></a><span data-ttu-id="52258-254">Remarks</span><span class="sxs-lookup"><span data-stu-id="52258-254">Remarks</span></span>

<span data-ttu-id="52258-255">Раздел **"Примечания** " раздела справки автоматически создается на основе имени функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-255">The **Remarks** section of the help topic is automatically generated from the function or script name.</span></span> <span data-ttu-id="52258-256">Нельзя изменить или повлиять на его содержимое.</span><span class="sxs-lookup"><span data-stu-id="52258-256">You cannot change or affect its content.</span></span>

## <a name="examples"></a><span data-ttu-id="52258-257">Примеры</span><span class="sxs-lookup"><span data-stu-id="52258-257">Examples</span></span>

### <a name="comment-based-help-for-a-function"></a><span data-ttu-id="52258-258">Справка на основе комментариев для функции</span><span class="sxs-lookup"><span data-stu-id="52258-258">Comment-based Help for a Function</span></span>

<span data-ttu-id="52258-259">Следующий пример функции включает в себя справку на основе комментариев:</span><span class="sxs-lookup"><span data-stu-id="52258-259">The following sample function includes comment-based help:</span></span>

```powershell
function Add-Extension
{
param ([string]$Name,[string]$Extension = "txt")
$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.

.PARAMETER Name
Specifies the file name.

.PARAMETER Extension
Specifies the extension. "Txt" is the default.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

<span data-ttu-id="52258-260">Будут получены следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="52258-260">The results are as follows:</span></span>

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

PARAMETERS

-Name
Specifies the file name.

Required?                    false
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-Extension
Specifies the extension. "Txt" is the default.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type
"get-help about_commonparameters".

INPUTS
None. You cannot pipe objects to Add-Extension.

OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a><span data-ttu-id="52258-261">Описания параметров в синтаксисе функции</span><span class="sxs-lookup"><span data-stu-id="52258-261">Parameter Descriptions in Function Syntax</span></span>

<span data-ttu-id="52258-262">Этот пример аналогичен предыдущему, за исключением того, что описания параметров вставляются в синтаксис функции.</span><span class="sxs-lookup"><span data-stu-id="52258-262">This example is the same as the previous one, except that the parameter descriptions are inserted in the function syntax.</span></span> <span data-ttu-id="52258-263">Этот формат наиболее удобен при кратком описании.</span><span class="sxs-lookup"><span data-stu-id="52258-263">This format is most useful when the descriptions are brief.</span></span>

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a><span data-ttu-id="52258-264">Справка на основе комментариев для сценария</span><span class="sxs-lookup"><span data-stu-id="52258-264">Comment-based Help for a Script</span></span>

<span data-ttu-id="52258-265">Следующий пример скрипта включает в себя справку на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="52258-265">The following sample script includes comment-based help.</span></span> <span data-ttu-id="52258-266">Обратите внимание на пустые строки между закрывающим `#>` и `Param` оператором.</span><span class="sxs-lookup"><span data-stu-id="52258-266">Notice the blank lines between the closing `#>` and the `Param` statement.</span></span> <span data-ttu-id="52258-267">В скрипте, не имеющем `Param` оператора, в разделе справки и первом объявлении функции должно быть по крайней мере две пустые строки между последним комментарием.</span><span class="sxs-lookup"><span data-stu-id="52258-267">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the help topic and the first function declaration.</span></span> <span data-ttu-id="52258-268">Без этих пустых строк `Get-Help` связывает раздел справки с функцией, а не со сценарием.</span><span class="sxs-lookup"><span data-stu-id="52258-268">Without these blank lines, `Get-Help` associates the help topic with the function, not the script.</span></span>

```powershell
<#
.SYNOPSIS

Performs monthly data updates.

.DESCRIPTION

The Update-Month.ps1 script updates the registry with new data generated
during the past month and generates a report.

.PARAMETER InputPath
Specifies the path to the CSV-based input file.

.PARAMETER OutputPath
Specifies the name and path for the CSV-based output file. By default,
MonthlyUpdates.ps1 generates a name from the date and time it runs, and
saves the output in the local directory.

.INPUTS

None. You cannot pipe objects to Update-Month.ps1.

.OUTPUTS

None. Update-Month.ps1 does not generate any output.

.EXAMPLE

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

<span data-ttu-id="52258-269">Следующая команда получает справку по скрипту.</span><span class="sxs-lookup"><span data-stu-id="52258-269">The following command gets the script help.</span></span> <span data-ttu-id="52258-270">Так как скрипт не находится в каталоге, указанном в `$env:Path` переменной среды, `Get-Help` команда, которая получает справку по скрипту, должна указывать путь к скрипту.</span><span class="sxs-lookup"><span data-stu-id="52258-270">Because the script is not in a directory that is listed in the `$env:Path` environment variable, the `Get-Help` command that gets the script help must specify the script path.</span></span>

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

-InputPath
Specifies the path to the CSV-based input file.

Required?                    true
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-OutputPath
Specifies the name and path for the CSV-based output file. By
default, MonthlyUpdates.ps1 generates a name from the date
and time it runs, and saves the output in the local directory.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type,
"get-help about_commonparameters".

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a><span data-ttu-id="52258-271">Перенаправление в XML-файл</span><span class="sxs-lookup"><span data-stu-id="52258-271">Redirecting to an XML File</span></span>

<span data-ttu-id="52258-272">Вы можете писать разделы справки на основе XML для функций и скриптов.</span><span class="sxs-lookup"><span data-stu-id="52258-272">You can write XML-based help topics for functions and scripts.</span></span> <span data-ttu-id="52258-273">Хотя справку на основе комментариев проще реализовать, для обновляемой справки и получения разделов справки на нескольких языках требуется справка на основе XML.</span><span class="sxs-lookup"><span data-stu-id="52258-273">Although comment-based help is easier to implement, XML-based help is required for Updatable Help and to provide help topics in multiple languages.</span></span>

<span data-ttu-id="52258-274">В следующем примере показаны первые несколько строк скрипта Update-Month.ps1.</span><span class="sxs-lookup"><span data-stu-id="52258-274">The following example shows the first few lines of the Update-Month.ps1 script.</span></span>
<span data-ttu-id="52258-275">В скрипте используется `.ExternalHelp` ключевое слово, чтобы указать путь к разделу справки на основе XML для скрипта.</span><span class="sxs-lookup"><span data-stu-id="52258-275">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based help topic for the script.</span></span>

<span data-ttu-id="52258-276">Обратите внимание, что значение `.ExternalHelp` ключевого слова отображается в той же строке, что и ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="52258-276">Note that the value of the `.ExternalHelp` keyword appears on the same line as the keyword.</span></span> <span data-ttu-id="52258-277">Любое другое размещение является неэффективным.</span><span class="sxs-lookup"><span data-stu-id="52258-277">Any other placement is ineffective.</span></span>

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

<span data-ttu-id="52258-278">В следующих примерах показаны три допустимые позиции `.ExternalHelp` ключевого слова в функции.</span><span class="sxs-lookup"><span data-stu-id="52258-278">The following examples show three valid placements of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a><span data-ttu-id="52258-279">Перенаправление на другой раздел справки</span><span class="sxs-lookup"><span data-stu-id="52258-279">Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="52258-280">Следующий код является выдержкой из начала встроенной функции справки в PowerShell, которая отображает один экран текста справки за раз.</span><span class="sxs-lookup"><span data-stu-id="52258-280">The following code is an excerpt from the beginning of the built-in help function in PowerShell, which displays one screen of help text at a time.</span></span>
<span data-ttu-id="52258-281">Поскольку в разделе справки для `Get-Help` командлета описана функция справки, функция Help использует `.ForwardHelpTargetName` `.ForwardHelpCategory` Ключевые слова и для перенаправления пользователя в `Get-Help` раздел справки по командлету.</span><span class="sxs-lookup"><span data-stu-id="52258-281">Because the help topic for the `Get-Help` cmdlet describes the help function, the help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the `Get-Help` cmdlet help topic.</span></span>

```powershell
function help
{

<#
.FORWARDHELPTARGETNAME Get-Help
.FORWARDHELPCATEGORY Cmdlet
#>
[CmdletBinding(DefaultParameterSetName='AllUsersView')]
param(
[Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
[System.String]
${Name},
...
```

<span data-ttu-id="52258-282">Эта функция используется в следующей команде:</span><span class="sxs-lookup"><span data-stu-id="52258-282">The following command uses this feature:</span></span>

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a><span data-ttu-id="52258-283">См. также статью</span><span class="sxs-lookup"><span data-stu-id="52258-283">See also</span></span>

[<span data-ttu-id="52258-284">about_Functions</span><span class="sxs-lookup"><span data-stu-id="52258-284">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="52258-285">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="52258-285">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="52258-286">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="52258-286">about_Scripts</span></span>](about_Scripts.md)

[<span data-ttu-id="52258-287">Написание справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="52258-287">How to Write Cmdlet Help</span></span>](https://go.microsoft.com/fwlink/?LinkID=123415)