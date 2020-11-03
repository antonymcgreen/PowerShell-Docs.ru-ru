---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: 691709fe3f5e4908ab3203df73f636981adf560c
ms.sourcegitcommit: b7ff031a12afd04910aeb98345ebee92f5845b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "93230177"
---
# <span data-ttu-id="17876-103">Get-Help</span><span class="sxs-lookup"><span data-stu-id="17876-103">Get-Help</span></span>

## <span data-ttu-id="17876-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="17876-104">SYNOPSIS</span></span>
<span data-ttu-id="17876-105">Отображает сведения о командах и концепциях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17876-105">Displays information about PowerShell commands and concepts.</span></span>

## <span data-ttu-id="17876-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="17876-106">SYNTAX</span></span>

### <span data-ttu-id="17876-107">AllUsersView (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="17876-107">AllUsersView (Default)</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Full] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="17876-108">DetailedView</span><span class="sxs-lookup"><span data-stu-id="17876-108">DetailedView</span></span>

```
Get-Help [[-Name] <String>] -Detailed [-Path <String>] [-Category <String[]>]
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="17876-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="17876-109">Examples</span></span>

```
Get-Help [[-Name] <String>] -Examples [-Path <String>] [-Category <String[]>]
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="17876-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="17876-110">Parameters</span></span>

```
Get-Help [[-Name] <String>] -Parameter <String[]> [-Path <String>] [-Category <String[]>]
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="17876-111">Миграция по сети</span><span class="sxs-lookup"><span data-stu-id="17876-111">Online</span></span>

```
Get-Help [[-Name] <String>] -Online [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="17876-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="17876-112">DESCRIPTION</span></span>

<span data-ttu-id="17876-113">`Get-Help`Командлет отображает сведения об основных понятиях и командах PowerShell, включая командлеты, функции, команды модель CIM (CIM), рабочие процессы, поставщики, псевдонимы и скрипты.</span><span class="sxs-lookup"><span data-stu-id="17876-113">The `Get-Help` cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.</span></span>

<span data-ttu-id="17876-114">Чтобы получить справку по командлету PowerShell, введите, `Get-Help` за которым следует имя командлета, например: `Get-Help Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="17876-114">To get help for a PowerShell cmdlet, type `Get-Help` followed by the cmdlet name, such as: `Get-Help Get-Process`.</span></span>

<span data-ttu-id="17876-115">Основные статьи справки в PowerShell начинаются с **about_** , например **about_Comparison_Operators** .</span><span class="sxs-lookup"><span data-stu-id="17876-115">Conceptual help articles in PowerShell begin with **about_** , such as **about_Comparison_Operators** .</span></span> <span data-ttu-id="17876-116">Чтобы просмотреть все **about_** статьи, введите `Get-Help about_*` .</span><span class="sxs-lookup"><span data-stu-id="17876-116">To see all **about_** articles, type `Get-Help about_*`.</span></span> <span data-ttu-id="17876-117">Чтобы просмотреть определенную статью, введите `Get-Help about_<article-name>` , например `Get-Help about_Comparison_Operators` .</span><span class="sxs-lookup"><span data-stu-id="17876-117">To see a particular article, type `Get-Help about_<article-name>`, such as `Get-Help about_Comparison_Operators`.</span></span>

<span data-ttu-id="17876-118">Чтобы получить справку для поставщика PowerShell, введите, `Get-Help` за которым следует имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="17876-118">To get help for a PowerShell provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="17876-119">Например, чтобы получить справку для поставщика сертификатов, введите `Get-Help Certificate` .</span><span class="sxs-lookup"><span data-stu-id="17876-119">For example, to get help for the Certificate provider, type `Get-Help Certificate`.</span></span>

<span data-ttu-id="17876-120">Можно также ввести `help` или `man` , который отображает один экран текста за раз.</span><span class="sxs-lookup"><span data-stu-id="17876-120">You can also type `help` or `man`, which displays one screen of text at a time.</span></span> <span data-ttu-id="17876-121">Или, `<cmdlet-name> -?` , то же, что и `Get-Help` , но работает только для командлетов.</span><span class="sxs-lookup"><span data-stu-id="17876-121">Or, `<cmdlet-name> -?`, that is identical to `Get-Help`, but only works for cmdlets.</span></span>

<span data-ttu-id="17876-122">`Get-Help` Возвращает содержимое справки, которое отображается в файлах справки на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17876-122">`Get-Help` gets the help content that it displays from help files on your computer.</span></span> <span data-ttu-id="17876-123">Без файлов справки `Get-Help` отображает только основные сведения о командлетах.</span><span class="sxs-lookup"><span data-stu-id="17876-123">Without the help files, `Get-Help` displays only basic information about cmdlets.</span></span> <span data-ttu-id="17876-124">К некоторым модулям PowerShell относятся файлы справки.</span><span class="sxs-lookup"><span data-stu-id="17876-124">Some PowerShell modules include help files.</span></span> <span data-ttu-id="17876-125">Начиная с версии PowerShell 3,0 модули, которые входят в состав операционной системы Windows, не включают файлы справки.</span><span class="sxs-lookup"><span data-stu-id="17876-125">Beginning in PowerShell 3.0, the modules that come with the Windows operating system don't include help files.</span></span> <span data-ttu-id="17876-126">Чтобы скачать или обновить файлы справки для модуля в PowerShell 3,0, используйте `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="17876-126">To download or update the help files for a module in PowerShell 3.0, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="17876-127">Можно также просмотреть справочные документы по PowerShell в Интернете в Документация Майкрософт. Чтобы получить оперативную версию файла справки, используйте параметр **Online** , например: `Get-Help Get-Process -Online` .</span><span class="sxs-lookup"><span data-stu-id="17876-127">You can also view the PowerShell help documents online in the Microsoft Docs. To get the online version of a help file, use the **Online** parameter, such as: `Get-Help Get-Process -Online`.</span></span> <span data-ttu-id="17876-128">Сведения о том, как прочитать всю документацию по PowerShell, см. в документации по Документация Майкрософт [PowerShell](/powershell).</span><span class="sxs-lookup"><span data-stu-id="17876-128">To read all the PowerShell documentation, see the Microsoft Docs [PowerShell Documentation](/powershell).</span></span>

<span data-ttu-id="17876-129">Если ввести `Get-Help` , за которым следует точное имя статьи справки, или слово, уникальное для статьи справки, `Get-Help` отображает содержимое статьи.</span><span class="sxs-lookup"><span data-stu-id="17876-129">If you type `Get-Help` followed by the exact name of a help article, or by a word unique to a help article, `Get-Help` displays the article's content.</span></span> <span data-ttu-id="17876-130">Если указать точное имя псевдонима команды, `Get-Help` выводит справку по исходной команде.</span><span class="sxs-lookup"><span data-stu-id="17876-130">If you specify the exact name of a command alias, `Get-Help` displays the help for the original command.</span></span> <span data-ttu-id="17876-131">Если ввести слово или слово, которое отображается в нескольких заголовках справочной статьи, `Get-Help` отображается список соответствующих заголовков.</span><span class="sxs-lookup"><span data-stu-id="17876-131">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span> <span data-ttu-id="17876-132">При вводе любого текста, который не отображается в заголовках статей справки, `Get-Help` отображается список статей, содержащих этот текст в их содержимом.</span><span class="sxs-lookup"><span data-stu-id="17876-132">If you enter any text that doesn't appear in any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="17876-133">`Get-Help` может получить статьи справки для всех поддерживаемых языков и языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="17876-133">`Get-Help` can get help articles for all supported languages and locales.</span></span> <span data-ttu-id="17876-134">`Get-Help` сначала ищет файлы справки в наборе языкового стандарта для Windows, затем в родительском языковом стандарте, например в **PT** для **pt-br** , а затем в резервном языковом стандарте.</span><span class="sxs-lookup"><span data-stu-id="17876-134">`Get-Help` first looks for help files in the locale set for Windows, then in the parent locale, such as **pt** for **pt-BR** , and then in a fallback locale.</span></span> <span data-ttu-id="17876-135">Начиная с версии PowerShell 3,0, если `Get-Help` не удается найти справку по резервному языку, он ищет статьи справки на английском языке, **en-US** , прежде чем возвращает сообщение об ошибке или отображает автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="17876-135">Beginning in PowerShell 3.0, if `Get-Help` doesn't find help in the fallback locale, it looks for help articles in English, **en-US** , before it returns an error message or displaying autogenerated help.</span></span>

<span data-ttu-id="17876-136">Сведения о символах, `Get-Help` отображаемых на схеме синтаксиса команды, см. в разделе [about_Command_Syntax](./About/about_Command_Syntax.md).</span><span class="sxs-lookup"><span data-stu-id="17876-136">For information about the symbols that `Get-Help` displays in the command syntax diagram, see [about_Command_Syntax](./About/about_Command_Syntax.md).</span></span>
<span data-ttu-id="17876-137">Дополнительные сведения об атрибутах параметров, таких как **Required** и **Disposition** , см. в разделе [about_Parameters](./About/about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="17876-137">For information about parameter attributes, such as **Required** and **Position** , see [about_Parameters](./About/about_Parameters.md).</span></span>

>[!NOTE]
> <span data-ttu-id="17876-138">В PowerShell 3,0 и PowerShell 4,0 `Get-Help` не удается найти **сведения о** статьях в модулях, если модуль не импортирован в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="17876-138">In PowerShell 3.0 and PowerShell 4.0, `Get-Help` can't find **About** articles in modules unless the module is imported into the current session.</span></span> <span data-ttu-id="17876-139">Это известная проблема.</span><span class="sxs-lookup"><span data-stu-id="17876-139">This is a known issue.</span></span> <span data-ttu-id="17876-140">Чтобы получить **сведения о** статьях в модуле, импортируйте модуль либо с помощью `Import-Module` командлета, либо путем запуска командлета, который включается в модуль.</span><span class="sxs-lookup"><span data-stu-id="17876-140">To get **About** articles in a module, import the module, either by using the `Import-Module` cmdlet or by running a cmdlet that's included in the module.</span></span>

## <span data-ttu-id="17876-141">Примеры</span><span class="sxs-lookup"><span data-stu-id="17876-141">EXAMPLES</span></span>

### <span data-ttu-id="17876-142">Пример 1. Отображение основных справочных сведений о командлете</span><span class="sxs-lookup"><span data-stu-id="17876-142">Example 1: Display basic help information about a cmdlet</span></span>

<span data-ttu-id="17876-143">В этих примерах отображаются основные справочные сведения о `Format-Table` командлете.</span><span class="sxs-lookup"><span data-stu-id="17876-143">These examples display basic help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

<span data-ttu-id="17876-144">`Get-Help <cmdlet-name>` — Это простейший синтаксис командлета по умолчанию `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="17876-144">`Get-Help <cmdlet-name>` is the simplest and default syntax of `Get-Help` cmdlet.</span></span> <span data-ttu-id="17876-145">Параметр **Name** можно опустить.</span><span class="sxs-lookup"><span data-stu-id="17876-145">You can omit the **Name** parameter.</span></span>

<span data-ttu-id="17876-146">Синтаксис `<cmdlet-name> -?` работает только для командлетов.</span><span class="sxs-lookup"><span data-stu-id="17876-146">The syntax `<cmdlet-name> -?` works only for cmdlets.</span></span>

### <span data-ttu-id="17876-147">Пример 2. Отображение основных сведений по одной странице за раз</span><span class="sxs-lookup"><span data-stu-id="17876-147">Example 2: Display basic information one page at a time</span></span>

<span data-ttu-id="17876-148">В этих примерах отображаются основные справочные сведения о `Format-Table` командлете по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="17876-148">These examples display basic help information about the `Format-Table` cmdlet one page at a time.</span></span>

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

<span data-ttu-id="17876-149">`help` — Это функция, которая выполняет `Get-Help` командлет внутренне и отображает результат по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="17876-149">`help` is a function that runs `Get-Help` cmdlet internally and displays the result one page at a time.</span></span>

<span data-ttu-id="17876-150">`man` псевдоним для `help` функции.</span><span class="sxs-lookup"><span data-stu-id="17876-150">`man` is an alias for the `help` function.</span></span>

<span data-ttu-id="17876-151">`Get-Help Format-Table` отправляет объект вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="17876-151">`Get-Help Format-Table` sends the object down the pipeline.</span></span> <span data-ttu-id="17876-152">`Out-Host -Paging` Получает выходные данные из конвейера и отображает их по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="17876-152">`Out-Host -Paging` receives the output from the pipeline and displays it one page at a time.</span></span> <span data-ttu-id="17876-153">Дополнительные сведения см. в разделе [Out-Host](Out-Host.md).</span><span class="sxs-lookup"><span data-stu-id="17876-153">For more information, see [Out-Host](Out-Host.md).</span></span>

### <span data-ttu-id="17876-154">Пример 3. Отображение дополнительных сведений для командлета</span><span class="sxs-lookup"><span data-stu-id="17876-154">Example 3: Display more information for a cmdlet</span></span>

<span data-ttu-id="17876-155">В этих примерах отображаются более подробные справочные сведения о `Format-Table` командлете.</span><span class="sxs-lookup"><span data-stu-id="17876-155">These examples display more detailed help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

<span data-ttu-id="17876-156">**Подробный** параметр отображает подробное представление статьи справки, включающее описание параметров и примеры.</span><span class="sxs-lookup"><span data-stu-id="17876-156">The **Detailed** parameter displays the help article's detailed view that includes parameter descriptions and examples.</span></span>

<span data-ttu-id="17876-157">Параметр **Full** отображает полное представление статьи справки, включающее описания параметров, примеры, типы входных и выходных объектов, а также дополнительные примечания.</span><span class="sxs-lookup"><span data-stu-id="17876-157">The **Full** parameter displays the help article's full view that includes parameter descriptions, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="17876-158">Параметры **Detailed** и **Full** действуют только для команд, в которых есть файлы справки, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17876-158">The **Detailed** and **Full** parameters are effective only for the commands that have help files installed on the computer.</span></span> <span data-ttu-id="17876-159">Параметры не вступают в силу для концептуальных ( **about_** ) справочных статей.</span><span class="sxs-lookup"><span data-stu-id="17876-159">The parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="17876-160">Пример 4. Отображение выбранных частей командлета с помощью параметров</span><span class="sxs-lookup"><span data-stu-id="17876-160">Example 4: Display selected parts of a cmdlet by using parameters</span></span>

<span data-ttu-id="17876-161">В этих примерах отображаются выбранные части `Format-Table` справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="17876-161">These examples display selected portions of the `Format-Table` cmdlet help.</span></span>

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

<span data-ttu-id="17876-162">Параметр " **примеры** " отображает разделы **имени** файла справки и **кратких** сведений, а также все примеры.</span><span class="sxs-lookup"><span data-stu-id="17876-162">The **Examples** parameter displays the help file's **NAME** and **SYNOPSIS** sections, and all the Examples.</span></span> <span data-ttu-id="17876-163">Нельзя указать пример числа, так как параметр **examples** является параметром Switch.</span><span class="sxs-lookup"><span data-stu-id="17876-163">You can't specify an Example number because the **Examples** parameter is a switch parameter.</span></span>

<span data-ttu-id="17876-164">Параметр **Parameter** отображает только описания указанных параметров.</span><span class="sxs-lookup"><span data-stu-id="17876-164">The **Parameter** parameter displays only the descriptions of the specified parameters.</span></span> <span data-ttu-id="17876-165">Если указать только `*` подстановочный знак звездочки (), будут выведены описания всех параметров.</span><span class="sxs-lookup"><span data-stu-id="17876-165">If you specify only the asterisk (`*`) wildcard character, it displays the descriptions of all parameters.</span></span>
<span data-ttu-id="17876-166">Если **параметр** указывает имя параметра, например **GroupBy** , отображается информация об этом параметре.</span><span class="sxs-lookup"><span data-stu-id="17876-166">When **Parameter** specifies a parameter name such as **GroupBy** , information about that parameter is shown.</span></span>

<span data-ttu-id="17876-167">Эти параметры не действуют для концептуальных ( **about_** ) статей справки.</span><span class="sxs-lookup"><span data-stu-id="17876-167">These parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="17876-168">Пример 5. отображение интерактивной версии справки</span><span class="sxs-lookup"><span data-stu-id="17876-168">Example 5: Display online version of help</span></span>

<span data-ttu-id="17876-169">В этом примере отображается интерактивная версия статьи справки для `Format-Table` командлета в веб-браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17876-169">This example displays the online version of the help article for the `Format-Table` cmdlet in your default web browser.</span></span>

```powershell
Get-Help Format-Table -Online
```

### <span data-ttu-id="17876-170">Пример 6. Отображение справки по справочной системе</span><span class="sxs-lookup"><span data-stu-id="17876-170">Example 6: Display help about the help system</span></span>

<span data-ttu-id="17876-171">`Get-Help`Командлет без параметров отображает сведения о справочной системе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17876-171">The `Get-Help` cmdlet without parameters displays information about the PowerShell help system.</span></span>

```powershell
Get-Help
```

### <span data-ttu-id="17876-172">Пример 7. Отображение доступных справочных статей</span><span class="sxs-lookup"><span data-stu-id="17876-172">Example 7: Display available help articles</span></span>

<span data-ttu-id="17876-173">В этом примере отображается список всех справочных статей, доступных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17876-173">This example displays a list of all help articles available on your computer.</span></span>

```powershell
Get-Help *
```

### <span data-ttu-id="17876-174">Пример 8. Отображение списка концептуальных статей</span><span class="sxs-lookup"><span data-stu-id="17876-174">Example 8: Display a list of conceptual articles</span></span>

<span data-ttu-id="17876-175">В этом примере отображается список концептуальных статей, входящих в состав справки по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17876-175">This example displays a list of the conceptual articles included in PowerShell help.</span></span> <span data-ttu-id="17876-176">Все эти статьи начинаются с символов **about_** .</span><span class="sxs-lookup"><span data-stu-id="17876-176">All these articles begin with the characters **about_** .</span></span> <span data-ttu-id="17876-177">Чтобы отобразить определенный файл справки, введите `Get-Help \<about_article-name\>` , например, `Get-Help about_Signing` .</span><span class="sxs-lookup"><span data-stu-id="17876-177">To display a particular help file, type `Get-Help \<about_article-name\>`, for example, `Get-Help about_Signing`.</span></span>

<span data-ttu-id="17876-178">Отображаются только основные статьи с файлами справки, установленными на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17876-178">Only the conceptual articles that have help files installed on your computer are displayed.</span></span> <span data-ttu-id="17876-179">Сведения о загрузке и установке файлов справки в PowerShell 3,0 см. в разделе [Update-Help](Update-Help.md).</span><span class="sxs-lookup"><span data-stu-id="17876-179">For information about downloading and installing help files in PowerShell 3.0, see [Update-Help](Update-Help.md).</span></span>

```powershell
Get-Help about_*
```

### <span data-ttu-id="17876-180">Пример 9. Поиск слова в справке по командлету</span><span class="sxs-lookup"><span data-stu-id="17876-180">Example 9: Search for a word in cmdlet help</span></span>

<span data-ttu-id="17876-181">В этом примере показано, как выполнить поиск слова в статье справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="17876-181">This example shows how to search for a word in a cmdlet help article.</span></span>

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

<span data-ttu-id="17876-182">`Get-Help` использует параметр **Full** для получения справочных сведений для `Add-Member` .</span><span class="sxs-lookup"><span data-stu-id="17876-182">`Get-Help` uses the **Full** parameter to get help information for `Add-Member`.</span></span> <span data-ttu-id="17876-183">Объект **MamlCommandHelpInfo** отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="17876-183">The **MamlCommandHelpInfo** object is sent down the pipeline.</span></span> <span data-ttu-id="17876-184">`Out-String` использует параметр **Stream** для преобразования объекта в строку.</span><span class="sxs-lookup"><span data-stu-id="17876-184">`Out-String` uses the **Stream** parameter to convert the object into a string.</span></span> <span data-ttu-id="17876-185">`Select-String` использует параметр **pattern** для поиска **Clixml** в строке.</span><span class="sxs-lookup"><span data-stu-id="17876-185">`Select-String` uses the **Pattern** parameter to search the string for **Clixml** .</span></span>

### <span data-ttu-id="17876-186">Пример 10. Отображение списка статей, содержащих слово</span><span class="sxs-lookup"><span data-stu-id="17876-186">Example 10: Display a list of articles that include a word</span></span>

<span data-ttu-id="17876-187">В этом примере отображается список статей, включающих **удаленное взаимодействие** по словам.</span><span class="sxs-lookup"><span data-stu-id="17876-187">This example displays a list of articles that include the word **remoting** .</span></span>

<span data-ttu-id="17876-188">При вводе слова, которое не отображается в заголовке статьи, `Get-Help` отображается список статей, содержащих это слово.</span><span class="sxs-lookup"><span data-stu-id="17876-188">When you enter a word that doesn't appear in any article title, `Get-Help` displays a list of articles that include that word.</span></span>

```powershell
Get-Help -Name remoting
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Install-PowerShellRemoting.ps1    External                            Install-PowerShellRemoting.ps1
Disable-PSRemoting                Cmdlet    Microsoft.PowerShell.Core Prevents remote users...
Enable-PSRemoting                 Cmdlet    Microsoft.PowerShell.Core Configures the computer...
```

### <span data-ttu-id="17876-189">Пример 11. Отображение справки, относящейся к поставщику</span><span class="sxs-lookup"><span data-stu-id="17876-189">Example 11: Display provider-specific help</span></span>

<span data-ttu-id="17876-190">В этом примере показаны два способа получения справки, относящейся к поставщику `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="17876-190">This example shows two ways of getting the provider-specific help for `Get-Item`.</span></span> <span data-ttu-id="17876-191">Эти команды позволяют получить справку, в которой объясняется, как использовать `Get-Item` командлет в узле **коллекции** данных поставщика SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17876-191">These commands get help that explains how to use the `Get-Item` cmdlet in the PowerShell SQL Server provider's **DataCollection** node.</span></span>

<span data-ttu-id="17876-192">В первом примере используется параметр `Get-Help` **path** для указания пути поставщика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="17876-192">The first example uses the `Get-Help` **Path** parameter to specify the SQL Server provider's path.</span></span>
<span data-ttu-id="17876-193">Так как путь поставщика указан, можно выполнить команду из любого расположения пути.</span><span class="sxs-lookup"><span data-stu-id="17876-193">Because the provider's path is specified, you can run the command from any path location.</span></span>

<span data-ttu-id="17876-194">Во втором примере используется `Set-Location` для перехода к пути поставщика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="17876-194">The second example uses `Set-Location` to navigate to the SQL Server provider's path.</span></span> <span data-ttu-id="17876-195">В этом расположении параметр **path** не требуется для `Get-Help` получения справки, относящейся к поставщику.</span><span class="sxs-lookup"><span data-stu-id="17876-195">From that location, the **Path** parameter isn't needed for `Get-Help` to get the provider-specific help.</span></span>

```powershell
Get-Help Get-Item -Path SQLSERVER:\DataCollection
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

```powershell
Set-Location SQLSERVER:\DataCollection
SQLSERVER:\DataCollection> Get-Help Get-Item
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

### <span data-ttu-id="17876-196">Пример 12. Отображение справки для сценария</span><span class="sxs-lookup"><span data-stu-id="17876-196">Example 12: Display help for a script</span></span>

<span data-ttu-id="17876-197">В этом примере возвращается Справка для `MyScript.ps1 script` .</span><span class="sxs-lookup"><span data-stu-id="17876-197">This example gets help for the `MyScript.ps1 script`.</span></span> <span data-ttu-id="17876-198">Сведения о том, как написать справку по функциям и сценариям, см. в разделе [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="17876-198">For information about how to write help for your functions and scripts, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span></span>

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## <span data-ttu-id="17876-199">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="17876-199">PARAMETERS</span></span>

### <span data-ttu-id="17876-200">-Category</span><span class="sxs-lookup"><span data-stu-id="17876-200">-Category</span></span>

<span data-ttu-id="17876-201">Выводит справку только для элементов, относящихся к указанной категории, и их псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="17876-201">Displays help only for items in the specified category and their aliases.</span></span> <span data-ttu-id="17876-202">Концептуальные статьи находятся в категории **HelpFile** .</span><span class="sxs-lookup"><span data-stu-id="17876-202">Conceptual articles are in the **HelpFile** category.</span></span>

<span data-ttu-id="17876-203">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="17876-203">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="17876-204">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="17876-204">Alias</span></span>
- <span data-ttu-id="17876-205">Командлет</span><span class="sxs-lookup"><span data-stu-id="17876-205">Cmdlet</span></span>
- <span data-ttu-id="17876-206">Поставщик</span><span class="sxs-lookup"><span data-stu-id="17876-206">Provider</span></span>
- <span data-ttu-id="17876-207">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="17876-207">General</span></span>
- <span data-ttu-id="17876-208">ВОПРОСЫ И ОТВЕТЫ</span><span class="sxs-lookup"><span data-stu-id="17876-208">FAQ</span></span>
- <span data-ttu-id="17876-209">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="17876-209">Glossary</span></span>
- <span data-ttu-id="17876-210">HelpFile</span><span class="sxs-lookup"><span data-stu-id="17876-210">HelpFile</span></span>
- <span data-ttu-id="17876-211">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="17876-211">ScriptCommand</span></span>
- <span data-ttu-id="17876-212">Компонент</span><span class="sxs-lookup"><span data-stu-id="17876-212">Function</span></span>
- <span data-ttu-id="17876-213">Filter</span><span class="sxs-lookup"><span data-stu-id="17876-213">Filter</span></span>
- <span data-ttu-id="17876-214">екстерналскрипт</span><span class="sxs-lookup"><span data-stu-id="17876-214">ExternalScript</span></span>
- <span data-ttu-id="17876-215">Все</span><span class="sxs-lookup"><span data-stu-id="17876-215">All</span></span>
- <span data-ttu-id="17876-216">дефаулселп</span><span class="sxs-lookup"><span data-stu-id="17876-216">DefaultHelp</span></span>
- <span data-ttu-id="17876-217">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="17876-217">Workflow</span></span>
- <span data-ttu-id="17876-218">DscResource</span><span class="sxs-lookup"><span data-stu-id="17876-218">DscResource</span></span>
- <span data-ttu-id="17876-219">Класс</span><span class="sxs-lookup"><span data-stu-id="17876-219">Class</span></span>
- <span data-ttu-id="17876-220">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="17876-220">Configuration</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Alias, Cmdlet, Provider, General, FAQ, Glossary, HelpFile, ScriptCommand, Function, Filter, ExternalScript, All, DefaultHelp, Workflow, DscResource, Class, Configuration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17876-221">-Component</span><span class="sxs-lookup"><span data-stu-id="17876-221">-Component</span></span>

<span data-ttu-id="17876-222">Отображает команды с указанным значением компонента, например **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="17876-222">Displays commands with the specified component value, such as **Exchange** .</span></span> <span data-ttu-id="17876-223">Введите название компонента.</span><span class="sxs-lookup"><span data-stu-id="17876-223">Enter a component name.</span></span>
<span data-ttu-id="17876-224">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="17876-224">Wildcard characters are permitted.</span></span> <span data-ttu-id="17876-225">Этот параметр не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="17876-225">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="17876-226">-Detailed</span><span class="sxs-lookup"><span data-stu-id="17876-226">-Detailed</span></span>

<span data-ttu-id="17876-227">Добавляет описания параметров и и примеры к основным справочным сведениям.</span><span class="sxs-lookup"><span data-stu-id="17876-227">Adds parameter descriptions and examples to the basic help display.</span></span> <span data-ttu-id="17876-228">Этот параметр эффективен, только если файлы справки установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17876-228">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="17876-229">Он не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="17876-229">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetailedView
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17876-230">-Examples</span><span class="sxs-lookup"><span data-stu-id="17876-230">-Examples</span></span>

<span data-ttu-id="17876-231">Выводит только имя, краткий обзор и параметры.</span><span class="sxs-lookup"><span data-stu-id="17876-231">Displays only the name, synopsis, and examples.</span></span> <span data-ttu-id="17876-232">Чтобы отобразить только примеры, введите `(Get-Help \<cmdlet-name\>).Examples` .</span><span class="sxs-lookup"><span data-stu-id="17876-232">To display only the examples, type `(Get-Help \<cmdlet-name\>).Examples`.</span></span>

<span data-ttu-id="17876-233">Этот параметр эффективен, только если файлы справки установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17876-233">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="17876-234">Он не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="17876-234">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Examples
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17876-235">-Full</span><span class="sxs-lookup"><span data-stu-id="17876-235">-Full</span></span>

<span data-ttu-id="17876-236">Отображает всю статью справки для командлета.</span><span class="sxs-lookup"><span data-stu-id="17876-236">Displays the entire help article for a cmdlet.</span></span> <span data-ttu-id="17876-237">**Полная** включает описания параметров и атрибуты, примеры, типы входных и выходных объектов, а также дополнительные примечания.</span><span class="sxs-lookup"><span data-stu-id="17876-237">**Full** includes parameter descriptions and attributes, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="17876-238">Этот параметр эффективен, только если файлы справки установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17876-238">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="17876-239">Он не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="17876-239">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersView
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17876-240">-Functionality</span><span class="sxs-lookup"><span data-stu-id="17876-240">-Functionality</span></span>

<span data-ttu-id="17876-241">Выводит справку по элементам с указанными функциями.</span><span class="sxs-lookup"><span data-stu-id="17876-241">Displays help for items with the specified functionality.</span></span> <span data-ttu-id="17876-242">Введите функцию.</span><span class="sxs-lookup"><span data-stu-id="17876-242">Enter the functionality.</span></span> <span data-ttu-id="17876-243">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="17876-243">Wildcard characters are permitted.</span></span> <span data-ttu-id="17876-244">Этот параметр не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="17876-244">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="17876-245">-Name</span><span class="sxs-lookup"><span data-stu-id="17876-245">-Name</span></span>

<span data-ttu-id="17876-246">Возвращает справку по указанной команде или понятию.</span><span class="sxs-lookup"><span data-stu-id="17876-246">Gets help about the specified command or concept.</span></span> <span data-ttu-id="17876-247">Введите имя командлета, функции, поставщика, скрипта или рабочего процесса, например `Get-Member` , имя концептуальной статьи, например `about_Objects` , или псевдоним, например `ls` .</span><span class="sxs-lookup"><span data-stu-id="17876-247">Enter the name of a cmdlet, function, provider, script, or workflow, such as `Get-Member`, a conceptual article name, such as `about_Objects`, or an alias, such as `ls`.</span></span> <span data-ttu-id="17876-248">Подстановочные знаки допускаются в именах командлетов и поставщиков, но нельзя использовать подстановочные знаки для поиска имен справочных статей по функциям и сценариев.</span><span class="sxs-lookup"><span data-stu-id="17876-248">Wildcard characters are permitted in cmdlet and provider names, but you can't use wildcard characters to find the names of function help and script help articles.</span></span>

<span data-ttu-id="17876-249">Чтобы получить справку для скрипта, который не находится по пути, указанному в `$env:Path` переменной среды, введите путь и имя файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="17876-249">To get help for a script that isn't located in a path that's listed in the `$env:Path` environment variable, type the script's path and file name.</span></span>

<span data-ttu-id="17876-250">Если ввести точное имя статьи справки, `Get-Help` отобразится ее содержимое.</span><span class="sxs-lookup"><span data-stu-id="17876-250">If you enter the exact name of a help article, `Get-Help` displays the article contents.</span></span>

<span data-ttu-id="17876-251">Если ввести слово или слово, которое отображается в нескольких заголовках справочной статьи, `Get-Help` отображается список соответствующих заголовков.</span><span class="sxs-lookup"><span data-stu-id="17876-251">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span>

<span data-ttu-id="17876-252">При вводе любого текста, который не соответствует заголовкам статей справки, `Get-Help` отображается список статей, содержащих этот текст в их содержимом.</span><span class="sxs-lookup"><span data-stu-id="17876-252">If you enter any text that doesn't match any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="17876-253">Названия концептуальных статей, например `about_Objects` , должны быть указаны на английском языке даже в версиях PowerShell, отличных от английского.</span><span class="sxs-lookup"><span data-stu-id="17876-253">The names of conceptual articles, such as `about_Objects`, must be entered in English, even in non-English versions of PowerShell.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="17876-254">-Online</span><span class="sxs-lookup"><span data-stu-id="17876-254">-Online</span></span>

<span data-ttu-id="17876-255">Отображает интерактивную версию статьи справки в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17876-255">Displays the online version of a help article in the default browser.</span></span> <span data-ttu-id="17876-256">Этот параметр допустим только для статей справки по командлетам, функциям, рабочим процессам и сценариям.</span><span class="sxs-lookup"><span data-stu-id="17876-256">This parameter is valid only for cmdlet, function, workflow, and script help articles.</span></span> <span data-ttu-id="17876-257">**Online** `Get-Help` В удаленном сеансе нельзя использовать параметр Online.</span><span class="sxs-lookup"><span data-stu-id="17876-257">You can't use the **Online** parameter with `Get-Help` in a remote session.</span></span>

<span data-ttu-id="17876-258">Сведения о поддержке этой функции в справочных статьях, которые вы пишете, см. в разделах [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), [поддержка справки в Интернете](/powershell/scripting/developer/module/supporting-online-help)и [написание справки по командлетам PowerShell](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="17876-258">For information about supporting this feature in help articles that you write, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help), and [Writing Help for PowerShell Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17876-259">-Parameter</span><span class="sxs-lookup"><span data-stu-id="17876-259">-Parameter</span></span>

<span data-ttu-id="17876-260">Выводит только подробное описание указанных параметров.</span><span class="sxs-lookup"><span data-stu-id="17876-260">Displays only the detailed descriptions of the specified parameters.</span></span> <span data-ttu-id="17876-261">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="17876-261">Wildcards are permitted.</span></span> <span data-ttu-id="17876-262">Этот параметр не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="17876-262">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="17876-263">-Path</span><span class="sxs-lookup"><span data-stu-id="17876-263">-Path</span></span>

<span data-ttu-id="17876-264">Возвращает справку с описанием того, как командлет работает по указанному пути к поставщику.</span><span class="sxs-lookup"><span data-stu-id="17876-264">Gets help that explains how the cmdlet works in the specified provider path.</span></span> <span data-ttu-id="17876-265">Введите путь к поставщику PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17876-265">Enter a PowerShell provider path.</span></span>

<span data-ttu-id="17876-266">Этот параметр возвращает настраиваемую версию статьи справки по командлету, в которой объясняется, как работает командлет в указанном пути поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17876-266">This parameter gets a customized version of a cmdlet help article that explains how the cmdlet works in the specified PowerShell provider path.</span></span> <span data-ttu-id="17876-267">Этот параметр действует только для справки о командлете поставщика и только в том случае, если поставщик содержит пользовательскую версию статьи справки командлета поставщика в файле справки.</span><span class="sxs-lookup"><span data-stu-id="17876-267">This parameter is effective only for help about a provider cmdlet and only when the provider includes a custom version of the provider cmdlet help article in its help file.</span></span> <span data-ttu-id="17876-268">Для использования этого параметра установите файл справки для модуля, включающего поставщик.</span><span class="sxs-lookup"><span data-stu-id="17876-268">To use this parameter, install the help file for the module that includes the provider.</span></span>

<span data-ttu-id="17876-269">Чтобы просмотреть справку по пользовательскому командлету для пути к поставщику, перейдите по пути поставщика и введите `Get-Help` команду или в любом расположении пути, чтобы указать путь к поставщику, с помощью параметра **path** в `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="17876-269">To see the custom cmdlet help for a provider path, go to the provider path location and enter a `Get-Help` command or, from any path location, use the **Path** parameter of `Get-Help` to specify the provider path.</span></span> <span data-ttu-id="17876-270">Можно также найти справку по настраиваемому командлету в Интернете в разделе справки по поставщику статьи справки.</span><span class="sxs-lookup"><span data-stu-id="17876-270">You can also find custom cmdlet help online in the provider help section of the help articles.</span></span>

<span data-ttu-id="17876-271">Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](./About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="17876-271">For more information about PowerShell providers, see [about_Providers](./About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="17876-272">-Role</span><span class="sxs-lookup"><span data-stu-id="17876-272">-Role</span></span>

<span data-ttu-id="17876-273">Выводит справку, настроенную для указанной роли пользователя.</span><span class="sxs-lookup"><span data-stu-id="17876-273">Displays help customized for the specified user role.</span></span> <span data-ttu-id="17876-274">Введите роль.</span><span class="sxs-lookup"><span data-stu-id="17876-274">Enter a role.</span></span> <span data-ttu-id="17876-275">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="17876-275">Wildcard characters are permitted.</span></span>

<span data-ttu-id="17876-276">Введите роль, которую пользователь имеет в организации.</span><span class="sxs-lookup"><span data-stu-id="17876-276">Enter the role that the user plays in an organization.</span></span> <span data-ttu-id="17876-277">Для некоторых командлетов в файлах справки содержится разный текст в зависимости от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="17876-277">Some cmdlets display different text in their help files based on the value of this parameter.</span></span> <span data-ttu-id="17876-278">Этот параметр не влияет на справку по основным командлетам.</span><span class="sxs-lookup"><span data-stu-id="17876-278">This parameter has no effect on help for the core cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="17876-279">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="17876-279">CommonParameters</span></span>

<span data-ttu-id="17876-280">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="17876-280">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="17876-281">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="17876-281">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="17876-282">Входные данные</span><span class="sxs-lookup"><span data-stu-id="17876-282">INPUTS</span></span>

### <span data-ttu-id="17876-283">Нет</span><span class="sxs-lookup"><span data-stu-id="17876-283">None</span></span>

<span data-ttu-id="17876-284">Вы не можете отправить объекты по конвейеру в `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="17876-284">You can't send objects down the pipeline to `Get-Help`.</span></span>

## <span data-ttu-id="17876-285">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="17876-285">OUTPUTS</span></span>

### <span data-ttu-id="17876-286">ExtendedCmdletHelpInfo</span><span class="sxs-lookup"><span data-stu-id="17876-286">ExtendedCmdletHelpInfo</span></span>

<span data-ttu-id="17876-287">При выполнении `Get-Help` команды, не имеющей файла справки, `Get-Help` возвращается объект **екстендедкмдлеселпинфо** , представляющий автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="17876-287">If you run `Get-Help` on a command that doesn't have a help file, `Get-Help` returns an **ExtendedCmdletHelpInfo** object that represents autogenerated help.</span></span>

### <span data-ttu-id="17876-288">System.String</span><span class="sxs-lookup"><span data-stu-id="17876-288">System.String</span></span>

<span data-ttu-id="17876-289">Если вы получаете общую справочную статью, `Get-Help` возвращает ее в виде строки.</span><span class="sxs-lookup"><span data-stu-id="17876-289">If you get a conceptual help article, `Get-Help` returns it as a string.</span></span>

### <span data-ttu-id="17876-290">MamlCommandHelpInfo</span><span class="sxs-lookup"><span data-stu-id="17876-290">MamlCommandHelpInfo</span></span>

<span data-ttu-id="17876-291">При получении команды, имеющей файл справки, `Get-Help` возвращает объект **MamlCommandHelpInfo** .</span><span class="sxs-lookup"><span data-stu-id="17876-291">If you get a command that has a help file, `Get-Help` returns a **MamlCommandHelpInfo** object.</span></span>

## <span data-ttu-id="17876-292">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="17876-292">NOTES</span></span>

<span data-ttu-id="17876-293">PowerShell 3,0 не включает файлы справки.</span><span class="sxs-lookup"><span data-stu-id="17876-293">PowerShell 3.0 doesn't include help files.</span></span> <span data-ttu-id="17876-294">Чтобы скачать и установить файлы справки, которые `Get-Help` выполняют чтение, используйте `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="17876-294">To download and install the help files that `Get-Help` reads, use the `Update-Help` cmdlet.</span></span> <span data-ttu-id="17876-295">С помощью `Update-Help` командлета можно скачать и установить файлы справки для основных команд, которые входят в состав PowerShell, а также для всех устанавливаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="17876-295">You can use the `Update-Help` cmdlet to download and install help files for the core commands that come with PowerShell and for any modules that you install.</span></span> <span data-ttu-id="17876-296">С его помощью можно также обновлять файлы справки на компьютере, чтобы они всегда были актуальны.</span><span class="sxs-lookup"><span data-stu-id="17876-296">You can also use it to update the help files so that the help on your computer is never outdated.</span></span>

<span data-ttu-id="17876-297">Кроме того, вы можете ознакомиться с справочными статьями, посвященными командам PowerShell Online, начиная с [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="17876-297">You can also read the help articles about the commands that come with PowerShell online starting at [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

<span data-ttu-id="17876-298">`Get-Help` Отображает справку в наборе языкового стандарта для операционной системы Windows или на резервном языке для этого языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="17876-298">`Get-Help` displays help in the locale set for the Windows operating system or in the fallback language for that locale.</span></span> <span data-ttu-id="17876-299">Если у вас нет файлов справки для основного или резервного языкового стандарта, `Get-Help` ведет себя так, как если бы на компьютере не было файлов справки.</span><span class="sxs-lookup"><span data-stu-id="17876-299">If you don't have help files for the primary or fallback locale, `Get-Help` behaves as if there are no help files on the computer.</span></span> <span data-ttu-id="17876-300">Чтобы получить справку для другого языкового стандарта, измените параметры с помощью **области** и **языка** на панели управления.</span><span class="sxs-lookup"><span data-stu-id="17876-300">To get help for a different locale, use **Region** and **Language** in Control Panel to change the settings.</span></span> <span data-ttu-id="17876-301">В Windows 10 **Параметры** , **время & язык** .</span><span class="sxs-lookup"><span data-stu-id="17876-301">On Windows 10, **Settings** , **Time & Language** .</span></span>

<span data-ttu-id="17876-302">Полный обзор справки включает таблицу сведений о параметрах.</span><span class="sxs-lookup"><span data-stu-id="17876-302">The full view of help includes a table of information about the parameters.</span></span> <span data-ttu-id="17876-303">В таблице содержатся указанные ниже поля.</span><span class="sxs-lookup"><span data-stu-id="17876-303">The table includes the following fields:</span></span>

- <span data-ttu-id="17876-304">**Обязательно** .</span><span class="sxs-lookup"><span data-stu-id="17876-304">**Required** .</span></span> <span data-ttu-id="17876-305">Показывает, является ли параметр необходимым (true) или необязательным (false).</span><span class="sxs-lookup"><span data-stu-id="17876-305">Indicates whether the parameter is required (true) or optional (false).</span></span>

- <span data-ttu-id="17876-306">**Расположение** .</span><span class="sxs-lookup"><span data-stu-id="17876-306">**Position** .</span></span> <span data-ttu-id="17876-307">Указывает, является ли параметр именованным или позиционированным (числовым).</span><span class="sxs-lookup"><span data-stu-id="17876-307">Indicates whether the parameter is named or positional (numeric).</span></span> <span data-ttu-id="17876-308">Позиционные параметры должны появляться в указанном месте команды.</span><span class="sxs-lookup"><span data-stu-id="17876-308">Positional parameters must appear in a specified place in the command.</span></span>

- <span data-ttu-id="17876-309">**С именем** указывает, что имя параметра является обязательным, но параметр может находиться в любом месте команды.</span><span class="sxs-lookup"><span data-stu-id="17876-309">**Named** indicates that the parameter name is required, but that the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="17876-310">**Numeric** указывает, что имя параметра является необязательным, но если имя не указано, параметр должен находиться в месте, указанном в номере.</span><span class="sxs-lookup"><span data-stu-id="17876-310">**Numeric** indicates that the parameter name is optional, but when the name is omitted, the parameter must be in the place specified by the number.</span></span> <span data-ttu-id="17876-311">Например, `2` указывает, что если имя параметра не указано, параметр должен быть вторым или единственным безымянным параметром в команде.</span><span class="sxs-lookup"><span data-stu-id="17876-311">For example, `2` indicates that when the parameter name is omitted, the parameter must be the second or only unnamed parameter in the command.</span></span> <span data-ttu-id="17876-312">Если используется имя параметра, параметр может располагаться в любом месте команды.</span><span class="sxs-lookup"><span data-stu-id="17876-312">When the parameter name is used, the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="17876-313">**Значение по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="17876-313">**Default value** .</span></span> <span data-ttu-id="17876-314">Значение параметра или поведение по умолчанию, используемое PowerShell, если параметр не включен в команду.</span><span class="sxs-lookup"><span data-stu-id="17876-314">The parameter value or default behavior that PowerShell uses if you don't include the parameter in the command.</span></span>

- <span data-ttu-id="17876-315">Принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="17876-315">Accepts pipeline input.</span></span> <span data-ttu-id="17876-316">Указывает, можно ли (true) или нет (false) отправку объектов в параметр через конвейер.</span><span class="sxs-lookup"><span data-stu-id="17876-316">Indicates whether you can (true) or can't (false) send objects to the parameter through a pipeline.</span></span> <span data-ttu-id="17876-317">**По имени свойства** означает, что конвейерный объект должен иметь свойство, имя которого совпадает с именем параметра.</span><span class="sxs-lookup"><span data-stu-id="17876-317">**By Property Name** means that the pipelined object must have a property that has the same name as the parameter name.</span></span>

- <span data-ttu-id="17876-318">**Принимает подстановочные знаки** .</span><span class="sxs-lookup"><span data-stu-id="17876-318">**Accepts wildcard characters** .</span></span> <span data-ttu-id="17876-319">Указывает, может ли значение параметра содержать подстановочные знаки, например звездочку ( `*` ) или вопросительный знак ( `?` ).</span><span class="sxs-lookup"><span data-stu-id="17876-319">Indicates whether the value of a parameter can include wildcard characters, such as an asterisk (`*`) or question mark (`?`).</span></span>

## <span data-ttu-id="17876-320">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="17876-320">RELATED LINKS</span></span>

[<span data-ttu-id="17876-321">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="17876-321">about_Command_Syntax</span></span>](About/about_Command_Syntax.md)

[<span data-ttu-id="17876-322">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="17876-322">about_Comment_Based_Help</span></span>](./About/about_Comment_Based_Help.md)

[<span data-ttu-id="17876-323">Get-Command</span><span class="sxs-lookup"><span data-stu-id="17876-323">Get-Command</span></span>](Get-Command.md)

[<span data-ttu-id="17876-324">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="17876-324">Supporting Updatable Help</span></span>](/powershell/scripting/developer/module/supporting-updatable-help)

[<span data-ttu-id="17876-325">Update-Help</span><span class="sxs-lookup"><span data-stu-id="17876-325">Update-Help</span></span>](Update-Help.md)

[<span data-ttu-id="17876-326">Написание разделов справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="17876-326">Writing Comment-Based Help Topics</span></span>](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[<span data-ttu-id="17876-327">Написание справки для командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="17876-327">Writing Help for PowerShell Cmdlets</span></span>](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)
