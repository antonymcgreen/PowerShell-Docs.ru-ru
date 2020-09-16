---
title: Справочная система
description: Овладение справочной системой — важное условие для успешной работы с PowerShell.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 8325a32ad8ec137781300e9d46cab52705f0805a
ms.sourcegitcommit: eaac7af89171379df2e20464ebee9fc7e7d7674a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89493663"
---
# <a name="chapter-2---the-help-system"></a><span data-ttu-id="57e39-103">Глава 2. Справочная система</span><span class="sxs-lookup"><span data-stu-id="57e39-103">Chapter 2 - The Help System</span></span>

<span data-ttu-id="57e39-104">Двум группам ИТ-специалистов предложили выполнить письменный тест без доступа к компьютеру на определение уровня их квалификации с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e39-104">Two groups of IT pros were given a written test without access to a computer to determine their skill level with PowerShell.</span></span> <span data-ttu-id="57e39-105">Начинающие пользователи PowerShell были определены в одну группу, опытные пользователи — в другую.</span><span class="sxs-lookup"><span data-stu-id="57e39-105">PowerShell beginners were placed in one group and experts in another.</span></span>
<span data-ttu-id="57e39-106">На основе полученных результатов теста уровень квалификации между двумя группами почти не отличался.</span><span class="sxs-lookup"><span data-stu-id="57e39-106">Based on the results of the test, there didn't seem to be much difference in the skill level between the two groups.</span></span> <span data-ttu-id="57e39-107">Обе группы получили второй тест, подобный первому.</span><span class="sxs-lookup"><span data-stu-id="57e39-107">Both groups were given a second test similar to the first one.</span></span> <span data-ttu-id="57e39-108">На этот раз пользователям был предоставлен доступ к компьютеру с помощью PowerShell без доступа к Интернету.</span><span class="sxs-lookup"><span data-stu-id="57e39-108">This time they were given access to a computer with PowerShell that didn't have access to the internet.</span></span> <span data-ttu-id="57e39-109">Результаты второго теста показали большое различие в уровне квалификации между двумя группами.</span><span class="sxs-lookup"><span data-stu-id="57e39-109">The results of the second test showed a huge difference in the skill level between the two groups.</span></span> <span data-ttu-id="57e39-110">Опытные пользователи не всегда знают ответы, но они знают, как их найти.</span><span class="sxs-lookup"><span data-stu-id="57e39-110">Experts don't always know the answers, but they know how to figure out the answers.</span></span>

<span data-ttu-id="57e39-111">Чем отличались результаты первого и второго тестов между двумя группами?</span><span class="sxs-lookup"><span data-stu-id="57e39-111">What was the difference in the results of the first and second test between these two groups?</span></span>

<span data-ttu-id="57e39-112">Результаты тестов были разными потому, что опытные пользователи не запоминают, как использовать тысячи команд в PowerShell,</span><span class="sxs-lookup"><span data-stu-id="57e39-112">The differences observed in these two tests were because experts don't memorize how to use thousands of commands in PowerShell.</span></span> <span data-ttu-id="57e39-113">а эффективно умеют пользоваться справочной системой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e39-113">They learn how to use the help system within PowerShell extremely well.</span></span>
<span data-ttu-id="57e39-114">Это позволяет им при необходимости находить нужные команды и использовать их.</span><span class="sxs-lookup"><span data-stu-id="57e39-114">This allows them to find the necessary commands when needed and how to use those commands once they've found them.</span></span>

<span data-ttu-id="57e39-115">Я слышал, как автор PowerShell Джеффри Сновер рассказывал подобную историю несколько раз.</span><span class="sxs-lookup"><span data-stu-id="57e39-115">I've heard Jeffrey Snover, the inventor of PowerShell, tell a similar story a number of times.</span></span>

<span data-ttu-id="57e39-116">Овладение справочной системой — важное условие для успешной работы с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e39-116">Mastering the help system is the key to being successful with PowerShell.</span></span>

## <a name="discoverability"></a><span data-ttu-id="57e39-117">Возможность обнаружения</span><span class="sxs-lookup"><span data-stu-id="57e39-117">Discoverability</span></span>

<span data-ttu-id="57e39-118">Скомпилированные команды в PowerShell называются командлетами.</span><span class="sxs-lookup"><span data-stu-id="57e39-118">Compiled commands in PowerShell are called cmdlets.</span></span> <span data-ttu-id="57e39-119">В оригинале слово cmdlet произносится полностью: "командлет".</span><span class="sxs-lookup"><span data-stu-id="57e39-119">Cmdlet is pronounced "command-let" (not CMD-let).</span></span> <span data-ttu-id="57e39-120">Имена командлетов соответствуют форме отдельных команд "глагол — существительное", что позволяет легко их находить.</span><span class="sxs-lookup"><span data-stu-id="57e39-120">Cmdlets names have the form of singular "Verb-Noun" commands to make them easily discoverable.</span></span> <span data-ttu-id="57e39-121">Например, командлет `Get-Process` определяет выполняемые процессы, а командлет `Get-Service` получает список служб и их состояний.</span><span class="sxs-lookup"><span data-stu-id="57e39-121">For example, the cmdlet for determining what processes are running is `Get-Process` and the cmdlet for retrieving a list of services and their statuses is `Get-Service`.</span></span> <span data-ttu-id="57e39-122">В PowerShell существуют другие типы команд, например псевдонимы и функции, которые будут рассмотрены далее в этом пособии.</span><span class="sxs-lookup"><span data-stu-id="57e39-122">There are other types of commands in PowerShell such as aliases and functions that will be covered later in this book.</span></span> <span data-ttu-id="57e39-123">Команда PowerShell — это универсальное понятие, которое часто используется для ссылки на любой тип команды в PowerShell, независимо от того, является ли он командлетом, функцией или псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="57e39-123">The term PowerShell command is a generic term that's often used to refer to any type of command in PowerShell, regardless of whether or not it's a cmdlet, function, or alias.</span></span>

## <a name="the-three-core-cmdlets-in-powershell"></a><span data-ttu-id="57e39-124">Три основных командлета в PowerShell</span><span class="sxs-lookup"><span data-stu-id="57e39-124">The Three Core Cmdlets in PowerShell</span></span>

- `Get-Command`
- `Get-Help`
- <span data-ttu-id="57e39-125">`Get-Member` (рассматривается в главе 3)</span><span class="sxs-lookup"><span data-stu-id="57e39-125">`Get-Member` (covered in chapter 3)</span></span>

<span data-ttu-id="57e39-126">Вопрос, который мне часто задают: как вы различаете команды в PowerShell?</span><span class="sxs-lookup"><span data-stu-id="57e39-126">One question I'm often asked is how do you figure out what the commands are in PowerShell?</span></span> <span data-ttu-id="57e39-127">Для определения команд можно использовать командлеты `Get-Command` и `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-127">Both `Get-Command` and `Get-Help` can be used to determine the commands.</span></span>

## <a name="get-help"></a><span data-ttu-id="57e39-128">Get-Help</span><span class="sxs-lookup"><span data-stu-id="57e39-128">Get-Help</span></span>

<span data-ttu-id="57e39-129">`Get-Help` — это многоцелевая команда.</span><span class="sxs-lookup"><span data-stu-id="57e39-129">`Get-Help` is a multipurpose command.</span></span> <span data-ttu-id="57e39-130">`Get-Help` помогает научиться использовать найденные команды.</span><span class="sxs-lookup"><span data-stu-id="57e39-130">`Get-Help` helps you learn how to use commands once you find them.</span></span> <span data-ttu-id="57e39-131">`Get-Help` также можно использовать для поиска команд, но, по сравнению с `Get-Command`, другим, менее прямым способом.</span><span class="sxs-lookup"><span data-stu-id="57e39-131">`Get-Help` can also be used to help locate commands, but in a different and more indirect way when compared to `Get-Command`.</span></span>

<span data-ttu-id="57e39-132">Если для поиска команд используется `Get-Help`, сначала выполняется поиск совпадений с подстановочными знаками имен команд на основе предоставленных входных данных.</span><span class="sxs-lookup"><span data-stu-id="57e39-132">When `Get-Help` is used to locate commands, it first searches for wildcard matches of command names based on the provided input.</span></span> <span data-ttu-id="57e39-133">Если командлет не находит совпадение, выполняется поиск по самим разделам справки, и, если совпадений не найдено, ошибка возвращается.</span><span class="sxs-lookup"><span data-stu-id="57e39-133">If it doesn't find a match, it searches through the help topics themselves, and if no match is found an error is returned.</span></span> <span data-ttu-id="57e39-134">Вопреки распространенному мнению, `Get-Help` можно использовать для поиска команд, не содержащих разделов справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-134">Contrary to popular belief, `Get-Help` can be used to find commands that don't have help topics.</span></span>

<span data-ttu-id="57e39-135">Первое, что нужно знать о справочной системе PowerShell, — как использовать командлет `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-135">The first thing you need to know about the help system in PowerShell is how to use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="57e39-136">Следующая команда позволяет вывести раздел справки для `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-136">The following command is used to display the help topic for `Get-Help`.</span></span>

```powershell
Get-Help -Name Get-Help
```

```Output
Do you want to run Update-Help?
The Update-Help cmdlet downloads the most current Help files for Windows PowerShell
modules, and installs them on your computer. For more information about the Update-Help
cmdlet, see http://go.microsoft.com/fwlink/?LinkId=210614.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="57e39-137">Начиная с PowerShell версии 3, справка PowerShell не поставляется вместе с операционной системой.</span><span class="sxs-lookup"><span data-stu-id="57e39-137">Beginning with PowerShell version 3, PowerShell help doesn't ship with the operating system.</span></span> <span data-ttu-id="57e39-138">При первом запуске `Get-Help` для команды выводится предыдущее сообщение.</span><span class="sxs-lookup"><span data-stu-id="57e39-138">The first time `Get-Help` is run for a command, the previous message is displayed.</span></span> <span data-ttu-id="57e39-139">Если вместо командлета `Get-Help` используется функция `help` или псевдоним `man`, этот запрос не появится.</span><span class="sxs-lookup"><span data-stu-id="57e39-139">If the `help` function or `man` alias is used instead of the `Get-Help` cmdlet, you don't receive this prompt.</span></span>

<span data-ttu-id="57e39-140">При согласии нажатием клавиши <kbd>Y</kbd> запускается командлет `Update-Help`, который по умолчанию требует доступа к Интернету.</span><span class="sxs-lookup"><span data-stu-id="57e39-140">Answering yes by pressing <kbd>Y</kbd> runs the `Update-Help` cmdlet, which requires internet access by default.</span></span> <span data-ttu-id="57e39-141">`Y` можно указать в верхнем или нижнем регистре.</span><span class="sxs-lookup"><span data-stu-id="57e39-141">`Y` can be specified in either upper or lower case.</span></span>

<span data-ttu-id="57e39-142">После загрузки справки и завершения обновления для указанной команды будет возвращен раздел справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-142">Once the help is downloaded and the update is complete, the help topic is returned for the specified command:</span></span>

```powershell
Get-Help -Name Get-Help
```

<span data-ttu-id="57e39-143">Попробуйте выполнить этот пример на компьютере, просмотрите выходные данные и запишите, как группируются сведения.</span><span class="sxs-lookup"><span data-stu-id="57e39-143">Take a moment to run that example on your computer, review the output, and take note of how the information is grouped:</span></span>

- <span data-ttu-id="57e39-144">NAME</span><span class="sxs-lookup"><span data-stu-id="57e39-144">NAME</span></span>
- <span data-ttu-id="57e39-145">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="57e39-145">SYNOPSIS</span></span>
- <span data-ttu-id="57e39-146">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57e39-146">SYNTAX</span></span>
- <span data-ttu-id="57e39-147">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="57e39-147">DESCRIPTION</span></span>
- <span data-ttu-id="57e39-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="57e39-148">RELATED LINKS</span></span>
- <span data-ttu-id="57e39-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="57e39-149">REMARKS</span></span>

<span data-ttu-id="57e39-150">Как вы видите, разделы справки могут содержать большой объем информации, причем это даже не весь раздел справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-150">As you can see, help topics can contain an enormous amount of information and this isn't even the entire help topic.</span></span>

<span data-ttu-id="57e39-151">Хотя это и не относится к PowerShell, параметр — это способ предоставления команде входных данных.</span><span class="sxs-lookup"><span data-stu-id="57e39-151">While not specific to PowerShell, a parameter is a way to provide input to a command.</span></span> <span data-ttu-id="57e39-152">`Get-Help` имеет много параметров, которые можно указать для возврата всего раздела справки или его подмножества.</span><span class="sxs-lookup"><span data-stu-id="57e39-152">`Get-Help` has many parameters that can be specified in order to return the entire help topic or a subset of it.</span></span>

<span data-ttu-id="57e39-153">В разделе синтаксиса раздела справки, который отображается в предыдущем наборе результатов, приводится список всех параметров `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-153">The syntax section of the help topic shown in the previous set of results lists all of the parameters for `Get-Help`.</span></span> <span data-ttu-id="57e39-154">На первый взгляд кажется, что одинаковые параметры приведены шесть раз по-разному.</span><span class="sxs-lookup"><span data-stu-id="57e39-154">At first glance, it appears the same parameters are listed six different times.</span></span> <span data-ttu-id="57e39-155">Каждый из этих блоков раздела синтаксиса представляет собой набор параметров.</span><span class="sxs-lookup"><span data-stu-id="57e39-155">Each of those different blocks in the syntax section is a parameter set.</span></span> <span data-ttu-id="57e39-156">Это означает, что командлет `Get-Help` имеет шесть разных наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="57e39-156">This means the `Get-Help` cmdlet has six different parameter sets.</span></span> <span data-ttu-id="57e39-157">Если посмотреть более внимательно, можно заметить, что в каждом наборе по крайней мере один параметр отличается.</span><span class="sxs-lookup"><span data-stu-id="57e39-157">If you take a closer look, you'll notice that at least one parameter is different in each of the parameter sets.</span></span>

<span data-ttu-id="57e39-158">Эти наборы параметров являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="57e39-158">Parameter sets are mutually exclusive.</span></span> <span data-ttu-id="57e39-159">После использования уникального параметра, который существует только в одном из наборов, можно использовать только те параметры, которые содержатся в этом наборе.</span><span class="sxs-lookup"><span data-stu-id="57e39-159">Once a unique parameter that only exists in one of the parameter sets is used, only parameters contained within that parameter set can be used.</span></span> <span data-ttu-id="57e39-160">Например, не удалось одновременно указать параметры **Full** и **Detailed**, так как они находятся в разных наборах.</span><span class="sxs-lookup"><span data-stu-id="57e39-160">For example, both the **Full** and **Detailed** parameters couldn't be specified at the same time because they are in different parameter sets.</span></span>

<span data-ttu-id="57e39-161">Каждый из следующих параметров находится в разных наборах.</span><span class="sxs-lookup"><span data-stu-id="57e39-161">Each of the following parameters are in different parameter sets:</span></span>

- <span data-ttu-id="57e39-162">Полное</span><span class="sxs-lookup"><span data-stu-id="57e39-162">Full</span></span>
- <span data-ttu-id="57e39-163">Подробно</span><span class="sxs-lookup"><span data-stu-id="57e39-163">Detailed</span></span>
- <span data-ttu-id="57e39-164">Примеры</span><span class="sxs-lookup"><span data-stu-id="57e39-164">Examples</span></span>
- <span data-ttu-id="57e39-165">Справка в Интернете</span><span class="sxs-lookup"><span data-stu-id="57e39-165">Online</span></span>
- <span data-ttu-id="57e39-166">Параметр</span><span class="sxs-lookup"><span data-stu-id="57e39-166">Parameter</span></span>
- <span data-ttu-id="57e39-167">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="57e39-167">ShowWindow</span></span>

<span data-ttu-id="57e39-168">Любые непонятные синтаксические конструкции в разделе синтаксиса, например квадратные и угловые скобки, имеют определенное значение и будут рассматриваться в приложении А к этому пособию.</span><span class="sxs-lookup"><span data-stu-id="57e39-168">All of the cryptic syntax such as square and angle brackets in the syntax section means something but will be covered in Appendix A of this book.</span></span> <span data-ttu-id="57e39-169">При всей важности непонятных синтаксических конструкций их обычно трудно запоминать тем, кто не работал с PowerShell и не использует их ежедневно.</span><span class="sxs-lookup"><span data-stu-id="57e39-169">While important, learning what the cryptic syntax is often difficult to retain for someone who is new to PowerShell and may not use it everyday.</span></span>

<span data-ttu-id="57e39-170">Дополнительные сведения о том, как распознать непонятные синтаксические конструкции, см. в [Приложение А][].</span><span class="sxs-lookup"><span data-stu-id="57e39-170">For more information to better understand the cryptic syntax, see [Appendix A][].</span></span>

<span data-ttu-id="57e39-171">Для начинающих пользователей существует простой способ вычислять аналогичную информацию, кроме обычного языка.</span><span class="sxs-lookup"><span data-stu-id="57e39-171">For beginners, there's an easier way to figure out the same information except in plain language.</span></span>

<span data-ttu-id="57e39-172">При указании параметра **Full** в значении `Get-Help` возвращается весь раздел справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-172">When the **Full** parameter of `Get-Help` is specified, the entire help topic is returned.</span></span>

```powershell
Get-Help -Name Get-Help -Full
```

<span data-ttu-id="57e39-173">Попробуйте выполнить этот пример на компьютере, просмотрите выходные данные и запишите, как группируются сведения.</span><span class="sxs-lookup"><span data-stu-id="57e39-173">Take a moment to run that example on your computer, review the output, and take note of how the information is grouped:</span></span>

- <span data-ttu-id="57e39-174">NAME</span><span class="sxs-lookup"><span data-stu-id="57e39-174">NAME</span></span>
- <span data-ttu-id="57e39-175">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="57e39-175">SYNOPSIS</span></span>
- <span data-ttu-id="57e39-176">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57e39-176">SYNTAX</span></span>
- <span data-ttu-id="57e39-177">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="57e39-177">DESCRIPTION</span></span>
- <span data-ttu-id="57e39-178">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="57e39-178">PARAMETERS</span></span>
- <span data-ttu-id="57e39-179">Входные данные</span><span class="sxs-lookup"><span data-stu-id="57e39-179">INPUTS</span></span>
- <span data-ttu-id="57e39-180">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="57e39-180">OUTPUTS</span></span>
- <span data-ttu-id="57e39-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="57e39-181">NOTES</span></span>
- <span data-ttu-id="57e39-182">Примеры</span><span class="sxs-lookup"><span data-stu-id="57e39-182">EXAMPLES</span></span>
- <span data-ttu-id="57e39-183">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="57e39-183">RELATED LINKS</span></span>

<span data-ttu-id="57e39-184">Заметьте, что использование параметра **Full** привело к возврату нескольких дополнительных разделов, один из которых представляет собой раздел ПАРАМЕТРОВ, содержащий больше данных, чем раздел СИНТАКСИСА с непонятными конструкциями.</span><span class="sxs-lookup"><span data-stu-id="57e39-184">Notice that using the **Full** parameter returned several additional sections, one of which is the PARAMETERS section that provides more information than the cryptic SYNTAX section.</span></span>

<span data-ttu-id="57e39-185">Параметр **Full** является параметром-переключателем,</span><span class="sxs-lookup"><span data-stu-id="57e39-185">The **Full** parameter is a switch parameter.</span></span> <span data-ttu-id="57e39-186">то есть тем, который не требует указывать значение.</span><span class="sxs-lookup"><span data-stu-id="57e39-186">A parameter that doesn't require a value is called a switch parameter.</span></span> <span data-ttu-id="57e39-187">Если параметр-переключатель указывается, его значение будет верным, а если не указывается, значение будет неверным.</span><span class="sxs-lookup"><span data-stu-id="57e39-187">When a switch parameter is specified, it's value is true and when it's not, it's value is false.</span></span>

<span data-ttu-id="57e39-188">Работая над этой главой в консоли PowerShell, вы заметили, что предыдущая команда для вывода полного раздела справки для `Get-Help` показалась на экране очень быстро и ее нельзя было прочитать.</span><span class="sxs-lookup"><span data-stu-id="57e39-188">If you've been working through this chapter in the PowerShell console, you noticed that the previous command to display the full help topic for `Get-Help` flew by on the screen without giving you a chance to read it.</span></span> <span data-ttu-id="57e39-189">Для этого существует более эффективный способ.</span><span class="sxs-lookup"><span data-stu-id="57e39-189">There's a better way.</span></span>

<span data-ttu-id="57e39-190">`Help` — это функция, передающая `Get-Help` функции с именем `more`, которая является оболочкой для исполняемого файла `more.com` в Windows.</span><span class="sxs-lookup"><span data-stu-id="57e39-190">`Help` is a function that pipes `Get-Help` to a function named `more`, which is a wrapper for the `more.com` executable file in Windows.</span></span> <span data-ttu-id="57e39-191">В консоли PowerShell командлет `help` открывает одну страницу справки за один раз.</span><span class="sxs-lookup"><span data-stu-id="57e39-191">In the PowerShell console, `help` provides one page of help at a time.</span></span> <span data-ttu-id="57e39-192">В интегрированной среде сценариев этот командлет работает так же, как `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-192">In the ISE, it works the same way as `Get-Help`.</span></span> <span data-ttu-id="57e39-193">Я рекомендую использовать функцию `help` вместо командлета `Get-Help`, так как она удобнее и меньше по длине.</span><span class="sxs-lookup"><span data-stu-id="57e39-193">My recommendation is to use the `help` function instead of the `Get-Help` cmdlet since it provides a better experience and it's less to type.</span></span>

<span data-ttu-id="57e39-194">При этом вводить меньше символов не всегда оказывается полезным.</span><span class="sxs-lookup"><span data-stu-id="57e39-194">Less typing isn't always a good thing, however.</span></span> <span data-ttu-id="57e39-195">Сохраняя команды в виде сценария или отправляя их другим пользователям, обязательно используйте полные имена командлетов и параметров.</span><span class="sxs-lookup"><span data-stu-id="57e39-195">If you're going to save your commands as a script or share them with someone else, be sure to use full cmdlet and parameter names.</span></span> <span data-ttu-id="57e39-196">Полные имена являются самодокументируемыми, поэтому их легче распознавать.</span><span class="sxs-lookup"><span data-stu-id="57e39-196">The full names are self-documenting, which makes them easier to understand.</span></span> <span data-ttu-id="57e39-197">Всегда помните о том, кому придется читать и распознавать ваши команды.</span><span class="sxs-lookup"><span data-stu-id="57e39-197">Think about the next person that has to read and understand your commands.</span></span> <span data-ttu-id="57e39-198">Этим человеком можете оказаться вы.</span><span class="sxs-lookup"><span data-stu-id="57e39-198">It could be you.</span></span> <span data-ttu-id="57e39-199">Ваши сотрудники и вы сами будете за это благодарны.</span><span class="sxs-lookup"><span data-stu-id="57e39-199">Your coworkers and future self will thank you.</span></span>

<span data-ttu-id="57e39-200">Попробуйте выполнить следующие команды в консоли PowerShell на компьютере с Windows 10 в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="57e39-200">Try running the following commands in the PowerShell console on your Windows 10 lab environment computer.</span></span>

```powershell
Get-Help -Name Get-Help -Full
help -Name Get-Help -Full
help Get-Help -Full
```

<span data-ttu-id="57e39-201">Появились ли различия в выходных данных приведенных выше команд после их запуска на компьютере с Windows 10 в лабораторной среде?</span><span class="sxs-lookup"><span data-stu-id="57e39-201">Did you notice any differences in the output from the previously listed commands when you ran them on your Windows 10 lab environment computer?</span></span>

<span data-ttu-id="57e39-202">Кроме последних двух параметров, которые возвращают результаты по одной странице за один раз, эти выходные данные ничем не отличаются.</span><span class="sxs-lookup"><span data-stu-id="57e39-202">There aren't any differences other than the last two options return the results one page at a time.</span></span>
<span data-ttu-id="57e39-203"><kbd>ПРОБЕЛ</kbd> используется для вывода следующей страницы содержимого с помощью функции `Help`, а <kbd>Ctrl</kbd>+<kbd>C</kbd> отменяет команды, выполняемые в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e39-203">The <kbd>spacebar</kbd> is used to display the next page of content when using the `Help` function and <kbd>Ctrl</kbd>+<kbd>C</kbd> cancels commands that are running in the PowerShell console.</span></span>

<span data-ttu-id="57e39-204">В первом примере используется командлет `Get-Help`, во втором — функция `Help`, в третьем параметр **Name** исключается с помощью функции `Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-204">The first example uses the `Get-Help` cmdlet, the second uses the `Help` function, and the third omits the **Name** parameter when using the `Help` function.</span></span> <span data-ttu-id="57e39-205">**Name** является позиционным параметром и используется в этом примере позиционно.</span><span class="sxs-lookup"><span data-stu-id="57e39-205">**Name** is a positional parameter and it's being used positionally in that example.</span></span> <span data-ttu-id="57e39-206">То есть это значение можно указать без имени параметра, если само это значение указано в правильном положении.</span><span class="sxs-lookup"><span data-stu-id="57e39-206">This means the value can be specified without specifying the parameter name, as long as the value itself is specified in the correct position.</span></span> <span data-ttu-id="57e39-207">Как узнать, в каком положении указывать значение?</span><span class="sxs-lookup"><span data-stu-id="57e39-207">How did I know what position to specify the value in?</span></span> <span data-ttu-id="57e39-208">Свериться со справкой, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="57e39-208">By reading the help as shown in the following example.</span></span>

```powershell
help Get-Help -Parameter Name
```

```Output
-Name <String>
    Gets help about the specified command or concept. Enter the name of a cmdlet, function,
    provider, script, or workflow, such as Get-Member, a conceptual article name, such as
    about_Objects, or an alias, such as ls. Wildcard characters are permitted in cmdlet and
    provider names, but you can't use wildcard characters to find the names of function help and
    script help articles.

    To get help for a script that isn't located in a path that's listed in the $env:Path
    environment variable, type the script's path and file name.

    If you enter the exact name of a help article, Get-Help displays the article contents.

    If you enter a word or word pattern that appears in several help article titles, Get-Help
    displays a list of the matching titles.

    If you enter a word that doesn't match any help article titles, Get-Help displays a list of
    articles that include that word in their contents.

    The names of conceptual articles, such as about_Objects, must be entered in English, even in
    non-English versions of PowerShell.

    Required?                    false
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  true
```

<span data-ttu-id="57e39-209">Заметьте, что в предыдущем примере параметр **Parameter** использовался вместе с функцией справки только для того, чтобы вернуть данные из раздела справки для параметра **Name**.</span><span class="sxs-lookup"><span data-stu-id="57e39-209">Notice that in the previous example, the **Parameter** parameter was used with the Help function to only return information from the help topic for the **Name** parameter.</span></span> <span data-ttu-id="57e39-210">Так намного точнее, чем пытаться вручную проверять то, что напоминает раздел справки в сто страниц.</span><span class="sxs-lookup"><span data-stu-id="57e39-210">This is much more concise than trying to manually sift through what sometimes seems like a hundred page help topic.</span></span>

<span data-ttu-id="57e39-211">На основе полученных результатов вы увидите, что параметр **Name** является позиционным и его нужно указать в нулевом положении (первое положение), если он используется позиционно.</span><span class="sxs-lookup"><span data-stu-id="57e39-211">Based on those results, you can see that the **Name** parameter is positional and must be specified in position zero (the first position) when used positionally.</span></span> <span data-ttu-id="57e39-212">Если указывается имя параметра, порядок указания параметров не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="57e39-212">The order that parameters are specified in doesn't matter if the parameter name is specified.</span></span>

<span data-ttu-id="57e39-213">Еще одна важная деталь: в параметре **Name** значение типа данных должно быть указано одной строкой, которая обозначается `<String>`.</span><span class="sxs-lookup"><span data-stu-id="57e39-213">One other important piece of information is that the **Name** parameter expects the datatype for its value to be a single string, which is denoted by `<String>`.</span></span> <span data-ttu-id="57e39-214">Если допускается несколько строк, тип данных будет приведен как `<String[]>`.</span><span class="sxs-lookup"><span data-stu-id="57e39-214">If it accepted multiple strings, the datatype would be listed as `<String[]>`.</span></span>

<span data-ttu-id="57e39-215">Может быть так, что вам не нужно выводить для команды весь раздел справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-215">Sometimes you simply don't want to display the entire help topic for a command.</span></span> <span data-ttu-id="57e39-216">Помимо параметра **Full**, существуют другие параметры, которые можно указать с помощью `Get-Help` или `Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-216">There are a number of other parameters besides **Full** that can be specified with `Get-Help` or `Help`.</span></span> <span data-ttu-id="57e39-217">Попробуйте выполнить следующие команды на компьютере с Windows 10 в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="57e39-217">Try running the following commands on your Windows 10 lab environment computer:</span></span>

```powershell
Get-Help -Name Get-Command -Full
Get-Help -Name Get-Command -Detailed
Get-Help -Name Get-Command -Examples
Get-Help -Name Get-Command -Online
Get-Help -Name Get-Command -Parameter Noun
Get-Help -Name Get-Command -ShowWindow
```

<span data-ttu-id="57e39-218">Как правило, вместе с `help <command name>` я использую параметр **Full** или **Online**.</span><span class="sxs-lookup"><span data-stu-id="57e39-218">I typically use `help <command name>` with the **Full** or **Online** parameter.</span></span> <span data-ttu-id="57e39-219">Если мне нужно посмотреть только примеры, я использую параметр **Examples**, а если мне нужно получить только конкретный параметр, я использую параметр **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="57e39-219">If I'm only interested in the examples, I'll use the **Examples** parameter and if I'm only interested in a specific parameter, I'll use the **Parameter** parameter.</span></span> <span data-ttu-id="57e39-220">Параметр **ShowWindow** открывает раздел справки в отдельном окне с возможностью поиска, которое можно открыть на другом мониторе, если их у вас несколько.</span><span class="sxs-lookup"><span data-stu-id="57e39-220">The **ShowWindow** parameter opens the help topic in a separate searchable window that can be placed on a different monitor if you have multiple monitors.</span></span> <span data-ttu-id="57e39-221">Я стараюсь не использовать параметр **ShowWindow**, потому что он содержит всем известную ошибку, при которой не выводится весь раздел справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-221">I've avoided the **ShowWindow** parameter because there's a known bug where it doesn't display the entire help topic.</span></span>

<span data-ttu-id="57e39-222">Если нужно открыть справку в отдельном окне, рекомендую использовать параметры **Online** или **Full** и передать результаты в `Out-GridView`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="57e39-222">If you want help in a separate window, my recommendation is to either use the **Online** parameter or use the **Full** parameter and pipe the results to `Out-GridView`, as shown in the following example.</span></span>

```powershell
help Get-Command -Full | Out-GridView
```

<span data-ttu-id="57e39-223">Для использования командлета `Out-GridView` и параметра **ShowWindow** командлета `Get-Help` требуется операционная система с графическим интерфейсом пользователя (GUI).</span><span class="sxs-lookup"><span data-stu-id="57e39-223">Both the `Out-GridView` cmdlet and the **ShowWindow** parameter of the `Get-Help` cmdlet require an operating system with a GUI (Graphical User Interface).</span></span> <span data-ttu-id="57e39-224">Они выводят сообщение об ошибке при попытке использовать любой из них в Windows Server, который установлен с помощью варианта установки Server Core (без GUI).</span><span class="sxs-lookup"><span data-stu-id="57e39-224">They will generate an error message if you attempt to use either of them on Windows Server that's been installed using the server core (no-GUI) installation option.</span></span>

<span data-ttu-id="57e39-225">Чтобы использовать `Get-Help` для поиска команд, используйте подстановочный знак звездочки (`*`) вместе с параметром **Name**.</span><span class="sxs-lookup"><span data-stu-id="57e39-225">To use `Get-Help` to find commands, use the asterisk (`*`) wildcard character with the **Name** parameter.</span></span> <span data-ttu-id="57e39-226">Укажите термин, в котором выполняется поиск команд, в качестве значения параметра **Name**, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="57e39-226">Specify a term that you're searching for commands on as the value for the **Name** parameter as shown in the following example.</span></span>

```powershell
help *process*
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
Exit-PSHostProcess                Cmdlet    Microsoft.PowerShell.Core Closes an intera...
Get-PSHostProcessInfo             Cmdlet    Microsoft.PowerShell.Core
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-AppvVirtualProcess            Function  AppvClient                ...
Start-AppvVirtualProcess          Function  AppvClient                ...
```

<span data-ttu-id="57e39-227">В предыдущем примере подстановочные знаки `*` добавлять необязательно, без них результат будет одинаковым.</span><span class="sxs-lookup"><span data-stu-id="57e39-227">In the previous example, the `*` wildcard characters are not required and omitting them produces the same result.</span></span> <span data-ttu-id="57e39-228">`Get-Help` автоматически добавляет подстановочные знаки в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="57e39-228">`Get-Help` automatically adds the wildcard characters behind the scenes.</span></span>

```powershell
help process
```

<span data-ttu-id="57e39-229">Предыдущая команда выдает те же результаты, что и при указании подстановочного знака `*` при каждом завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="57e39-229">The previous command produces the same results as specifying the `*` wildcard character on each end of process.</span></span>

<span data-ttu-id="57e39-230">Я предпочитаю добавлять подстановочные знаки, так как этот вариант всегда работает стабильно.</span><span class="sxs-lookup"><span data-stu-id="57e39-230">I prefer to add them since that's the option that always works consistently.</span></span> <span data-ttu-id="57e39-231">В остальных случаях именно эти знаки, а не какие-либо другие необходимо использовать в определенных сценариях.</span><span class="sxs-lookup"><span data-stu-id="57e39-231">Otherwise, they are required in certain scenarios and not others.</span></span> <span data-ttu-id="57e39-232">Если добавить подстановочный знак в середину значения, он больше не будет к нему автоматически добавляться в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="57e39-232">As soon as you add a wildcard character in the middle of the value, they're no longer automatically added behind the scenes to the value you specified.</span></span>

```powershell
help pr*cess
```

<span data-ttu-id="57e39-233">Эта команда не возвращает результаты, если подстановочный знак `*` добавляется в начало, конец или в начало и конец командлета `pr*cess`.</span><span class="sxs-lookup"><span data-stu-id="57e39-233">No results are returned by that command unless the `*` wildcard character is added to the beginning, end, or both the beginning and end of `pr*cess`.</span></span>

<span data-ttu-id="57e39-234">Если указанное значение начинается с тире, создается ошибка, так как PowerShell интерпретирует его как имя параметра, а имени параметра для командлета `Get-Help` не существует.</span><span class="sxs-lookup"><span data-stu-id="57e39-234">If the value you specified begins with a dash, then an error is generated because PowerShell interprets it as a parameter name and no such parameter name exists for the `Get-Help` cmdlet.</span></span>

```powershell
help -process
```

<span data-ttu-id="57e39-235">При попытке найти команды, которые заканчиваются на `-process`, нужно в начало значения добавить только подстановочный знак `*`.</span><span class="sxs-lookup"><span data-stu-id="57e39-235">If what you're attempting to look for are commands that end with `-process`, you only need to add the `*` wildcard character to the beginning of the value.</span></span>

```powershell
help *-process
```

<span data-ttu-id="57e39-236">При поиске команд PowerShell с помощью `Get-Help` нужно указывать менее точные параметры поиска.</span><span class="sxs-lookup"><span data-stu-id="57e39-236">When searching for PowerShell commands with `Get-Help`, you want to be a little more vague instead of being too specific with what you're searching for.</span></span>

<span data-ttu-id="57e39-237">При предыдущем поиске командлета `process` были найдены только те команды, которые содержали в имени `process` и возвращали только эти результаты.</span><span class="sxs-lookup"><span data-stu-id="57e39-237">Searching for `process` earlier found only commands that contained `process` in the name of the command and returned only those results.</span></span> <span data-ttu-id="57e39-238">Если командлет `Get-Help` будет использоваться для поиска `processes`, он не найдет совпадений для имен команд, поэтому будет выполнять поиск каждого раздела справки в PowerShell в системе и возвращать все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="57e39-238">When `Get-Help` is used to search for `processes`, it doesn't find any matches for command names, so it performs a search of every help topic in PowerShell on your system and returns any matches it finds.</span></span> <span data-ttu-id="57e39-239">Это приведет к возврату большого количества результатов.</span><span class="sxs-lookup"><span data-stu-id="57e39-239">This causes it to return an enormous number of results.</span></span>

```powershell
Get-Help processes
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Disconnect-PSSession              Cmdlet    Microsoft.PowerShell.Core Disconnects from...
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
ForEach-Object                    Cmdlet    Microsoft.PowerShell.Core Performs an oper...
Get-PSSessionConfiguration        Cmdlet    Microsoft.PowerShell.Core Gets the registe...
New-PSTransportOption             Cmdlet    Microsoft.PowerShell.Core Creates an objec...
Out-Host                          Cmdlet    Microsoft.PowerShell.Core Sends output to ...
Where-Object                      Cmdlet    Microsoft.PowerShell.Core Selects objects ...
Clear-Variable                    Cmdlet    Microsoft.PowerShell.U... Deletes the valu...
Compare-Object                    Cmdlet    Microsoft.PowerShell.U... Compares two set...
Convert-String                    Cmdlet    Microsoft.PowerShell.U... Formats a string...
ConvertFrom-Csv                   Cmdlet    Microsoft.PowerShell.U... Converts object ...
ConvertTo-Html                    Cmdlet    Microsoft.PowerShell.U... Converts Microso...
ConvertTo-Xml                     Cmdlet    Microsoft.PowerShell.U... Creates an XML-b...
Debug-Runspace                    Cmdlet    Microsoft.PowerShell.U... Starts an intera...
Export-Csv                        Cmdlet    Microsoft.PowerShell.U... Converts objects...
Export-FormatData                 Cmdlet    Microsoft.PowerShell.U... Saves formatting...
Format-List                       Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Format-Table                      Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Get-Random                        Cmdlet    Microsoft.PowerShell.U... Gets a random nu...
Get-Unique                        Cmdlet    Microsoft.PowerShell.U... Returns unique i...
Group-Object                      Cmdlet    Microsoft.PowerShell.U... Groups objects t...
Import-Clixml                     Cmdlet    Microsoft.PowerShell.U... Imports a CLIXML...
Import-Csv                        Cmdlet    Microsoft.PowerShell.U... Creates table-li...
Measure-Object                    Cmdlet    Microsoft.PowerShell.U... Calculates the n...
Out-File                          Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Out-GridView                      Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Select-Object                     Cmdlet    Microsoft.PowerShell.U... Selects objects ...
Set-Variable                      Cmdlet    Microsoft.PowerShell.U... Sets the value o...
Sort-Object                       Cmdlet    Microsoft.PowerShell.U... Sorts objects by...
Tee-Object                        Cmdlet    Microsoft.PowerShell.U... Saves command ou...
Trace-Command                     Cmdlet    Microsoft.PowerShell.U... Configures and s...
Write-Output                      Cmdlet    Microsoft.PowerShell.U... Sends the specif...
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Get-WmiObject                     Cmdlet    Microsoft.PowerShell.M... Gets instances o...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-Counter                       Cmdlet    Microsoft.PowerShell.D... Gets performance...
Invoke-WSManAction                Cmdlet    Microsoft.WSMan.Manage... Invokes an actio...
Remove-WSManInstance              Cmdlet    Microsoft.WSMan.Manage... Deletes a manage...
Get-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Displays managem...
New-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Creates a new in...
Set-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Modifies the man...
about_Arithmetic_Operators        HelpFile                            Describes the op...
about_Arrays                      HelpFile                            Describes arrays...
about_Debuggers                   HelpFile                            Describes the Wi...
about_Execution_Policies          HelpFile                            Describes the Wi...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Foreach                     HelpFile                            Describes a lang...
about_Functions                   HelpFile                            Describes how to...
about_Language_Keywords           HelpFile                            Describes the ke...
about_Methods                     HelpFile                            Describes how to...
about_Objects                     HelpFile                            Provides essenti...
about_Parallel                    HelpFile                            Describes the Pa...
about_Pipelines                   HelpFile                            Combining comman...
about_Preference_Variables        HelpFile                            Variables that c...
about_Remote                      HelpFile                            Describes how to...
about_Remote_Output               HelpFile                            Describes how to...
about_Sequence                    HelpFile                            Describes the Se...
about_Session_Configuration_Files HelpFile                            Describes sessio...
about_Variables                   HelpFile                            Describes how va...
about_Windows_PowerShell_5.0      HelpFile                            Describes new fe...
about_WQL                         HelpFile                            Describes WMI Qu...
about_WS-Management_Cmdlets       HelpFile                            Provides an over...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Parallel                    HelpFile                            Describes the Pa...
about_Sequence                    HelpFile                            Describes the Se...
```

<span data-ttu-id="57e39-240">С помощью `Help` для поиска `process` вернулось 10 результатов, а для поиска `processes` — 68.</span><span class="sxs-lookup"><span data-stu-id="57e39-240">Using `Help` to search for `process` returned 10 results and using it to search for `processes` returned 68 results.</span></span> <span data-ttu-id="57e39-241">Если найден только один результат, вместо списка команд будет отображаться раздел справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-241">If only one result is found, the help topic itself will be displayed instead of a list of commands.</span></span>

```powershell
get-help *hotfix*
```

```Output
NAME
    Get-HotFix

SYNOPSIS
    Gets the hotfixes that have been applied to the local and remote computers.


SYNTAX
    Get-HotFix [-ComputerName <String[]>] [-Credential <PSCredential>] [-Description
    <String[]>] [<CommonParameters>]

    Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential
    <PSCredential>] [<CommonParameters>]


DESCRIPTION
    The Get-Hotfix cmdlet gets hotfixes (also called updates) that have been installed
    on either the local computer (or on specified remote computers) by Windows Update,
    Microsoft Update, or Windows Server Update Services; the cmdlet also gets hotfixes
    or updates that have been installed manually by users.


RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821586
    Win32_QuickFixEngineering http://go.microsoft.com/fwlink/?LinkID=145071
    Get-ComputerRestorePoint
    Add-Content

REMARKS
    To see the examples, type: "get-help Get-HotFix -examples".
    For more information, type: "get-help Get-HotFix -detailed".
    For technical information, type: "get-help Get-HotFix -full".
    For online help, type: "get-help Get-HotFix -online"
```

<span data-ttu-id="57e39-242">Теперь давайте развеем миф о том, что `Help` в PowerShell может находить только команды, содержащие разделы справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-242">Now to debunk the myth that `Help` in PowerShell can only find commands that have help topics.</span></span>

```powershell
help *more*
```

```Output
NAME
    more

SYNTAX
    more [[-paths] <string[]>]


ALIASES
    None


REMARKS
    None
```

<span data-ttu-id="57e39-243">Заметьте, в предыдущем примере `more` не содержит раздела справки, но системе `Help` в PowerShell удалось ее найти.</span><span class="sxs-lookup"><span data-stu-id="57e39-243">Notice in the previous example that `more` doesn't have a help topic, yet the `Help` system in PowerShell was able to find it.</span></span> <span data-ttu-id="57e39-244">Система нашла только одно совпадение и вернула основные сведения о синтаксисе, которые будут отображаться, если команда не содержит раздела справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-244">It only found one match and returned the basic syntax information that you'll see when a command doesn't have a help topic.</span></span>

<span data-ttu-id="57e39-245">PowerShell содержит множество концептуальных разделов справки ("О программе").</span><span class="sxs-lookup"><span data-stu-id="57e39-245">PowerShell contains numerous conceptual (About) help topics.</span></span> <span data-ttu-id="57e39-246">Следующая команда используется для возврата списка всех разделов **О программе** в системе.</span><span class="sxs-lookup"><span data-stu-id="57e39-246">The following command can be used to return a list of all **About** help topics on your system.</span></span>

```powershell
help About_*
```

<span data-ttu-id="57e39-247">При ограничении результатов одним из разделов справки "О программе" вместо возврата списка отображается действительный раздел.</span><span class="sxs-lookup"><span data-stu-id="57e39-247">Limiting the results to one single About help topic displays the actual help topic instead of returning a list.</span></span>

```powershell
help about_Updatable_Help
```

<span data-ttu-id="57e39-248">Для отображения разделов справки **О программе** справочную систему в PowerShell необходимо обновлять.</span><span class="sxs-lookup"><span data-stu-id="57e39-248">The help system in PowerShell has to be updated in order for the **About** help topics to be present.</span></span> <span data-ttu-id="57e39-249">Если по какой-либо причине не удалось выполнить первоначальное обновление системы справки на компьютере, эти файлы будут недоступны, пока командлет `Update-Help` не будет успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="57e39-249">If for some reason the initial update of the help system failed on your computer, the files will not be available until the `Update-Help` cmdlet has been run successfully.</span></span>

## <a name="get-command"></a><span data-ttu-id="57e39-250">Get-Command</span><span class="sxs-lookup"><span data-stu-id="57e39-250">Get-Command</span></span>

<span data-ttu-id="57e39-251">`Get-Command` облегчает поиск команд.</span><span class="sxs-lookup"><span data-stu-id="57e39-251">`Get-Command` is designed to help you locate commands.</span></span> <span data-ttu-id="57e39-252">Выполнение `Get-Command` без указания параметров возвращает список всех команд в системе.</span><span class="sxs-lookup"><span data-stu-id="57e39-252">Running `Get-Command` without any parameters returns a list of all the commands on your system.</span></span> <span data-ttu-id="57e39-253">В приведенном ниже примере показано использование командлета `Get-Command`, который определяет команды, работающие с процессами.</span><span class="sxs-lookup"><span data-stu-id="57e39-253">The following example demonstrates using the `Get-Command` cmdlet to determine what commands exist for working with processes:</span></span>

```powershell
Get-Command -Noun Process
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsof...
Cmdlet          Get-Process                                        3.1.0.0    Microsof...
Cmdlet          Start-Process                                      3.1.0.0    Microsof...
Cmdlet          Stop-Process                                       3.1.0.0    Microsof...
Cmdlet          Wait-Process                                       3.1.0.0    Microsof...
```

<span data-ttu-id="57e39-254">Заметьте: в предыдущем примере, где выполнялся командлет `Get-Command`, используется параметр **Noun**, а командлет `Process` указан в качестве значения для параметра **Noun**.</span><span class="sxs-lookup"><span data-stu-id="57e39-254">Notice in the previous example where `Get-Command` was run, the **Noun** parameter is used and `Process` is specified as the value for the **Noun** parameter.</span></span> <span data-ttu-id="57e39-255">Что делать, если вы не знаете, как использовать командлет `Get-Command`?</span><span class="sxs-lookup"><span data-stu-id="57e39-255">What if you didn't know how to use the `Get-Command` cmdlet?</span></span> <span data-ttu-id="57e39-256">`Get-Help` можно использовать для вывода раздела справки для `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="57e39-256">You could use `Get-Help` to display the help topic for `Get-Command`.</span></span>

<span data-ttu-id="57e39-257">Параметры **Name**, **Noun** и **Verb** поддерживают добавление подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="57e39-257">The **Name**, **Noun**, and **Verb** parameters accept wildcards.</span></span> <span data-ttu-id="57e39-258">В приведенном ниже примере показаны подстановочные знаки, используемые с параметром **Name**.</span><span class="sxs-lookup"><span data-stu-id="57e39-258">The following example shows wildcards being used with the **Name** parameter:</span></span>

```Output
Get-Command -Name *service*
```

```powershell
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Function        Set-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          New-Service                                        3.1.0.0    Microsof...
Cmdlet          New-WebServiceProxy                                3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
Application     AgentService.exe                                   10.0.14... C:\Windo...
Application     SensorDataService.exe                              10.0.14... C:\Windo...
Application     services.exe                                       10.0.14... C:\Windo...
Application     services.msc                                       0.0.0.0    C:\Windo...
Application     TieringEngineService.exe                           10.0.14... C:\Windo...
```

<span data-ttu-id="57e39-259">Я стараюсь не использовать подстановочные знаки с параметром **Name** для `Get-Command`, так как он возвращает и исполняемые файлы, которые не являются собственными командами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e39-259">I'm not a fan of using wildcards with the **Name** parameter of `Get-Command` since it also returns executable files that are not native PowerShell commands.</span></span>

<span data-ttu-id="57e39-260">При использовании подстановочных знаков с параметром **Name** рекомендую ограничить результаты с помощью параметра **CommandType**.</span><span class="sxs-lookup"><span data-stu-id="57e39-260">If you are going to use wildcard characters with the **Name** parameter, I recommend limiting the results with the **CommandType** parameter.</span></span>

```powershell
Get-Command -Name *service* -CommandType Cmdlet, Function, Alias
```

<span data-ttu-id="57e39-261">Оптимально использовать параметр **Verb** или **Noun** либо оба этих параметра, так как только команды PowerShell состоят из глаголов и существительных.</span><span class="sxs-lookup"><span data-stu-id="57e39-261">A better option is to use either the **Verb** or **Noun** parameter or both of them since only PowerShell commands have both verbs and nouns.</span></span>

<span data-ttu-id="57e39-262">Что делать, есть в разделе справки найдены ошибки?</span><span class="sxs-lookup"><span data-stu-id="57e39-262">Found something wrong with a help topic?</span></span> <span data-ttu-id="57e39-263">Можете не волноваться: материалы разделов справки в PowerShell открыты и доступны в репозитории [PowerShell-Docs][] на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="57e39-263">The good news is the help topics for PowerShell have been open-sourced and available in the [PowerShell-Docs][] repository on GitHub.</span></span> <span data-ttu-id="57e39-264">Исправив неверную информацию, вы поможете не только себе, но и другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="57e39-264">Pay it forward by not only fixing the incorrect information for yourself, but everyone else as well.</span></span> <span data-ttu-id="57e39-265">Для этого разместите репозиторий документации PowerShell на сайте GitHub, обновите раздел справки и отправьте запрос на включение внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="57e39-265">Simply fork the PowerShell documentation repository on GitHub, update the help topic, and submit a pull request.</span></span>
<span data-ttu-id="57e39-266">После того как этот запрос будет принят, исправленный документ появится в общем доступе.</span><span class="sxs-lookup"><span data-stu-id="57e39-266">Once the pull request is accepted, the corrected documentation is available for everyone.</span></span>

## <a name="updating-help"></a><span data-ttu-id="57e39-267">Обновление справки</span><span class="sxs-lookup"><span data-stu-id="57e39-267">Updating Help</span></span>

<span data-ttu-id="57e39-268">Локальная копия разделов справки PowerShell была ранее впервые обновлена с помощью запрошенной команды.</span><span class="sxs-lookup"><span data-stu-id="57e39-268">The local copy of the PowerShell help topics was previously updated the first-time help on a command was requested.</span></span> <span data-ttu-id="57e39-269">Рекомендуется периодически обновлять справочную систему, так как содержимое справки может обновляться.</span><span class="sxs-lookup"><span data-stu-id="57e39-269">It's recommended to periodically update the help system because there can be updates to the help content from time to time.</span></span> <span data-ttu-id="57e39-270">Для обновления разделов справки используется командлет `Update-Help`.</span><span class="sxs-lookup"><span data-stu-id="57e39-270">The `Update-Help` cmdlet is used to update the help topics.</span></span>
<span data-ttu-id="57e39-271">Для этого требуется доступ к Интернету по умолчанию, а вам необходимо запустить PowerShell с повышенными правами администратора.</span><span class="sxs-lookup"><span data-stu-id="57e39-271">It requires internet access by default and for you to be running PowerShell elevated as an administrator.</span></span>

```powershell
Update-Help
```

```Output
Update-Help : Failed to update Help for the module(s) 'BitsTransfer' with UI culture(s)
{en-US} : The value of the HelpInfoUri key in the module manifest must resolve to a
container or root URL on a website where the help files are stored. The HelpInfoUri
'https://technet.microsoft.com/en-us/library/dd819413.aspx' does not resolve to a
container.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : InvalidOperation: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : InvalidHelpInfoUri,Microsoft.PowerShell.Commands.UpdateHel
   pCommand

Update-Help : Failed to update Help for the module(s) 'NetworkControllerDiagnostics,
StorageReplica' with UI culture(s) {en-US} : Unable to retrieve the HelpInfo XML file
for UI culture en-US. Make sure the HelpInfoUri property in the module manifest is valid
or check your network connection and then try the command again.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : ResourceUnavailable: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : UnableToRetrieveHelpInfoXml,Microsoft.PowerShell.Commands.
   UpdateHelpCommand
```

<span data-ttu-id="57e39-272">Два модуля вернули распространенные ошибки.</span><span class="sxs-lookup"><span data-stu-id="57e39-272">A couple of the modules returned errors, which is not uncommon.</span></span> <span data-ttu-id="57e39-273">Если на компьютере отсутствует доступ к Интернету, можно использовать командлет `Save-Help` на другом компьютере с доступом к Интернету, чтобы сначала сохранить обновленную справочную информацию в общей папке, а затем использовать параметр **SourcePath** для `Update-Help`, чтобы указать это сетевое расположение для разделов справки.</span><span class="sxs-lookup"><span data-stu-id="57e39-273">If the machine didn't have internet access, you could use the `Save-Help` cmdlet on another machine that does have internet access to first save the updated help information to a file share on your network and then use the **SourcePath** parameter of `Update-Help` to specify this network location for the help topics.</span></span>

<span data-ttu-id="57e39-274">Для периодического обновления содержимого справки на компьютере настройте запланированную задачу или добавление логики в скрипт профилирования в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e39-274">Consider setting up a scheduled task or adding some logic to your profile script in PowerShell to periodically update the help content on your computer.</span></span> <span data-ttu-id="57e39-275">Сценарии профилирования будут рассматриваться в следующей главе.</span><span class="sxs-lookup"><span data-stu-id="57e39-275">Profile scripts will be discussed in an upcoming chapter.</span></span>

## <a name="summary"></a><span data-ttu-id="57e39-276">Сводка</span><span class="sxs-lookup"><span data-stu-id="57e39-276">Summary</span></span>

<span data-ttu-id="57e39-277">В этой главе вы узнали, как найти команды с помощью командлетов `Get-Help` и `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="57e39-277">In this chapter you've learned how to find commands with both `Get-Help` and `Get-Command`.</span></span> <span data-ttu-id="57e39-278">Кроме того, вы научились пользоваться справочной системой, которая позволяет использовать найденные команды.</span><span class="sxs-lookup"><span data-stu-id="57e39-278">You've learned how to use the help system to figure out how to use commands once you find them.</span></span> <span data-ttu-id="57e39-279">Мы также рассмотрели, как обновлять содержимое разделов справки при доступных обновлениях.</span><span class="sxs-lookup"><span data-stu-id="57e39-279">You've also learned how to update the content of the help topics when updates are available.</span></span>

<span data-ttu-id="57e39-280">Мне нужно, чтобы вы изучали по одной команде PowerShell в день.</span><span class="sxs-lookup"><span data-stu-id="57e39-280">My challenge to you is to learn a PowerShell command a day.</span></span>

```powershell
Get-Command | Get-Random | Get-Help -Full
```

## <a name="review"></a><span data-ttu-id="57e39-281">Просмотр</span><span class="sxs-lookup"><span data-stu-id="57e39-281">Review</span></span>

1. <span data-ttu-id="57e39-282">Является ли параметр **DisplayName** `Get-Service` позиционным?</span><span class="sxs-lookup"><span data-stu-id="57e39-282">Is the **DisplayName** parameter of `Get-Service` positional?</span></span>
1. <span data-ttu-id="57e39-283">Сколько наборов параметров содержится в командлете `Get-Process`?</span><span class="sxs-lookup"><span data-stu-id="57e39-283">How many parameter sets does the `Get-Process` cmdlet have?</span></span>
1. <span data-ttu-id="57e39-284">Какие команды PowerShell используются для работы с журналами событий?</span><span class="sxs-lookup"><span data-stu-id="57e39-284">What PowerShell commands exist for working with event logs?</span></span>
1. <span data-ttu-id="57e39-285">Какая команда PowerShell возвращает список процессов PowerShell, запущенных на компьютере?</span><span class="sxs-lookup"><span data-stu-id="57e39-285">What is the PowerShell command for returning a list of PowerShell processes running on your computer?</span></span>
1. <span data-ttu-id="57e39-286">Как обновить содержимое справки PowerShell, сохраненное на компьютере?</span><span class="sxs-lookup"><span data-stu-id="57e39-286">How do you update the PowerShell help content that's stored on your computer?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="57e39-287">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="57e39-287">Recommended Reading</span></span>

<span data-ttu-id="57e39-288">Если вы хотите более подробно изучить темы, описанные в этой главе, рекомендую ознакомиться со следующими разделами справки по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57e39-288">If you want to know more information about the topics covered in this chapter, I recommend reading the following PowerShell help topics.</span></span>

- <span data-ttu-id="57e39-289">[Get-Help][]</span><span class="sxs-lookup"><span data-stu-id="57e39-289">[Get-Help][]</span></span>
- <span data-ttu-id="57e39-290">[Get-Command][]</span><span class="sxs-lookup"><span data-stu-id="57e39-290">[Get-Command][]</span></span>
- <span data-ttu-id="57e39-291">[Update-Help][]</span><span class="sxs-lookup"><span data-stu-id="57e39-291">[Update-Help][]</span></span>
- <span data-ttu-id="57e39-292">[Save-Help][]</span><span class="sxs-lookup"><span data-stu-id="57e39-292">[Save-Help][]</span></span>
- <span data-ttu-id="57e39-293">[about_Updatable_Help][]</span><span class="sxs-lookup"><span data-stu-id="57e39-293">[about_Updatable_Help][]</span></span>
- <span data-ttu-id="57e39-294">[about_Command_Syntax][]</span><span class="sxs-lookup"><span data-stu-id="57e39-294">[about_Command_Syntax][]</span></span>

<span data-ttu-id="57e39-295">В следующей главе вы узнаете о командлете `Get-Member`, а также об объектах, свойствах и методах.</span><span class="sxs-lookup"><span data-stu-id="57e39-295">In the next chapter, you'll learn about the `Get-Member` cmdlet as well as objects, properties, and methods.</span></span>

<!-- link references -->
[Get-Help]: /powershell/module/microsoft.powershell.core/get-help
[Get-Command]: /powershell/module/microsoft.powershell.core/get-command
[Update-Help]: /powershell/module/microsoft.powershell.core/update-help
[Save-Help]: /powershell/module/microsoft.powershell.core/save-help
[about_Updatable_Help]: /powershell/module/microsoft.powershell.core/about/about_updatable_help
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[PowerShell-Docs]: https://github.com/powershell/powershell
[Приложение А]: appendix-a.md
[Appendix A]: appendix-a.md
