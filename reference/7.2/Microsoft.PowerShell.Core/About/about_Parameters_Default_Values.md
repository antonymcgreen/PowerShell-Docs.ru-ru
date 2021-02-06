---
description: Описывает, как задать пользовательские значения по умолчанию для параметров командлета и дополнительных функций.
Locale: en-US
ms.date: 05/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: 102f163287717f7c9cd4f430704cc27ddea7ff4c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604375"
---
# <a name="about-parameters-default-values"></a><span data-ttu-id="d19ba-103">О параметрах значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d19ba-103">About Parameters Default Values</span></span>

## <a name="short-description"></a><span data-ttu-id="d19ba-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d19ba-104">Short description</span></span>

<span data-ttu-id="d19ba-105">Описывает, как задать пользовательские значения по умолчанию для параметров командлета и дополнительных функций.</span><span class="sxs-lookup"><span data-stu-id="d19ba-105">Describes how to set custom default values for cmdlet parameters and advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="d19ba-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d19ba-106">Long description</span></span>

<span data-ttu-id="d19ba-107">`$PSDefaultParameterValues`Переменная предпочтения позволяет указать пользовательские значения по умолчанию для любого командлета или расширенной функции.</span><span class="sxs-lookup"><span data-stu-id="d19ba-107">The `$PSDefaultParameterValues` preference variable lets you specify custom default values for any cmdlet or advanced function.</span></span> <span data-ttu-id="d19ba-108">Командлеты и дополнительные функции используют пользовательское значение по умолчанию, если в команде не указано другое значение.</span><span class="sxs-lookup"><span data-stu-id="d19ba-108">Cmdlets and advanced functions use the custom default value unless you specify another value in the command.</span></span>

<span data-ttu-id="d19ba-109">Авторы командлетов и дополнительных функций устанавливают стандартные значения по умолчанию для их параметров.</span><span class="sxs-lookup"><span data-stu-id="d19ba-109">The authors of cmdlets and advanced functions set standard default values for their parameters.</span></span> <span data-ttu-id="d19ba-110">Как правило, стандартные значения по умолчанию полезны, но они могут быть не подходящими для всех сред.</span><span class="sxs-lookup"><span data-stu-id="d19ba-110">Typically, the standard default values are useful, but they might not be appropriate for all environments.</span></span>

<span data-ttu-id="d19ba-111">Эта функция особенно полезна, если необходимо указать одно и то же альтернативное значение параметра практически при каждом использовании команды или если определенное значение параметра трудно запомнить, например имя сервера электронной почты или GUID проекта.</span><span class="sxs-lookup"><span data-stu-id="d19ba-111">This feature is especially useful when you must specify the same alternate parameter value nearly every time you use the command or when a particular parameter value is difficult to remember, such as an email server name or project GUID.</span></span>

<span data-ttu-id="d19ba-112">Если требуемое значение по умолчанию зависит от прогнозируемого значения, можно указать блок скрипта, который предоставляет различные значения по умолчанию для параметра в различных условиях.</span><span class="sxs-lookup"><span data-stu-id="d19ba-112">If the desired default value varies predictably, you can specify a script block that provides different default values for a parameter under different conditions.</span></span>

<span data-ttu-id="d19ba-113">`$PSDefaultParameterValues` впервые появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d19ba-113">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

## <a name="syntax"></a><span data-ttu-id="d19ba-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d19ba-114">Syntax</span></span>

<span data-ttu-id="d19ba-115">`$PSDefaultParameterValues`Переменная является хэш-таблицей, которая проверяет формат ключей как тип объекта **System. Management. Automation. дефаултпараметердиктионари**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-115">The `$PSDefaultParameterValues` variable is a hash table that validates the format of keys as an object type of **System.Management.Automation.DefaultParameterDictionary**.</span></span> <span data-ttu-id="d19ba-116">Хэш-таблица содержит пары " **ключ-значение** ".</span><span class="sxs-lookup"><span data-stu-id="d19ba-116">The hash table contains **Key/Value** pairs.</span></span> <span data-ttu-id="d19ba-117">**Ключ** имеет формат `CmdletName:ParameterName` .</span><span class="sxs-lookup"><span data-stu-id="d19ba-117">A **Key** is in the format `CmdletName:ParameterName`.</span></span> <span data-ttu-id="d19ba-118">**Значением является значение** **DefaultValue** или **ScriptBlock** , назначенное ключу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-118">A **Value** is the **DefaultValue** or **ScriptBlock** assigned to the key.</span></span>

<span data-ttu-id="d19ba-119">Синтаксис `$PSDefaultParameterValues` переменной предпочтения выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d19ba-119">The syntax of the `$PSDefaultParameterValues` preference variable is as follows:</span></span>

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

<span data-ttu-id="d19ba-120">В значениях **CmdletName** и **ParameterName** разрешены подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d19ba-120">Wildcard characters are permitted in the **CmdletName** and **ParameterName** values.</span></span>

<span data-ttu-id="d19ba-121">Чтобы задать, изменить, добавить или удалить определенную пару " **ключ-значение** " из `$PSDefaultParameterValues` , используйте методы для изменения стандартной хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="d19ba-121">To set, change, add, or remove a specific **Key/Value** pair from `$PSDefaultParameterValues`, use the methods to edit a standard hash table.</span></span> <span data-ttu-id="d19ba-122">Например, методы **Add** и **Remove** .</span><span class="sxs-lookup"><span data-stu-id="d19ba-122">For example, the **Add** and **Remove** methods.</span></span> <span data-ttu-id="d19ba-123">Эти методы не перезаписывают другие значения в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="d19ba-123">These methods don't overwrite other values in the hash table.</span></span>

<span data-ttu-id="d19ba-124">Существует другой синтаксис, который не перезаписывает существующую `$PSDefaultParameterValues` хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-124">There's another syntax that doesn't overwrite an existing `$PSDefaultParameterValues` hash table.</span></span> <span data-ttu-id="d19ba-125">Чтобы добавить или изменить определенную пару " **ключ-значение** ", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d19ba-125">To add or change a specific **Key/Value** pair, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="d19ba-126">**CmdletName** должен быть именем командлета или именем расширенной функции, использующей атрибут **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="d19ba-126">The **CmdletName** must be the name of a cmdlet or the name of an advanced function that uses the **CmdletBinding** attribute.</span></span> <span data-ttu-id="d19ba-127">Нельзя использовать `$PSDefaultParameterValues` для указания значений по умолчанию для скриптов или простых функций.</span><span class="sxs-lookup"><span data-stu-id="d19ba-127">You can't use `$PSDefaultParameterValues` to specify default values for scripts or simple functions.</span></span>

<span data-ttu-id="d19ba-128">**DefaultValue** может быть объектом или блоком скрипта.</span><span class="sxs-lookup"><span data-stu-id="d19ba-128">The **DefaultValue** can be an object or a script block.</span></span> <span data-ttu-id="d19ba-129">Если значение является блоком сценария, PowerShell вычисляет блок скрипта и использует результат в качестве значения параметра.</span><span class="sxs-lookup"><span data-stu-id="d19ba-129">If the value is a script block, PowerShell evaluates the script block and uses the result as the parameter value.</span></span> <span data-ttu-id="d19ba-130">Если указанный параметр принимает значение блока сценария, заключите значение блока скрипта во второй набор фигурных скобок, например:</span><span class="sxs-lookup"><span data-stu-id="d19ba-130">When the specified parameter accepts a script block value, enclose the script block value in a second set of braces, such as:</span></span>

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

<span data-ttu-id="d19ba-131">Дополнительные сведения см. в следующих документах:</span><span class="sxs-lookup"><span data-stu-id="d19ba-131">For more information, see the following documents:</span></span>

- [<span data-ttu-id="d19ba-132">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="d19ba-132">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="d19ba-133">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="d19ba-133">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="d19ba-134">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="d19ba-134">about_Preference_Variables</span></span>](about_Preference_Variables.md)

## <a name="examples"></a><span data-ttu-id="d19ba-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="d19ba-135">Examples</span></span>

### <a name="how-to-set-psdefaultparametervalues"></a><span data-ttu-id="d19ba-136">Как задать \$ псдефаултпараметервалуес</span><span class="sxs-lookup"><span data-stu-id="d19ba-136">How to set \$PSDefaultParameterValues</span></span>

<span data-ttu-id="d19ba-137">`$PSDefaultParameterValues` — это переменная предпочтения, которая существует только в сеансе, в котором она задана.</span><span class="sxs-lookup"><span data-stu-id="d19ba-137">`$PSDefaultParameterValues` is a preference variable, so it exists only in the session in which it's set.</span></span> <span data-ttu-id="d19ba-138">У него нет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d19ba-138">It has no default value.</span></span>

<span data-ttu-id="d19ba-139">Чтобы задать `$PSDefaultParameterValues` , введите имя переменной и одну или несколько пар " **ключ-значение** ".</span><span class="sxs-lookup"><span data-stu-id="d19ba-139">To set `$PSDefaultParameterValues`, type the variable name and one or more **Key/Value** pairs.</span></span> <span data-ttu-id="d19ba-140">При выполнении другой `$PSDefaultParameterValues` команды она перезаписывает существующую хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-140">If you run another `$PSDefaultParameterValues` command, it overwrites the existing hash table.</span></span>

<span data-ttu-id="d19ba-141">Примеры изменения пар " **ключ-значение** " без перезаписи значений существующих хэш-таблиц см. в разделе [Добавление значений в \$ псдефаултпараметервалуес](#how-to-add-values-to-psdefaultparametervalues) или [изменение значений в \$ псдефаултпараметервалуес](#how-to-change-values-in-psdefaultparametervalues).</span><span class="sxs-lookup"><span data-stu-id="d19ba-141">For examples about how to change **Key/Value** pairs without overwriting existing hash table values, see [How to add values to \$PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) or [How to change values in \$PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).</span></span>

<span data-ttu-id="d19ba-142">Чтобы сохранить `$PSDefaultParameterValues` данные для будущих сеансов, добавьте `$PSDefaultParameterValues` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d19ba-142">To save `$PSDefaultParameterValues` for future sessions, add a `$PSDefaultParameterValues` command to your PowerShell profile.</span></span> <span data-ttu-id="d19ba-143">Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d19ba-143">For more information, see [about_Profiles](about_Profiles.md).</span></span>

#### <a name="set-a-custom-default-value"></a><span data-ttu-id="d19ba-144">Задать пользовательское значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d19ba-144">Set a custom default value</span></span>

<span data-ttu-id="d19ba-145">Пара " **ключ-значение** " задает `Send-MailMessage:SmtpServer` для ключа пользовательское значение по умолчанию **Server123**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-145">The **Key/Value** pair sets the `Send-MailMessage:SmtpServer` key to a custom default value of **Server123**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a><span data-ttu-id="d19ba-146">Установка значений по умолчанию для нескольких параметров</span><span class="sxs-lookup"><span data-stu-id="d19ba-146">Set default values for multiple parameters</span></span>

<span data-ttu-id="d19ba-147">Чтобы задать значения по умолчанию для нескольких параметров, разделите каждую пару « **ключ-значение** » точкой с запятой ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="d19ba-147">To set default values for multiple parameters, separate each **Key/Value** pair with a semicolon (`;`).</span></span> <span data-ttu-id="d19ba-148">`Send-MailMessage:SmtpServer` `Get-WinEvent:LogName` Для ключей и задаются пользовательские значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d19ba-148">The `Send-MailMessage:SmtpServer` and `Get-WinEvent:LogName` keys are set to custom default values.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a><span data-ttu-id="d19ba-149">Использование подстановочных знаков и параметров переключателей</span><span class="sxs-lookup"><span data-stu-id="d19ba-149">Use wildcards and switch parameters</span></span>

<span data-ttu-id="d19ba-150">Имена командлетов и параметров могут содержать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d19ba-150">The cmdlet and parameter names can contain wildcard characters.</span></span> <span data-ttu-id="d19ba-151">Используйте `$True` и `$False` для задания значений параметров переключателя, например **verbose**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-151">Use `$True` and `$False` to set values for switch parameters, such as **Verbose**.</span></span> <span data-ttu-id="d19ba-152">Параметр **verbose** для общего параметра имеет значение `$True` для всех команд.</span><span class="sxs-lookup"><span data-stu-id="d19ba-152">The common parameter's **Verbose** parameter is set to `$True` for all commands.</span></span>

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a><span data-ttu-id="d19ba-153">Использовать массив для значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d19ba-153">Use an array for the default value</span></span>

<span data-ttu-id="d19ba-154">Если параметр может принимать несколько значений, массив, в качестве значений по умолчанию можно задать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="d19ba-154">If a parameter can accept multiple values, an array, you can set multiple values as the default values.</span></span> <span data-ttu-id="d19ba-155">Значение по умолчанию `Invoke-Command:ComputerName` для ключа равно значению массива **Server01** и **Server02**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-155">The default value of the `Invoke-Command:ComputerName` key is set to an array value of **Server01** and **Server02**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a><span data-ttu-id="d19ba-156">Использовать блок сценария</span><span class="sxs-lookup"><span data-stu-id="d19ba-156">Use a script block</span></span>

<span data-ttu-id="d19ba-157">Можно использовать блок скрипта для задания различных значений по умолчанию для параметра в различных условиях.</span><span class="sxs-lookup"><span data-stu-id="d19ba-157">You can use a script block to specify different default values for a parameter under different conditions.</span></span> <span data-ttu-id="d19ba-158">PowerShell вычисляет блок скрипта и использует результат в качестве значения параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d19ba-158">PowerShell evaluates the script block and uses the result as the default parameter value.</span></span>

<span data-ttu-id="d19ba-159">`Format-Table:AutoSize`Набор ключей, который переключает параметр на значение по умолчанию **true**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-159">The `Format-Table:AutoSize` key sets that switch parameter to a default value of **True**.</span></span> <span data-ttu-id="d19ba-160">`If`Инструкция содержит условие, которое `$host.Name` должно быть консолью PowerShell **ConsoleHost**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-160">The `If` statement contains a condition that the `$host.Name` must be the PowerShell console, **ConsoleHost**.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

<span data-ttu-id="d19ba-161">Если параметр принимает значение блока сценария, заключите блок сценария в дополнительный набор фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="d19ba-161">If a parameter accepts a script block value, enclose the script block in an extra set of braces.</span></span> <span data-ttu-id="d19ba-162">Когда PowerShell вычисляет внешний блок скрипта, результатом является внутренний блок скрипта, который задается как значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d19ba-162">When PowerShell evaluates the outer script block, the result is the inner script block, and that is set as the default parameter value.</span></span>

<span data-ttu-id="d19ba-163">`Invoke-Command:ScriptBlock`Ключ задается в качестве значения по умолчанию для **журнала системных событий** , так как блок скрипта заключен во второй набор фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="d19ba-163">The `Invoke-Command:ScriptBlock` key set to a default value of the **System event log** because the script block is enclosed in a second set of braces.</span></span> <span data-ttu-id="d19ba-164">Результат блока скрипта передается в `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="d19ba-164">The result of the script block is passed to the `Invoke-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a><span data-ttu-id="d19ba-165">Как получить \$ псдефаултпараметервалуес</span><span class="sxs-lookup"><span data-stu-id="d19ba-165">How to get \$PSDefaultParameterValues</span></span>

<span data-ttu-id="d19ba-166">Значения хэш-таблицы отображаются путем ввода `$PSDefaultParameterValues` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d19ba-166">The hash table values are displayed by entering `$PSDefaultParameterValues` at the PowerShell prompt.</span></span>

<span data-ttu-id="d19ba-167">Для `$PSDefaultParameterValues` хэш-таблицы заданы три пары " **ключ-значение** ".</span><span class="sxs-lookup"><span data-stu-id="d19ba-167">A `$PSDefaultParameterValues` hash table is set with three **Key/Value** pairs.</span></span>
<span data-ttu-id="d19ba-168">Эта хэш-таблица используется в следующих примерах, в которых описывается добавление, изменение и удаление значений из `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="d19ba-168">This hash table is used in the following examples that describe how to add, change, and remove values from `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

<span data-ttu-id="d19ba-169">Чтобы получить значение определенного `CmdletName:ParameterName` ключа, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d19ba-169">To get the value of a specific `CmdletName:ParameterName` key, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

<span data-ttu-id="d19ba-170">Например, чтобы получить значение для `Send-MailMessage:SmtpServer` ключа.</span><span class="sxs-lookup"><span data-stu-id="d19ba-170">For example, to get the value for the `Send-MailMessage:SmtpServer` key.</span></span>

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a><span data-ttu-id="d19ba-171">Добавление значений в \$ псдефаултпараметервалуес</span><span class="sxs-lookup"><span data-stu-id="d19ba-171">How to add values to \$PSDefaultParameterValues</span></span>

<span data-ttu-id="d19ba-172">Чтобы добавить значение в `$PSDefaultParameterValues` , используйте метод **Add** .</span><span class="sxs-lookup"><span data-stu-id="d19ba-172">To add a value to `$PSDefaultParameterValues`, use the **Add** method.</span></span> <span data-ttu-id="d19ba-173">Добавление значения не влияет на существующие значения хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="d19ba-173">Adding a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="d19ba-174">Используйте запятую ( `,` ), чтобы отделить **ключ** от **значения**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-174">Use a comma (`,`) to separate the **Key** from the **Value**.</span></span> <span data-ttu-id="d19ba-175">В следующем синтаксисе показано, как использовать метод **Add** для `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="d19ba-175">The following syntax shows how to use the **Add** method for `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

<span data-ttu-id="d19ba-176">Хэш-таблица, созданная в предыдущем примере, обновляется новой парой " **ключ-значение** ".</span><span class="sxs-lookup"><span data-stu-id="d19ba-176">The hash table created in the prior example is updated with a new **Key/Value** pair.</span></span> <span data-ttu-id="d19ba-177">Метод **Add** задает `Get-Process:Name` для ключа значение **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-177">The **Add** method sets the `Get-Process:Name` key to the value **PowerShell**.</span></span>

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

<span data-ttu-id="d19ba-178">Следующий синтаксис выполняет тот же результат.</span><span class="sxs-lookup"><span data-stu-id="d19ba-178">The following syntax accomplishes the same result.</span></span>

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

<span data-ttu-id="d19ba-179">`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-179">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="d19ba-180">`Get-Process:Name`Ключ добавлен.</span><span class="sxs-lookup"><span data-stu-id="d19ba-180">The `Get-Process:Name` key was added.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a><span data-ttu-id="d19ba-181">Удаление значений из \$ псдефаултпараметервалуес</span><span class="sxs-lookup"><span data-stu-id="d19ba-181">How to remove values from \$PSDefaultParameterValues</span></span>

<span data-ttu-id="d19ba-182">Чтобы удалить значение из `$PSDefaultParameterValues` , используйте метод **Remove** хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="d19ba-182">To remove a value from `$PSDefaultParameterValues`, use the **Remove** method of hash tables.</span></span> <span data-ttu-id="d19ba-183">Удаление значения не влияет на существующие значения хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="d19ba-183">Removing a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="d19ba-184">В следующем синтаксисе показано, как использовать метод **Remove** для `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="d19ba-184">The following syntax shows how to use the **Remove** method on `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

<span data-ttu-id="d19ba-185">В этом примере хэш-таблица, созданная в предыдущем примере, обновляется для удаления пары " **ключ-значение** ".</span><span class="sxs-lookup"><span data-stu-id="d19ba-185">In this example, the hash table created in the prior example is updated to remove a **Key/Value** pair.</span></span> <span data-ttu-id="d19ba-186">Метод **Remove** удаляет `Get-Process:Name` ключ.</span><span class="sxs-lookup"><span data-stu-id="d19ba-186">The **Remove** method removes the `Get-Process:Name` key.</span></span>

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

<span data-ttu-id="d19ba-187">`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-187">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="d19ba-188">`Get-Process:Name`Ключ был удален.</span><span class="sxs-lookup"><span data-stu-id="d19ba-188">The `Get-Process:Name` key was removed.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a><span data-ttu-id="d19ba-189">Изменение значений в \$ псдефаултпараметервалуес</span><span class="sxs-lookup"><span data-stu-id="d19ba-189">How to change values in \$PSDefaultParameterValues</span></span>

<span data-ttu-id="d19ba-190">Изменения в определенном значении не влияют на существующие значения хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="d19ba-190">Changes to a specific value don't affect existing hash table values.</span></span> <span data-ttu-id="d19ba-191">Чтобы изменить определенную пару " **ключ-значение** " в `$PSDefaultParameterValues` , используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d19ba-191">To change a specific **Key/Value** pair in `$PSDefaultParameterValues`, use the following syntax:</span></span>

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="d19ba-192">В этом примере хэш-таблица, созданная в предыдущем примере, обновляется для изменения пары " **ключ-значение** ".</span><span class="sxs-lookup"><span data-stu-id="d19ba-192">In this example, the hash table created in the prior example is updated to change a **Key/Value** pair.</span></span> <span data-ttu-id="d19ba-193">Следующая команда изменяет `Send-MailMessage:SmtpServer` ключ на новое значение **ServerXYZ**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-193">The following command changes the `Send-MailMessage:SmtpServer` key to a new value of **ServerXYZ**.</span></span>

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

<span data-ttu-id="d19ba-194">`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-194">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="d19ba-195">`Send-MailMessage:SmtpServer`Ключ был изменен на новое значение.</span><span class="sxs-lookup"><span data-stu-id="d19ba-195">The `Send-MailMessage:SmtpServer` key was changed to a new value.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a><span data-ttu-id="d19ba-196">Отключение и повторное включение \$ псдефаултпараметервалуес</span><span class="sxs-lookup"><span data-stu-id="d19ba-196">How to disable and re-enable \$PSDefaultParameterValues</span></span>

<span data-ttu-id="d19ba-197">Можно временно отключить и снова включить `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="d19ba-197">You can temporarily disable and then re-enable `$PSDefaultParameterValues`.</span></span>
<span data-ttu-id="d19ba-198">Отключение `$PSDefaultParameterValues` полезно, если выполняются сценарии, для которых требуются разные значения параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d19ba-198">Disabling `$PSDefaultParameterValues` is useful if you're running scripts that need different default parameter values.</span></span>

<span data-ttu-id="d19ba-199">Чтобы отключить `$PSDefaultParameterValues` , добавьте ключ `Disabled` со значением **true**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-199">To disable `$PSDefaultParameterValues`, add a key of `Disabled` with a value of **True**.</span></span> <span data-ttu-id="d19ba-200">Значения в сохраняются `$PSDefaultParameterValues` , но не вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-200">The values in `$PSDefaultParameterValues` are preserved, but aren't effective.</span></span>

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

<span data-ttu-id="d19ba-201">Следующий синтаксис выполняет тот же результат.</span><span class="sxs-lookup"><span data-stu-id="d19ba-201">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

<span data-ttu-id="d19ba-202">`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу со значением `Disabled` ключа.</span><span class="sxs-lookup"><span data-stu-id="d19ba-202">The `$PSDefaultParameterValues` variable displays the updated hash table with the value for the `Disabled` key.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

<span data-ttu-id="d19ba-203">Для повторного включения `$PSDefaultParameterValues` удалите **отключенный** ключ или измените значение **отключенного** ключа на `$False` .</span><span class="sxs-lookup"><span data-stu-id="d19ba-203">To re-enable `$PSDefaultParameterValues`, remove the **Disabled** key or change the value of the **Disabled** key to `$False`.</span></span> <span data-ttu-id="d19ba-204">Предыдущее значение `$PSDefaultParameterValues` вступает в силу еще раз.</span><span class="sxs-lookup"><span data-stu-id="d19ba-204">The previous value of `$PSDefaultParameterValues` is effective again.</span></span>

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

<span data-ttu-id="d19ba-205">Следующий синтаксис выполняет тот же результат.</span><span class="sxs-lookup"><span data-stu-id="d19ba-205">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

<span data-ttu-id="d19ba-206">`$PSDefaultParameterValues`Переменная отображает обновленную хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="d19ba-206">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="d19ba-207">При использовании метода **Remove** `Disabled` ключ удаляется из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d19ba-207">When the **Remove** method is used, the `Disabled` key is removed from the output.</span></span>
<span data-ttu-id="d19ba-208">Если для повторного включения использовался альтернативный синтаксис `$PSDefaultParameterValues` , `Disabled` ключ отображается как **false**.</span><span class="sxs-lookup"><span data-stu-id="d19ba-208">If the alternate syntax was used to re-enable `$PSDefaultParameterValues`, the `Disabled` key is displayed as **False**.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a><span data-ttu-id="d19ba-209">См. также</span><span class="sxs-lookup"><span data-stu-id="d19ba-209">See also</span></span>

[<span data-ttu-id="d19ba-210">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d19ba-210">about_CommonParameters</span></span>](https://go.microsoft.com/fwlink/?LinkID=113216)

[<span data-ttu-id="d19ba-211">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="d19ba-211">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="d19ba-212">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="d19ba-212">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="d19ba-213">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="d19ba-213">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="d19ba-214">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="d19ba-214">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="d19ba-215">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="d19ba-215">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="d19ba-216">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="d19ba-216">about_Script_Blocks</span></span>](about_Script_Blocks.md)

