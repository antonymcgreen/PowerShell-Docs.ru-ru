---
description: Описывает `Prompt` функцию и демонстрирует создание пользовательской `Prompt` функции.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: 9ae18afce9aec258181f4829b02b33bd942b3e10
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231341"
---
# <a name="about-prompts"></a><span data-ttu-id="a63bc-104">О запросах</span><span class="sxs-lookup"><span data-stu-id="a63bc-104">About Prompts</span></span>

## <a name="short-description"></a><span data-ttu-id="a63bc-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="a63bc-105">Short description</span></span>
<span data-ttu-id="a63bc-106">Описывает `Prompt` функцию и демонстрирует создание пользовательской `Prompt` функции.</span><span class="sxs-lookup"><span data-stu-id="a63bc-106">Describes the `Prompt` function and demonstrates how to create a custom `Prompt` function.</span></span>

## <a name="long-description"></a><span data-ttu-id="a63bc-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a63bc-107">Long description</span></span>

<span data-ttu-id="a63bc-108">Командная строка PowerShell указывает, что PowerShell готов выполнить команду:</span><span class="sxs-lookup"><span data-stu-id="a63bc-108">The PowerShell command prompt indicates that PowerShell is ready to run a command:</span></span>

```
PS C:\>
```

<span data-ttu-id="a63bc-109">Командная строка PowerShell определяется встроенной `Prompt` функцией.</span><span class="sxs-lookup"><span data-stu-id="a63bc-109">The PowerShell prompt is determined by the built-in `Prompt` function.</span></span> <span data-ttu-id="a63bc-110">Вы можете настроить запрос, создав собственную `Prompt` функцию и сохранив ее в профиле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a63bc-110">You can customize the prompt by creating your own `Prompt` function and saving it in your PowerShell profile.</span></span>

## <a name="about-the-prompt-function"></a><span data-ttu-id="a63bc-111">О функции Prompt</span><span class="sxs-lookup"><span data-stu-id="a63bc-111">About the Prompt function</span></span>

<span data-ttu-id="a63bc-112">`Prompt`Функция определяет внешний вид командной строки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a63bc-112">The `Prompt` function determines the appearance of the PowerShell prompt.</span></span>
<span data-ttu-id="a63bc-113">PowerShell поставляется с встроенной `Prompt` функцией, но ее можно переопределить, определив собственную `Prompt` функцию.</span><span class="sxs-lookup"><span data-stu-id="a63bc-113">PowerShell comes with a built-in `Prompt` function, but you can override it by defining your own `Prompt` function.</span></span>

<span data-ttu-id="a63bc-114">`Prompt`Функция имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a63bc-114">The `Prompt` function has the following syntax:</span></span>

```powershell
function Prompt { <function-body> }
```

<span data-ttu-id="a63bc-115">`Prompt`Функция должна возвращать объект.</span><span class="sxs-lookup"><span data-stu-id="a63bc-115">The `Prompt` function must return an object.</span></span> <span data-ttu-id="a63bc-116">Рекомендуется возвращать строку или объект, отформатированный в виде строки.</span><span class="sxs-lookup"><span data-stu-id="a63bc-116">As a best practice, return a string or an object that is formatted as a string.</span></span> <span data-ttu-id="a63bc-117">Максимальная рекомендуемая длина — 80 символов.</span><span class="sxs-lookup"><span data-stu-id="a63bc-117">The maximum recommended length is 80 characters.</span></span>

<span data-ttu-id="a63bc-118">Например, следующая `Prompt` функция возвращает строку "Hello, World", за которой следует правая угловая скобка ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="a63bc-118">For example, the following `Prompt` function returns a "Hello, World" string followed by a  right angle bracket (`>`).</span></span>

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a><span data-ttu-id="a63bc-119">Получение функции Prompt</span><span class="sxs-lookup"><span data-stu-id="a63bc-119">Getting the Prompt function</span></span>

<span data-ttu-id="a63bc-120">Чтобы получить `Prompt` функцию, используйте `Get-Command` командлет или `Get-Item` командлет на диске функции.</span><span class="sxs-lookup"><span data-stu-id="a63bc-120">To get the `Prompt` function, use the `Get-Command` cmdlet or use the `Get-Item` cmdlet in the Function drive.</span></span>

<span data-ttu-id="a63bc-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="a63bc-121">For example:</span></span>

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

<span data-ttu-id="a63bc-122">Чтобы получить скрипт, который задает значение запроса, используйте метод Dot, чтобы получить свойство **ScriptBlock** `Prompt` функции.</span><span class="sxs-lookup"><span data-stu-id="a63bc-122">To get the script that sets the value of the prompt, use the dot method to get the **ScriptBlock** property of the `Prompt` function.</span></span>

<span data-ttu-id="a63bc-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="a63bc-123">For example:</span></span>

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

<span data-ttu-id="a63bc-124">Как и все функции, `Prompt` функция хранится на `Function:` диске.</span><span class="sxs-lookup"><span data-stu-id="a63bc-124">Like all functions, the `Prompt` function is stored in the `Function:` drive.</span></span>
<span data-ttu-id="a63bc-125">Чтобы отобразить скрипт, который создает текущую `Prompt` функцию, введите:</span><span class="sxs-lookup"><span data-stu-id="a63bc-125">To display the script that creates the current `Prompt` function, type:</span></span>

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a><span data-ttu-id="a63bc-126">Запрос по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a63bc-126">The default prompt</span></span>

<span data-ttu-id="a63bc-127">Запрос по умолчанию отображается только в том случае, если `Prompt` функция создает ошибку или не возвращает объект.</span><span class="sxs-lookup"><span data-stu-id="a63bc-127">The default prompt appears only when the `Prompt` function generates an error or does not return an object.</span></span>

<span data-ttu-id="a63bc-128">Запрос PowerShell по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a63bc-128">The default PowerShell prompt is:</span></span>

```
PS>
```

<span data-ttu-id="a63bc-129">Например, следующая команда задает `Prompt` для функции значение `$null` , которое является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="a63bc-129">For example, the following command sets the `Prompt` function to `$null`, which is invalid.</span></span> <span data-ttu-id="a63bc-130">В результате появится запрос по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a63bc-130">As a result, the default prompt appears.</span></span>

```powershell
PS C:\> function prompt {$null}
PS>
```

<span data-ttu-id="a63bc-131">Так как PowerShell поставляется со встроенным запросом, обычно не отображается запрос по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a63bc-131">Because PowerShell comes with a built-in prompt, you usually do not see the default prompt.</span></span>

### <a name="built-in-prompt"></a><span data-ttu-id="a63bc-132">Встроенный запрос</span><span class="sxs-lookup"><span data-stu-id="a63bc-132">Built-in prompt</span></span>

<span data-ttu-id="a63bc-133">PowerShell включает встроенную `Prompt` функцию.</span><span class="sxs-lookup"><span data-stu-id="a63bc-133">PowerShell includes a built-in `Prompt` function.</span></span>

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="a63bc-134">Функция использует командлет, `Test-Path` чтобы определить, `$PSDebugContext` заполнена ли автоматическая переменная.</span><span class="sxs-lookup"><span data-stu-id="a63bc-134">The function uses the `Test-Path` cmdlet to determine whether the `$PSDebugContext` automatic variable is populated.</span></span> <span data-ttu-id="a63bc-135">Если `$PSDebugContext` заполняется, выполняется в режиме отладки и `[DBG]:` добавляется в командную строку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a63bc-135">If `$PSDebugContext` is populated, you are in debugging mode, and `[DBG]:` is added to the prompt, as follows:</span></span>

```Output
[DBG]: PS C:\ps-test>
```

<span data-ttu-id="a63bc-136">Если `$PSDebugContext` параметр не заполнен, функция добавляет `PS` в запрос.</span><span class="sxs-lookup"><span data-stu-id="a63bc-136">If `$PSDebugContext` is not populated, the function adds `PS` to the prompt.</span></span>
<span data-ttu-id="a63bc-137">И функция использует `Get-Location` командлет для получения текущего расположения каталога файловой системы.</span><span class="sxs-lookup"><span data-stu-id="a63bc-137">And, the function uses the `Get-Location` cmdlet to get the current file system directory location.</span></span> <span data-ttu-id="a63bc-138">Затем добавляется правая угловая скобка ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="a63bc-138">Then, it adds a right angle bracket (`>`).</span></span>

<span data-ttu-id="a63bc-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="a63bc-139">For example:</span></span>

```Output
PS C:\ps-test>
```

<span data-ttu-id="a63bc-140">В случае вложенного запроса функция добавляет в запрос две угловые скобки ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="a63bc-140">If you are in a nested prompt, the function adds two angle brackets (`>>`) to the prompt.</span></span> <span data-ttu-id="a63bc-141">(Во вложенном запросе, если значение `$NestedPromptLevel` автоматической переменной больше 1.)</span><span class="sxs-lookup"><span data-stu-id="a63bc-141">(You are in a nested prompt if the value of the `$NestedPromptLevel` automatic variable is greater than 1.)</span></span>

<span data-ttu-id="a63bc-142">Например, при отладке во вложенной командной строке запрос будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a63bc-142">For example, when you are debugging in a nested prompt, the prompt resembles the following prompt:</span></span>

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a><span data-ttu-id="a63bc-143">Изменения в приглашении</span><span class="sxs-lookup"><span data-stu-id="a63bc-143">Changes to the prompt</span></span>

<span data-ttu-id="a63bc-144">`Enter-PSSession`Командлет добавляет имя удаленного компьютера к текущей `Prompt` функции.</span><span class="sxs-lookup"><span data-stu-id="a63bc-144">The `Enter-PSSession` cmdlet prepends the name of the remote computer to the current `Prompt` function.</span></span> <span data-ttu-id="a63bc-145">При использовании `Enter-PSSession` командлета для запуска сеанса с удаленным компьютером Командная строка изменится, включив в нее имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="a63bc-145">When you use the `Enter-PSSession` cmdlet to start a session with a remote computer, the command prompt changes to include the name of the remote computer.</span></span> <span data-ttu-id="a63bc-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="a63bc-146">For example:</span></span>

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

<span data-ttu-id="a63bc-147">Другие хост приложения PowerShell и другие оболочки могут иметь собственные настраиваемые командные запросы.</span><span class="sxs-lookup"><span data-stu-id="a63bc-147">Other PowerShell host applications and alternate shells might have their own custom command prompts.</span></span>

<span data-ttu-id="a63bc-148">Дополнительные сведения об `$PSDebugContext` и `$NestedPromptLevel` автоматических переменных см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a63bc-148">For more information about the `$PSDebugContext` and `$NestedPromptLevel` automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

### <a name="how-to-customize-the-prompt"></a><span data-ttu-id="a63bc-149">Настройка командной строки</span><span class="sxs-lookup"><span data-stu-id="a63bc-149">How to customize the prompt</span></span>

<span data-ttu-id="a63bc-150">Чтобы настроить запрос, напишите новую `Prompt` функцию.</span><span class="sxs-lookup"><span data-stu-id="a63bc-150">To customize the prompt, write a new `Prompt` function.</span></span> <span data-ttu-id="a63bc-151">Функция не защищена, поэтому ее можно перезаписать.</span><span class="sxs-lookup"><span data-stu-id="a63bc-151">The function is not protected, so you can overwrite it.</span></span>

<span data-ttu-id="a63bc-152">Чтобы написать `Prompt` функцию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a63bc-152">To write a `Prompt` function, type the following:</span></span>

```powershell
function prompt { }
```

<span data-ttu-id="a63bc-153">Затем между фигурными скобками введите команды или строку, которая создает запрос.</span><span class="sxs-lookup"><span data-stu-id="a63bc-153">Then, between the braces, enter the commands or the string that creates your prompt.</span></span>

<span data-ttu-id="a63bc-154">Например, следующий запрос включает имя компьютера:</span><span class="sxs-lookup"><span data-stu-id="a63bc-154">For example, the following prompt includes your computer name:</span></span>

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

<span data-ttu-id="a63bc-155">На компьютере Server01 запрос будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a63bc-155">On the Server01 computer, the prompt resembles the following prompt:</span></span>

```Output
PS [Server01] >
```

<span data-ttu-id="a63bc-156">Следующая `Prompt` функция включает текущие дату и время:</span><span class="sxs-lookup"><span data-stu-id="a63bc-156">The following `Prompt` function includes the current date and time:</span></span>

```powershell
function prompt {"$(Get-Date)> "}
```

<span data-ttu-id="a63bc-157">Запрос будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a63bc-157">The prompt resembles the following prompt:</span></span>

```Output
03/15/2012 17:49:47>
```

<span data-ttu-id="a63bc-158">Можно также изменить функцию по умолчанию `Prompt` .</span><span class="sxs-lookup"><span data-stu-id="a63bc-158">You can also change the default `Prompt` function:</span></span>

<span data-ttu-id="a63bc-159">Например, следующая измененная `Prompt` функция добавляет во `[ADMIN]:` встроенный запрос PowerShell при открытии PowerShell с помощью команды **Запуск от имени администратора** :</span><span class="sxs-lookup"><span data-stu-id="a63bc-159">For example, the following modified `Prompt` function adds `[ADMIN]:` to the built-in PowerShell prompt when PowerShell is opened by using the **Run as administrator** option:</span></span>

```powershell
function prompt {
  $identity = [Security.Principal.WindowsIdentity]::GetCurrent()
  $principal = [Security.Principal.WindowsPrincipal] $identity
  $adminRole = [Security.Principal.WindowsBuiltInRole]::Administrator

  $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
    elseif($principal.IsInRole($adminRole)) { "[ADMIN]: " }
    else { '' }
  ) + 'PS ' + $(Get-Location) +
    $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="a63bc-160">При запуске PowerShell с помощью команды **Запуск от имени администратора** отображается запрос, напоминающий следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="a63bc-160">When you start PowerShell by using the **Run as administrator** option, a prompt that resembles the following prompt appears:</span></span>

```Output
[ADMIN]: PS C:\ps-test>
```

<span data-ttu-id="a63bc-161">Следующая `Prompt` функция ОТОБРАЖАЕТ идентификатор журнала следующей команды.</span><span class="sxs-lookup"><span data-stu-id="a63bc-161">The following `Prompt` function displays the history ID of the next command.</span></span> <span data-ttu-id="a63bc-162">Чтобы просмотреть журнал команд, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="a63bc-162">To view the command history, use the `Get-History` cmdlet.</span></span>

```powershell
function prompt {
   # The at sign creates an array in case only one history item exists.
   $history = @(Get-History)
   if($history.Count -gt 0)
   {
      $lastItem = $history[$history.Count - 1]
      $lastId = $lastItem.Id
   }

   $nextCommand = $lastId + 1
   $currentDirectory = Get-Location
   "PS: $nextCommand $currentDirectory >"
}
```

<span data-ttu-id="a63bc-163">В следующем запросе `Write-Host` `Get-Random` командлеты и используются для создания запроса, который изменяет цвет случайным образом.</span><span class="sxs-lookup"><span data-stu-id="a63bc-163">The following prompt uses the `Write-Host` and `Get-Random` cmdlets to create a prompt that changes color randomly.</span></span> <span data-ttu-id="a63bc-164">Поскольку `Write-Host` операции записи в текущее ведущее приложение не возвращают объект, эта функция включает `Return` оператор.</span><span class="sxs-lookup"><span data-stu-id="a63bc-164">Because `Write-Host` writes to the current host application but does not return an object, this function includes a `Return` statement.</span></span> <span data-ttu-id="a63bc-165">Без него PowerShell использует запрос по умолчанию `PS>` .</span><span class="sxs-lookup"><span data-stu-id="a63bc-165">Without it, PowerShell uses the default prompt, `PS>`.</span></span>

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a><span data-ttu-id="a63bc-166">Сохранение функции Prompt</span><span class="sxs-lookup"><span data-stu-id="a63bc-166">Saving the Prompt function</span></span>

<span data-ttu-id="a63bc-167">Как и любая функция, `Prompt` функция существует только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a63bc-167">Like any function, the `Prompt` function exists only in the current session.</span></span> <span data-ttu-id="a63bc-168">Чтобы сохранить `Prompt` функцию для будущих сеансов, добавьте ее в профили PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a63bc-168">To save the `Prompt` function for future sessions, add it to your PowerShell profiles.</span></span> <span data-ttu-id="a63bc-169">Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a63bc-169">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a63bc-170">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a63bc-170">See also</span></span>

[<span data-ttu-id="a63bc-171">Get-Location</span><span class="sxs-lookup"><span data-stu-id="a63bc-171">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)

[<span data-ttu-id="a63bc-172">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="a63bc-172">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="a63bc-173">Get-History</span><span class="sxs-lookup"><span data-stu-id="a63bc-173">Get-History</span></span>](xref:Microsoft.PowerShell.Core.Get-History)

[<span data-ttu-id="a63bc-174">Get-Random</span><span class="sxs-lookup"><span data-stu-id="a63bc-174">Get-Random</span></span>](xref:Microsoft.PowerShell.Utility.Get-Random)

[<span data-ttu-id="a63bc-175">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a63bc-175">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)

[<span data-ttu-id="a63bc-176">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="a63bc-176">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="a63bc-177">about_Functions</span><span class="sxs-lookup"><span data-stu-id="a63bc-177">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="a63bc-178">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="a63bc-178">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="a63bc-179">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="a63bc-179">about_Debuggers</span></span>](about_Debuggers.md)

[<span data-ttu-id="a63bc-180">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="a63bc-180">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
