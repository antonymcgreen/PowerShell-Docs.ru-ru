---
ms.date: 08/27/2018
keywords: powershell,командлет
title: Использование знакомых имен команд
ms.assetid: 021e2424-c64e-4fa5-aa98-aa6405758d5d
ms.openlocfilehash: c5665f64fd832eb9c807f413a8e879f63db7f8c6
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403511"
---
# <a name="using-familiar-command-names"></a><span data-ttu-id="b826c-103">Использование знакомых имен команд</span><span class="sxs-lookup"><span data-stu-id="b826c-103">Using familiar command names</span></span>

<span data-ttu-id="b826c-104">PowerShell поддерживает псевдонимы для вызова команд с помощью альтернативных имен.</span><span class="sxs-lookup"><span data-stu-id="b826c-104">PowerShell supports aliases to refer to commands by alternate names.</span></span> <span data-ttu-id="b826c-105">Благодаря наличию псевдонимов пользователи с опытом работы с другими оболочками могут использовать уже известные им распространенные имена команд для выполнения схожих операций в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b826c-105">Aliasing allows users with experience in other shells to use common command names that they already know for similar operations in PowerShell.</span></span>

<span data-ttu-id="b826c-106">Механизм псевдонимов заключается в связывании нового имени с определенной командой.</span><span class="sxs-lookup"><span data-stu-id="b826c-106">Aliasing associates a new name with another command.</span></span> <span data-ttu-id="b826c-107">Например, в PowerShell есть внутренняя функция с именем `Clear-Host`, которая очищает командное окно.</span><span class="sxs-lookup"><span data-stu-id="b826c-107">For example, PowerShell has an internal function named `Clear-Host` that clears the output window.</span></span> <span data-ttu-id="b826c-108">Вы можете ввести в командной строке псевдоним `cls` или `clear`.</span><span class="sxs-lookup"><span data-stu-id="b826c-108">You can type either the `cls` or `clear` alias at a command prompt.</span></span> <span data-ttu-id="b826c-109">PowerShell интерпретирует эти псевдонимы и запускает функцию `Clear-Host`.</span><span class="sxs-lookup"><span data-stu-id="b826c-109">PowerShell interprets these aliases and runs the `Clear-Host` function.</span></span>

<span data-ttu-id="b826c-110">Это помогает пользователям изучать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b826c-110">This feature helps users to learn PowerShell.</span></span> <span data-ttu-id="b826c-111">Большинство пользователей **cmd.exe** и Unix используют обширный набор команд со знакомыми именами.</span><span class="sxs-lookup"><span data-stu-id="b826c-111">First, most **cmd.exe** and Unix users have a large repertoire of commands that users already know by name.</span></span> <span data-ttu-id="b826c-112">Их эквиваленты в PowerShell могут возвращать отличающиеся результаты.</span><span class="sxs-lookup"><span data-stu-id="b826c-112">The PowerShell equivalents may not produce identical results.</span></span> <span data-ttu-id="b826c-113">Но эти результаты достаточно схожи, чтобы пользователи могли работать, не зная имя соответствующей команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b826c-113">However, the results are close enough that users can do work without knowing the PowerShell command name.</span></span> <span data-ttu-id="b826c-114">Моторная память — еще один источник неудобств при изучении новой командной оболочки.</span><span class="sxs-lookup"><span data-stu-id="b826c-114">"Finger memory" is another major source of frustration when learning a new command shell.</span></span> <span data-ttu-id="b826c-115">Если вы много лет использовали **cmd.exe**, вы можете по привычке ввести команду `cls`, чтобы очистить экран.</span><span class="sxs-lookup"><span data-stu-id="b826c-115">If you have used **cmd.exe** for years, you might reflexively type the `cls` command to clear the screen.</span></span> <span data-ttu-id="b826c-116">Если псевдоним для `Clear-Host` не настроен, вы получите сообщение об ошибке и не будете знать, как очистить экран.</span><span class="sxs-lookup"><span data-stu-id="b826c-116">Without the alias for `Clear-Host`, you receive an error message and won't know what to do to clear the output.</span></span>

<span data-ttu-id="b826c-117">В списке ниже перечислен ряд распространенных команд **cmd.exe** и Unix, которые можно использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b826c-117">The following list shows a few of the common **cmd.exe** and Unix commands that you can use in PowerShell:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="b826c-118">cat</span><span class="sxs-lookup"><span data-stu-id="b826c-118">cat</span></span>|<span data-ttu-id="b826c-119">dir</span><span class="sxs-lookup"><span data-stu-id="b826c-119">dir</span></span>|<span data-ttu-id="b826c-120">подключить</span><span class="sxs-lookup"><span data-stu-id="b826c-120">mount</span></span>|<span data-ttu-id="b826c-121">rm</span><span class="sxs-lookup"><span data-stu-id="b826c-121">rm</span></span>|
|<span data-ttu-id="b826c-122">cd</span><span class="sxs-lookup"><span data-stu-id="b826c-122">cd</span></span>|<span data-ttu-id="b826c-123">echo</span><span class="sxs-lookup"><span data-stu-id="b826c-123">echo</span></span>|<span data-ttu-id="b826c-124">move</span><span class="sxs-lookup"><span data-stu-id="b826c-124">move</span></span>|<span data-ttu-id="b826c-125">rmdir</span><span class="sxs-lookup"><span data-stu-id="b826c-125">rmdir</span></span>|
|<span data-ttu-id="b826c-126">chdir</span><span class="sxs-lookup"><span data-stu-id="b826c-126">chdir</span></span>|<span data-ttu-id="b826c-127">erase</span><span class="sxs-lookup"><span data-stu-id="b826c-127">erase</span></span>|<span data-ttu-id="b826c-128">popd</span><span class="sxs-lookup"><span data-stu-id="b826c-128">popd</span></span>|<span data-ttu-id="b826c-129">sleep</span><span class="sxs-lookup"><span data-stu-id="b826c-129">sleep</span></span>|
|<span data-ttu-id="b826c-130">clear</span><span class="sxs-lookup"><span data-stu-id="b826c-130">clear</span></span>|<span data-ttu-id="b826c-131">h</span><span class="sxs-lookup"><span data-stu-id="b826c-131">h</span></span>|<span data-ttu-id="b826c-132">ps</span><span class="sxs-lookup"><span data-stu-id="b826c-132">ps</span></span>|<span data-ttu-id="b826c-133">sort</span><span class="sxs-lookup"><span data-stu-id="b826c-133">sort</span></span>|
|<span data-ttu-id="b826c-134">cls</span><span class="sxs-lookup"><span data-stu-id="b826c-134">cls</span></span>|<span data-ttu-id="b826c-135">history</span><span class="sxs-lookup"><span data-stu-id="b826c-135">history</span></span>|<span data-ttu-id="b826c-136">pushd</span><span class="sxs-lookup"><span data-stu-id="b826c-136">pushd</span></span>|<span data-ttu-id="b826c-137">tee</span><span class="sxs-lookup"><span data-stu-id="b826c-137">tee</span></span>|
|<span data-ttu-id="b826c-138">copy</span><span class="sxs-lookup"><span data-stu-id="b826c-138">copy</span></span>|<span data-ttu-id="b826c-139">kill</span><span class="sxs-lookup"><span data-stu-id="b826c-139">kill</span></span>|<span data-ttu-id="b826c-140">pwd</span><span class="sxs-lookup"><span data-stu-id="b826c-140">pwd</span></span>|<span data-ttu-id="b826c-141">type</span><span class="sxs-lookup"><span data-stu-id="b826c-141">type</span></span>|
|<span data-ttu-id="b826c-142">del</span><span class="sxs-lookup"><span data-stu-id="b826c-142">del</span></span>|<span data-ttu-id="b826c-143">lp</span><span class="sxs-lookup"><span data-stu-id="b826c-143">lp</span></span>|<span data-ttu-id="b826c-144">r</span><span class="sxs-lookup"><span data-stu-id="b826c-144">r</span></span>|<span data-ttu-id="b826c-145">write</span><span class="sxs-lookup"><span data-stu-id="b826c-145">write</span></span>|
|<span data-ttu-id="b826c-146">diff</span><span class="sxs-lookup"><span data-stu-id="b826c-146">diff</span></span>|<span data-ttu-id="b826c-147">ls</span><span class="sxs-lookup"><span data-stu-id="b826c-147">ls</span></span>|<span data-ttu-id="b826c-148">ren</span><span class="sxs-lookup"><span data-stu-id="b826c-148">ren</span></span>||

<span data-ttu-id="b826c-149">Командлет `Get-Alias` показывает исходное имя собственный команды PowerShell, связанной с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="b826c-149">The `Get-Alias` cmdlet shows you the real name of the native PowerShell command associated with an alias.</span></span>

```powershell
PS> Get-Alias cls
```

```Output
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Alias           cls -> Clear-Host
```

## <a name="interpreting-standard-aliases"></a><span data-ttu-id="b826c-150">Интерпретация стандартных псевдонимов</span><span class="sxs-lookup"><span data-stu-id="b826c-150">Interpreting standard aliases</span></span>

<span data-ttu-id="b826c-151">Описанные выше псевдонимы предназначены для обеспечения совместимости имен, используемых в других командных оболочках.</span><span class="sxs-lookup"><span data-stu-id="b826c-151">The aliases we described previous were designed for name-compatibility with other command shells.</span></span>
<span data-ttu-id="b826c-152">Большинство встроенных псевдонимов PowerShell созданы для краткости.</span><span class="sxs-lookup"><span data-stu-id="b826c-152">Most aliases built into PowerShell are designed for brevity.</span></span> <span data-ttu-id="b826c-153">Более короткие имена проще ввести, но их сложнее читать, если не знать, что они означают.</span><span class="sxs-lookup"><span data-stu-id="b826c-153">Shorter names are easier to type, but are difficult to read if you don't know what they refer to.</span></span>

<span data-ttu-id="b826c-154">Псевдонимы PowerShell — это попытка найти компромисс между ясностью и краткостью.</span><span class="sxs-lookup"><span data-stu-id="b826c-154">PowerShell aliases try to compromise between clarity and brevity.</span></span> <span data-ttu-id="b826c-155">PowerShell использует стандартный набор псевдонимов для распространенных существительных и глаголов.</span><span class="sxs-lookup"><span data-stu-id="b826c-155">PowerShell uses a standard set of aliases for common nouns and verbs.</span></span>

<span data-ttu-id="b826c-156">Пример сокращений:</span><span class="sxs-lookup"><span data-stu-id="b826c-156">Example abbreviations:</span></span>

| <span data-ttu-id="b826c-157">Существительное или глагол</span><span class="sxs-lookup"><span data-stu-id="b826c-157">Noun or Verb</span></span> | <span data-ttu-id="b826c-158">Сокращение</span><span class="sxs-lookup"><span data-stu-id="b826c-158">Abbreviation</span></span> |
|--------------|--------------|
| <span data-ttu-id="b826c-159">Get</span><span class="sxs-lookup"><span data-stu-id="b826c-159">Get</span></span>          | <span data-ttu-id="b826c-160">g</span><span class="sxs-lookup"><span data-stu-id="b826c-160">g</span></span>            |
| <span data-ttu-id="b826c-161">Установить</span><span class="sxs-lookup"><span data-stu-id="b826c-161">Set</span></span>          | <span data-ttu-id="b826c-162">s</span><span class="sxs-lookup"><span data-stu-id="b826c-162">s</span></span>            |
| <span data-ttu-id="b826c-163">Элемент</span><span class="sxs-lookup"><span data-stu-id="b826c-163">Item</span></span>         | <span data-ttu-id="b826c-164">i</span><span class="sxs-lookup"><span data-stu-id="b826c-164">i</span></span>            |
| <span data-ttu-id="b826c-165">Расположение</span><span class="sxs-lookup"><span data-stu-id="b826c-165">Location</span></span>     | <span data-ttu-id="b826c-166">l</span><span class="sxs-lookup"><span data-stu-id="b826c-166">l</span></span>            |
| <span data-ttu-id="b826c-167">Команда</span><span class="sxs-lookup"><span data-stu-id="b826c-167">Command</span></span>      | <span data-ttu-id="b826c-168">cm</span><span class="sxs-lookup"><span data-stu-id="b826c-168">cm</span></span>           |
| <span data-ttu-id="b826c-169">Alias</span><span class="sxs-lookup"><span data-stu-id="b826c-169">Alias</span></span>        | <span data-ttu-id="b826c-170">al</span><span class="sxs-lookup"><span data-stu-id="b826c-170">al</span></span>           |

<span data-ttu-id="b826c-171">Эти псевдонимы легко понять, если вы знаете краткие имена.</span><span class="sxs-lookup"><span data-stu-id="b826c-171">These aliases are understandable when you know the shorthand names.</span></span>

| <span data-ttu-id="b826c-172">Имя командлета</span><span class="sxs-lookup"><span data-stu-id="b826c-172">Cmdlet name</span></span>    | <span data-ttu-id="b826c-173">Alias</span><span class="sxs-lookup"><span data-stu-id="b826c-173">Alias</span></span> |
|----------------|-------|
| `Get-Item `    | <span data-ttu-id="b826c-174">gi</span><span class="sxs-lookup"><span data-stu-id="b826c-174">gi</span></span>    |
| `Set-Item`     | <span data-ttu-id="b826c-175">si</span><span class="sxs-lookup"><span data-stu-id="b826c-175">si</span></span>    |
| `Get-Location` | <span data-ttu-id="b826c-176">gl</span><span class="sxs-lookup"><span data-stu-id="b826c-176">gl</span></span>    |
| `Set-Location` | <span data-ttu-id="b826c-177">sl</span><span class="sxs-lookup"><span data-stu-id="b826c-177">sl</span></span>    |
| `Get-Command`  | <span data-ttu-id="b826c-178">gcm</span><span class="sxs-lookup"><span data-stu-id="b826c-178">gcm</span></span>   |
| `Get-Alias`    | <span data-ttu-id="b826c-179">gal</span><span class="sxs-lookup"><span data-stu-id="b826c-179">gal</span></span>   |

<span data-ttu-id="b826c-180">Когда вы изучите псевдонимы PowerShell, вы сразу догадаетесь, что псевдоним **sal** соответствует `Set-Alias`.</span><span class="sxs-lookup"><span data-stu-id="b826c-180">Once you're familiar with PowerShell aliasing, it's easy to guess that the **sal** alias refers to `Set-Alias`.</span></span>

## <a name="creating-new-aliases"></a><span data-ttu-id="b826c-181">Создание псевдонимов</span><span class="sxs-lookup"><span data-stu-id="b826c-181">Creating new aliases</span></span>

<span data-ttu-id="b826c-182">Собственные псевдонимы можно создать с помощью командлета `Set-Alias`.</span><span class="sxs-lookup"><span data-stu-id="b826c-182">You can create your own aliases using the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="b826c-183">Например, указанные ниже инструкции создают описанные выше стандартные псевдонимы командлетов.</span><span class="sxs-lookup"><span data-stu-id="b826c-183">For example, the following statements create the standard cmdlet aliases previously discussed:</span></span>

```powershell
Set-Alias -Name gi -Value Get-Item
Set-Alias -Name si -Value Set-Item
Set-Alias -Name gl -Value Get-Location
Set-Alias -Name sl -Value Set-Location
Set-Alias -Name gcm -Value Get-Command
```

<span data-ttu-id="b826c-184">Сама оболочка PowerShell использует похожие команды во время запуска, но эти псевдонимы нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="b826c-184">Internally, PowerShell uses similar commands during startup, but these aliases are not changeable.</span></span>
<span data-ttu-id="b826c-185">Если вы попытаетесь выполнить одну из перечисленных выше команд, вы получите ошибку с сообщением о том, что псевдоним изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="b826c-185">If you try to execute one of these commands, you get an error explaining that the alias can't be modified.</span></span> <span data-ttu-id="b826c-186">Например:</span><span class="sxs-lookup"><span data-stu-id="b826c-186">For example:</span></span>

```
PS> Set-Alias -Name gi -Value Get-Item
Set-Alias : Alias is not writeable because alias gi is read-only or constant and cannot be written to.
At line:1 char:10
+ Set-Alias  <<<< -Name gi -Value Get-Item
```