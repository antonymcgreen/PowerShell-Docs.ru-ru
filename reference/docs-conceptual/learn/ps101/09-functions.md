---
title: Функции
description: С помощью функций PowerShell можно создавать средства для многократного использования в сценариях.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 9554c0b4d3932b7371201f7b08c8b9d26a567f5e
ms.sourcegitcommit: e85e56d6614cbd30e01965a5cf03fb3f5ca78103
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "94589143"
---
# <a name="chapter-9---functions"></a><span data-ttu-id="91b45-103">Глава 9. Функции</span><span class="sxs-lookup"><span data-stu-id="91b45-103">Chapter 9 - Functions</span></span>

<span data-ttu-id="91b45-104">Если вы пишете однострочные коды и сценарии PowerShell, которые часто приходится изменять для применения в различных ситуациях, возможно, их стоит преобразовать в многократно используемую функцию.</span><span class="sxs-lookup"><span data-stu-id="91b45-104">If you're writing PowerShell one-liners or scripts and find yourself often having to modify them for different scenarios, there's a good chance that it's a good candidate to be turned into a function that can be reused.</span></span>

<span data-ttu-id="91b45-105">По возможности я предпочитаю писать функции, потому что они больше ориентированы на работу со средствами.</span><span class="sxs-lookup"><span data-stu-id="91b45-105">Whenever possible, I prefer to write functions because they are more tool oriented.</span></span> <span data-ttu-id="91b45-106">Я могу поместить функции в модуль сценария, отправить этот модуль в `$env:PSModulePath` и вызвать функции без необходимости физического определения их местонахождения.</span><span class="sxs-lookup"><span data-stu-id="91b45-106">I can put the functions in a script module, put that module in the `$env:PSModulePath`, and call the functions without needing to physically locate where they're saved.</span></span> <span data-ttu-id="91b45-107">С помощью модуля PowerShellGet эти модули можно легко запрашивать в репозитории NuGet.</span><span class="sxs-lookup"><span data-stu-id="91b45-107">Using the PowerShellGet module, it's easy to share those modules in a NuGet repository.</span></span> <span data-ttu-id="91b45-108">PowerShellGet поставляется с PowerShell версии 5.0 и выше.</span><span class="sxs-lookup"><span data-stu-id="91b45-108">PowerShellGet ships with PowerShell version 5.0 and higher.</span></span> <span data-ttu-id="91b45-109">Он доступен в виде отдельного скачиваемого файла для PowerShell версии 3.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="91b45-109">It is available as a separate download for PowerShell version 3.0 and higher.</span></span>

<span data-ttu-id="91b45-110">Не нужно ничего усложнять.</span><span class="sxs-lookup"><span data-stu-id="91b45-110">Don't over complicate things.</span></span> <span data-ttu-id="91b45-111">Будьте проще и выбирайте самый прямой путь для решения задач.</span><span class="sxs-lookup"><span data-stu-id="91b45-111">Keep it simple and use the most straight forward way to accomplish a task.</span></span> <span data-ttu-id="91b45-112">Избегайте псевдонимов и позиционных параметров в любом многократно используемом коде.</span><span class="sxs-lookup"><span data-stu-id="91b45-112">Avoid aliases and positional parameters in any code that you reuse.</span></span> <span data-ttu-id="91b45-113">Отформатируйте код, чтобы сделать его удобочитаемым.</span><span class="sxs-lookup"><span data-stu-id="91b45-113">Format your code for readability.</span></span> <span data-ttu-id="91b45-114">Не указывайте значения прямо в коде — используйте параметры и переменные.</span><span class="sxs-lookup"><span data-stu-id="91b45-114">Don't hardcode values; use parameters and variables.</span></span> <span data-ttu-id="91b45-115">Не пишите лишний код, даже если это ничему не повредит.</span><span class="sxs-lookup"><span data-stu-id="91b45-115">Don't write unnecessary code even if it doesn't hurt anything.</span></span> <span data-ttu-id="91b45-116">Он усложнит ситуацию.</span><span class="sxs-lookup"><span data-stu-id="91b45-116">It adds unnecessary complexity.</span></span> <span data-ttu-id="91b45-117">При написании кода PowerShell очень важно обращать внимание на детали.</span><span class="sxs-lookup"><span data-stu-id="91b45-117">Attention to detail goes a long way when writing any PowerShell code.</span></span>

## <a name="naming"></a><span data-ttu-id="91b45-118">Именование</span><span class="sxs-lookup"><span data-stu-id="91b45-118">Naming</span></span>

<span data-ttu-id="91b45-119">При именовании функций в PowerShell используйте имя в [Регистр Pascal][] с утвержденным глаголом и существительным в единственном числе.</span><span class="sxs-lookup"><span data-stu-id="91b45-119">When naming your functions in PowerShell, use a [Pascal case][] name with an approved verb and a singular noun.</span></span> <span data-ttu-id="91b45-120">Кроме того, перед существительным рекомендуется добавить префикс.</span><span class="sxs-lookup"><span data-stu-id="91b45-120">I also recommend prefixing the noun.</span></span> <span data-ttu-id="91b45-121">Например: `<ApprovedVerb>-<Prefix><SingularNoun>`.</span><span class="sxs-lookup"><span data-stu-id="91b45-121">For example: `<ApprovedVerb>-<Prefix><SingularNoun>`.</span></span>

<span data-ttu-id="91b45-122">В PowerShell есть конкретный список утвержденных глаголов, которые можно получить, выполнив `Get-Verb`.</span><span class="sxs-lookup"><span data-stu-id="91b45-122">In PowerShell, there's a specific list of approved verbs that can be obtained by running `Get-Verb`.</span></span>

```powershell
Get-Verb | Sort-Object -Property Verb
```

```Output
Verb        Group
----        -----
Add         Common
Approve     Lifecycle
Assert      Lifecycle
Backup      Data
Block       Security
Checkpoint  Data
Clear       Common
Close       Common
Compare     Data
Complete    Lifecycle
Compress    Data
Confirm     Lifecycle
Connect     Communications
Convert     Data
ConvertFrom Data
ConvertTo   Data
Copy        Common
Debug       Diagnostic
Deny        Lifecycle
Disable     Lifecycle
Disconnect  Communications
Dismount    Data
Edit        Data
Enable      Lifecycle
Enter       Common
Exit        Common
Expand      Data
Export      Data
Find        Common
Format      Common
Get         Common
Grant       Security
Group       Data
Hide        Common
Import      Data
Initialize  Data
Install     Lifecycle
Invoke      Lifecycle
Join        Common
Limit       Data
Lock        Common
Measure     Diagnostic
Merge       Data
Mount       Data
Move        Common
New         Common
Open        Common
Optimize    Common
Out         Data
Ping        Diagnostic
Pop         Common
Protect     Security
Publish     Data
Push        Common
Read        Communications
Receive     Communications
Redo        Common
Register    Lifecycle
Remove      Common
Rename      Common
Repair      Diagnostic
Request     Lifecycle
Reset       Common
Resize      Common
Resolve     Diagnostic
Restart     Lifecycle
Restore     Data
Resume      Lifecycle
Revoke      Security
Save        Data
Search      Common
Select      Common
Send        Communications
Set         Common
Show        Common
Skip        Common
Split       Common
Start       Lifecycle
Step        Common
Stop        Lifecycle
Submit      Lifecycle
Suspend     Lifecycle
Switch      Common
Sync        Data
Test        Diagnostic
Trace       Diagnostic
Unblock     Security
Undo        Common
Uninstall   Lifecycle
Unlock      Common
Unprotect   Security
Unpublish   Data
Unregister  Lifecycle
Update      Data
Use         Other
Wait        Lifecycle
Watch       Common
Write       Communications
```

<span data-ttu-id="91b45-123">В предыдущем примере результаты отсортированы по столбцу **Verb**.</span><span class="sxs-lookup"><span data-stu-id="91b45-123">In the previous example, I've sorted the results by the **Verb** column.</span></span> <span data-ttu-id="91b45-124">Взглянув на столбец **Group**, вы получите представление о том, как эти глаголы используются.</span><span class="sxs-lookup"><span data-stu-id="91b45-124">The **Group** column gives you an idea of how these verbs are used.</span></span> <span data-ttu-id="91b45-125">При добавлении функций в модуль важно выбрать утвержденную команду в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b45-125">It's important to choose an approved verb in PowerShell when functions are added to a module.</span></span> <span data-ttu-id="91b45-126">Если будет выбран неутвержденный глагол, модуль создаст предупреждение во время загрузки.</span><span class="sxs-lookup"><span data-stu-id="91b45-126">The module generates a warning message at load time if you choose an unapproved verb.</span></span> <span data-ttu-id="91b45-127">Из-за этого предупреждения ваши функции выглядят непрофессионально.</span><span class="sxs-lookup"><span data-stu-id="91b45-127">That warning message makes your functions look unprofessional.</span></span> <span data-ttu-id="91b45-128">Кроме того, неутвержденные глаголы ограничивают возможности обнаружения функций.</span><span class="sxs-lookup"><span data-stu-id="91b45-128">Unapproved verbs also limit the discoverability of your functions.</span></span>

## <a name="a-simple-function"></a><span data-ttu-id="91b45-129">Простая функция</span><span class="sxs-lookup"><span data-stu-id="91b45-129">A simple function</span></span>

<span data-ttu-id="91b45-130">Функция в PowerShell объявляется с помощью ключевого слова function, за которым следует имя функции, а затем — открывающая и закрывающая фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="91b45-130">A function in PowerShell is declared with the function keyword followed by the function name and then an open and closing curly brace.</span></span> <span data-ttu-id="91b45-131">В этих скобках содержится код, который будет выполнять функция.</span><span class="sxs-lookup"><span data-stu-id="91b45-131">The code that the function will execute is contained within those curly braces.</span></span>

```powershell
function Get-Version {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="91b45-132">Показан простой пример функции, возвращающей версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b45-132">The function shown is a simple example that returns the version of PowerShell.</span></span>

```powershell
Get-Version
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="91b45-133">Существует большая вероятность возникновения конфликта имен функций, названных примерно как `Get-Version`, и команд по умолчанию в PowerShell или команд, которые могут написать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="91b45-133">There's a good chance of name conflict with functions named something like `Get-Version` and default commands in PowerShell or commands that others may write.</span></span> <span data-ttu-id="91b45-134">Именно поэтому в целях предотвращения конфликтов имен рекомендуется добавлять префикс к части функции, выраженной существительным.</span><span class="sxs-lookup"><span data-stu-id="91b45-134">This is why I recommend prefixing the noun portion of your functions to help prevent naming conflicts.</span></span> <span data-ttu-id="91b45-135">В следующем примере используется префикс PS.</span><span class="sxs-lookup"><span data-stu-id="91b45-135">In the following example, I'll use the prefix "PS".</span></span>

```powershell
function Get-PSVersion {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="91b45-136">Эта функция идентична предыдущей, за исключением имени.</span><span class="sxs-lookup"><span data-stu-id="91b45-136">Other than the name, this function is identical to the previous one.</span></span>

```powershell
Get-PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="91b45-137">Даже при добавлении префикса типа PS все равно есть большая вероятность конфликта имен.</span><span class="sxs-lookup"><span data-stu-id="91b45-137">Even when prefixing the noun with something like PS, there's still a good chance of having a name conflict.</span></span> <span data-ttu-id="91b45-138">Обычно перед существительным в имени функции я указываю свои инициалы.</span><span class="sxs-lookup"><span data-stu-id="91b45-138">I typically prefix my function nouns with my initials.</span></span> <span data-ttu-id="91b45-139">Разработайте свой стандарт и придерживайтесь его.</span><span class="sxs-lookup"><span data-stu-id="91b45-139">Develop a standard and stick to it.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="91b45-140">Эта функция ничем не отличается от двух предыдущих, кроме использования более соответствующего имени для предотвращения конфликтов именования с другими командами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b45-140">This function is no different than the previous two other than using a more sensible name to try to prevent naming conflicts with other PowerShell commands.</span></span>

```powershell
Get-MrPSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="91b45-141">Функции, загруженные в память, можно увидеть на PSDrive **Function**.</span><span class="sxs-lookup"><span data-stu-id="91b45-141">Once loaded into memory, you can see functions on the **Function** PSDrive.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-Version
Function        Get-PSVersion
Function        Get-MrPSVersion
```

<span data-ttu-id="91b45-142">Чтобы удалить эти функции из текущего сеанса, необходимо удалить их из PSDrive **Function** или закрыть и повторно открыть PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b45-142">If you want to remove these functions from your current session, you'll have to remove them from the **Function** PSDrive or close and reopen PowerShell.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version | Remove-Item
```

<span data-ttu-id="91b45-143">Убедитесь, что функции действительно удалены.</span><span class="sxs-lookup"><span data-stu-id="91b45-143">Verify that the functions were indeed removed.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

<span data-ttu-id="91b45-144">Если функции были загружены в составе модуля, то, чтобы удалить их, можно выгрузить модуль.</span><span class="sxs-lookup"><span data-stu-id="91b45-144">If the functions were loaded as part of a module, the module can be unloaded to remove them.</span></span>

```powershell
Remove-Module -Name <ModuleName>
```

<span data-ttu-id="91b45-145">Командлет `Remove-Module` удаляет модули из памяти в текущем сеансе PowerShell, но не удаляет их из системы или с диска.</span><span class="sxs-lookup"><span data-stu-id="91b45-145">The `Remove-Module` cmdlet removes modules from memory in your current PowerShell session, it doesn't remove them from your system or from disk.</span></span>

## <a name="parameters"></a><span data-ttu-id="91b45-146">Параметры</span><span class="sxs-lookup"><span data-stu-id="91b45-146">Parameters</span></span>

<span data-ttu-id="91b45-147">Не присваивайте значения статически!</span><span class="sxs-lookup"><span data-stu-id="91b45-147">Don't statically assign values!</span></span> <span data-ttu-id="91b45-148">Используйте параметры и переменные.</span><span class="sxs-lookup"><span data-stu-id="91b45-148">Use parameters and variables.</span></span> <span data-ttu-id="91b45-149">Когда дело доходит до именования параметров, по возможности используйте те же имена, что и у командлетов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91b45-149">When it comes to naming your parameters, use the same name as the default cmdlets for your parameter names whenever possible.</span></span>

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-150">Почему в качестве имени параметра я использовал **ComputerName**, а не **Computer**, **ServerName** или **Host**?</span><span class="sxs-lookup"><span data-stu-id="91b45-150">Why did I use **ComputerName** and not **Computer**, **ServerName**, or **Host** for my parameter name?</span></span> <span data-ttu-id="91b45-151">Потому что я хотел, чтобы мои функции были стандартизированы как стандартные командлеты.</span><span class="sxs-lookup"><span data-stu-id="91b45-151">It's because I wanted my function standardized like the default cmdlets.</span></span>

<span data-ttu-id="91b45-152">Я создам функцию, которая будет запрашивать все команды в системе и возвращать количество команд с конкретными именами параметров.</span><span class="sxs-lookup"><span data-stu-id="91b45-152">I'll create a function to query all of the commands on a system and return the number of them that have specific parameter names.</span></span>

```powershell
function Get-MrParameterCount {
    param (
        [string[]]$ParameterName
    )

    foreach ($Parameter in $ParameterName) {
        $Results = Get-Command -ParameterName $Parameter -ErrorAction SilentlyContinue

        [pscustomobject]@{
            ParameterName = $Parameter
            NumberOfCmdlets = $Results.Count
        }
    }
}
```

<span data-ttu-id="91b45-153">Как видно в приведенных ниже результатах, у 39 команд есть параметр **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="91b45-153">As you can see in the results shown below, 39 commands that have a **ComputerName** parameter.</span></span> <span data-ttu-id="91b45-154">Командлеты с такими параметрами, как **Computer**, **ServerName**, **Host** или **Machine**, не найдены.</span><span class="sxs-lookup"><span data-stu-id="91b45-154">There aren't any cmdlets that have parameters such as **Computer**, **ServerName**, **Host**, or **Machine**.</span></span>

```powershell
Get-MrParameterCount -ParameterName ComputerName, Computer, ServerName, Host, Machine
```

```Output
ParameterName NumberOfCmdlets
------------- ---------------
ComputerName               39
Computer                    0
ServerName                  0
Host                        0
Machine                     0
```

<span data-ttu-id="91b45-155">Кроме того, имена параметров рекомендуется указывать в том же регистре, что и имена командлетов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91b45-155">I also recommend using the same case for your parameter names as the default cmdlets.</span></span> <span data-ttu-id="91b45-156">Используйте `ComputerName`, а не `computername`.</span><span class="sxs-lookup"><span data-stu-id="91b45-156">Use `ComputerName`, not `computername`.</span></span> <span data-ttu-id="91b45-157">В этом случае функции выглядят и работают как командлеты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91b45-157">This makes your functions look and feel like the default cmdlets.</span></span> <span data-ttu-id="91b45-158">Это очень удобно для пользователей, уже знакомых с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b45-158">People who are already familiar with PowerShell will feel right at home.</span></span>

## <a name="advanced-functions"></a><span data-ttu-id="91b45-159">Расширенные функции</span><span class="sxs-lookup"><span data-stu-id="91b45-159">Advanced Functions</span></span>

<span data-ttu-id="91b45-160">Функцию в PowerShell можно легко преобразовать в расширенную.</span><span class="sxs-lookup"><span data-stu-id="91b45-160">Turning a function in PowerShell into an advanced function is really simple.</span></span> <span data-ttu-id="91b45-161">Одно из различий между функцией и расширенной функцией заключается в том, что расширенные функции имеют ряд общих параметров, которые добавляются в функцию автоматически.</span><span class="sxs-lookup"><span data-stu-id="91b45-161">One of the differences between a function and an advanced function is that advanced functions have a number of common parameters that are added to the function automatically.</span></span> <span data-ttu-id="91b45-162">К этим общим параметрам относятся такие параметры, как **Verbose** и **Debug**.</span><span class="sxs-lookup"><span data-stu-id="91b45-162">These common parameters include parameters such as **Verbose** and **Debug**.</span></span>

<span data-ttu-id="91b45-163">Я начну с функции `Test-MrParameter`, которая использовалась в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="91b45-163">I'll start out with the `Test-MrParameter` function that was used in the previous section.</span></span>

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-164">Хочу обратить ваше внимание на то, что функция `Test-MrParameter` не имеет общих параметров.</span><span class="sxs-lookup"><span data-stu-id="91b45-164">What I want you to notice is that the `Test-MrParameter` function doesn't have any common parameters.</span></span> <span data-ttu-id="91b45-165">Существует несколько различных способов просмотра общих параметров.</span><span class="sxs-lookup"><span data-stu-id="91b45-165">There are a couple of different ways to see the common parameters.</span></span> <span data-ttu-id="91b45-166">Один из них — просмотр синтаксиса с помощью `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="91b45-166">One is by viewing the syntax using `Get-Command`.</span></span>

```powershell
Get-Command -Name Test-MrParameter -Syntax
```

```Output
Test-MrParameter [[-ComputerName] <Object>]
```

<span data-ttu-id="91b45-167">Другой — детализация параметров с помощью `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="91b45-167">Another is to drill down into the parameters with `Get-Command`.</span></span>

```powershell
(Get-Command -Name Test-MrParameter).Parameters.Keys
```

```Output
ComputerName
```

<span data-ttu-id="91b45-168">Добавьте `CmdletBinding`, чтобы преобразовать функцию в расширенную.</span><span class="sxs-lookup"><span data-stu-id="91b45-168">Add `CmdletBinding` to turn the function into an advanced function.</span></span>

```powershell
function Test-MrCmdletBinding {

    [CmdletBinding()] #<<-- This turns a regular function into an advanced function
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-169">При добавлении `CmdletBinding` общие параметры добавляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="91b45-169">Adding `CmdletBinding` adds the common parameters automatically.</span></span> <span data-ttu-id="91b45-170">Для `CmdletBinding` требуется блок `param`, но блок `param` может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="91b45-170">`CmdletBinding` requires a `param` block, but the `param` block can be empty.</span></span>

```powershell
Get-Command -Name Test-MrCmdletBinding -Syntax
```

```Output
Test-MrCmdletBinding [[-ComputerName] <Object>] [<CommonParameters>]
```

<span data-ttu-id="91b45-171">Если выполнить детализацию параметров с помощью `Get-Command`, можно увидеть имена параметров, включая общие параметры.</span><span class="sxs-lookup"><span data-stu-id="91b45-171">Drilling down into the parameters with `Get-Command` shows the actual parameter names including the common ones.</span></span>

```powershell
(Get-Command -Name Test-MrCmdletBinding).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
```

## <a name="supportsshouldprocess"></a><span data-ttu-id="91b45-172">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="91b45-172">SupportsShouldProcess</span></span>

<span data-ttu-id="91b45-173">`SupportsShouldProcess` добавляет параметры **WhatIf** и **Confirm**.</span><span class="sxs-lookup"><span data-stu-id="91b45-173">`SupportsShouldProcess` adds **WhatIf** and **Confirm** parameters.</span></span> <span data-ttu-id="91b45-174">Они необходимы только для команд, которые вносят изменения.</span><span class="sxs-lookup"><span data-stu-id="91b45-174">These are only needed for commands that make changes.</span></span>

```powershell
function Test-MrSupportsShouldProcess {

    [CmdletBinding(SupportsShouldProcess)]
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-175">Обратите внимание, что теперь появились параметры **WhatIf** и **Confirm**.</span><span class="sxs-lookup"><span data-stu-id="91b45-175">Notice that there are now **WhatIf** and **Confirm** parameters.</span></span>

```powershell
Get-Command -Name Test-MrSupportsShouldProcess -Syntax
```

```Output
Test-MrSupportsShouldProcess [[-ComputerName] <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="91b45-176">Опять же: с помощью `Get-Command` можно получить список фактических имен параметров, включая общие параметры и WhatIf и Confirm.</span><span class="sxs-lookup"><span data-stu-id="91b45-176">Once again, you can also use `Get-Command` to return a list of the actual parameter names including the common ones along with WhatIf and Confirm.</span></span>

```powershell
(Get-Command -Name Test-MrSupportsShouldProcess).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
WhatIf
Confirm
```

## <a name="parameter-validation"></a><span data-ttu-id="91b45-177">Проверка параметров</span><span class="sxs-lookup"><span data-stu-id="91b45-177">Parameter Validation</span></span>

<span data-ttu-id="91b45-178">Входные данные следует проверять в самом начале.</span><span class="sxs-lookup"><span data-stu-id="91b45-178">Validate input early on.</span></span> <span data-ttu-id="91b45-179">Для чего продолжать выполнение кода, если это невозможно сделать без допустимых входных данных?</span><span class="sxs-lookup"><span data-stu-id="91b45-179">Why allow your code to continue on a path when it's not possible to run without valid input?</span></span>

<span data-ttu-id="91b45-180">Всегда вводите переменные, используемые для параметров (с указанием типа данных).</span><span class="sxs-lookup"><span data-stu-id="91b45-180">Always type the variables that are being used for your parameters (specify a datatype).</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-181">В предыдущем примере в качестве типа данных для параметра **ComputerName** указано **String**.</span><span class="sxs-lookup"><span data-stu-id="91b45-181">In the previous example, I've specified **String** as the datatype for the **ComputerName** parameter.</span></span> <span data-ttu-id="91b45-182">Это означает, что допускается только одно имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="91b45-182">This causes it to allow only a single computer name to be specified.</span></span> <span data-ttu-id="91b45-183">Если задается несколько имен компьютеров в виде списка с разделителями-запятыми, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="91b45-183">If more than one computer name is specified via a comma-separated list, an error is generated.</span></span>

```powershell
Test-MrParameterValidation -ComputerName Server01, Server02
```

```Output
Test-MrParameterValidation : Cannot process argument transformation on parameter
'ComputerName'. Cannot convert value to type System.String.
At line:1 char:42
+ Test-MrParameterValidation -ComputerName Server01, Server02
+
    + CategoryInfo          : InvalidData: (:) [Test-MrParameterValidation], ParameterBindingArg
     umentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Test-MrParameterValidation
```

<span data-ttu-id="91b45-184">Проблема с текущим определением заключается в том, что значение параметра **ComputerName** можно опустить, но оно требуется для успешного выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="91b45-184">The problem with the current definition is that it's valid to omit the value of the **ComputerName** parameter, but a value is required for the function to complete successfully.</span></span> <span data-ttu-id="91b45-185">Именно в таком случае будет полезен атрибут параметра `Mandatory`.</span><span class="sxs-lookup"><span data-stu-id="91b45-185">This is where the `Mandatory` parameter attribute comes in handy.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-186">В предыдущем примере используется синтаксис, совместимый с PowerShell версии 3.0 и более поздними.</span><span class="sxs-lookup"><span data-stu-id="91b45-186">The syntax used in the previous example is PowerShell version 3.0 and higher compatible.</span></span>
<span data-ttu-id="91b45-187">Чтобы обеспечить совместимость функции с PowerShell версии 2.0 и более поздними, можно указать `[Parameter(Mandatory=$true)]`.</span><span class="sxs-lookup"><span data-stu-id="91b45-187">`[Parameter(Mandatory=$true)]` could be specified instead to make the function compatible with PowerShell version 2.0 and higher.</span></span> <span data-ttu-id="91b45-188">Теперь, когда потребуется значение параметра **ComputerName**, которое пока не задано, функция выведет соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="91b45-188">Now that the **ComputerName** is required, if one isn't specified, the function will prompt for one.</span></span>

```powershell
Test-MrParameterValidation
```

```Output
cmdlet Test-MrParameterValidation at command pipeline position 1
Supply values for the following parameters:
ComputerName:
```

<span data-ttu-id="91b45-189">Чтобы разрешить несколько значений для параметра **ComputerName**, используйте тип данных **String**, но добавьте к нему открывающие и закрывающие квадратные скобки, позволяющие использовать массив строк.</span><span class="sxs-lookup"><span data-stu-id="91b45-189">If you want to allow for more than one value for the **ComputerName** parameter, use the **String** datatype but add open and closed square brackets to the datatype to allow for an array of strings.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string[]]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-190">Возможно, вы захотите указать значение по умолчанию для параметра **ComputerName**, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="91b45-190">Maybe you want to specify a default value for the **ComputerName** parameter if one isn't specified.</span></span>
<span data-ttu-id="91b45-191">Проблема в том, что значения по умолчанию нельзя использовать с обязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="91b45-191">The problem is that default values can't be used with mandatory parameters.</span></span> <span data-ttu-id="91b45-192">Вместо этого потребуется атрибут проверки параметров `ValidateNotNullOrEmpty` со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91b45-192">Instead, you'll need to use the `ValidateNotNullOrEmpty` parameter validation attribute with a default value.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="91b45-193">Даже при задании значения по умолчанию старайтесь не прибегать к статическим значениям.</span><span class="sxs-lookup"><span data-stu-id="91b45-193">Even when setting a default value, try not to use static values.</span></span> <span data-ttu-id="91b45-194">В предыдущем примере в качестве значения по умолчанию используется `$env:COMPUTERNAME`, которое автоматически преобразуется в имя локального компьютера, если значение не указано.</span><span class="sxs-lookup"><span data-stu-id="91b45-194">In the previous example, `$env:COMPUTERNAME` is used as the default value, which is automatically translated into the local computer name if a value is not provided.</span></span>

## <a name="verbose-output"></a><span data-ttu-id="91b45-195">Подробные выходные данные</span><span class="sxs-lookup"><span data-stu-id="91b45-195">Verbose Output</span></span>

<span data-ttu-id="91b45-196">Несмотря на всю пользу встроенных комментариев, особенно при написании сложного кода, их никогда не увидят пользователи, если только не заглянут в сам код.</span><span class="sxs-lookup"><span data-stu-id="91b45-196">While inline comments are useful, especially if you're writing some complex code, they never get seen by users unless they look into the code itself.</span></span>

<span data-ttu-id="91b45-197">Функция, показанная в следующем примере, содержит встроенный комментарий в цикле `foreach`.</span><span class="sxs-lookup"><span data-stu-id="91b45-197">The function shown in the following example has an inline comment in the `foreach` loop.</span></span> <span data-ttu-id="91b45-198">Хотя этот конкретный комментарий может быть не так уж сложно обнаружить, представьте, что было бы, если бы функция включала сотни строк кода.</span><span class="sxs-lookup"><span data-stu-id="91b45-198">While this particular comment may not be that difficult to locate, imagine if the function included hundreds of lines of code.</span></span>

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        #Attempting to perform some action on $Computer <<-- Don't use
        #inline comments like this, use write verbose instead.
        Write-Output $Computer
    }

}
```

<span data-ttu-id="91b45-199">Лучшим вариантом является использование `Write-Verbose` вместо встроенных комментариев.</span><span class="sxs-lookup"><span data-stu-id="91b45-199">A better option is to use `Write-Verbose` instead of inline comments.</span></span>

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        Write-Verbose -Message "Attempting to perform some action on $Computer"
        Write-Output $Computer
    }

}
```

<span data-ttu-id="91b45-200">Если функция вызывается без параметра **verbose**, подробные выходные данные отображаться не будут.</span><span class="sxs-lookup"><span data-stu-id="91b45-200">When the function is called without the **Verbose** parameter, the verbose output won't be displayed.</span></span>

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02
```

<span data-ttu-id="91b45-201">При вызове функции с параметром **verbose** будут выведены подробные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="91b45-201">When it's called with the **Verbose** parameter, the verbose output will be displayed.</span></span>

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02 -Verbose
```

## <a name="pipeline-input"></a><span data-ttu-id="91b45-202">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="91b45-202">Pipeline Input</span></span>

<span data-ttu-id="91b45-203">Если требуется, чтобы функция принимала входные данные конвейера, необходимо написать дополнительный код.</span><span class="sxs-lookup"><span data-stu-id="91b45-203">When you want your function to accept pipeline input, some additional coding is necessary.</span></span> <span data-ttu-id="91b45-204">Как говорилось ранее в этой книге, команды могут принимать входные данные конвейера **по значению** (по типу) или **по имени свойства**.</span><span class="sxs-lookup"><span data-stu-id="91b45-204">As mentioned earlier in this book, commands can accept pipeline input **by value** (by type) or **by property name**.</span></span> <span data-ttu-id="91b45-205">Вы можете писать свои функции так же, как машинные команды, чтобы они принимали один тип входных данных или оба.</span><span class="sxs-lookup"><span data-stu-id="91b45-205">You can write your functions just like the native commands so that they accept either one or both of these types of input.</span></span>

<span data-ttu-id="91b45-206">Чтобы принимать входные данные конвейера **по значению**, укажите атрибут параметра `ValueFromPipeline` для этого конкретного параметра.</span><span class="sxs-lookup"><span data-stu-id="91b45-206">To accept pipeline input **by value**, specified the `ValueFromPipeline` parameter attribute for that particular parameter.</span></span> <span data-ttu-id="91b45-207">Помните, что входные данные конвейера **по значению** можно принимать только от одного из каждого типа данных.</span><span class="sxs-lookup"><span data-stu-id="91b45-207">Keep in mind that you can only accept pipeline input **by value** from one of each datatype.</span></span> <span data-ttu-id="91b45-208">Например, если есть два параметра, принимающих строковые входные данные, то только один из них может принимать входные данные конвейера **по значению**, так как, если это условие указано для обоих строковых параметров, входным данным конвейера будет неизвестно, к какому параметру следует выполнить привязку.</span><span class="sxs-lookup"><span data-stu-id="91b45-208">For example, if you have two parameters that accept string input, only one of those can accept pipeline input **by value** because if you specified it for both of the string parameters, the pipeline input wouldn't know which one to bind to.</span></span> <span data-ttu-id="91b45-209">Это еще одна причина, по которой я называю этот тип входных данных конвейера _по типу_ вместо **по значению**.</span><span class="sxs-lookup"><span data-stu-id="91b45-209">This is another reason I call this type of pipeline input _by type_ instead of **by value**.</span></span>

<span data-ttu-id="91b45-210">Входные данные конвейера поступают в один элемент за раз аналогично тому, как элементы обрабатываются в цикле `foreach`.</span><span class="sxs-lookup"><span data-stu-id="91b45-210">Pipeline input comes in one item at a time similar to the way items are handled in a `foreach` loop.</span></span>
<span data-ttu-id="91b45-211">Если в качестве входных данных принимается массив, для обработки каждого из этих элементов требуется как минимум блок `process`.</span><span class="sxs-lookup"><span data-stu-id="91b45-211">At a minimum, a `process` block is required to process each of these items if you're accepting an array as input.</span></span> <span data-ttu-id="91b45-212">Если в качестве входных данных принимается только одно значение, блок `process` не требуется, но я по-прежнему рекомендую указывать его для обеспечения согласованности.</span><span class="sxs-lookup"><span data-stu-id="91b45-212">If you're only accepting a single value as input, a `process` block isn't necessary, but I still recommend specifying it for consistency.</span></span>

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline)]
        [string[]]$ComputerName
    )

    PROCESS {
        Write-Output $ComputerName
    }

}
```

<span data-ttu-id="91b45-213">Прием входных данных конвейера **по имени свойства** происходит аналогично, за исключением того, что указывается с помощью атрибута параметра `ValueFromPipelineByPropertyName` и может быть указан для любого числа параметров независимо от типа данных.</span><span class="sxs-lookup"><span data-stu-id="91b45-213">Accepting pipeline input **by property name** is similar except it's specified with the `ValueFromPipelineByPropertyName` parameter attribute and it can be specified for any number of parameters regardless of datatype.</span></span> <span data-ttu-id="91b45-214">Ключевом момент в том, что выходными данными команды, в которую передается параметр, должно быть имя свойства, совпадающее с именем параметра или псевдонимом параметра вашей функции.</span><span class="sxs-lookup"><span data-stu-id="91b45-214">The key is that the output of the command that's being piped in has to have a property name that matches the name of the parameter or a parameter alias of your function.</span></span>

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
            Write-Output $ComputerName
    }

}
```

<span data-ttu-id="91b45-215">Блоки `BEGIN` и `END` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="91b45-215">`BEGIN` and `END` blocks are optional.</span></span> <span data-ttu-id="91b45-216">`BEGIN` указывается перед блоком `PROCESS` и используется для выполнения всех начальных задач до получения элементов из конвейера.</span><span class="sxs-lookup"><span data-stu-id="91b45-216">`BEGIN` would be specified before the `PROCESS` block and is used to perform any initial work prior to the items being received from the pipeline.</span></span> <span data-ttu-id="91b45-217">Разобраться с этим очень важно.</span><span class="sxs-lookup"><span data-stu-id="91b45-217">This is important to understand.</span></span> <span data-ttu-id="91b45-218">Переданные значения недоступны в блоке `BEGIN`.</span><span class="sxs-lookup"><span data-stu-id="91b45-218">Values that are piped in are not accessible in the `BEGIN` block.</span></span> <span data-ttu-id="91b45-219">Блок `END` указывается после блока `PROCESS` и используется для очистки после обработки всех переданных элементов.</span><span class="sxs-lookup"><span data-stu-id="91b45-219">The `END` block would be specified after the `PROCESS` block and is used for cleanup once all of the items that are piped in have been processed.</span></span>

## <a name="error-handling"></a><span data-ttu-id="91b45-220">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="91b45-220">Error Handling</span></span>

<span data-ttu-id="91b45-221">Функция, показанная в следующем примере, создает необработанное исключение, если не удается связаться с компьютером.</span><span class="sxs-lookup"><span data-stu-id="91b45-221">The function shown in the following example generates an unhandled exception when a computer can't be contacted.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            Test-WSMan -ComputerName $Computer
        }
    }

}
```

<span data-ttu-id="91b45-222">В PowerShell существует несколько различных способов обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="91b45-222">There are a couple of different ways to handle errors in PowerShell.</span></span> <span data-ttu-id="91b45-223">Более современным является `Try/Catch`.</span><span class="sxs-lookup"><span data-stu-id="91b45-223">`Try/Catch` is the more modern way to handle errors.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

<span data-ttu-id="91b45-224">Хотя функция, показанная в предыдущем примере, использует обработку ошибок, она также выдает необработанное исключение, так как команда не создает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="91b45-224">Although the function shown in the previous example uses error handling, it also generates an unhandled exception because the command doesn't generate a terminating error.</span></span> <span data-ttu-id="91b45-225">Разобраться с этим очень важно!</span><span class="sxs-lookup"><span data-stu-id="91b45-225">This is also important to understand.</span></span> <span data-ttu-id="91b45-226">Перехватываются только устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="91b45-226">Only terminating errors are caught.</span></span> <span data-ttu-id="91b45-227">Чтобы преобразовать неустранимую ошибку в устранимую, укажите параметр **ErrorAction** со значением **Stop**.</span><span class="sxs-lookup"><span data-stu-id="91b45-227">Specify the **ErrorAction** parameter with **Stop** as the value to turn a non-terminating error into a terminating one.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer -ErrorAction Stop
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

<span data-ttu-id="91b45-228">Не изменяйте глобальную переменную `$ErrorActionPreference`, если в этом нет крайней необходимости.</span><span class="sxs-lookup"><span data-stu-id="91b45-228">Don't modify the global `$ErrorActionPreference` variable unless absolutely necessary.</span></span> <span data-ttu-id="91b45-229">Если вы используете нечто вроде .NET непосредственно в функции PowerShell, параметр **ErrorAction** невозможно указать в самой команде.</span><span class="sxs-lookup"><span data-stu-id="91b45-229">If you're using something like .NET directly from within your PowerShell function, you can't specify the **ErrorAction** on the command itself.</span></span> <span data-ttu-id="91b45-230">В этом случае может потребоваться изменить глобальную переменную `$ErrorActionPreference`, но, если вы измените ее, верните ее к исходному виду сразу же после того, как попробуете запустить команду.</span><span class="sxs-lookup"><span data-stu-id="91b45-230">In that scenario, you might need to change the global `$ErrorActionPreference` variable, but if you do change it, change it back immediately after trying the command.</span></span>

## <a name="comment-based-help"></a><span data-ttu-id="91b45-231">Справка на основе комментариев</span><span class="sxs-lookup"><span data-stu-id="91b45-231">Comment-Based Help</span></span>

<span data-ttu-id="91b45-232">В функции рекомендуется добавить справку на основе комментариев, чтобы пользователи, которым вы предоставляете доступ к функциям, могли знать, как их использовать.</span><span class="sxs-lookup"><span data-stu-id="91b45-232">It's considered to be a best practice to add comment based help to your functions so the people you're sharing them with will know how to use them.</span></span>

```powershell
function Get-MrAutoStoppedService {

<#
.SYNOPSIS
    Returns a list of services that are set to start automatically, are not
    currently running, excluding the services that are set to delayed start.

.DESCRIPTION
    Get-MrAutoStoppedService is a function that returns a list of services from
    the specified remote computer(s) that are set to start automatically, are not
    currently running, and it excludes the services that are set to start automatically
    with a delayed startup.

.PARAMETER ComputerName
    The remote computer(s) to check the status of the services on.

.PARAMETER Credential
    Specifies a user account that has permission to perform this action. The default
    is the current user.

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1', 'Server2'

.EXAMPLE
     'Server1', 'Server2' | Get-MrAutoStoppedService

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1' -Credential (Get-Credential)

.INPUTS
    String

.OUTPUTS
    PSCustomObject

.NOTES
    Author:  Mike F Robbins
    Website: http://mikefrobbins.com
    Twitter: @mikefrobbins
#>

    [CmdletBinding()]
    param (

    )

    #Function Body

}
```

<span data-ttu-id="91b45-233">Добавленную справку на основе комментариев можно получить так же, как встроенные команды по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91b45-233">When you add comment based help to your functions, help can be retrieved for them just like the default built-in commands.</span></span>

<span data-ttu-id="91b45-234">Весь синтаксис написания функции в PowerShell может показаться слишком объемным и перегруженным, особенно для тех, кто только начинает работу с этой оболочкой.</span><span class="sxs-lookup"><span data-stu-id="91b45-234">All of the syntax for writing a function in PowerShell can seem overwhelming especially for someone who is just getting started.</span></span> <span data-ttu-id="91b45-235">Часто, если я не могу вспомнить какой-то синтаксис, я открываю вторую копию ISE на отдельном мониторе, просматриваю фрагмент "Cmdlet (расширенная функция) — Complete" и одновременно ввожу код для функции.</span><span class="sxs-lookup"><span data-stu-id="91b45-235">Often times if I can't remember the syntax for something, I'll open a second copy of the ISE on a separate monitor and view the "Cmdlet (advanced function) - Complete" snippet while typing in the code for my function.</span></span> <span data-ttu-id="91b45-236">В интегрированной среде сценариев PowerShell доступ к фрагментам кода можно получить с помощью сочетания клавиш <kbd>CTRL</kbd>+<kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="91b45-236">Snippets can be accessed in the PowerShell ISE using the <kbd>Ctrl</kbd>+<kbd>J</kbd> key combination.</span></span>

## <a name="summary"></a><span data-ttu-id="91b45-237">Сводка</span><span class="sxs-lookup"><span data-stu-id="91b45-237">Summary</span></span>

<span data-ttu-id="91b45-238">В этой главе вы изучили основы написания функций в PowerShell, узнали, как преобразовать функцию в расширенную функцию, и ознакомились с некоторыми самыми важными моментами, которые следует учитывать при написании функций PowerShell, такими как проверка параметров, вывод подробных данных, входные данные конвейера, обработка ошибок и справка на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="91b45-238">In this chapter you've learned the basics of writing functions in PowerShell to include how to turn a function into an advanced function and some of the more important elements that you should consider when writing PowerShell functions such as parameter validation, verbose output, pipeline input, error handling, and comment based help.</span></span>

## <a name="review"></a><span data-ttu-id="91b45-239">Просмотр</span><span class="sxs-lookup"><span data-stu-id="91b45-239">Review</span></span>

1. <span data-ttu-id="91b45-240">Как получить список утвержденных глаголов в PowerShell?</span><span class="sxs-lookup"><span data-stu-id="91b45-240">How do you obtain a list of approved verbs in PowerShell?</span></span>
1. <span data-ttu-id="91b45-241">Как преобразовать функцию PowerShell в расширенную функцию?</span><span class="sxs-lookup"><span data-stu-id="91b45-241">How do you turn a PowerShell function into an advanced function?</span></span>
1. <span data-ttu-id="91b45-242">Когда следует добавлять параметры **WhatIf** и **Confirm** в функции PowerShell?</span><span class="sxs-lookup"><span data-stu-id="91b45-242">When should **WhatIf** and **Confirm** parameters be added to your PowerShell functions?</span></span>
1. <span data-ttu-id="91b45-243">Как преобразовать неустранимую ошибку в устранимую?</span><span class="sxs-lookup"><span data-stu-id="91b45-243">How do you turn a non-terminating error into a terminating one?</span></span>
1. <span data-ttu-id="91b45-244">Для чего нужно добавлять справку на основе комментариев к функциям?</span><span class="sxs-lookup"><span data-stu-id="91b45-244">Why should you add comment based help to your functions?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="91b45-245">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="91b45-245">Recommended Reading</span></span>

- <span data-ttu-id="91b45-246">[about_Functions][]</span><span class="sxs-lookup"><span data-stu-id="91b45-246">[about_Functions][]</span></span>
- <span data-ttu-id="91b45-247">[about_Functions_Advanced_Parameters][]</span><span class="sxs-lookup"><span data-stu-id="91b45-247">[about_Functions_Advanced_Parameters][]</span></span>
- <span data-ttu-id="91b45-248">[about_CommonParameters][]</span><span class="sxs-lookup"><span data-stu-id="91b45-248">[about_CommonParameters][]</span></span>
- <span data-ttu-id="91b45-249">[about_Functions_CmdletBindingAttribute][]</span><span class="sxs-lookup"><span data-stu-id="91b45-249">[about_Functions_CmdletBindingAttribute][]</span></span>
- <span data-ttu-id="91b45-250">[about_Functions_Advanced][]</span><span class="sxs-lookup"><span data-stu-id="91b45-250">[about_Functions_Advanced][]</span></span>
- <span data-ttu-id="91b45-251">[about_Try_Catch_Finally][]</span><span class="sxs-lookup"><span data-stu-id="91b45-251">[about_Try_Catch_Finally][]</span></span>
- <span data-ttu-id="91b45-252">[about_Comment_Based_Help][]</span><span class="sxs-lookup"><span data-stu-id="91b45-252">[about_Comment_Based_Help][]</span></span>
- <span data-ttu-id="91b45-253">[Видео: создание инструментов PowerShell с помощью расширенных функций и модулей сценариев][]</span><span class="sxs-lookup"><span data-stu-id="91b45-253">[Video: PowerShell Toolmaking with Advanced Functions and Script Modules][]</span></span>

<!-- link references -->
[about_Functions]: /powershell/module/microsoft.powershell.core/about/about_functions
[about_Functions_Advanced_Parameters]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters
[about_CommonParameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[about_Functions_CmdletBindingAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute
[about_Functions_Advanced]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[about_Try_Catch_Finally]: /powershell/module/microsoft.powershell.core/about/about_try_catch_finally
[about_Comment_Based_Help]: /powershell/module/microsoft.powershell.core/about/about_comment_based_help
[Видео: создание инструментов PowerShell с помощью расширенных функций и модулей сценариев]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/
[Video: PowerShell Toolmaking with Advanced Functions and Script Modules]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/
[Регистр Pascal]: /dotnet/standard/design-guidelines/capitalization-conventions
[Pascal case]: /dotnet/standard/design-guidelines/capitalization-conventions
