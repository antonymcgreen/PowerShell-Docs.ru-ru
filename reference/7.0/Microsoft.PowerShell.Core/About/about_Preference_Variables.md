---
description: Переменные, которые настраивают поведение PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 2f290020a66b2db15c41cc9581ae3582dda8c96d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231006"
---
# <a name="about-preference-variables"></a><span data-ttu-id="b362d-104">Сведения о переменных предпочтений</span><span class="sxs-lookup"><span data-stu-id="b362d-104">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="b362d-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="b362d-105">Short description</span></span>

<span data-ttu-id="b362d-106">Переменные, которые настраивают поведение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-106">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b362d-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b362d-107">Long description</span></span>

<span data-ttu-id="b362d-108">PowerShell включает набор переменных, которые позволяют настроить его поведение.</span><span class="sxs-lookup"><span data-stu-id="b362d-108">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="b362d-109">Эти переменные предпочтений работают подобно параметрам в системах на основе графического пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b362d-109">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="b362d-110">Переменные предпочтений влияют на операционную среду PowerShell, и все команды выполняются в среде.</span><span class="sxs-lookup"><span data-stu-id="b362d-110">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="b362d-111">Во многих случаях командлеты имеют параметры, которые можно использовать для переопределения поведения предпочтений для конкретной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-111">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="b362d-112">В следующей таблице перечислены переменные предпочтений и их значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b362d-112">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="b362d-113">Переменная</span><span class="sxs-lookup"><span data-stu-id="b362d-113">Variable</span></span>             |       <span data-ttu-id="b362d-114">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b362d-114">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="b362d-115">Высокий</span><span class="sxs-lookup"><span data-stu-id="b362d-115">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="b362d-116">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="b362d-116">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="b362d-117">Continue</span><span class="sxs-lookup"><span data-stu-id="b362d-117">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="b362d-118">конЦисевиев</span><span class="sxs-lookup"><span data-stu-id="b362d-118">ConciseView</span></span>               |
| `$FormatEnumerationLimit`        | <span data-ttu-id="b362d-119">4</span><span class="sxs-lookup"><span data-stu-id="b362d-119">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="b362d-120">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="b362d-120">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="b362d-121">False (не записано в журнал)</span><span class="sxs-lookup"><span data-stu-id="b362d-121">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="b362d-122">False (не записано в журнал)</span><span class="sxs-lookup"><span data-stu-id="b362d-122">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="b362d-123">True (в журнале)</span><span class="sxs-lookup"><span data-stu-id="b362d-123">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="b362d-124">True (в журнале)</span><span class="sxs-lookup"><span data-stu-id="b362d-124">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="b362d-125">True (в журнале)</span><span class="sxs-lookup"><span data-stu-id="b362d-125">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="b362d-126">True (в журнале)</span><span class="sxs-lookup"><span data-stu-id="b362d-126">True (logged)</span></span>             |
| `$MaximumHistoryCount`           | <span data-ttu-id="b362d-127">4096</span><span class="sxs-lookup"><span data-stu-id="b362d-127">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="b362d-128">(Символ пробела ( `" "` ))</span><span class="sxs-lookup"><span data-stu-id="b362d-128">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="b362d-129">Объект UTF8Encoding</span><span class="sxs-lookup"><span data-stu-id="b362d-129">UTF8Encoding object</span></span>       |
| `$ProgressPreference`            | <span data-ttu-id="b362d-130">Продолжить</span><span class="sxs-lookup"><span data-stu-id="b362d-130">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="b362d-131">(Нет-пустая хэш-таблица)</span><span class="sxs-lookup"><span data-stu-id="b362d-131">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="b362d-132">(нет)</span><span class="sxs-lookup"><span data-stu-id="b362d-132">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="b362d-133">Все</span><span class="sxs-lookup"><span data-stu-id="b362d-133">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="b362d-134">wsman</span><span class="sxs-lookup"><span data-stu-id="b362d-134">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="b362d-135">См. [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="b362d-135">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="b362d-136">(нет)</span><span class="sxs-lookup"><span data-stu-id="b362d-136">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="b362d-137">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="b362d-137">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="b362d-138">Continue</span><span class="sxs-lookup"><span data-stu-id="b362d-138">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="b362d-139">Неверно</span><span class="sxs-lookup"><span data-stu-id="b362d-139">False</span></span>                     |

<span data-ttu-id="b362d-140">PowerShell включает в себя следующие переменные среды, в которых хранятся пользовательские настройки.</span><span class="sxs-lookup"><span data-stu-id="b362d-140">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="b362d-141">Дополнительные сведения об этих переменных среды см. в разделе [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-141">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="b362d-142">Изменения в привилегированной переменной вступают в силу только в скриптах и функциях, если эти скрипты или функции определены в той же области видимости, в которой использовалась предпочтение.</span><span class="sxs-lookup"><span data-stu-id="b362d-142">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="b362d-143">Дополнительные сведения см. в разделе [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-143">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="b362d-144">Работа с переменными предпочтений</span><span class="sxs-lookup"><span data-stu-id="b362d-144">Working with preference variables</span></span>

<span data-ttu-id="b362d-145">В этом документе описываются все переменные предпочтений.</span><span class="sxs-lookup"><span data-stu-id="b362d-145">This document describes each of the preference variables.</span></span>

<span data-ttu-id="b362d-146">Чтобы отобразить текущее значение конкретной привилегированной переменной, введите имя переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-146">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="b362d-147">Например, следующая команда отображает `$ConfirmPreference` значение переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-147">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="b362d-148">Чтобы изменить значение переменной, используйте инструкцию присваивания.</span><span class="sxs-lookup"><span data-stu-id="b362d-148">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="b362d-149">Например, следующая инструкция изменяет `$ConfirmPreference` значение параметра на **Medium**.</span><span class="sxs-lookup"><span data-stu-id="b362d-149">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium**.</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="b362d-150">Заданные значения относятся к текущему сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-150">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="b362d-151">Чтобы сделать переменные эффективными во всех сеансах PowerShell, добавьте их в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-151">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="b362d-152">Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-152">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="b362d-153">Работа в удаленном режиме</span><span class="sxs-lookup"><span data-stu-id="b362d-153">Working remotely</span></span>

<span data-ttu-id="b362d-154">При выполнении команд на удаленном компьютере эти удаленные команды распространяются только на настройки, заданные в клиенте PowerShell удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="b362d-154">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="b362d-155">Например, при выполнении удаленной команды значение переменной удаленного компьютера `$DebugPreference` определяет реакцию PowerShell на отладку сообщений.</span><span class="sxs-lookup"><span data-stu-id="b362d-155">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="b362d-156">Дополнительные сведения об удаленных командах см. в разделе [about_Remote](about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-156">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="b362d-157">\$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="b362d-157">\$ConfirmPreference</span></span>

<span data-ttu-id="b362d-158">Определяет, будет ли PowerShell автоматически запрашивать подтверждение перед запуском командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="b362d-158">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="b362d-159">`$ConfirmPreference`Допустимые значения переменной: **High** , **Medium** или **Low**.</span><span class="sxs-lookup"><span data-stu-id="b362d-159">The `$ConfirmPreference` variable's valid values are **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="b362d-160">Командлетам и функциям назначается риск: **высокий** , **средний** или **низкий**.</span><span class="sxs-lookup"><span data-stu-id="b362d-160">Cmdlets and functions are assigned a risk of **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="b362d-161">Если значение `$ConfirmPreference` переменной меньше или равно риску, назначенному командлету или функции, PowerShell автоматически запрашивает подтверждение перед выполнением командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="b362d-161">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="b362d-162">Если `$ConfirmPreference` переменная имеет значение **None** , PowerShell никогда не выводит запрос автоматически перед выполнением командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="b362d-162">If the value of the `$ConfirmPreference` variable is **None** , PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="b362d-163">Чтобы изменить поведение подтверждения для всех командлетов и функций в сеансе, измените `$ConfirmPreference` значение переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-163">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="b362d-164">Чтобы переопределить `$ConfirmPreference` для одной команды, используйте параметр **Confirm** командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="b362d-164">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="b362d-165">Чтобы запросить подтверждение, используйте `-Confirm` .</span><span class="sxs-lookup"><span data-stu-id="b362d-165">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="b362d-166">Чтобы отключить подтверждение, используйте `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="b362d-166">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="b362d-167">Допустимые значения `$ConfirmPreference` :</span><span class="sxs-lookup"><span data-stu-id="b362d-167">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="b362d-168">**Нет** : PowerShell не выводит запрос автоматически.</span><span class="sxs-lookup"><span data-stu-id="b362d-168">**None** : PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="b362d-169">Чтобы запросить подтверждение определенной команды, используйте параметр **Confirm** командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="b362d-169">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="b362d-170">**Низкий** : PowerShell запрашивает подтверждение перед выполнением командлетов или функций с низким, средним или высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="b362d-170">**Low** : PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="b362d-171">**Средний** : PowerShell запрашивает подтверждение перед выполнением командлетов или функций со средним или высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="b362d-171">**Medium** : PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="b362d-172">**Высокий** : PowerShell запрашивает подтверждение перед запуском командлетов или функций с высоким риском.</span><span class="sxs-lookup"><span data-stu-id="b362d-172">**High** : PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="b362d-173">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b362d-173">Detailed explanation</span></span>

<span data-ttu-id="b362d-174">PowerShell может автоматически запрашивать подтверждение перед выполнением действия.</span><span class="sxs-lookup"><span data-stu-id="b362d-174">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="b362d-175">Например, если командлет или функция значительно затронет систему, чтобы удалить данные или использовать значительный объем системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b362d-175">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="b362d-176">Оценка риска — это атрибут командлета или функции, известный как его **ConfirmImpact**.</span><span class="sxs-lookup"><span data-stu-id="b362d-176">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact**.</span></span> <span data-ttu-id="b362d-177">Пользователи не могут изменить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="b362d-177">Users can't change it.</span></span>

<span data-ttu-id="b362d-178">Командлеты и функции, которые могут представлять риск для системы, имеют параметр **Confirm** , который можно использовать для запроса или подавления подтверждения отдельной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-178">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="b362d-179">Так как большинство командлетов и функций используют значение риска по умолчанию ( **ConfirmImpact** ) **Medium** , а значение по умолчанию `$ConfirmPreference` — **High** , возникает нередкое автоматическое подтверждение.</span><span class="sxs-lookup"><span data-stu-id="b362d-179">Because most cmdlets and functions use the default risk value, **ConfirmImpact** , of **Medium** , and the default value of `$ConfirmPreference` is **High** , automatic confirmation rarely occurs.</span></span> <span data-ttu-id="b362d-180">Однако можно активировать автоматическое подтверждение, изменив значение `$ConfirmPreference` на **средний** или **низкий**.</span><span class="sxs-lookup"><span data-stu-id="b362d-180">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low**.</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-181">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-181">Examples</span></span>

<span data-ttu-id="b362d-182">В этом примере показано воздействие `$ConfirmPreference` значения переменной по умолчанию **High**.</span><span class="sxs-lookup"><span data-stu-id="b362d-182">This example shows the effect of the `$ConfirmPreference` variable's default value, **High**.</span></span> <span data-ttu-id="b362d-183">**Высокое** значение служит только для подтверждения командлетов и функций с высоким риском.</span><span class="sxs-lookup"><span data-stu-id="b362d-183">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="b362d-184">Поскольку большинство командлетов и функций являются средним риском, они не подтверждают и не `Remove-Item` удаляют файл.</span><span class="sxs-lookup"><span data-stu-id="b362d-184">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="b362d-185">`-Confirm`При добавлении команды к команде пользователю предлагается подтверждение.</span><span class="sxs-lookup"><span data-stu-id="b362d-185">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="b362d-186">Используйте `-Confirm` для запроса подтверждения.</span><span class="sxs-lookup"><span data-stu-id="b362d-186">Use `-Confirm` to request confirmation.</span></span>

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

<span data-ttu-id="b362d-187">В следующем примере показан результат изменения значения `$ConfirmPreference` на **Medium**.</span><span class="sxs-lookup"><span data-stu-id="b362d-187">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium**.</span></span> <span data-ttu-id="b362d-188">Так как большинство командлетов и функций являются средним уровнем риска, они автоматически подтверждаются.</span><span class="sxs-lookup"><span data-stu-id="b362d-188">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="b362d-189">Чтобы отключить запрос подтверждения для одной команды, используйте параметр **Confirm** со значением `$false` .</span><span class="sxs-lookup"><span data-stu-id="b362d-189">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a><span data-ttu-id="b362d-190">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="b362d-190">\$DebugPreference</span></span>

<span data-ttu-id="b362d-191">Определяет реакцию PowerShell на отладку сообщений, созданных скриптом, командлетом или поставщиком, или с помощью `Write-Debug` команды в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b362d-191">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="b362d-192">Некоторые командлеты отображают сообщения об отладке, которые обычно являются техническими сообщениями, предназначенными для программистов и специалистов технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="b362d-192">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="b362d-193">По умолчанию сообщения отладки не отображаются, но можно отобразить сообщения отладки, изменив значение `$DebugPreference` .</span><span class="sxs-lookup"><span data-stu-id="b362d-193">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="b362d-194">Для отображения или скрытия сообщений об отладке для определенной команды можно использовать параметр **отладки** Common командлета.</span><span class="sxs-lookup"><span data-stu-id="b362d-194">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="b362d-195">См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-195">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="b362d-196">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-196">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-197">**Остановить** : отображает сообщение отладки и прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-197">**Stop** : Displays the debug message and stops executing.</span></span> <span data-ttu-id="b362d-198">Записывает ошибку в консоль.</span><span class="sxs-lookup"><span data-stu-id="b362d-198">Writes an error to the console.</span></span>
- <span data-ttu-id="b362d-199">**Запрос** : отображает сообщение об отладке и спрашивает, нужно ли продолжить.</span><span class="sxs-lookup"><span data-stu-id="b362d-199">**Inquire** : Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="b362d-200">Добавление общего параметра **Debug** к команде, если команда настроена для создания сообщения отладки, изменяет значение `$DebugPreference` переменной на " **запрос** ".</span><span class="sxs-lookup"><span data-stu-id="b362d-200">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire**.</span></span>
- <span data-ttu-id="b362d-201">**Продолжить** : отображает сообщение отладки и продолжает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-201">**Continue** : Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="b362d-202">**SilentlyContinue** : (по умолчанию) не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="b362d-202">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="b362d-203">Сообщение отладки не отображается, и выполнение продолжается без прерывания.</span><span class="sxs-lookup"><span data-stu-id="b362d-203">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-204">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-204">Examples</span></span>

<span data-ttu-id="b362d-205">В следующих примерах показан результат изменения значений `$DebugPreference` при `Write-Debug` входе команды в командную строку.</span><span class="sxs-lookup"><span data-stu-id="b362d-205">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="b362d-206">Это изменение затрагивает все сообщения отладки, включая сообщения, созданные командлетами и скриптами.</span><span class="sxs-lookup"><span data-stu-id="b362d-206">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="b362d-207">В примерах показан параметр **Debug** , который отображает или скрывает сообщения отладки, связанные с одной командой.</span><span class="sxs-lookup"><span data-stu-id="b362d-207">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="b362d-208">В этом примере показано воздействие `$DebugPreference` значения переменной по умолчанию **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="b362d-208">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue**.</span></span> <span data-ttu-id="b362d-209">По умолчанию `Write-Debug` сообщение отладки командлета не отображается, и обработка продолжится.</span><span class="sxs-lookup"><span data-stu-id="b362d-209">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="b362d-210">При использовании параметра **Debug** он переопределяет предпочтение для одной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-210">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="b362d-211">Отобразится сообщение отладки.</span><span class="sxs-lookup"><span data-stu-id="b362d-211">The debug message is displayed.</span></span>

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="b362d-212">В этом примере показан результат действия `$DebugPreference` со значением **Continue** .</span><span class="sxs-lookup"><span data-stu-id="b362d-212">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="b362d-213">Отобразится сообщение отладки, и команда продолжит обработку.</span><span class="sxs-lookup"><span data-stu-id="b362d-213">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="b362d-214">В этом примере используется параметр **Debug** со значением, `$false` чтобы подавить сообщение для одной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-214">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="b362d-215">Сообщение отладки не отображается.</span><span class="sxs-lookup"><span data-stu-id="b362d-215">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="b362d-216">В этом примере показано, как `$DebugPreference` задается значение параметра « **останавливает** ».</span><span class="sxs-lookup"><span data-stu-id="b362d-216">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="b362d-217">Появится сообщение об отладке, и команда будет остановлена.</span><span class="sxs-lookup"><span data-stu-id="b362d-217">The debug message is displayed and the command is stopped.</span></span>

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

<span data-ttu-id="b362d-218">В этом примере используется параметр **Debug** со значением, `$false` чтобы подавить сообщение для одной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-218">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="b362d-219">Сообщение отладки не отображается, и обработка не остановлена.</span><span class="sxs-lookup"><span data-stu-id="b362d-219">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="b362d-220">В этом примере показан результат `$DebugPreference` задания значения запроса. **Inquire**</span><span class="sxs-lookup"><span data-stu-id="b362d-220">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="b362d-221">Появится сообщение об отладке, и пользователю будет предложено подтвердить.</span><span class="sxs-lookup"><span data-stu-id="b362d-221">The debug message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="b362d-222">В этом примере используется параметр **Debug** со значением, `$false` чтобы подавить сообщение для одной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-222">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="b362d-223">Сообщение отладки не отображается, и обработка продолжится.</span><span class="sxs-lookup"><span data-stu-id="b362d-223">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="b362d-224">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="b362d-224">\$ErrorActionPreference</span></span>

<span data-ttu-id="b362d-225">Определяет, как PowerShell реагирует на устранимую ошибку, которая не останавливает обработку командлетов.</span><span class="sxs-lookup"><span data-stu-id="b362d-225">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="b362d-226">Например, в командной строке или в скрипте, командлете или поставщике, например в ошибках, создаваемых `Write-Error` командлетом.</span><span class="sxs-lookup"><span data-stu-id="b362d-226">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="b362d-227">Можно использовать общий параметр командлета **ErrorAction** , чтобы переопределить предпочтения для определенной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-227">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="b362d-228">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-228">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-229">**Останов** — введите отладчик при возникновении ошибки или при возникновении исключения.</span><span class="sxs-lookup"><span data-stu-id="b362d-229">**Break** - Enter the debugger when an error occurs or when an exception is raised.</span></span>
- <span data-ttu-id="b362d-230">**Продолжить** : (по умолчанию) отображает сообщение об ошибке и продолжает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-230">**Continue** : (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="b362d-231">**Ignore** : подавляет вывод сообщения об ошибке и продолжение выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-231">**Ignore** : Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="b362d-232">Значение **Ignore** предназначено для использования в отдельных командах, а не для использования в качестве сохраненного предпочтения.</span><span class="sxs-lookup"><span data-stu-id="b362d-232">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="b362d-233">**Ignore** не является допустимым значением для `$ErrorActionPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-233">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="b362d-234">**Запрос** : отображает сообщение об ошибке и запрашивает, нужно ли продолжить.</span><span class="sxs-lookup"><span data-stu-id="b362d-234">**Inquire** : Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="b362d-235">**SilentlyContinue** : не влияет.</span><span class="sxs-lookup"><span data-stu-id="b362d-235">**SilentlyContinue** : No effect.</span></span> <span data-ttu-id="b362d-236">Сообщение об ошибке не отображается, и выполнение продолжается без прерывания.</span><span class="sxs-lookup"><span data-stu-id="b362d-236">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="b362d-237">**Остановить** : отображает сообщение об ошибке и прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-237">**Stop** : Displays the error message and stops executing.</span></span> <span data-ttu-id="b362d-238">В дополнение к созданной ошибке, значение « **останавливает** » создает объект актионпреференцестопексцептион для потока ошибок.</span><span class="sxs-lookup"><span data-stu-id="b362d-238">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="b362d-239">поток</span><span class="sxs-lookup"><span data-stu-id="b362d-239">stream</span></span>
- <span data-ttu-id="b362d-240">**Приостановить** : автоматически приостанавливает задание рабочего процесса, чтобы обеспечить дальнейшее исследование.</span><span class="sxs-lookup"><span data-stu-id="b362d-240">**Suspend** : Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="b362d-241">После изучения рабочий процесс можно возобновить.</span><span class="sxs-lookup"><span data-stu-id="b362d-241">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="b362d-242">Значение **приостановки** предназначено для использования в отдельных командах, а не для использования в качестве сохраненного предпочтения.</span><span class="sxs-lookup"><span data-stu-id="b362d-242">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="b362d-243">**Приостановка** не является допустимым значением для `$ErrorActionPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-243">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="b362d-244">`$ErrorActionPreference` и параметр **ErrorAction** не влияет на то, как PowerShell реагирует на прерывание ошибок, которые останавливают обработку командлетов.</span><span class="sxs-lookup"><span data-stu-id="b362d-244">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="b362d-245">Дополнительные сведения об общем параметре **ErrorAction** см. в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-245">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-246">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-246">Examples</span></span>

<span data-ttu-id="b362d-247">В этих примерах показано воздействие различных значений `$ErrorActionPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-247">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="b362d-248">Параметр **ErrorAction** используется для переопределения `$ErrorActionPreference` значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-248">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="b362d-249">В этом примере показано `$ErrorActionPreference` значение по умолчанию, **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="b362d-249">This example shows the `$ErrorActionPreference` default value, **Continue**.</span></span> <span data-ttu-id="b362d-250">Создается устранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="b362d-250">A non-terminating error is generated.</span></span> <span data-ttu-id="b362d-251">Сообщение отображается и обработка продолжится.</span><span class="sxs-lookup"><span data-stu-id="b362d-251">The message is displayed and processing continues.</span></span>

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error: Test Error
Hello World
```

<span data-ttu-id="b362d-252">В этом примере показано `$ErrorActionPreference` значение по умолчанию — **запрос**.</span><span class="sxs-lookup"><span data-stu-id="b362d-252">This example shows the `$ErrorActionPreference` default value, **Inquire**.</span></span> <span data-ttu-id="b362d-253">Выводится сообщение об ошибке, и отображается запрос на ввод действия.</span><span class="sxs-lookup"><span data-stu-id="b362d-253">An error is generated and a prompt for action is shown.</span></span>

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="b362d-254">В этом примере показан `$ErrorActionPreference` набор для **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="b362d-254">This example shows the `$ErrorActionPreference` set to **SilentlyContinue**.</span></span>
<span data-ttu-id="b362d-255">Сообщение об ошибке подавляется.</span><span class="sxs-lookup"><span data-stu-id="b362d-255">The error message is suppressed.</span></span>

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

<span data-ttu-id="b362d-256">В этом примере показан `$ErrorActionPreference` набор для **отмены**.</span><span class="sxs-lookup"><span data-stu-id="b362d-256">This example shows the `$ErrorActionPreference` set to **Stop**.</span></span> <span data-ttu-id="b362d-257">Он также показывает дополнительный объект, созданный для `$Error` переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-257">It also shows the extra object generated to the `$Error` variable.</span></span>

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error: Test Error

ErrorRecord                 : Test Error
WasThrownFromThrowStatement : False
TargetSite                  : System.Collections.ObjectModel.Collection`1[System.Management.Automation.PSObject]
                              Invoke(System.Collections.IEnumerable)
StackTrace                  :    at System.Management.Automation.Runspaces.PipelineBase.Invoke(IEnumerable input)
                                 at Microsoft.PowerShell.Executor.ExecuteCommandHelper(Pipeline tempPipeline,
                              Exception& exceptionThrown, ExecutionOptions options)
Message                     : The running command stopped because the preference variable "ErrorActionPreference" or
                              common parameter is set to Stop: Test Error
Data                        : {System.Management.Automation.Interpreter.InterpretedFrameInfo}
InnerException              :
HelpLink                    :
Source                      : System.Management.Automation
HResult                     : -2146233087

Write-Error: Test Error
```

### <a name="errorview"></a><span data-ttu-id="b362d-258">\$еррорвиев</span><span class="sxs-lookup"><span data-stu-id="b362d-258">\$ErrorView</span></span>

<span data-ttu-id="b362d-259">Определяет формат вывода сообщений об ошибках в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-259">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="b362d-260">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-260">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-261">**КонЦисевиев** : (по умолчанию) предоставляет краткое сообщение об ошибке и рефакторингное представление для расширенных построителей модулей.</span><span class="sxs-lookup"><span data-stu-id="b362d-261">**ConciseView** : (Default) Provides a concise error message and a refactored view for advanced module builders.</span></span> <span data-ttu-id="b362d-262">Если ошибка происходит из командной строки, это сообщение об ошибке одной строки.</span><span class="sxs-lookup"><span data-stu-id="b362d-262">If the error is from command line it's a single line error message.</span></span> <span data-ttu-id="b362d-263">В противном случае вы получите многострочное сообщение об ошибке, содержащее ошибку, и указатель на ошибку, указывающий, где она встречается в этой строке.</span><span class="sxs-lookup"><span data-stu-id="b362d-263">Otherwise, you receive a multiline error message that contains the error and a pointer to the error showing where it occurs in that line.</span></span> <span data-ttu-id="b362d-264">Если терминал поддерживает виртуальный терминал, то для предоставления цветовой контрастности используются коды цветов ANSI.</span><span class="sxs-lookup"><span data-stu-id="b362d-264">If the terminal supports Virtual Terminal, then ANSI color codes are used to provide color accent.</span></span> <span data-ttu-id="b362d-265">Цвет диакритических знаков можно изменить в `$Host.PrivateData.ErrorAccentColor` .</span><span class="sxs-lookup"><span data-stu-id="b362d-265">The Accent color can be changed at `$Host.PrivateData.ErrorAccentColor`.</span></span> <span data-ttu-id="b362d-266">Используйте `Get-Error` командлет, чтобы получить исчерпывающее подробное представление о полном сообщении об ошибке, включая внутренние исключения.</span><span class="sxs-lookup"><span data-stu-id="b362d-266">Use `Get-Error` cmdlet for a comprehensive detailed view of the fully qualified error, including inner exceptions.</span></span>

  <span data-ttu-id="b362d-267">**КонЦисевиев** был добавлен в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="b362d-267">**ConciseView** was added in PowerShell 7.</span></span>

- <span data-ttu-id="b362d-268">**Нормалвиев** : подробное представление, предназначенное для большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="b362d-268">**NormalView** : A detailed view designed for most users.</span></span> <span data-ttu-id="b362d-269">Состоит из описания ошибки и имени объекта, участвующего в ошибке.</span><span class="sxs-lookup"><span data-stu-id="b362d-269">Consists of a description of the error and the name of the object involved in the error.</span></span>

- <span data-ttu-id="b362d-270">**Категоривиев** : краткое структурированное представление, предназначенное для рабочих сред.</span><span class="sxs-lookup"><span data-stu-id="b362d-270">**CategoryView** : A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="b362d-271">Используется следующий формат:</span><span class="sxs-lookup"><span data-stu-id="b362d-271">The format is as follows:</span></span>

  <span data-ttu-id="b362d-272">{Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}</span><span class="sxs-lookup"><span data-stu-id="b362d-272">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="b362d-273">Дополнительные сведения о полях в **категоривиев** см. в разделе класс [ерроркатегоринфо](/dotnet/api/system.management.automation.errorcategoryinfo) .</span><span class="sxs-lookup"><span data-stu-id="b362d-273">For more information about the fields in **CategoryView** , see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-274">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-274">Examples</span></span>

<span data-ttu-id="b362d-275">В этом примере показано, как возникает ошибка, если значением `$ErrorView` по умолчанию является **конЦисевиев**.</span><span class="sxs-lookup"><span data-stu-id="b362d-275">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="b362d-276">`Get-ChildItem` используется для поиска несуществующего каталога.</span><span class="sxs-lookup"><span data-stu-id="b362d-276">`Get-ChildItem` is used to find a non-existent directory.</span></span>

```powershell
Get-ChildItem -path 'C:\NoRealDirectory'
```

```Output
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.
```

<span data-ttu-id="b362d-277">В этом примере показано, как возникает ошибка, если значением `$ErrorView` по умолчанию является **конЦисевиев**.</span><span class="sxs-lookup"><span data-stu-id="b362d-277">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="b362d-278">`Script.ps1` запускается и вызывает ошибку из `Get-Item` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b362d-278">`Script.ps1` is run and throws an error from `Get-Item` statement.</span></span>

```powershell
./Script.ps1
```

```Output
Get-Item: C:\Script.ps1
Line |
  11 | Get-Item -Path .\stuff
     | ^ Cannot find path 'C:\demo\stuff' because it does not exist.
```

<span data-ttu-id="b362d-279">В этом примере показано, как возникает ошибка при изменении значения `$ErrorView` на **нормалвиев**.</span><span class="sxs-lookup"><span data-stu-id="b362d-279">This example shows how an error appears when the value of `$ErrorView` is changed to **NormalView**.</span></span> <span data-ttu-id="b362d-280">`Get-ChildItem` используется для поиска несуществующего файла.</span><span class="sxs-lookup"><span data-stu-id="b362d-280">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="b362d-281">В этом примере показано, как эта же ошибка возникает при `$ErrorView` изменении значения на **категоривиев**.</span><span class="sxs-lookup"><span data-stu-id="b362d-281">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView**.</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="b362d-282">В этом примере показано, что значение `$ErrorView` влияет только на отображение ошибок.</span><span class="sxs-lookup"><span data-stu-id="b362d-282">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="b362d-283">Она не изменяет структуру объекта Error, который хранится в `$Error` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-283">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="b362d-284">Дополнительные сведения об `$Error` автоматической переменной см. в разделе [about_automatic_variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-284">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="b362d-285">Следующая команда принимает объект **ерроррекорд** , связанный с самой последней ошибкой в массиве ошибок, **элемент 0** , и форматирует все свойства объекта Error в списке.</span><span class="sxs-lookup"><span data-stu-id="b362d-285">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0** , and formats all the error object's properties in a list.</span></span>

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a><span data-ttu-id="b362d-286">\$форматенумератионлимит</span><span class="sxs-lookup"><span data-stu-id="b362d-286">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="b362d-287">Определяет, сколько элементов перечисления включается в отображение.</span><span class="sxs-lookup"><span data-stu-id="b362d-287">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="b362d-288">Эта переменная не влияет на базовые объекты, а только на отображение.</span><span class="sxs-lookup"><span data-stu-id="b362d-288">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="b362d-289">Если значение меньше `$FormatEnumerationLimit` числа перечисленных элементов, в PowerShell добавляется многоточие ( `...` ), показывающее, что элементы не показаны.</span><span class="sxs-lookup"><span data-stu-id="b362d-289">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="b362d-290">**Допустимые значения** : целые числа ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="b362d-290">**Valid values** : Integers (`Int32`)</span></span>

<span data-ttu-id="b362d-291">**Значение по умолчанию** : 4</span><span class="sxs-lookup"><span data-stu-id="b362d-291">**Default value** : 4</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-292">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-292">Examples</span></span>

<span data-ttu-id="b362d-293">В этом примере показано, как использовать `$FormatEnumerationLimit` переменную для улучшения отображения перечисленных элементов.</span><span class="sxs-lookup"><span data-stu-id="b362d-293">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="b362d-294">В этом примере команда создает таблицу, в которой перечислены все службы, выполняющиеся на компьютере, в двух группах: одна для **запуска** служб, а другая для **остановленных** служб.</span><span class="sxs-lookup"><span data-stu-id="b362d-294">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="b362d-295">Он использует `Get-Service` команду для получения всех служб, а затем отправляет результаты по конвейеру в `Group-Object` командлет, который группирует результаты по состоянию службы.</span><span class="sxs-lookup"><span data-stu-id="b362d-295">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="b362d-296">Результатом является таблица со списком состояний в столбце **имя** и процессами в столбце **Group** .</span><span class="sxs-lookup"><span data-stu-id="b362d-296">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="b362d-297">Чтобы изменить метки столбцов, используйте хэш-таблицу, описанную в разделе [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-297">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="b362d-298">Дополнительные сведения см. в примерах в разделе [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="b362d-298">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="b362d-299">Найти текущее значение `$FormatEnumerationLimit` .</span><span class="sxs-lookup"><span data-stu-id="b362d-299">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="b362d-300">Список всех служб, сгруппированных по **состоянию**.</span><span class="sxs-lookup"><span data-stu-id="b362d-300">List all services grouped by **Status**.</span></span> <span data-ttu-id="b362d-301">Существует не более четырех служб, перечисленных в столбце **Group** для каждого состояния, так как `$FormatEnumerationLimit` имеет значение **4**.</span><span class="sxs-lookup"><span data-stu-id="b362d-301">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4**.</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="b362d-302">Чтобы увеличить количество элементов в списке, увеличьте значение `$FormatEnumerationLimit` до **1000**.</span><span class="sxs-lookup"><span data-stu-id="b362d-302">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000**.</span></span> <span data-ttu-id="b362d-303">Используйте `Get-Service` и `Group-Object` для вывода служб.</span><span class="sxs-lookup"><span data-stu-id="b362d-303">Use `Get-Service` and `Group-Object` to display the services.</span></span>

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

<span data-ttu-id="b362d-304">Используйте `Format-Table` с параметром **Wrap** для вывода списка служб.</span><span class="sxs-lookup"><span data-stu-id="b362d-304">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a><span data-ttu-id="b362d-305">\$InformationPreference</span><span class="sxs-lookup"><span data-stu-id="b362d-305">\$InformationPreference</span></span>

<span data-ttu-id="b362d-306">`$InformationPreference`Переменная позволяет задать параметры потока информации, которые должны отображаться для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b362d-306">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="b362d-307">В частности, информационные сообщения, добавленные в команды или скрипты путем добавления командлета [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) .</span><span class="sxs-lookup"><span data-stu-id="b362d-307">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="b362d-308">Если используется параметр **InformationAction** , его значение переопределяет значение `$InformationPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-308">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="b362d-309">`Write-Information` впервые появился в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="b362d-309">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="b362d-310">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-310">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-311">**Остановить** : останавливает выполнение команды или скрипта при возникновении `Write-Information` команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-311">**Stop** : Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="b362d-312">**Запрос** : отображает информационное сообщение, указанное в `Write-Information` команде, а затем спрашивает, хотите ли вы продолжить.</span><span class="sxs-lookup"><span data-stu-id="b362d-312">**Inquire** : Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="b362d-313">**Продолжить** : отображает информационное сообщение и продолжает выполняться.</span><span class="sxs-lookup"><span data-stu-id="b362d-313">**Continue** : Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="b362d-314">**Приостановка** доступна только для рабочих процессов, которые не поддерживаются в PowerShell 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="b362d-314">**Suspend** is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>
- <span data-ttu-id="b362d-315">**SilentlyContinue** : (по умолчанию) не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="b362d-315">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="b362d-316">Информационные сообщения не отображаются, и сценарий продолжается без прерывания.</span><span class="sxs-lookup"><span data-stu-id="b362d-316">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="b362d-317">\$Событие log \*</span><span class="sxs-lookup"><span data-stu-id="b362d-317">\$Log\*Event</span></span>

<span data-ttu-id="b362d-318">Переменные настройки \*\*события log \*\*\* определяют, какие типы событий записываются в журнал событий PowerShell в Просмотр событий.</span><span class="sxs-lookup"><span data-stu-id="b362d-318">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="b362d-319">По умолчанию регистрируются только события подсистемы и поставщика.</span><span class="sxs-lookup"><span data-stu-id="b362d-319">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="b362d-320">Но вы можете использовать переменные настройки \*\*событий Log \*\*\* для настройки журнала, например ведения журнала событий о командах.</span><span class="sxs-lookup"><span data-stu-id="b362d-320">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="b362d-321">Ниже приведены переменные настройки \*\*события log \*\*\* .</span><span class="sxs-lookup"><span data-stu-id="b362d-321">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="b362d-322">`$LogCommandHealthEvent`: Регистрирует ошибки и исключения при инициализации и обработке команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-322">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="b362d-323">Значение по умолчанию — `$false` (не заносится в журнал).</span><span class="sxs-lookup"><span data-stu-id="b362d-323">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="b362d-324">`$LogCommandLifecycleEvent`: Записывает в журнал запуск и остановку команд и командных конвейеров и исключений безопасности при обнаружении команд.</span><span class="sxs-lookup"><span data-stu-id="b362d-324">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="b362d-325">Значение по умолчанию — `$false` (не заносится в журнал).</span><span class="sxs-lookup"><span data-stu-id="b362d-325">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="b362d-326">`$LogEngineHealthEvent`: Регистрирует ошибки и сбои сеансов.</span><span class="sxs-lookup"><span data-stu-id="b362d-326">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="b362d-327">Значение по умолчанию — `$true` (Протоколируется).</span><span class="sxs-lookup"><span data-stu-id="b362d-327">The default is `$true` (logged).</span></span>
- <span data-ttu-id="b362d-328">`$LogEngineLifecycleEvent`: Записывает в журнал открытие и закрытие сеансов.</span><span class="sxs-lookup"><span data-stu-id="b362d-328">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="b362d-329">Значение по умолчанию — `$true` (Протоколируется).</span><span class="sxs-lookup"><span data-stu-id="b362d-329">The default is `$true` (logged).</span></span>
- <span data-ttu-id="b362d-330">`$LogProviderHealthEvent`: Регистрирует ошибки поставщика, такие как ошибки чтения и записи, ошибки поиска и ошибки вызова.</span><span class="sxs-lookup"><span data-stu-id="b362d-330">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="b362d-331">Значение по умолчанию — `$true` (Протоколируется).</span><span class="sxs-lookup"><span data-stu-id="b362d-331">The default is `$true` (logged).</span></span>
- <span data-ttu-id="b362d-332">`$LogProviderLifecycleEvent`: Регистрирует Добавление и удаление поставщиков PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-332">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="b362d-333">Значение по умолчанию — `$true` (Протоколируется).</span><span class="sxs-lookup"><span data-stu-id="b362d-333">The default is `$true` (logged).</span></span> <span data-ttu-id="b362d-334">Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-334">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="b362d-335">Чтобы включить \*\*событие log \*\*\* , введите переменную со значением `$true` , например:</span><span class="sxs-lookup"><span data-stu-id="b362d-335">To enable a **Log\*Event** , type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="b362d-336">Чтобы отключить тип события, введите переменную со значением `$false` , например:</span><span class="sxs-lookup"><span data-stu-id="b362d-336">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="b362d-337">Включенные события вступают в силу только для текущей консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-337">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="b362d-338">Чтобы применить конфигурацию ко всем консолям, сохраните параметры переменной в профиле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-338">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="b362d-339">Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-339">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="b362d-340">\$максимумхисторикаунт</span><span class="sxs-lookup"><span data-stu-id="b362d-340">\$MaximumHistoryCount</span></span>

<span data-ttu-id="b362d-341">Определяет, сколько команд сохраняется в журнале команд для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="b362d-341">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="b362d-342">**Допустимые значения** : 1-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="b362d-342">**Valid values** : 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="b362d-343">**По умолчанию** : 4096</span><span class="sxs-lookup"><span data-stu-id="b362d-343">**Default** : 4096</span></span>

<span data-ttu-id="b362d-344">Чтобы определить количество команд, сохраненных в журнале команд, введите:</span><span class="sxs-lookup"><span data-stu-id="b362d-344">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="b362d-345">Чтобы просмотреть команды, сохраненные в журнале сеанса, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="b362d-345">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="b362d-346">Дополнительные сведения см. в разделе [about_History](about_History.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-346">For more information, see [about_History](about_History.md).</span></span>

### <a name="ofs"></a><span data-ttu-id="b362d-347">\$OFS</span><span class="sxs-lookup"><span data-stu-id="b362d-347">\$OFS</span></span>

<span data-ttu-id="b362d-348">Разделитель полей вывода (OFS) определяет символ, разделяющий элементы массива, которые преобразуются в строку.</span><span class="sxs-lookup"><span data-stu-id="b362d-348">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="b362d-349">**Допустимые значения** : любая строка.</span><span class="sxs-lookup"><span data-stu-id="b362d-349">**Valid values** : Any string.</span></span>

<span data-ttu-id="b362d-350">**По умолчанию** : пробел</span><span class="sxs-lookup"><span data-stu-id="b362d-350">**Default** : Space</span></span>

<span data-ttu-id="b362d-351">По умолчанию `$OFS` переменная не существует, а разделитель выходного файла является пробелом, но можно добавить эту переменную и задать ее в любой строке.</span><span class="sxs-lookup"><span data-stu-id="b362d-351">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="b362d-352">Вы можете изменить значение `$OFS` в своем сеансе, введя `$OFS="<value>"` .</span><span class="sxs-lookup"><span data-stu-id="b362d-352">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="b362d-353">Если вы ожидаете значение по умолчанию пробела ( `" "` ) в скрипте, модуле или выходных данных конфигурации, будьте внимательны в том, что `$OFS` значение по умолчанию не было изменено в других местах кода.</span><span class="sxs-lookup"><span data-stu-id="b362d-353">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-354">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-354">Examples</span></span>

<span data-ttu-id="b362d-355">В этом примере показано, что пространство используется для разделения значений при преобразовании массива в строку.</span><span class="sxs-lookup"><span data-stu-id="b362d-355">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="b362d-356">В этом случае массив целых чисел хранится в переменной, а переменная преобразуется в строку.</span><span class="sxs-lookup"><span data-stu-id="b362d-356">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="b362d-357">Чтобы изменить разделитель, добавьте `$OFS` переменную, назначив ей значение.</span><span class="sxs-lookup"><span data-stu-id="b362d-357">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="b362d-358">Переменная должна иметь имя `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="b362d-358">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="b362d-359">Чтобы восстановить поведение по умолчанию, можно назначить пробел ( `" "` ) значению `$OFS` или удалить переменную.</span><span class="sxs-lookup"><span data-stu-id="b362d-359">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="b362d-360">Следующие команды удаляют переменную и проверяют, что разделитель является пробелом.</span><span class="sxs-lookup"><span data-stu-id="b362d-360">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="b362d-361">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="b362d-361">\$OutputEncoding</span></span>

<span data-ttu-id="b362d-362">Определяет метод кодировки символов, используемый PowerShell при отправке текста в другие приложения.</span><span class="sxs-lookup"><span data-stu-id="b362d-362">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="b362d-363">Например, если приложение возвращает строки в Юникоде в PowerShell, может потребоваться изменить значение на **UnicodeEncoding** , чтобы правильно отправить символы.</span><span class="sxs-lookup"><span data-stu-id="b362d-363">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="b362d-364">Допустимы следующие значения: объекты, производные от класса кодирования, такие как **ASCIIEncoding** , **сбкскодепажеенкодинг** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** и **UnicodeEncoding**.</span><span class="sxs-lookup"><span data-stu-id="b362d-364">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding** , **SBCSCodePageEncoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** , and **UnicodeEncoding**.</span></span>

<span data-ttu-id="b362d-365">**По умолчанию** : объект UTF8Encoding (System. Text. UTF8Encoding)</span><span class="sxs-lookup"><span data-stu-id="b362d-365">**Default** : UTF8Encoding object (System.Text.UTF8Encoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-366">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-366">Examples</span></span>

<span data-ttu-id="b362d-367">В этом примере показано, как заставить команду Windows **findstr.exe** работать в PowerShell на компьютере, локализованном для языка, который использует символы Юникода, например китайский.</span><span class="sxs-lookup"><span data-stu-id="b362d-367">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="b362d-368">Первая команда находит значение `$OutputEncoding` .</span><span class="sxs-lookup"><span data-stu-id="b362d-368">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="b362d-369">Поскольку значение является объектом кодировки, отобразится только свойство **EncodingName** .</span><span class="sxs-lookup"><span data-stu-id="b362d-369">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="b362d-370">В этом примере используется команда **findstr.exe** для поиска двух китайских символов, которые содержатся в `Test.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="b362d-370">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="b362d-371">При выполнении этой **findstr.exe** команды в командной строке Windows ( **cmd.exe** ) **findstr.exe** находит символы в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="b362d-371">When this **findstr.exe** command is run in the Windows Command Prompt ( **cmd.exe** ), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="b362d-372">Однако при выполнении той **findstr.exe** же команды в PowerShell символы не найдены, так как PowerShell отправляет их в **findstr.exe** в тексте ASCII, а не в тексте в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="b362d-372">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="b362d-373">Чтобы команда работала в PowerShell, присвойте `$OutputEncoding` свойству **OutputEncoding** консоли значение, основанное на языковом стандарте, выбранном для Windows.</span><span class="sxs-lookup"><span data-stu-id="b362d-373">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="b362d-374">Поскольку **OutputEncoding** является статическим свойством консоли, в команде следует использовать двойные двоеточия ( `::` ).</span><span class="sxs-lookup"><span data-stu-id="b362d-374">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="b362d-375">После изменения кодировки команда **findstr.exe** находит символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="b362d-375">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="b362d-376">\$прогресспреференце</span><span class="sxs-lookup"><span data-stu-id="b362d-376">\$ProgressPreference</span></span>

<span data-ttu-id="b362d-377">Определяет, как PowerShell реагирует на обновления хода выполнения, создаваемые сценарием, командлетом или поставщиком, например индикаторами выполнения, созданными командлетом [записи](xref:Microsoft.PowerShell.Utility.Write-Progress) .</span><span class="sxs-lookup"><span data-stu-id="b362d-377">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="b362d-378">`Write-Progress`Командлет создает индикаторы выполнения, отображающие состояние команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-378">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="b362d-379">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-379">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-380">**Завершение** : не отображает индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="b362d-380">**Stop** : Doesn't display the progress bar.</span></span> <span data-ttu-id="b362d-381">Вместо этого отображается сообщение об ошибке и прекращается выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-381">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="b362d-382">**Запрос** : не отображает индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="b362d-382">**Inquire** : Doesn't display the progress bar.</span></span> <span data-ttu-id="b362d-383">Запрашивает разрешение на продолжение.</span><span class="sxs-lookup"><span data-stu-id="b362d-383">Prompts for permission to continue.</span></span> <span data-ttu-id="b362d-384">При ответе с помощью `Y` или `A` отображается индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="b362d-384">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="b362d-385">**Продолжить** : (по умолчанию) отображает индикатор выполнения и продолжает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-385">**Continue** : (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="b362d-386">**SilentlyContinue** : выполняет команду, но не отображает индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="b362d-386">**SilentlyContinue** : Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="b362d-387">\$Привилегированной PSEmailServer</span><span class="sxs-lookup"><span data-stu-id="b362d-387">\$PSEmailServer</span></span>

<span data-ttu-id="b362d-388">Указывает сервер электронной почты по умолчанию, используемый для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b362d-388">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="b362d-389">Эта переменная предпочтений используется командлетами, которые отправляют электронную почту, например командлет [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) .</span><span class="sxs-lookup"><span data-stu-id="b362d-389">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="b362d-390">\$псдефаултпараметервалуес</span><span class="sxs-lookup"><span data-stu-id="b362d-390">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="b362d-391">Задает значения по умолчанию для параметров командлетов и дополнительных функций.</span><span class="sxs-lookup"><span data-stu-id="b362d-391">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="b362d-392">Значение `$PSDefaultParameterValues` является хэш-таблицей, в которой ключ состоит из имени командлета и имени параметра, разделенных двоеточием ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="b362d-392">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="b362d-393">Значение — это пользовательское значение по умолчанию, которое вы указали.</span><span class="sxs-lookup"><span data-stu-id="b362d-393">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="b362d-394">`$PSDefaultParameterValues` впервые появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b362d-394">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="b362d-395">Дополнительные сведения об этой переменной предпочтений см. в разделе [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-395">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="b362d-396">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="b362d-396">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="b362d-397">Включает и отключает автоматический импорт модулей в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b362d-397">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="b362d-398">По умолчанию используется значение **ALL** .</span><span class="sxs-lookup"><span data-stu-id="b362d-398">**All** is the default.</span></span> <span data-ttu-id="b362d-399">Независимо от значения переменной можно импортировать модуль с помощью [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) .</span><span class="sxs-lookup"><span data-stu-id="b362d-399">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="b362d-400">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b362d-400">Valid values are:</span></span>

- <span data-ttu-id="b362d-401">**Все** : модули импортируются автоматически при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="b362d-401">**All** : Modules are imported automatically on first-use.</span></span> <span data-ttu-id="b362d-402">Чтобы импортировать модуль, необходимо получить или использовать любую команду в модуле.</span><span class="sxs-lookup"><span data-stu-id="b362d-402">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="b362d-403">Например, воспользуйтесь `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="b362d-403">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="b362d-404">**Модулекуалифиед** : модули импортируются автоматически только в том случае, если пользователь использует полное имя модуля команды в модуле.</span><span class="sxs-lookup"><span data-stu-id="b362d-404">**ModuleQualified** : Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="b362d-405">Например, если пользователь вводит `MyModule\MyCommand` , PowerShell импортирует модуль **MyModule** .</span><span class="sxs-lookup"><span data-stu-id="b362d-405">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="b362d-406">**Нет** : автоматический импорт модулей отключен в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b362d-406">**None** : Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="b362d-407">Чтобы импортировать модуль, используйте `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="b362d-407">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="b362d-408">Дополнительные сведения об автоматическом импорте модулей см. в разделе [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-408">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="b362d-409">\$PSSessionApplicationName</span><span class="sxs-lookup"><span data-stu-id="b362d-409">\$PSSessionApplicationName</span></span>

<span data-ttu-id="b362d-410">Указывает имя приложения по умолчанию для удаленной команды, которая использует веб-службы для технологии управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="b362d-410">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="b362d-411">Дополнительные сведения см. в разделе [About служба удаленного управления Windows](/windows/win32/winrm/about-windows-remote-management).</span><span class="sxs-lookup"><span data-stu-id="b362d-411">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="b362d-412">Имя системного приложения по умолчанию — `WSMAN` , но вы можете использовать эту переменную настройки, чтобы изменить значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b362d-412">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="b362d-413">Имя приложения — это последний узел в универсальном коде ресурса (URI) соединения.</span><span class="sxs-lookup"><span data-stu-id="b362d-413">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="b362d-414">Например, имя приложения в следующем примере URI — `WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="b362d-414">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="b362d-415">Имя приложения по умолчанию используется, если в удаленной команде не указан универсальный код ресурса (URI) соединения или имя приложения.</span><span class="sxs-lookup"><span data-stu-id="b362d-415">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="b362d-416">Служба **WinRM** использует имя приложения для выбора прослушивателя, который будет обслуживать запрос на подключение.</span><span class="sxs-lookup"><span data-stu-id="b362d-416">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="b362d-417">Значение параметра должно соответствовать значению свойства **URLPrefix** прослушивателя на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b362d-417">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="b362d-418">Чтобы переопределить системные значения по умолчанию и значение этой переменной и выбрать другое имя приложения для конкретного сеанса, используйте параметры **ConnectionURI** или **applicationName** командлетов [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)или [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .</span><span class="sxs-lookup"><span data-stu-id="b362d-418">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="b362d-419">`$PSSessionApplicationName`Переменная предпочтений задается на локальном компьютере, но указывает на прослушиватель на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b362d-419">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="b362d-420">Если указанное имя приложения не существует на удаленном компьютере, команда для установки сеанса завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b362d-420">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="b362d-421">\$PSSessionConfigurationName</span><span class="sxs-lookup"><span data-stu-id="b362d-421">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="b362d-422">Задает конфигурацию сеанса по умолчанию, используемую для **PSSession** , созданной в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b362d-422">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="b362d-423">Эта переменная предпочтений задается на локальном компьютере, но она указывает конфигурацию сеанса, расположенную на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b362d-423">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="b362d-424">Значение `$PSSessionConfigurationName` переменной является полным URI ресурса.</span><span class="sxs-lookup"><span data-stu-id="b362d-424">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="b362d-425">Значение по умолчанию `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` указывает на конфигурацию сеанса **Microsoft. PowerShell** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b362d-425">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="b362d-426">Если указано только имя конфигурации, в начале добавляется следующий URI схемы:</span><span class="sxs-lookup"><span data-stu-id="b362d-426">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="b362d-427">Можно переопределить значение по умолчанию и выбрать другую конфигурацию сеанса для конкретного сеанса с помощью параметра **configurationName** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, или.</span><span class="sxs-lookup"><span data-stu-id="b362d-427">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="b362d-428">Значение этой переменной можно изменить в любое время.</span><span class="sxs-lookup"><span data-stu-id="b362d-428">You can change the value of this variable at any time.</span></span> <span data-ttu-id="b362d-429">В этом случае следует помнить, что выбранная конфигурация сеанса должна существовать на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b362d-429">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="b362d-430">В противном случае команда для создания сеанса, использующего конфигурацию сеанса, завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b362d-430">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="b362d-431">Эта переменная предпочтений не определяет, какие конфигурации локального сеанса используются, когда удаленные пользователи создают сеанс, который подключается к этому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="b362d-431">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="b362d-432">Однако можно использовать разрешения для конфигураций локального сеанса, чтобы определить, какие пользователи могут их использовать.</span><span class="sxs-lookup"><span data-stu-id="b362d-432">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="b362d-433">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="b362d-433">\$PSSessionOption</span></span>

<span data-ttu-id="b362d-434">Устанавливает значения по умолчанию для дополнительных параметров пользователя в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="b362d-434">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="b362d-435">Эти настройки параметров переопределяют системные значения по умолчанию для параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="b362d-435">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="b362d-436">`$PSSessionOption`Переменная содержит объект **PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="b362d-436">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="b362d-437">Дополнительные сведения см. в разделе [System. Management. Automation. Remoting. PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span><span class="sxs-lookup"><span data-stu-id="b362d-437">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="b362d-438">Каждое свойство объекта представляет параметр сеанса.</span><span class="sxs-lookup"><span data-stu-id="b362d-438">Each property of the object represents a session option.</span></span> <span data-ttu-id="b362d-439">Например, свойство « **уплотнение** » включает сжатие данных во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="b362d-439">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="b362d-440">По умолчанию `$PSSessionOption` переменная содержит объект **PSSessionOption** со значениями по умолчанию для всех параметров, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b362d-440">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

<span data-ttu-id="b362d-441">Описание этих параметров и дополнительные сведения см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="b362d-441">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="b362d-442">Дополнительные сведения об удаленных командах и сеансах см. в разделе [about_Remote](about_Remote.md) и [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-442">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="b362d-443">Чтобы изменить значение `$PSSessionOption` привилегированной переменной, используйте `New-PSSessionOption` командлет, чтобы создать объект **PSSessionOption** с предпочтительными значениями параметров.</span><span class="sxs-lookup"><span data-stu-id="b362d-443">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="b362d-444">Сохраните выходные данные в переменную с именем `$PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="b362d-444">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="b362d-445">Чтобы использовать `$PSSessionOption` переменную предпочтений в каждом сеансе PowerShell, добавьте `New-PSSessionOption` команду, которая создает `$PSSessionOption` переменную в профиле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-445">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="b362d-446">Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-446">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="b362d-447">Можно задать пользовательские параметры для определенного удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="b362d-447">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="b362d-448">Заданные параметры имеют приоритет над системными значениями по умолчанию и значением `$PSSessionOption` привилегированной переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-448">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="b362d-449">Чтобы задать настраиваемые параметры сеанса, используйте `New-PSSessionOption` командлет для создания объекта **PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="b362d-449">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="b362d-450">Затем используйте объект **PSSessionOption** в качестве значения параметра **SessionOption** в командлетах, которые создают сеанс, например `New-PSSession` , `Enter-PSSession` и `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="b362d-450">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="b362d-451">$Transcript</span><span class="sxs-lookup"><span data-stu-id="b362d-451">$Transcript</span></span>

<span data-ttu-id="b362d-452">Используется `Start-Transcript` для указания имени и расположения файла транскрипции.</span><span class="sxs-lookup"><span data-stu-id="b362d-452">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="b362d-453">Если значение параметра **path** не указано, `Start-Transcript` использует путь в значении `$Transcript` глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="b362d-453">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="b362d-454">Если эта переменная не создана, сохраняет записи `Start-Transcript` в `$Home\My Documents` каталоге в виде `\PowerShell_transcript.<time-stamp>.txt` файлов.</span><span class="sxs-lookup"><span data-stu-id="b362d-454">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="b362d-455">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="b362d-455">\$VerbosePreference</span></span>

<span data-ttu-id="b362d-456">Определяет, как PowerShell реагирует на подробные сообщения, создаваемые сценарием, командлетом или поставщиком, например сообщения, созданные командлетом [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) .</span><span class="sxs-lookup"><span data-stu-id="b362d-456">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="b362d-457">Подробные сообщения описывают действия, выполняемые для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-457">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="b362d-458">По умолчанию подробные сообщения не отображаются, но это поведение можно изменить, изменив значение `$VerbosePreference` .</span><span class="sxs-lookup"><span data-stu-id="b362d-458">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="b362d-459">Для отображения или скрытия подробных сообщений для определенной команды можно использовать параметр **verbose** Common.</span><span class="sxs-lookup"><span data-stu-id="b362d-459">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="b362d-460">См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-460">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="b362d-461">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-461">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-462">**Остановить**. Отображает подробное сообщение и сообщение об ошибке, а затем прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-462">**Stop** : Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="b362d-463">**Запрос** : Отображает подробное сообщение, а затем выводит приглашение, указывающее, нужно ли продолжить.</span><span class="sxs-lookup"><span data-stu-id="b362d-463">**Inquire** : Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="b362d-464">**Продолжить** : Отображает подробное сообщение, а затем продолжает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-464">**Continue** : Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="b362d-465">**SilentlyContinue** : (по умолчанию) не отображает подробное сообщение.</span><span class="sxs-lookup"><span data-stu-id="b362d-465">**SilentlyContinue** : (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="b362d-466">Продолжение исполнения.</span><span class="sxs-lookup"><span data-stu-id="b362d-466">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-467">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-467">Examples</span></span>

<span data-ttu-id="b362d-468">В этих примерах показан результат различных значений `$VerbosePreference` параметров и параметр **verbose** для переопределения значения предпочтения.</span><span class="sxs-lookup"><span data-stu-id="b362d-468">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="b362d-469">В этом примере показано действие значения **SilentlyContinue** , которое является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b362d-469">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="b362d-470">Команда использует параметр **Message** , но не записывает сообщение в консоль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b362d-470">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="b362d-471">При использовании параметра **verbose** сообщение записывается.</span><span class="sxs-lookup"><span data-stu-id="b362d-471">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="b362d-472">В этом примере показан результат выполнения значения **Continue** .</span><span class="sxs-lookup"><span data-stu-id="b362d-472">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="b362d-473">`$VerbosePreference`Переменная установлена для **продолжения** и отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="b362d-473">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="b362d-474">В этом примере используется параметр **verbose** со значением `$false` , переопределяющим значение **Continue** .</span><span class="sxs-lookup"><span data-stu-id="b362d-474">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="b362d-475">Сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="b362d-475">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="b362d-476">В этом примере показано воздействие значения " **Отключить** ".</span><span class="sxs-lookup"><span data-stu-id="b362d-476">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="b362d-477">`$VerbosePreference`Для переменной задано значение " **останавливаться** ", и отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="b362d-477">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="b362d-478">Команда остановлена.</span><span class="sxs-lookup"><span data-stu-id="b362d-478">The command is stopped.</span></span>

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="b362d-479">В этом примере используется параметр **verbose** со значением `$false` , переопределяющим значение параметра **останавливает** .</span><span class="sxs-lookup"><span data-stu-id="b362d-479">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="b362d-480">Сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="b362d-480">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="b362d-481">В этом примере показано **воздействие значения запроса** .</span><span class="sxs-lookup"><span data-stu-id="b362d-481">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="b362d-482">`$VerbosePreference`Для переменной задано значение " **запрос** ".</span><span class="sxs-lookup"><span data-stu-id="b362d-482">The `$VerbosePreference` variable is set to **Inquire**.</span></span> <span data-ttu-id="b362d-483">Отображается сообщение, и пользователю предлагается подтверждение.</span><span class="sxs-lookup"><span data-stu-id="b362d-483">The message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="b362d-484">В этом примере используется параметр **verbose** со значением `$false` , переопределяющим значение запроса **Inquire** .</span><span class="sxs-lookup"><span data-stu-id="b362d-484">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="b362d-485">Пользователю не выводится запрос, и сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="b362d-485">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="b362d-486">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="b362d-486">\$WarningPreference</span></span>

<span data-ttu-id="b362d-487">Определяет, как PowerShell реагирует на предупреждающие сообщения, созданные сценарием, командлетом или поставщиком, например сообщения, созданные командлетом [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) .</span><span class="sxs-lookup"><span data-stu-id="b362d-487">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="b362d-488">По умолчанию отображаются предупреждающие сообщения, и выполнение продолжится, но это поведение можно изменить, изменив значение `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="b362d-488">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="b362d-489">Вы можете использовать общий параметр **WarningAction** командлета, чтобы определить реакцию PowerShell на предупреждения от определенной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-489">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="b362d-490">См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b362d-490">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="b362d-491">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-491">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-492">**Остановить** : отображает предупреждающее сообщение и сообщение об ошибке, а затем прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-492">**Stop** : Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="b362d-493">**Запрос** : отображает предупреждающее сообщение, а затем запрашивает разрешение на продолжение.</span><span class="sxs-lookup"><span data-stu-id="b362d-493">**Inquire** : Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="b362d-494">**Продолжить** : (по умолчанию) отображает предупреждающее сообщение, а затем продолжает выполнение.</span><span class="sxs-lookup"><span data-stu-id="b362d-494">**Continue** : (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="b362d-495">**SilentlyContinue** : не отображает предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="b362d-495">**SilentlyContinue** : Doesn't display the warning message.</span></span> <span data-ttu-id="b362d-496">Продолжение исполнения.</span><span class="sxs-lookup"><span data-stu-id="b362d-496">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-497">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-497">Examples</span></span>

<span data-ttu-id="b362d-498">В этих примерах показано воздействие различных значений `$WarningPreference` .</span><span class="sxs-lookup"><span data-stu-id="b362d-498">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="b362d-499">Параметр **WarningAction** переопределяет значение предпочтения.</span><span class="sxs-lookup"><span data-stu-id="b362d-499">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="b362d-500">В этом примере показано воздействие значения по умолчанию на **Continue**.</span><span class="sxs-lookup"><span data-stu-id="b362d-500">This example shows the effect of the default value, **Continue**.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="b362d-501">В этом примере для подавления предупреждения используется параметр **WarningAction** со значением **SilentlyContinue** .</span><span class="sxs-lookup"><span data-stu-id="b362d-501">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="b362d-502">Сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="b362d-502">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="b362d-503">В этом примере `$WarningPreference` переменная изменяется на значение **SilentlyContinue** .</span><span class="sxs-lookup"><span data-stu-id="b362d-503">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="b362d-504">Сообщение не отображается.</span><span class="sxs-lookup"><span data-stu-id="b362d-504">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="b362d-505">В этом примере параметр **WarningAction** используется для отмены при создании предупреждения.</span><span class="sxs-lookup"><span data-stu-id="b362d-505">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

<span data-ttu-id="b362d-506">В этом примере `$WarningPreference` переменная изменяется на значение **Inquire** запроса.</span><span class="sxs-lookup"><span data-stu-id="b362d-506">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="b362d-507">Пользователю предлагается подтверждение.</span><span class="sxs-lookup"><span data-stu-id="b362d-507">The user is prompted for confirmation.</span></span>

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="b362d-508">В этом примере используется параметр **WarningAction** со значением **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="b362d-508">This example uses the **WarningAction** parameter with the value **SilentlyContinue**.</span></span> <span data-ttu-id="b362d-509">Команда продолжит выполняться, и сообщение не будет выводиться.</span><span class="sxs-lookup"><span data-stu-id="b362d-509">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="b362d-510">В этом примере `$WarningPreference` значение изменяется на « **останавливается** ».</span><span class="sxs-lookup"><span data-stu-id="b362d-510">This example changes the `$WarningPreference` value to **Stop**.</span></span>

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

<span data-ttu-id="b362d-511">В этом примере используется **WarningAction** **со значением запроса** .</span><span class="sxs-lookup"><span data-stu-id="b362d-511">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="b362d-512">Пользователь получает запрос при возникновении предупреждения.</span><span class="sxs-lookup"><span data-stu-id="b362d-512">The user is prompted when a warning occurs.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

### <a name="whatifpreference"></a><span data-ttu-id="b362d-513">\$вхатифпреференце</span><span class="sxs-lookup"><span data-stu-id="b362d-513">\$WhatIfPreference</span></span>

<span data-ttu-id="b362d-514">Определяет, включается ли параметр **WhatIf** автоматически для каждой команды, поддерживающей эту возможность.</span><span class="sxs-lookup"><span data-stu-id="b362d-514">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="b362d-515">Если параметр **WhatIf** включен, командлет сообщает о ожидаемом результате команды, но не выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="b362d-515">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="b362d-516">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b362d-516">The valid values are as follows:</span></span>

- <span data-ttu-id="b362d-517">**False** ( **0** , не включено): (по умолчанию) **WhatIf** не включен автоматически.</span><span class="sxs-lookup"><span data-stu-id="b362d-517">**False** ( **0** , not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="b362d-518">Чтобы включить его вручную, используйте параметр **WhatIf** командлета.</span><span class="sxs-lookup"><span data-stu-id="b362d-518">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="b362d-519">**True** ( **1** , включено): **WhatIf** автоматически включается для любой команды, которая его поддерживает.</span><span class="sxs-lookup"><span data-stu-id="b362d-519">**True** ( **1** , enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="b362d-520">Пользователи могут использовать параметр **WhatIf** со значением **false** , чтобы отключить его вручную, например `-WhatIf:$false` .</span><span class="sxs-lookup"><span data-stu-id="b362d-520">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="b362d-521">Примеры</span><span class="sxs-lookup"><span data-stu-id="b362d-521">Examples</span></span>

<span data-ttu-id="b362d-522">В этих примерах показано воздействие различных значений `$WhatIfPreference` .</span><span class="sxs-lookup"><span data-stu-id="b362d-522">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="b362d-523">Они показывают, как использовать параметр **WhatIf** для переопределения значения предпочтений для определенной команды.</span><span class="sxs-lookup"><span data-stu-id="b362d-523">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="b362d-524">В этом примере показан результат использования `$WhatIfPreference` переменной значения по умолчанию, равной **false**.</span><span class="sxs-lookup"><span data-stu-id="b362d-524">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False**.</span></span> <span data-ttu-id="b362d-525">Используйте `Get-ChildItem` , чтобы убедиться, что файл существует.</span><span class="sxs-lookup"><span data-stu-id="b362d-525">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="b362d-526">`Remove-Item` Удаляет файл.</span><span class="sxs-lookup"><span data-stu-id="b362d-526">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="b362d-527">После удаления файла можно проверить его удаление с помощью `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="b362d-527">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

<span data-ttu-id="b362d-528">В этом примере показан результат использования параметра **WhatIf** , если значение `$WhatIfPreference` равно **false**.</span><span class="sxs-lookup"><span data-stu-id="b362d-528">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False**.</span></span>

<span data-ttu-id="b362d-529">Убедитесь, что файл существует.</span><span class="sxs-lookup"><span data-stu-id="b362d-529">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="b362d-530">Используйте параметр **WhatIf** для определения результата попытки удаления файла.</span><span class="sxs-lookup"><span data-stu-id="b362d-530">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="b362d-531">Убедитесь, что файл не был удален.</span><span class="sxs-lookup"><span data-stu-id="b362d-531">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="b362d-532">В этом примере показан результат выполнения `$WhatIfPreference` переменной значения **true**.</span><span class="sxs-lookup"><span data-stu-id="b362d-532">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True**.</span></span> <span data-ttu-id="b362d-533">При использовании `Remove-Item` для удаления файла отображается путь к файлу, но файл не удаляется.</span><span class="sxs-lookup"><span data-stu-id="b362d-533">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="b362d-534">Попытка удаления файла.</span><span class="sxs-lookup"><span data-stu-id="b362d-534">Attempt to delete a file.</span></span> <span data-ttu-id="b362d-535">Появится сообщение о том, что произойдет при `Remove-Item` запуске, но файл не будет удален.</span><span class="sxs-lookup"><span data-stu-id="b362d-535">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="b362d-536">Используйте `Get-ChildItem` для проверки того, что файл не был удален.</span><span class="sxs-lookup"><span data-stu-id="b362d-536">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="b362d-537">В этом примере показано, как удалить файл, если значение `$WhatIfPreference` равно **true**.</span><span class="sxs-lookup"><span data-stu-id="b362d-537">This example shows how to delete a file when the value of `$WhatIfPreference` is **True**.</span></span> <span data-ttu-id="b362d-538">В нем используется параметр **WhatIf** со значением `$false` .</span><span class="sxs-lookup"><span data-stu-id="b362d-538">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="b362d-539">Используйте `Get-ChildItem` для проверки удаления файла.</span><span class="sxs-lookup"><span data-stu-id="b362d-539">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="b362d-540">Ниже приведены примеры `Get-Process` командлета, который не поддерживает **WhatIf** и `Stop-Process` поддерживает **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="b362d-540">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf**.</span></span> <span data-ttu-id="b362d-541">`$WhatIfPreference`Значение переменной равно **true**.</span><span class="sxs-lookup"><span data-stu-id="b362d-541">The `$WhatIfPreference` variable's value is **True**.</span></span>

<span data-ttu-id="b362d-542">`Get-Process` не поддерживает **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="b362d-542">`Get-Process` doesn't support **WhatIf**.</span></span> <span data-ttu-id="b362d-543">При выполнении команды отображается процесс **Winword** .</span><span class="sxs-lookup"><span data-stu-id="b362d-543">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="b362d-544">`Stop-Process` поддерживает **WhatIf**.</span><span class="sxs-lookup"><span data-stu-id="b362d-544">`Stop-Process` does support **WhatIf**.</span></span> <span data-ttu-id="b362d-545">Процесс **Winword** не остановлен.</span><span class="sxs-lookup"><span data-stu-id="b362d-545">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="b362d-546">Поведение WhatIf можно переопределить с `Stop-Process` **WhatIf** помощью параметра **WhatIf** со значением `$false` .</span><span class="sxs-lookup"><span data-stu-id="b362d-546">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="b362d-547">Процесс **Winword** остановлен.</span><span class="sxs-lookup"><span data-stu-id="b362d-547">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="b362d-548">Чтобы убедиться, что процесс **Winword** был остановлен, используйте `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="b362d-548">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="b362d-549">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b362d-549">See also</span></span>

[<span data-ttu-id="b362d-550">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="b362d-550">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="b362d-551">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b362d-551">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="b362d-552">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="b362d-552">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="b362d-553">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="b362d-553">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="b362d-554">about_Remote</span><span class="sxs-lookup"><span data-stu-id="b362d-554">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="b362d-555">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="b362d-555">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="b362d-556">about_Variables</span><span class="sxs-lookup"><span data-stu-id="b362d-556">about_Variables</span></span>](about_Variables.md)
