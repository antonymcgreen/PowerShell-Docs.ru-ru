---
description: Предотвращает запуск скрипта без необходимых элементов.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: 5c4eb4e272f214ffe906fd1a3f1c127824183d4a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232637"
---
# <a name="about-requires"></a><span data-ttu-id="f34bc-104">О программе требуется</span><span class="sxs-lookup"><span data-stu-id="f34bc-104">About Requires</span></span>

## <a name="short-description"></a><span data-ttu-id="f34bc-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="f34bc-105">Short description</span></span>
<span data-ttu-id="f34bc-106">Предотвращает запуск скрипта без необходимых элементов.</span><span class="sxs-lookup"><span data-stu-id="f34bc-106">Prevents a script from running without the required elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="f34bc-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f34bc-107">Long description</span></span>

<span data-ttu-id="f34bc-108">`#Requires`Инструкция предотвращает выполнение скрипта, если не выполнены версия PowerShell, модули (и версия), а также оснастки (и версия) и предварительные требования к выпуску.</span><span class="sxs-lookup"><span data-stu-id="f34bc-108">The `#Requires` statement prevents a script from running unless the PowerShell version, modules (and version), or snap-ins (and version), and edition prerequisites are met.</span></span> <span data-ttu-id="f34bc-109">Если необходимые условия не соблюдены, PowerShell не выполняет сценарий.</span><span class="sxs-lookup"><span data-stu-id="f34bc-109">If the prerequisites aren't met, PowerShell doesn't run the script.</span></span>

### <a name="syntax"></a><span data-ttu-id="f34bc-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f34bc-110">Syntax</span></span>

```
#Requires -Assembly { <Path to .dll> | <.NET assembly specification> }
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

<span data-ttu-id="f34bc-111">Дополнительные сведения о синтаксисе см. в разделе [скриптрекуирементс](/dotnet/api/system.management.automation.language.scriptrequirements).</span><span class="sxs-lookup"><span data-stu-id="f34bc-111">For more information about the syntax, see [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span></span>

### <a name="rules-for-use"></a><span data-ttu-id="f34bc-112">Правила использования</span><span class="sxs-lookup"><span data-stu-id="f34bc-112">Rules for use</span></span>

<span data-ttu-id="f34bc-113">Скрипт может включать более одной `#Requires` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f34bc-113">A script can include more than one `#Requires` statement.</span></span> <span data-ttu-id="f34bc-114">`#Requires`Инструкции могут присутствовать в любой строке скрипта.</span><span class="sxs-lookup"><span data-stu-id="f34bc-114">The `#Requires` statements can appear on any line in a script.</span></span>

<span data-ttu-id="f34bc-115">Размещение `#Requires` оператора внутри функции не ограничивает ее область действия.</span><span class="sxs-lookup"><span data-stu-id="f34bc-115">Placing a `#Requires` statement inside a function does NOT limit its scope.</span></span> <span data-ttu-id="f34bc-116">Все `#Requires` инструкции всегда применяются глобально и должны выполняться, прежде чем скрипт сможет выполняться.</span><span class="sxs-lookup"><span data-stu-id="f34bc-116">All `#Requires` statements are always applied globally, and must be met, before the script can execute.</span></span>

> [!WARNING]
> <span data-ttu-id="f34bc-117">Хотя `#Requires` инструкция может присутствовать в любой строке скрипта, ее расположение в скрипте не влияет на последовательность своего приложения.</span><span class="sxs-lookup"><span data-stu-id="f34bc-117">Even though a `#Requires` statement can appear on any line in a script, its position in a script does not affect the sequence of its application.</span></span> <span data-ttu-id="f34bc-118">Глобальное состояние, `#Requires` перед выполнением скрипта должна быть удовлетворена инструкция.</span><span class="sxs-lookup"><span data-stu-id="f34bc-118">The global state the `#Requires` statement presents must be met before script execution.</span></span>

<span data-ttu-id="f34bc-119">Пример</span><span class="sxs-lookup"><span data-stu-id="f34bc-119">Example:</span></span>

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

<span data-ttu-id="f34bc-120">Можно подумать, что приведенный выше код не должен выполняться, так как необходимый модуль был удален до `#Requires` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f34bc-120">You might think that the above code shouldn't run because the required module was removed before the `#Requires` statement.</span></span> <span data-ttu-id="f34bc-121">Однако `#Requires` перед выполнением скрипта должно быть выполнено состояние.</span><span class="sxs-lookup"><span data-stu-id="f34bc-121">However, the `#Requires` state had to be met before the script could even execute.</span></span> <span data-ttu-id="f34bc-122">Первая строка скрипта не проверяла требуемое состояние.</span><span class="sxs-lookup"><span data-stu-id="f34bc-122">Then the first line of the script invalidated the required state.</span></span>

### <a name="parameters"></a><span data-ttu-id="f34bc-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="f34bc-123">Parameters</span></span>

#### <a name="-assembly-assembly-path--net-assembly-specification"></a><span data-ttu-id="f34bc-124">-Assembly \<Assembly path> |\<.NET assembly specification></span><span class="sxs-lookup"><span data-stu-id="f34bc-124">-Assembly \<Assembly path> | \<.NET assembly specification></span></span>

<span data-ttu-id="f34bc-125">Указывает путь к DLL-файлу сборки или имени сборки .NET.</span><span class="sxs-lookup"><span data-stu-id="f34bc-125">Specifies the path to the assembly DLL file or a .NET assembly name.</span></span> <span data-ttu-id="f34bc-126">Параметр **Assembly** появился в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="f34bc-126">The **Assembly** parameter was introduced in PowerShell 5.0.</span></span> <span data-ttu-id="f34bc-127">Дополнительные сведения о сборках .NET см. в разделе [имена сборок](/dotnet/standard/assembly/names).</span><span class="sxs-lookup"><span data-stu-id="f34bc-127">For more information about .NET assemblies, see [Assembly names](/dotnet/standard/assembly/names).</span></span>

<span data-ttu-id="f34bc-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="f34bc-128">For example:</span></span>

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a><span data-ttu-id="f34bc-129">-Version \<N\> [. \<n\> ]</span><span class="sxs-lookup"><span data-stu-id="f34bc-129">-Version \<N\>[.\<n\>]</span></span>

<span data-ttu-id="f34bc-130">Указывает минимальную версию PowerShell, требуемую для скрипта.</span><span class="sxs-lookup"><span data-stu-id="f34bc-130">Specifies the minimum version of PowerShell that the script requires.</span></span> <span data-ttu-id="f34bc-131">Введите основной номер версии и необязательный дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="f34bc-131">Enter a major version number and optional minor version number.</span></span>

<span data-ttu-id="f34bc-132">Пример:</span><span class="sxs-lookup"><span data-stu-id="f34bc-132">For example:</span></span>

```powershell
#Requires -Version 6.0
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a><span data-ttu-id="f34bc-133">-PSSnapin \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]</span><span class="sxs-lookup"><span data-stu-id="f34bc-133">-PSSnapin \<PSSnapin-Name\> [-Version \<N\>[.\<n\>]]</span></span>

<span data-ttu-id="f34bc-134">Указывает оснастку PowerShell, требуемую для скрипта.</span><span class="sxs-lookup"><span data-stu-id="f34bc-134">Specifies a PowerShell snap-in that the script requires.</span></span> <span data-ttu-id="f34bc-135">Введите имя оснастки и номер необязательной версии.</span><span class="sxs-lookup"><span data-stu-id="f34bc-135">Enter the snap-in name and an optional version number.</span></span>

<span data-ttu-id="f34bc-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="f34bc-136">For example:</span></span>

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a><span data-ttu-id="f34bc-137">-Modules \<Module-Name\> |\<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="f34bc-137">-Modules \<Module-Name\> | \<Hashtable\></span></span>

<span data-ttu-id="f34bc-138">Указывает модули PowerShell, необходимые для скрипта.</span><span class="sxs-lookup"><span data-stu-id="f34bc-138">Specifies PowerShell modules that the script requires.</span></span> <span data-ttu-id="f34bc-139">Введите имя модуля и номер необязательной версии.</span><span class="sxs-lookup"><span data-stu-id="f34bc-139">Enter the module name and an optional version number.</span></span>

<span data-ttu-id="f34bc-140">Если необходимые модули не находятся в текущем сеансе, PowerShell импортирует их.</span><span class="sxs-lookup"><span data-stu-id="f34bc-140">If the required modules aren't in the current session, PowerShell imports them.</span></span>
<span data-ttu-id="f34bc-141">Если не удается импортировать модули, PowerShell выдает ошибку, завершающуюся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f34bc-141">If the modules can't be imported, PowerShell throws a terminating error.</span></span>

<span data-ttu-id="f34bc-142">Для каждого модуля введите имя модуля ( \<String\> ) или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="f34bc-142">For each module, type the module name (\<String\>) or a hash table.</span></span> <span data-ttu-id="f34bc-143">Значение может быть сочетанием строк и хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="f34bc-143">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="f34bc-144">Хэш-таблица содержит следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="f34bc-144">The hash table has the following keys.</span></span>

- <span data-ttu-id="f34bc-145">`ModuleName` - **Обязательное требование** Указывает имя модуля.</span><span class="sxs-lookup"><span data-stu-id="f34bc-145">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="f34bc-146">`GUID` - **Необязательно** Указывает идентификатор GUID модуля.</span><span class="sxs-lookup"><span data-stu-id="f34bc-146">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="f34bc-147">**Также необходимо** указать один из трех указанных ниже ключей.</span><span class="sxs-lookup"><span data-stu-id="f34bc-147">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="f34bc-148">Эти ключи нельзя использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="f34bc-148">These keys can't be used together.</span></span>
  - <span data-ttu-id="f34bc-149">`ModuleVersion` — Указывает минимальную допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="f34bc-149">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="f34bc-150">`RequiredVersion` — Указывает точную, требуемую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="f34bc-150">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="f34bc-151">`MaximumVersion` — Указывает максимально допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="f34bc-151">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="f34bc-152">`RequiredVersion` был добавлен в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="f34bc-152">`RequiredVersion` was added in Windows PowerShell 5.0.</span></span>
> <span data-ttu-id="f34bc-153">`MaximumVersion` был добавлен в Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="f34bc-153">`MaximumVersion` was added in Windows PowerShell 5.1.</span></span>

<span data-ttu-id="f34bc-154">Пример:</span><span class="sxs-lookup"><span data-stu-id="f34bc-154">For example:</span></span>

<span data-ttu-id="f34bc-155">Требовать `AzureRM.Netcore` установки (версии `0.12.0` или выше).</span><span class="sxs-lookup"><span data-stu-id="f34bc-155">Require that `AzureRM.Netcore` (version `0.12.0` or greater) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; ModuleVersion="0.12.0" }
```

<span data-ttu-id="f34bc-156">Требовать `AzureRM.Netcore` установку **только** версии `0.12.0` .</span><span class="sxs-lookup"><span data-stu-id="f34bc-156">Require that `AzureRM.Netcore` ( **only** version `0.12.0`) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12.0" }
```

<span data-ttu-id="f34bc-157">Требует `AzureRM.Netcore` установки (версии `0.12.0` или меньше).</span><span class="sxs-lookup"><span data-stu-id="f34bc-157">Requires that `AzureRM.Netcore` (version `0.12.0` or lesser) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; MaximumVersion="0.12.0" }
```

<span data-ttu-id="f34bc-158">Требовать установки любой версии `AzureRM.Netcore` и `PowerShellGet` .</span><span class="sxs-lookup"><span data-stu-id="f34bc-158">Require that any version of `AzureRM.Netcore` and `PowerShellGet` is installed.</span></span>

```powershell
#Requires -Modules AzureRM.Netcore, PowerShellGet
```

<span data-ttu-id="f34bc-159">При использовании `RequiredVersion` ключа убедитесь, что строка версии точно соответствует требуемой строке версии.</span><span class="sxs-lookup"><span data-stu-id="f34bc-159">When using the `RequiredVersion` key, ensure your version string exactly matches the version string you require.</span></span>

```powershell
Get-Module AzureRM.Netcore -ListAvailable
```

```Output
    Directory: /home/azureuser/.local/share/powershell/Modules

ModuleType Version Name            PSEdition ExportedCommands
---------- ------- ----            --------- ----------------
Script     0.12.0  AzureRM.Netcore Core
```

<span data-ttu-id="f34bc-160">В следующем примере происходит сбой, так как **0,12** не полностью соответствует **0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="f34bc-160">The following example fails because **0.12** doesn't exactly match **0.12.0**.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12" }
```

#### <a name="-psedition-psedition-name"></a><span data-ttu-id="f34bc-161">-PSEdition \<PSEdition-Name\></span><span class="sxs-lookup"><span data-stu-id="f34bc-161">-PSEdition \<PSEdition-Name\></span></span>

<span data-ttu-id="f34bc-162">Указывает выпуск PowerShell, который требуется для скрипта.</span><span class="sxs-lookup"><span data-stu-id="f34bc-162">Specifies a PowerShell edition that the script requires.</span></span> <span data-ttu-id="f34bc-163">Допустимые значения: **Core** для PowerShell Core и **Desktop** для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f34bc-163">Valid values are **Core** for PowerShell Core and **Desktop** for Windows PowerShell.</span></span>

<span data-ttu-id="f34bc-164">Пример:</span><span class="sxs-lookup"><span data-stu-id="f34bc-164">For example:</span></span>

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a><span data-ttu-id="f34bc-165">-Шеллид</span><span class="sxs-lookup"><span data-stu-id="f34bc-165">-ShellId</span></span>

<span data-ttu-id="f34bc-166">Указывает оболочку, требуемую для скрипта.</span><span class="sxs-lookup"><span data-stu-id="f34bc-166">Specifies the shell that the script requires.</span></span> <span data-ttu-id="f34bc-167">Введите идентификатор оболочки.</span><span class="sxs-lookup"><span data-stu-id="f34bc-167">Enter the shell ID.</span></span> <span data-ttu-id="f34bc-168">При использовании параметра **шеллид** необходимо также включить параметр **PSSnapin** .</span><span class="sxs-lookup"><span data-stu-id="f34bc-168">If you use the **ShellId** parameter, you must also include the **PSSnapin** parameter.</span></span>
<span data-ttu-id="f34bc-169">Текущую **шеллид** можно найти, запросив `$ShellId` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="f34bc-169">You can find the current **ShellId** by querying the `$ShellId` automatic variable.</span></span>

<span data-ttu-id="f34bc-170">Пример:</span><span class="sxs-lookup"><span data-stu-id="f34bc-170">For example:</span></span>

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> <span data-ttu-id="f34bc-171">Этот параметр предназначен для использования в мини-оболочках, которые являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="f34bc-171">This parameter is intended for use in mini-shells, which have been deprecated.</span></span>

#### <a name="-runasadministrator"></a><span data-ttu-id="f34bc-172">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="f34bc-172">-RunAsAdministrator</span></span>

<span data-ttu-id="f34bc-173">Когда этот параметр Switch добавляется к `#Requires` оператору, он указывает, что сеанс PowerShell, в котором выполняется скрипт, должен быть запущен с повышенными правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="f34bc-173">When this switch parameter is added to your `#Requires` statement, it specifies that the PowerShell session in which you're running the script must be started with elevated user rights.</span></span> <span data-ttu-id="f34bc-174">Параметр **рунасадминистратор** игнорируется в операционной системе, отличной от Windows.</span><span class="sxs-lookup"><span data-stu-id="f34bc-174">The **RunAsAdministrator** parameter is ignored on a non-Windows operating system.</span></span> <span data-ttu-id="f34bc-175">Параметр **рунасадминистратор** появился в PowerShell 4,0.</span><span class="sxs-lookup"><span data-stu-id="f34bc-175">The **RunAsAdministrator** parameter was introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="f34bc-176">Пример:</span><span class="sxs-lookup"><span data-stu-id="f34bc-176">For example:</span></span>

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a><span data-ttu-id="f34bc-177">Примеры</span><span class="sxs-lookup"><span data-stu-id="f34bc-177">Examples</span></span>

<span data-ttu-id="f34bc-178">Следующий скрипт содержит две `#Requires` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f34bc-178">The following script has two `#Requires` statements.</span></span> <span data-ttu-id="f34bc-179">Если требования, указанные в обоих инструкциях, не выполняются, скрипт не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f34bc-179">If the requirements specified in both statements aren't met, the script doesn't run.</span></span> <span data-ttu-id="f34bc-180">Каждая `#Requires` инструкция должна быть первым элементом в строке:</span><span class="sxs-lookup"><span data-stu-id="f34bc-180">Each `#Requires` statement must be the first item on a line:</span></span>

```powershell
#Requires -Modules AzureRM.Netcore
#Requires -Version 6.0
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a><span data-ttu-id="f34bc-181">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f34bc-181">See also</span></span>

[<span data-ttu-id="f34bc-182">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="f34bc-182">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="f34bc-183">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="f34bc-183">about_Language_Keywords</span></span>](about_Language_Keywords.md)
