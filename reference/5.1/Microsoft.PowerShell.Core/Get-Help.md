---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: a9a7aa7730d920bb78e0ae64daa50e5a28921163
ms.sourcegitcommit: b7ff031a12afd04910aeb98345ebee92f5845b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "93230166"
---
# <span data-ttu-id="9001d-103">Get-Help</span><span class="sxs-lookup"><span data-stu-id="9001d-103">Get-Help</span></span>

## <span data-ttu-id="9001d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9001d-104">SYNOPSIS</span></span>
<span data-ttu-id="9001d-105">Отображает сведения о командах и концепциях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9001d-105">Displays information about PowerShell commands and concepts.</span></span>

## <span data-ttu-id="9001d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9001d-106">SYNTAX</span></span>

### <span data-ttu-id="9001d-107">AllUsersView (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9001d-107">AllUsersView (Default)</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [-Full] [<CommonParameters>]
```

### <span data-ttu-id="9001d-108">DetailedView</span><span class="sxs-lookup"><span data-stu-id="9001d-108">DetailedView</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Detailed [<CommonParameters>]
```

### <span data-ttu-id="9001d-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="9001d-109">Examples</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Examples [<CommonParameters>]
```

### <span data-ttu-id="9001d-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="9001d-110">Parameters</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Parameter <String> [<CommonParameters>]
```

### <span data-ttu-id="9001d-111">Миграция по сети</span><span class="sxs-lookup"><span data-stu-id="9001d-111">Online</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Online [<CommonParameters>]
```

### <span data-ttu-id="9001d-112">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="9001d-112">ShowWindow</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -ShowWindow [<CommonParameters>]
```

## <span data-ttu-id="9001d-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9001d-113">DESCRIPTION</span></span>

<span data-ttu-id="9001d-114">`Get-Help`Командлет отображает сведения об основных понятиях и командах PowerShell, включая командлеты, функции, команды модель CIM (CIM), рабочие процессы, поставщики, псевдонимы и скрипты.</span><span class="sxs-lookup"><span data-stu-id="9001d-114">The `Get-Help` cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.</span></span>

<span data-ttu-id="9001d-115">Чтобы получить справку по командлету PowerShell, введите, `Get-Help` за которым следует имя командлета, например: `Get-Help Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="9001d-115">To get help for a PowerShell cmdlet, type `Get-Help` followed by the cmdlet name, such as: `Get-Help Get-Process`.</span></span>

<span data-ttu-id="9001d-116">Основные статьи справки в PowerShell начинаются с **about_** , например **about_Comparison_Operators** .</span><span class="sxs-lookup"><span data-stu-id="9001d-116">Conceptual help articles in PowerShell begin with **about_** , such as **about_Comparison_Operators** .</span></span> <span data-ttu-id="9001d-117">Чтобы просмотреть все **about_** статьи, введите `Get-Help about_*` .</span><span class="sxs-lookup"><span data-stu-id="9001d-117">To see all **about_** articles, type `Get-Help about_*`.</span></span> <span data-ttu-id="9001d-118">Чтобы просмотреть определенную статью, введите `Get-Help about_<article-name>` , например `Get-Help about_Comparison_Operators` .</span><span class="sxs-lookup"><span data-stu-id="9001d-118">To see a particular article, type `Get-Help about_<article-name>`, such as `Get-Help about_Comparison_Operators`.</span></span>

<span data-ttu-id="9001d-119">Чтобы получить справку для поставщика PowerShell, введите, `Get-Help` за которым следует имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="9001d-119">To get help for a PowerShell provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="9001d-120">Например, чтобы получить справку для поставщика сертификатов, введите `Get-Help Certificate` .</span><span class="sxs-lookup"><span data-stu-id="9001d-120">For example, to get help for the Certificate provider, type `Get-Help Certificate`.</span></span>

<span data-ttu-id="9001d-121">Можно также ввести `help` или `man` , который отображает один экран текста за раз.</span><span class="sxs-lookup"><span data-stu-id="9001d-121">You can also type `help` or `man`, which displays one screen of text at a time.</span></span> <span data-ttu-id="9001d-122">Или, `<cmdlet-name> -?` , то же, что и `Get-Help` , но работает только для командлетов.</span><span class="sxs-lookup"><span data-stu-id="9001d-122">Or, `<cmdlet-name> -?`, that is identical to `Get-Help`, but only works for cmdlets.</span></span>

<span data-ttu-id="9001d-123">`Get-Help` Возвращает содержимое справки, которое отображается в файлах справки на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9001d-123">`Get-Help` gets the help content that it displays from help files on your computer.</span></span> <span data-ttu-id="9001d-124">Без файлов справки `Get-Help` отображает только основные сведения о командлетах.</span><span class="sxs-lookup"><span data-stu-id="9001d-124">Without the help files, `Get-Help` displays only basic information about cmdlets.</span></span> <span data-ttu-id="9001d-125">К некоторым модулям PowerShell относятся файлы справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-125">Some PowerShell modules include help files.</span></span> <span data-ttu-id="9001d-126">Начиная с версии PowerShell 3,0 модули, которые входят в состав операционной системы Windows, не включают файлы справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-126">Beginning in PowerShell 3.0, the modules that come with the Windows operating system don't include help files.</span></span> <span data-ttu-id="9001d-127">Чтобы скачать или обновить файлы справки для модуля в PowerShell 3,0, используйте `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="9001d-127">To download or update the help files for a module in PowerShell 3.0, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="9001d-128">Можно также просмотреть справочные документы по PowerShell в Интернете в Документация Майкрософт. Чтобы получить оперативную версию файла справки, используйте параметр **Online** , например: `Get-Help Get-Process -Online` .</span><span class="sxs-lookup"><span data-stu-id="9001d-128">You can also view the PowerShell help documents online in the Microsoft Docs. To get the online version of a help file, use the **Online** parameter, such as: `Get-Help Get-Process -Online`.</span></span> <span data-ttu-id="9001d-129">Сведения о том, как прочитать всю документацию по PowerShell, см. в документации по Документация Майкрософт [PowerShell](/powershell).</span><span class="sxs-lookup"><span data-stu-id="9001d-129">To read all the PowerShell documentation, see the Microsoft Docs [PowerShell Documentation](/powershell).</span></span>

<span data-ttu-id="9001d-130">Если ввести `Get-Help` , за которым следует точное имя статьи справки, или слово, уникальное для статьи справки, `Get-Help` отображает содержимое статьи.</span><span class="sxs-lookup"><span data-stu-id="9001d-130">If you type `Get-Help` followed by the exact name of a help article, or by a word unique to a help article, `Get-Help` displays the article's content.</span></span> <span data-ttu-id="9001d-131">Если указать точное имя псевдонима команды, `Get-Help` выводит справку по исходной команде.</span><span class="sxs-lookup"><span data-stu-id="9001d-131">If you specify the exact name of a command alias, `Get-Help` displays the help for the original command.</span></span> <span data-ttu-id="9001d-132">Если ввести слово или слово, которое отображается в нескольких заголовках справочной статьи, `Get-Help` отображается список соответствующих заголовков.</span><span class="sxs-lookup"><span data-stu-id="9001d-132">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span> <span data-ttu-id="9001d-133">При вводе любого текста, который не отображается в заголовках статей справки, `Get-Help` отображается список статей, содержащих этот текст в их содержимом.</span><span class="sxs-lookup"><span data-stu-id="9001d-133">If you enter any text that doesn't appear in any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="9001d-134">`Get-Help` может получить статьи справки для всех поддерживаемых языков и языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="9001d-134">`Get-Help` can get help articles for all supported languages and locales.</span></span> <span data-ttu-id="9001d-135">`Get-Help` сначала ищет файлы справки в наборе языкового стандарта для Windows, затем в родительском языковом стандарте, например в **PT** для **pt-br** , а затем в резервном языковом стандарте.</span><span class="sxs-lookup"><span data-stu-id="9001d-135">`Get-Help` first looks for help files in the locale set for Windows, then in the parent locale, such as **pt** for **pt-BR** , and then in a fallback locale.</span></span> <span data-ttu-id="9001d-136">Начиная с версии PowerShell 3,0, если `Get-Help` не удается найти справку по резервному языку, он ищет статьи справки на английском языке, **en-US** , прежде чем возвращает сообщение об ошибке или отображает автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="9001d-136">Beginning in PowerShell 3.0, if `Get-Help` doesn't find help in the fallback locale, it looks for help articles in English, **en-US** , before it returns an error message or displaying autogenerated help.</span></span>

<span data-ttu-id="9001d-137">Сведения о символах, `Get-Help` отображаемых на схеме синтаксиса команды, см. в разделе [about_Command_Syntax](./About/about_Command_Syntax.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-137">For information about the symbols that `Get-Help` displays in the command syntax diagram, see [about_Command_Syntax](./About/about_Command_Syntax.md).</span></span>
<span data-ttu-id="9001d-138">Дополнительные сведения об атрибутах параметров, таких как **Required** и **Disposition** , см. в разделе [about_Parameters](./About/about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-138">For information about parameter attributes, such as **Required** and **Position** , see [about_Parameters](./About/about_Parameters.md).</span></span>

>[!NOTE]
> <span data-ttu-id="9001d-139">В PowerShell 3,0 и PowerShell 4,0 `Get-Help` не удается найти **сведения о** статьях в модулях, если модуль не импортирован в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="9001d-139">In PowerShell 3.0 and PowerShell 4.0, `Get-Help` can't find **About** articles in modules unless the module is imported into the current session.</span></span> <span data-ttu-id="9001d-140">Это известная проблема.</span><span class="sxs-lookup"><span data-stu-id="9001d-140">This is a known issue.</span></span> <span data-ttu-id="9001d-141">Чтобы получить **сведения о** статьях в модуле, импортируйте модуль либо с помощью `Import-Module` командлета, либо путем запуска командлета, который включается в модуль.</span><span class="sxs-lookup"><span data-stu-id="9001d-141">To get **About** articles in a module, import the module, either by using the `Import-Module` cmdlet or by running a cmdlet that's included in the module.</span></span>

## <span data-ttu-id="9001d-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="9001d-142">EXAMPLES</span></span>

### <span data-ttu-id="9001d-143">Пример 1. Отображение основных справочных сведений о командлете</span><span class="sxs-lookup"><span data-stu-id="9001d-143">Example 1: Display basic help information about a cmdlet</span></span>

<span data-ttu-id="9001d-144">В этих примерах отображаются основные справочные сведения о `Format-Table` командлете.</span><span class="sxs-lookup"><span data-stu-id="9001d-144">These examples display basic help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

<span data-ttu-id="9001d-145">`Get-Help <cmdlet-name>` — Это простейший синтаксис командлета по умолчанию `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="9001d-145">`Get-Help <cmdlet-name>` is the simplest and default syntax of `Get-Help` cmdlet.</span></span> <span data-ttu-id="9001d-146">Параметр **Name** можно опустить.</span><span class="sxs-lookup"><span data-stu-id="9001d-146">You can omit the **Name** parameter.</span></span>

<span data-ttu-id="9001d-147">Синтаксис `<cmdlet-name> -?` работает только для командлетов.</span><span class="sxs-lookup"><span data-stu-id="9001d-147">The syntax `<cmdlet-name> -?` works only for cmdlets.</span></span>

### <span data-ttu-id="9001d-148">Пример 2. Отображение основных сведений по одной странице за раз</span><span class="sxs-lookup"><span data-stu-id="9001d-148">Example 2: Display basic information one page at a time</span></span>

<span data-ttu-id="9001d-149">В этих примерах отображаются основные справочные сведения о `Format-Table` командлете по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="9001d-149">These examples display basic help information about the `Format-Table` cmdlet one page at a time.</span></span>

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

<span data-ttu-id="9001d-150">`help` — Это функция, которая выполняет `Get-Help` командлет внутренне и отображает результат по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="9001d-150">`help` is a function that runs `Get-Help` cmdlet internally and displays the result one page at a time.</span></span>

<span data-ttu-id="9001d-151">`man` псевдоним для `help` функции.</span><span class="sxs-lookup"><span data-stu-id="9001d-151">`man` is an alias for the `help` function.</span></span>

<span data-ttu-id="9001d-152">`Get-Help Format-Table` отправляет объект вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9001d-152">`Get-Help Format-Table` sends the object down the pipeline.</span></span> <span data-ttu-id="9001d-153">`Out-Host -Paging` Получает выходные данные из конвейера и отображает их по одной странице за раз.</span><span class="sxs-lookup"><span data-stu-id="9001d-153">`Out-Host -Paging` receives the output from the pipeline and displays it one page at a time.</span></span> <span data-ttu-id="9001d-154">Дополнительные сведения см. в разделе [Out-Host](Out-Host.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-154">For more information, see [Out-Host](Out-Host.md).</span></span>

### <span data-ttu-id="9001d-155">Пример 3. Отображение дополнительных сведений для командлета</span><span class="sxs-lookup"><span data-stu-id="9001d-155">Example 3: Display more information for a cmdlet</span></span>

<span data-ttu-id="9001d-156">В этих примерах отображаются более подробные справочные сведения о `Format-Table` командлете.</span><span class="sxs-lookup"><span data-stu-id="9001d-156">These examples display more detailed help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

<span data-ttu-id="9001d-157">**Подробный** параметр отображает подробное представление статьи справки, включающее описание параметров и примеры.</span><span class="sxs-lookup"><span data-stu-id="9001d-157">The **Detailed** parameter displays the help article's detailed view that includes parameter descriptions and examples.</span></span>

<span data-ttu-id="9001d-158">Параметр **Full** отображает полное представление статьи справки, включающее описания параметров, примеры, типы входных и выходных объектов, а также дополнительные примечания.</span><span class="sxs-lookup"><span data-stu-id="9001d-158">The **Full** parameter displays the help article's full view that includes parameter descriptions, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="9001d-159">Параметры **Detailed** и **Full** действуют только для команд, в которых есть файлы справки, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9001d-159">The **Detailed** and **Full** parameters are effective only for the commands that have help files installed on the computer.</span></span> <span data-ttu-id="9001d-160">Параметры не вступают в силу для концептуальных ( **about_** ) справочных статей.</span><span class="sxs-lookup"><span data-stu-id="9001d-160">The parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="9001d-161">Пример 4. Отображение выбранных частей командлета с помощью параметров</span><span class="sxs-lookup"><span data-stu-id="9001d-161">Example 4: Display selected parts of a cmdlet by using parameters</span></span>

<span data-ttu-id="9001d-162">В этих примерах отображаются выбранные части `Format-Table` справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="9001d-162">These examples display selected portions of the `Format-Table` cmdlet help.</span></span>

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

<span data-ttu-id="9001d-163">Параметр " **примеры** " отображает разделы **имени** файла справки и **кратких** сведений, а также все примеры.</span><span class="sxs-lookup"><span data-stu-id="9001d-163">The **Examples** parameter displays the help file's **NAME** and **SYNOPSIS** sections, and all the Examples.</span></span> <span data-ttu-id="9001d-164">Нельзя указать пример числа, так как параметр **examples** является параметром Switch.</span><span class="sxs-lookup"><span data-stu-id="9001d-164">You can't specify an Example number because the **Examples** parameter is a switch parameter.</span></span>

<span data-ttu-id="9001d-165">Параметр **Parameter** отображает только описания указанных параметров.</span><span class="sxs-lookup"><span data-stu-id="9001d-165">The **Parameter** parameter displays only the descriptions of the specified parameters.</span></span> <span data-ttu-id="9001d-166">Если указать только `*` подстановочный знак звездочки (), будут выведены описания всех параметров.</span><span class="sxs-lookup"><span data-stu-id="9001d-166">If you specify only the asterisk (`*`) wildcard character, it displays the descriptions of all parameters.</span></span>
<span data-ttu-id="9001d-167">Если **параметр** указывает имя параметра, например **GroupBy** , отображается информация об этом параметре.</span><span class="sxs-lookup"><span data-stu-id="9001d-167">When **Parameter** specifies a parameter name such as **GroupBy** , information about that parameter is shown.</span></span>

<span data-ttu-id="9001d-168">Эти параметры не действуют для концептуальных ( **about_** ) статей справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-168">These parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="9001d-169">Пример 5. отображение интерактивной версии справки</span><span class="sxs-lookup"><span data-stu-id="9001d-169">Example 5: Display online version of help</span></span>

<span data-ttu-id="9001d-170">В этом примере отображается интерактивная версия статьи справки для `Format-Table` командлета в веб-браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9001d-170">This example displays the online version of the help article for the `Format-Table` cmdlet in your default web browser.</span></span>

```powershell
Get-Help Format-Table -Online
```

### <span data-ttu-id="9001d-171">Пример 6. Отображение справки по справочной системе</span><span class="sxs-lookup"><span data-stu-id="9001d-171">Example 6: Display help about the help system</span></span>

<span data-ttu-id="9001d-172">`Get-Help`Командлет без параметров отображает сведения о справочной системе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9001d-172">The `Get-Help` cmdlet without parameters displays information about the PowerShell help system.</span></span>

```powershell
Get-Help
```

### <span data-ttu-id="9001d-173">Пример 7. Отображение доступных справочных статей</span><span class="sxs-lookup"><span data-stu-id="9001d-173">Example 7: Display available help articles</span></span>

<span data-ttu-id="9001d-174">В этом примере отображается список всех справочных статей, доступных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9001d-174">This example displays a list of all help articles available on your computer.</span></span>

```powershell
Get-Help *
```

### <span data-ttu-id="9001d-175">Пример 8. Отображение списка концептуальных статей</span><span class="sxs-lookup"><span data-stu-id="9001d-175">Example 8: Display a list of conceptual articles</span></span>

<span data-ttu-id="9001d-176">В этом примере отображается список концептуальных статей, входящих в состав справки по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9001d-176">This example displays a list of the conceptual articles included in PowerShell help.</span></span> <span data-ttu-id="9001d-177">Все эти статьи начинаются с символов **about_** .</span><span class="sxs-lookup"><span data-stu-id="9001d-177">All these articles begin with the characters **about_** .</span></span> <span data-ttu-id="9001d-178">Чтобы отобразить определенный файл справки, введите `Get-Help \<about_article-name\>` , например, `Get-Help about_Signing` .</span><span class="sxs-lookup"><span data-stu-id="9001d-178">To display a particular help file, type `Get-Help \<about_article-name\>`, for example, `Get-Help about_Signing`.</span></span>

<span data-ttu-id="9001d-179">Отображаются только основные статьи с файлами справки, установленными на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9001d-179">Only the conceptual articles that have help files installed on your computer are displayed.</span></span> <span data-ttu-id="9001d-180">Сведения о загрузке и установке файлов справки в PowerShell 3,0 см. в разделе [Update-Help](Update-Help.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-180">For information about downloading and installing help files in PowerShell 3.0, see [Update-Help](Update-Help.md).</span></span>

```powershell
Get-Help about_*
```

### <span data-ttu-id="9001d-181">Пример 9. Поиск слова в справке по командлету</span><span class="sxs-lookup"><span data-stu-id="9001d-181">Example 9: Search for a word in cmdlet help</span></span>

<span data-ttu-id="9001d-182">В этом примере показано, как выполнить поиск слова в статье справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="9001d-182">This example shows how to search for a word in a cmdlet help article.</span></span>

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

<span data-ttu-id="9001d-183">`Get-Help` использует параметр **Full** для получения справочных сведений для `Add-Member` .</span><span class="sxs-lookup"><span data-stu-id="9001d-183">`Get-Help` uses the **Full** parameter to get help information for `Add-Member`.</span></span> <span data-ttu-id="9001d-184">Объект **MamlCommandHelpInfo** отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9001d-184">The **MamlCommandHelpInfo** object is sent down the pipeline.</span></span> <span data-ttu-id="9001d-185">`Out-String` использует параметр **Stream** для преобразования объекта в строку.</span><span class="sxs-lookup"><span data-stu-id="9001d-185">`Out-String` uses the **Stream** parameter to convert the object into a string.</span></span> <span data-ttu-id="9001d-186">`Select-String` использует параметр **pattern** для поиска **Clixml** в строке.</span><span class="sxs-lookup"><span data-stu-id="9001d-186">`Select-String` uses the **Pattern** parameter to search the string for **Clixml** .</span></span>

### <span data-ttu-id="9001d-187">Пример 10. Отображение списка статей, содержащих слово</span><span class="sxs-lookup"><span data-stu-id="9001d-187">Example 10: Display a list of articles that include a word</span></span>

<span data-ttu-id="9001d-188">В этом примере отображается список статей, включающих **удаленное взаимодействие** по словам.</span><span class="sxs-lookup"><span data-stu-id="9001d-188">This example displays a list of articles that include the word **remoting** .</span></span>

<span data-ttu-id="9001d-189">При вводе слова, которое не отображается в заголовке статьи, `Get-Help` отображается список статей, содержащих это слово.</span><span class="sxs-lookup"><span data-stu-id="9001d-189">When you enter a word that doesn't appear in any article title, `Get-Help` displays a list of articles that include that word.</span></span>

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

### <span data-ttu-id="9001d-190">Пример 11. Отображение справки, относящейся к поставщику</span><span class="sxs-lookup"><span data-stu-id="9001d-190">Example 11: Display provider-specific help</span></span>

<span data-ttu-id="9001d-191">В этом примере показаны два способа получения справки, относящейся к поставщику `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="9001d-191">This example shows two ways of getting the provider-specific help for `Get-Item`.</span></span> <span data-ttu-id="9001d-192">Эти команды позволяют получить справку, в которой объясняется, как использовать `Get-Item` командлет в узле **коллекции** данных поставщика SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9001d-192">These commands get help that explains how to use the `Get-Item` cmdlet in the PowerShell SQL Server provider's **DataCollection** node.</span></span>

<span data-ttu-id="9001d-193">В первом примере используется параметр `Get-Help` **path** для указания пути поставщика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9001d-193">The first example uses the `Get-Help` **Path** parameter to specify the SQL Server provider's path.</span></span>
<span data-ttu-id="9001d-194">Так как путь поставщика указан, можно выполнить команду из любого расположения пути.</span><span class="sxs-lookup"><span data-stu-id="9001d-194">Because the provider's path is specified, you can run the command from any path location.</span></span>

<span data-ttu-id="9001d-195">Во втором примере используется `Set-Location` для перехода к пути поставщика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9001d-195">The second example uses `Set-Location` to navigate to the SQL Server provider's path.</span></span> <span data-ttu-id="9001d-196">В этом расположении параметр **path** не требуется для `Get-Help` получения справки, относящейся к поставщику.</span><span class="sxs-lookup"><span data-stu-id="9001d-196">From that location, the **Path** parameter isn't needed for `Get-Help` to get the provider-specific help.</span></span>

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

### <span data-ttu-id="9001d-197">Пример 12. Отображение справки для сценария</span><span class="sxs-lookup"><span data-stu-id="9001d-197">Example 12: Display help for a script</span></span>

<span data-ttu-id="9001d-198">В этом примере возвращается Справка для `MyScript.ps1 script` .</span><span class="sxs-lookup"><span data-stu-id="9001d-198">This example gets help for the `MyScript.ps1 script`.</span></span> <span data-ttu-id="9001d-199">Сведения о том, как написать справку по функциям и сценариям, см. в разделе [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-199">For information about how to write help for your functions and scripts, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span></span>

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## <span data-ttu-id="9001d-200">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9001d-200">PARAMETERS</span></span>

### <span data-ttu-id="9001d-201">-Category</span><span class="sxs-lookup"><span data-stu-id="9001d-201">-Category</span></span>

<span data-ttu-id="9001d-202">Выводит справку только для элементов, относящихся к указанной категории, и их псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="9001d-202">Displays help only for items in the specified category and their aliases.</span></span> <span data-ttu-id="9001d-203">Концептуальные статьи находятся в категории **HelpFile** .</span><span class="sxs-lookup"><span data-stu-id="9001d-203">Conceptual articles are in the **HelpFile** category.</span></span>

<span data-ttu-id="9001d-204">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9001d-204">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9001d-205">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="9001d-205">Alias</span></span>
- <span data-ttu-id="9001d-206">Командлет</span><span class="sxs-lookup"><span data-stu-id="9001d-206">Cmdlet</span></span>
- <span data-ttu-id="9001d-207">Поставщик</span><span class="sxs-lookup"><span data-stu-id="9001d-207">Provider</span></span>
- <span data-ttu-id="9001d-208">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="9001d-208">General</span></span>
- <span data-ttu-id="9001d-209">ВОПРОСЫ И ОТВЕТЫ</span><span class="sxs-lookup"><span data-stu-id="9001d-209">FAQ</span></span>
- <span data-ttu-id="9001d-210">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="9001d-210">Glossary</span></span>
- <span data-ttu-id="9001d-211">HelpFile</span><span class="sxs-lookup"><span data-stu-id="9001d-211">HelpFile</span></span>
- <span data-ttu-id="9001d-212">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="9001d-212">ScriptCommand</span></span>
- <span data-ttu-id="9001d-213">Компонент</span><span class="sxs-lookup"><span data-stu-id="9001d-213">Function</span></span>
- <span data-ttu-id="9001d-214">Filter</span><span class="sxs-lookup"><span data-stu-id="9001d-214">Filter</span></span>
- <span data-ttu-id="9001d-215">екстерналскрипт</span><span class="sxs-lookup"><span data-stu-id="9001d-215">ExternalScript</span></span>
- <span data-ttu-id="9001d-216">Все</span><span class="sxs-lookup"><span data-stu-id="9001d-216">All</span></span>
- <span data-ttu-id="9001d-217">дефаулселп</span><span class="sxs-lookup"><span data-stu-id="9001d-217">DefaultHelp</span></span>
- <span data-ttu-id="9001d-218">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="9001d-218">Workflow</span></span>
- <span data-ttu-id="9001d-219">DscResource</span><span class="sxs-lookup"><span data-stu-id="9001d-219">DscResource</span></span>
- <span data-ttu-id="9001d-220">Класс</span><span class="sxs-lookup"><span data-stu-id="9001d-220">Class</span></span>
- <span data-ttu-id="9001d-221">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="9001d-221">Configuration</span></span>

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

### <span data-ttu-id="9001d-222">-Component</span><span class="sxs-lookup"><span data-stu-id="9001d-222">-Component</span></span>

<span data-ttu-id="9001d-223">Отображает команды с указанным значением компонента, например **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="9001d-223">Displays commands with the specified component value, such as **Exchange** .</span></span> <span data-ttu-id="9001d-224">Введите название компонента.</span><span class="sxs-lookup"><span data-stu-id="9001d-224">Enter a component name.</span></span>
<span data-ttu-id="9001d-225">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9001d-225">Wildcard characters are permitted.</span></span> <span data-ttu-id="9001d-226">Этот параметр не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="9001d-226">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

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

### <span data-ttu-id="9001d-227">-Detailed</span><span class="sxs-lookup"><span data-stu-id="9001d-227">-Detailed</span></span>

<span data-ttu-id="9001d-228">Добавляет описания параметров и и примеры к основным справочным сведениям.</span><span class="sxs-lookup"><span data-stu-id="9001d-228">Adds parameter descriptions and examples to the basic help display.</span></span> <span data-ttu-id="9001d-229">Этот параметр эффективен, только если файлы справки установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9001d-229">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="9001d-230">Он не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="9001d-230">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

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

### <span data-ttu-id="9001d-231">-Examples</span><span class="sxs-lookup"><span data-stu-id="9001d-231">-Examples</span></span>

<span data-ttu-id="9001d-232">Выводит только имя, краткий обзор и параметры.</span><span class="sxs-lookup"><span data-stu-id="9001d-232">Displays only the name, synopsis, and examples.</span></span> <span data-ttu-id="9001d-233">Чтобы отобразить только примеры, введите `(Get-Help \<cmdlet-name\>).Examples` .</span><span class="sxs-lookup"><span data-stu-id="9001d-233">To display only the examples, type `(Get-Help \<cmdlet-name\>).Examples`.</span></span>

<span data-ttu-id="9001d-234">Этот параметр эффективен, только если файлы справки установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9001d-234">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="9001d-235">Он не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="9001d-235">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

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

### <span data-ttu-id="9001d-236">-Full</span><span class="sxs-lookup"><span data-stu-id="9001d-236">-Full</span></span>

<span data-ttu-id="9001d-237">Отображает всю статью справки для командлета.</span><span class="sxs-lookup"><span data-stu-id="9001d-237">Displays the entire help article for a cmdlet.</span></span> <span data-ttu-id="9001d-238">**Полная** включает описания параметров и атрибуты, примеры, типы входных и выходных объектов, а также дополнительные примечания.</span><span class="sxs-lookup"><span data-stu-id="9001d-238">**Full** includes parameter descriptions and attributes, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="9001d-239">Этот параметр эффективен, только если файлы справки установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9001d-239">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="9001d-240">Он не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="9001d-240">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

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

### <span data-ttu-id="9001d-241">-Functionality</span><span class="sxs-lookup"><span data-stu-id="9001d-241">-Functionality</span></span>

<span data-ttu-id="9001d-242">Выводит справку по элементам с указанными функциями.</span><span class="sxs-lookup"><span data-stu-id="9001d-242">Displays help for items with the specified functionality.</span></span> <span data-ttu-id="9001d-243">Введите функцию.</span><span class="sxs-lookup"><span data-stu-id="9001d-243">Enter the functionality.</span></span> <span data-ttu-id="9001d-244">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9001d-244">Wildcard characters are permitted.</span></span> <span data-ttu-id="9001d-245">Этот параметр не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="9001d-245">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

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

### <span data-ttu-id="9001d-246">-Name</span><span class="sxs-lookup"><span data-stu-id="9001d-246">-Name</span></span>

<span data-ttu-id="9001d-247">Возвращает справку по указанной команде или понятию.</span><span class="sxs-lookup"><span data-stu-id="9001d-247">Gets help about the specified command or concept.</span></span> <span data-ttu-id="9001d-248">Введите имя командлета, функции, поставщика, скрипта или рабочего процесса, например `Get-Member` , имя концептуальной статьи, например `about_Objects` , или псевдоним, например `ls` .</span><span class="sxs-lookup"><span data-stu-id="9001d-248">Enter the name of a cmdlet, function, provider, script, or workflow, such as `Get-Member`, a conceptual article name, such as `about_Objects`, or an alias, such as `ls`.</span></span> <span data-ttu-id="9001d-249">Подстановочные знаки допускаются в именах командлетов и поставщиков, но нельзя использовать подстановочные знаки для поиска имен справочных статей по функциям и сценариев.</span><span class="sxs-lookup"><span data-stu-id="9001d-249">Wildcard characters are permitted in cmdlet and provider names, but you can't use wildcard characters to find the names of function help and script help articles.</span></span>

<span data-ttu-id="9001d-250">Чтобы получить справку для скрипта, который не находится по пути, указанному в `$env:Path` переменной среды, введите путь и имя файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="9001d-250">To get help for a script that isn't located in a path that's listed in the `$env:Path` environment variable, type the script's path and file name.</span></span>

<span data-ttu-id="9001d-251">Если ввести точное имя статьи справки, `Get-Help` отобразится ее содержимое.</span><span class="sxs-lookup"><span data-stu-id="9001d-251">If you enter the exact name of a help article, `Get-Help` displays the article contents.</span></span>

<span data-ttu-id="9001d-252">Если ввести слово или слово, которое отображается в нескольких заголовках справочной статьи, `Get-Help` отображается список соответствующих заголовков.</span><span class="sxs-lookup"><span data-stu-id="9001d-252">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span>

<span data-ttu-id="9001d-253">При вводе любого текста, который не соответствует заголовкам статей справки, `Get-Help` отображается список статей, содержащих этот текст в их содержимом.</span><span class="sxs-lookup"><span data-stu-id="9001d-253">If you enter any text that doesn't match any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="9001d-254">Названия концептуальных статей, например `about_Objects` , должны быть указаны на английском языке даже в версиях PowerShell, отличных от английского.</span><span class="sxs-lookup"><span data-stu-id="9001d-254">The names of conceptual articles, such as `about_Objects`, must be entered in English, even in non-English versions of PowerShell.</span></span>

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

### <span data-ttu-id="9001d-255">-Online</span><span class="sxs-lookup"><span data-stu-id="9001d-255">-Online</span></span>

<span data-ttu-id="9001d-256">Отображает интерактивную версию статьи справки в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9001d-256">Displays the online version of a help article in the default browser.</span></span> <span data-ttu-id="9001d-257">Этот параметр допустим только для статей справки по командлетам, функциям, рабочим процессам и сценариям.</span><span class="sxs-lookup"><span data-stu-id="9001d-257">This parameter is valid only for cmdlet, function, workflow, and script help articles.</span></span> <span data-ttu-id="9001d-258">**Online** `Get-Help` В удаленном сеансе нельзя использовать параметр Online.</span><span class="sxs-lookup"><span data-stu-id="9001d-258">You can't use the **Online** parameter with `Get-Help` in a remote session.</span></span>

<span data-ttu-id="9001d-259">Сведения о поддержке этой функции в справочных статьях, которые вы пишете, см. в разделах [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), [поддержка справки в Интернете](/powershell/scripting/developer/module/supporting-online-help)и [написание справки по командлетам PowerShell](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="9001d-259">For information about supporting this feature in help articles that you write, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help), and [Writing Help for PowerShell Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

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

### <span data-ttu-id="9001d-260">-Parameter</span><span class="sxs-lookup"><span data-stu-id="9001d-260">-Parameter</span></span>

<span data-ttu-id="9001d-261">Выводит только подробное описание указанных параметров.</span><span class="sxs-lookup"><span data-stu-id="9001d-261">Displays only the detailed descriptions of the specified parameters.</span></span> <span data-ttu-id="9001d-262">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9001d-262">Wildcards are permitted.</span></span> <span data-ttu-id="9001d-263">Этот параметр не влияет на отображение концептуальной справки ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="9001d-263">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9001d-264">-Path</span><span class="sxs-lookup"><span data-stu-id="9001d-264">-Path</span></span>

<span data-ttu-id="9001d-265">Возвращает справку с описанием того, как командлет работает по указанному пути к поставщику.</span><span class="sxs-lookup"><span data-stu-id="9001d-265">Gets help that explains how the cmdlet works in the specified provider path.</span></span> <span data-ttu-id="9001d-266">Введите путь к поставщику PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9001d-266">Enter a PowerShell provider path.</span></span>

<span data-ttu-id="9001d-267">Этот параметр возвращает настраиваемую версию статьи справки по командлету, в которой объясняется, как работает командлет в указанном пути поставщика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9001d-267">This parameter gets a customized version of a cmdlet help article that explains how the cmdlet works in the specified PowerShell provider path.</span></span> <span data-ttu-id="9001d-268">Этот параметр действует только для справки о командлете поставщика и только в том случае, если поставщик содержит пользовательскую версию статьи справки командлета поставщика в файле справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-268">This parameter is effective only for help about a provider cmdlet and only when the provider includes a custom version of the provider cmdlet help article in its help file.</span></span> <span data-ttu-id="9001d-269">Для использования этого параметра установите файл справки для модуля, включающего поставщик.</span><span class="sxs-lookup"><span data-stu-id="9001d-269">To use this parameter, install the help file for the module that includes the provider.</span></span>

<span data-ttu-id="9001d-270">Чтобы просмотреть справку по пользовательскому командлету для пути к поставщику, перейдите по пути поставщика и введите `Get-Help` команду или в любом расположении пути, чтобы указать путь к поставщику, с помощью параметра **path** в `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="9001d-270">To see the custom cmdlet help for a provider path, go to the provider path location and enter a `Get-Help` command or, from any path location, use the **Path** parameter of `Get-Help` to specify the provider path.</span></span> <span data-ttu-id="9001d-271">Можно также найти справку по настраиваемому командлету в Интернете в разделе справки по поставщику статьи справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-271">You can also find custom cmdlet help online in the provider help section of the help articles.</span></span>

<span data-ttu-id="9001d-272">Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](./About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9001d-272">For more information about PowerShell providers, see [about_Providers](./About/about_Providers.md).</span></span>

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

### <span data-ttu-id="9001d-273">-Role</span><span class="sxs-lookup"><span data-stu-id="9001d-273">-Role</span></span>

<span data-ttu-id="9001d-274">Выводит справку, настроенную для указанной роли пользователя.</span><span class="sxs-lookup"><span data-stu-id="9001d-274">Displays help customized for the specified user role.</span></span> <span data-ttu-id="9001d-275">Введите роль.</span><span class="sxs-lookup"><span data-stu-id="9001d-275">Enter a role.</span></span> <span data-ttu-id="9001d-276">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9001d-276">Wildcard characters are permitted.</span></span>

<span data-ttu-id="9001d-277">Введите роль, которую пользователь имеет в организации.</span><span class="sxs-lookup"><span data-stu-id="9001d-277">Enter the role that the user plays in an organization.</span></span> <span data-ttu-id="9001d-278">Для некоторых командлетов в файлах справки содержится разный текст в зависимости от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="9001d-278">Some cmdlets display different text in their help files based on the value of this parameter.</span></span> <span data-ttu-id="9001d-279">Этот параметр не влияет на справку по основным командлетам.</span><span class="sxs-lookup"><span data-stu-id="9001d-279">This parameter has no effect on help for the core cmdlets.</span></span>

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

### <span data-ttu-id="9001d-280">-ShowWindow</span><span class="sxs-lookup"><span data-stu-id="9001d-280">-ShowWindow</span></span>

<span data-ttu-id="9001d-281">Выводит раздел справки в окне для более удобного чтения.</span><span class="sxs-lookup"><span data-stu-id="9001d-281">Displays the help topic in a window for easier reading.</span></span> <span data-ttu-id="9001d-282">Окно содержит **функцию поиска и** окно **параметров** , которые позволяют задать параметры для экрана, включая параметры для вывода только выбранных разделов раздела справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-282">The window includes a **Find** search feature and a **Settings** box that lets you set options for the display, including options to display only selected sections of a help topic.</span></span>

<span data-ttu-id="9001d-283">Параметр **ShowWindow** поддерживает разделы справки для команд (командлеты, функции, команды CIM, рабочие процессы, скрипты) и концептуальные **сведения о** статьях.</span><span class="sxs-lookup"><span data-stu-id="9001d-283">The **ShowWindow** parameter supports help topics for commands (cmdlets, functions, CIM commands, workflows, scripts) and conceptual **About** articles.</span></span> <span data-ttu-id="9001d-284">Он не поддерживает справку по поставщикам.</span><span class="sxs-lookup"><span data-stu-id="9001d-284">It does not support provider help.</span></span>

<span data-ttu-id="9001d-285">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9001d-285">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShowWindow
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9001d-286">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9001d-286">CommonParameters</span></span>

<span data-ttu-id="9001d-287">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9001d-287">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9001d-288">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9001d-288">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9001d-289">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9001d-289">INPUTS</span></span>

### <span data-ttu-id="9001d-290">Нет</span><span class="sxs-lookup"><span data-stu-id="9001d-290">None</span></span>

<span data-ttu-id="9001d-291">Вы не можете отправить объекты по конвейеру в `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="9001d-291">You can't send objects down the pipeline to `Get-Help`.</span></span>

## <span data-ttu-id="9001d-292">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9001d-292">OUTPUTS</span></span>

### <span data-ttu-id="9001d-293">ExtendedCmdletHelpInfo</span><span class="sxs-lookup"><span data-stu-id="9001d-293">ExtendedCmdletHelpInfo</span></span>

<span data-ttu-id="9001d-294">При выполнении `Get-Help` команды, не имеющей файла справки, `Get-Help` возвращается объект **екстендедкмдлеселпинфо** , представляющий автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="9001d-294">If you run `Get-Help` on a command that doesn't have a help file, `Get-Help` returns an **ExtendedCmdletHelpInfo** object that represents autogenerated help.</span></span>

### <span data-ttu-id="9001d-295">System.String</span><span class="sxs-lookup"><span data-stu-id="9001d-295">System.String</span></span>

<span data-ttu-id="9001d-296">Если вы получаете общую справочную статью, `Get-Help` возвращает ее в виде строки.</span><span class="sxs-lookup"><span data-stu-id="9001d-296">If you get a conceptual help article, `Get-Help` returns it as a string.</span></span>

### <span data-ttu-id="9001d-297">MamlCommandHelpInfo</span><span class="sxs-lookup"><span data-stu-id="9001d-297">MamlCommandHelpInfo</span></span>

<span data-ttu-id="9001d-298">При получении команды, имеющей файл справки, `Get-Help` возвращает объект **MamlCommandHelpInfo** .</span><span class="sxs-lookup"><span data-stu-id="9001d-298">If you get a command that has a help file, `Get-Help` returns a **MamlCommandHelpInfo** object.</span></span>

## <span data-ttu-id="9001d-299">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9001d-299">NOTES</span></span>

<span data-ttu-id="9001d-300">PowerShell 3,0 не включает файлы справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-300">PowerShell 3.0 doesn't include help files.</span></span> <span data-ttu-id="9001d-301">Чтобы скачать и установить файлы справки, которые `Get-Help` выполняют чтение, используйте `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="9001d-301">To download and install the help files that `Get-Help` reads, use the `Update-Help` cmdlet.</span></span> <span data-ttu-id="9001d-302">С помощью `Update-Help` командлета можно скачать и установить файлы справки для основных команд, которые входят в состав PowerShell, а также для всех устанавливаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="9001d-302">You can use the `Update-Help` cmdlet to download and install help files for the core commands that come with PowerShell and for any modules that you install.</span></span> <span data-ttu-id="9001d-303">С его помощью можно также обновлять файлы справки на компьютере, чтобы они всегда были актуальны.</span><span class="sxs-lookup"><span data-stu-id="9001d-303">You can also use it to update the help files so that the help on your computer is never outdated.</span></span>

<span data-ttu-id="9001d-304">Кроме того, вы можете ознакомиться с справочными статьями, посвященными командам PowerShell Online, начиная с [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9001d-304">You can also read the help articles about the commands that come with PowerShell online starting at [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

<span data-ttu-id="9001d-305">`Get-Help` Отображает справку в наборе языкового стандарта для операционной системы Windows или на резервном языке для этого языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="9001d-305">`Get-Help` displays help in the locale set for the Windows operating system or in the fallback language for that locale.</span></span> <span data-ttu-id="9001d-306">Если у вас нет файлов справки для основного или резервного языкового стандарта, `Get-Help` ведет себя так, как если бы на компьютере не было файлов справки.</span><span class="sxs-lookup"><span data-stu-id="9001d-306">If you don't have help files for the primary or fallback locale, `Get-Help` behaves as if there are no help files on the computer.</span></span> <span data-ttu-id="9001d-307">Чтобы получить справку для другого языкового стандарта, измените параметры с помощью **области** и **языка** на панели управления.</span><span class="sxs-lookup"><span data-stu-id="9001d-307">To get help for a different locale, use **Region** and **Language** in Control Panel to change the settings.</span></span> <span data-ttu-id="9001d-308">В Windows 10 **Параметры** , **время & язык** .</span><span class="sxs-lookup"><span data-stu-id="9001d-308">On Windows 10, **Settings** , **Time & Language** .</span></span>

<span data-ttu-id="9001d-309">Полный обзор справки включает таблицу сведений о параметрах.</span><span class="sxs-lookup"><span data-stu-id="9001d-309">The full view of help includes a table of information about the parameters.</span></span> <span data-ttu-id="9001d-310">В таблице содержатся указанные ниже поля.</span><span class="sxs-lookup"><span data-stu-id="9001d-310">The table includes the following fields:</span></span>

- <span data-ttu-id="9001d-311">**Обязательно** .</span><span class="sxs-lookup"><span data-stu-id="9001d-311">**Required** .</span></span> <span data-ttu-id="9001d-312">Показывает, является ли параметр необходимым (true) или необязательным (false).</span><span class="sxs-lookup"><span data-stu-id="9001d-312">Indicates whether the parameter is required (true) or optional (false).</span></span>

- <span data-ttu-id="9001d-313">**Расположение** .</span><span class="sxs-lookup"><span data-stu-id="9001d-313">**Position** .</span></span> <span data-ttu-id="9001d-314">Указывает, является ли параметр именованным или позиционированным (числовым).</span><span class="sxs-lookup"><span data-stu-id="9001d-314">Indicates whether the parameter is named or positional (numeric).</span></span> <span data-ttu-id="9001d-315">Позиционные параметры должны появляться в указанном месте команды.</span><span class="sxs-lookup"><span data-stu-id="9001d-315">Positional parameters must appear in a specified place in the command.</span></span>

- <span data-ttu-id="9001d-316">**С именем** указывает, что имя параметра является обязательным, но параметр может находиться в любом месте команды.</span><span class="sxs-lookup"><span data-stu-id="9001d-316">**Named** indicates that the parameter name is required, but that the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="9001d-317">**Numeric** указывает, что имя параметра является необязательным, но если имя не указано, параметр должен находиться в месте, указанном в номере.</span><span class="sxs-lookup"><span data-stu-id="9001d-317">**Numeric** indicates that the parameter name is optional, but when the name is omitted, the parameter must be in the place specified by the number.</span></span> <span data-ttu-id="9001d-318">Например, `2` указывает, что если имя параметра не указано, параметр должен быть вторым или единственным безымянным параметром в команде.</span><span class="sxs-lookup"><span data-stu-id="9001d-318">For example, `2` indicates that when the parameter name is omitted, the parameter must be the second or only unnamed parameter in the command.</span></span> <span data-ttu-id="9001d-319">Если используется имя параметра, параметр может располагаться в любом месте команды.</span><span class="sxs-lookup"><span data-stu-id="9001d-319">When the parameter name is used, the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="9001d-320">**Значение по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="9001d-320">**Default value** .</span></span> <span data-ttu-id="9001d-321">Значение параметра или поведение по умолчанию, используемое PowerShell, если параметр не включен в команду.</span><span class="sxs-lookup"><span data-stu-id="9001d-321">The parameter value or default behavior that PowerShell uses if you don't include the parameter in the command.</span></span>

- <span data-ttu-id="9001d-322">Принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="9001d-322">Accepts pipeline input.</span></span> <span data-ttu-id="9001d-323">Указывает, можно ли (true) или нет (false) отправку объектов в параметр через конвейер.</span><span class="sxs-lookup"><span data-stu-id="9001d-323">Indicates whether you can (true) or can't (false) send objects to the parameter through a pipeline.</span></span> <span data-ttu-id="9001d-324">**По имени свойства** означает, что конвейерный объект должен иметь свойство, имя которого совпадает с именем параметра.</span><span class="sxs-lookup"><span data-stu-id="9001d-324">**By Property Name** means that the pipelined object must have a property that has the same name as the parameter name.</span></span>

- <span data-ttu-id="9001d-325">**Принимает подстановочные знаки** .</span><span class="sxs-lookup"><span data-stu-id="9001d-325">**Accepts wildcard characters** .</span></span> <span data-ttu-id="9001d-326">Указывает, может ли значение параметра содержать подстановочные знаки, например звездочку ( `*` ) или вопросительный знак ( `?` ).</span><span class="sxs-lookup"><span data-stu-id="9001d-326">Indicates whether the value of a parameter can include wildcard characters, such as an asterisk (`*`) or question mark (`?`).</span></span>

## <span data-ttu-id="9001d-327">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9001d-327">RELATED LINKS</span></span>

[<span data-ttu-id="9001d-328">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="9001d-328">about_Command_Syntax</span></span>](About/about_Command_Syntax.md)

[<span data-ttu-id="9001d-329">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="9001d-329">about_Comment_Based_Help</span></span>](./About/about_Comment_Based_Help.md)

[<span data-ttu-id="9001d-330">Get-Command</span><span class="sxs-lookup"><span data-stu-id="9001d-330">Get-Command</span></span>](Get-Command.md)

[<span data-ttu-id="9001d-331">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="9001d-331">Supporting Updatable Help</span></span>](/powershell/scripting/developer/module/supporting-updatable-help)

[<span data-ttu-id="9001d-332">Update-Help</span><span class="sxs-lookup"><span data-stu-id="9001d-332">Update-Help</span></span>](Update-Help.md)

[<span data-ttu-id="9001d-333">Написание разделов справки на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="9001d-333">Writing Comment-Based Help Topics</span></span>](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[<span data-ttu-id="9001d-334">Написание справки для командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="9001d-334">Writing Help for PowerShell Cmdlets</span></span>](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)
