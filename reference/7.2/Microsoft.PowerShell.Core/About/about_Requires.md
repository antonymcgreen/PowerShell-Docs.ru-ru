---
description: Предотвращает запуск скрипта без необходимых элементов.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: d340de615923437bb3e29c1984ef8849fe03a40e
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "99605276"
---
# <a name="about-requires"></a><span data-ttu-id="b5092-103">О программе требуется</span><span class="sxs-lookup"><span data-stu-id="b5092-103">About Requires</span></span>

## <a name="short-description"></a><span data-ttu-id="b5092-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="b5092-104">Short description</span></span>
<span data-ttu-id="b5092-105">Предотвращает запуск скрипта без необходимых элементов.</span><span class="sxs-lookup"><span data-stu-id="b5092-105">Prevents a script from running without the required elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="b5092-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b5092-106">Long description</span></span>

<span data-ttu-id="b5092-107">`#Requires`Инструкция предотвращает выполнение скрипта, если не выполнены версия PowerShell, модули (и версия), а также оснастки (и версия) и предварительные требования к выпуску.</span><span class="sxs-lookup"><span data-stu-id="b5092-107">The `#Requires` statement prevents a script from running unless the PowerShell version, modules (and version), or snap-ins (and version), and edition prerequisites are met.</span></span> <span data-ttu-id="b5092-108">Если необходимые условия не соблюдены, PowerShell не выполняет сценарий.</span><span class="sxs-lookup"><span data-stu-id="b5092-108">If the prerequisites aren't met, PowerShell doesn't run the script.</span></span>

### <a name="syntax"></a><span data-ttu-id="b5092-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5092-109">Syntax</span></span>

```
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

<span data-ttu-id="b5092-110">Дополнительные сведения о синтаксисе см. в разделе [скриптрекуирементс](/dotnet/api/system.management.automation.language.scriptrequirements).</span><span class="sxs-lookup"><span data-stu-id="b5092-110">For more information about the syntax, see [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span></span>

### <a name="rules-for-use"></a><span data-ttu-id="b5092-111">Правила использования</span><span class="sxs-lookup"><span data-stu-id="b5092-111">Rules for use</span></span>

<span data-ttu-id="b5092-112">Скрипт может включать более одной `#Requires` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b5092-112">A script can include more than one `#Requires` statement.</span></span> <span data-ttu-id="b5092-113">`#Requires`Инструкции могут присутствовать в любой строке скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5092-113">The `#Requires` statements can appear on any line in a script.</span></span>

<span data-ttu-id="b5092-114">Размещение `#Requires` оператора внутри функции не ограничивает ее область действия.</span><span class="sxs-lookup"><span data-stu-id="b5092-114">Placing a `#Requires` statement inside a function does NOT limit its scope.</span></span> <span data-ttu-id="b5092-115">Все `#Requires` инструкции всегда применяются глобально и должны выполняться, прежде чем скрипт сможет выполняться.</span><span class="sxs-lookup"><span data-stu-id="b5092-115">All `#Requires` statements are always applied globally, and must be met, before the script can execute.</span></span>

> [!WARNING]
> <span data-ttu-id="b5092-116">Хотя `#Requires` инструкция может присутствовать в любой строке скрипта, ее расположение в скрипте не влияет на последовательность своего приложения.</span><span class="sxs-lookup"><span data-stu-id="b5092-116">Even though a `#Requires` statement can appear on any line in a script, its position in a script does not affect the sequence of its application.</span></span> <span data-ttu-id="b5092-117">Глобальное состояние, `#Requires` перед выполнением скрипта должна быть удовлетворена инструкция.</span><span class="sxs-lookup"><span data-stu-id="b5092-117">The global state the `#Requires` statement presents must be met before script execution.</span></span>

<span data-ttu-id="b5092-118">Пример.</span><span class="sxs-lookup"><span data-stu-id="b5092-118">Example:</span></span>

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

<span data-ttu-id="b5092-119">Можно подумать, что приведенный выше код не должен выполняться, так как необходимый модуль был удален до `#Requires` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b5092-119">You might think that the above code shouldn't run because the required module was removed before the `#Requires` statement.</span></span> <span data-ttu-id="b5092-120">Однако `#Requires` перед выполнением скрипта должно быть выполнено состояние.</span><span class="sxs-lookup"><span data-stu-id="b5092-120">However, the `#Requires` state had to be met before the script could even execute.</span></span> <span data-ttu-id="b5092-121">Первая строка скрипта не проверяла требуемое состояние.</span><span class="sxs-lookup"><span data-stu-id="b5092-121">Then the first line of the script invalidated the required state.</span></span>

### <a name="parameters"></a><span data-ttu-id="b5092-122">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5092-122">Parameters</span></span>

#### <a name="-assembly-assembly-path--net-assembly-specification"></a><span data-ttu-id="b5092-123">-Assembly \<Assembly path> |\<.NET assembly specification></span><span class="sxs-lookup"><span data-stu-id="b5092-123">-Assembly \<Assembly path> | \<.NET assembly specification></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5092-124">`-Assembly`Синтаксис является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="b5092-124">The `-Assembly` syntax is deprecated.</span></span> <span data-ttu-id="b5092-125">Она не обслуживает никаких функций.</span><span class="sxs-lookup"><span data-stu-id="b5092-125">It serves no function.</span></span> <span data-ttu-id="b5092-126">Синтаксис был добавлен в PowerShell 5,1, но вспомогательный код никогда не был реализован.</span><span class="sxs-lookup"><span data-stu-id="b5092-126">The syntax was added in PowerShell 5.1 but the supporting code was never implemented.</span></span> <span data-ttu-id="b5092-127">Синтаксис по-прежнему принимается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="b5092-127">The syntax is still accepted for backward compatibility.</span></span>

<span data-ttu-id="b5092-128">Указывает путь к DLL-файлу сборки или имени сборки .NET.</span><span class="sxs-lookup"><span data-stu-id="b5092-128">Specifies the path to the assembly DLL file or a .NET assembly name.</span></span> <span data-ttu-id="b5092-129">Параметр **Assembly** появился в PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="b5092-129">The **Assembly** parameter was introduced in PowerShell 5.0.</span></span> <span data-ttu-id="b5092-130">Дополнительные сведения о сборках .NET см. в разделе [имена сборок](/dotnet/standard/assembly/names).</span><span class="sxs-lookup"><span data-stu-id="b5092-130">For more information about .NET assemblies, see [Assembly names](/dotnet/standard/assembly/names).</span></span>

<span data-ttu-id="b5092-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5092-131">For example:</span></span>

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a><span data-ttu-id="b5092-132">-Version \<N\> [. \<n\> ]</span><span class="sxs-lookup"><span data-stu-id="b5092-132">-Version \<N\>[.\<n\>]</span></span>

<span data-ttu-id="b5092-133">Указывает минимальную версию PowerShell, требуемую для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5092-133">Specifies the minimum version of PowerShell that the script requires.</span></span> <span data-ttu-id="b5092-134">Введите основной номер версии и необязательный дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="b5092-134">Enter a major version number and optional minor version number.</span></span>

<span data-ttu-id="b5092-135">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5092-135">For example:</span></span>

```powershell
#Requires -Version 6.0
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a><span data-ttu-id="b5092-136">-PSSnapin \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]</span><span class="sxs-lookup"><span data-stu-id="b5092-136">-PSSnapin \<PSSnapin-Name\> [-Version \<N\>[.\<n\>]]</span></span>

<span data-ttu-id="b5092-137">Указывает оснастку PowerShell, требуемую для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5092-137">Specifies a PowerShell snap-in that the script requires.</span></span> <span data-ttu-id="b5092-138">Введите имя оснастки и номер необязательной версии.</span><span class="sxs-lookup"><span data-stu-id="b5092-138">Enter the snap-in name and an optional version number.</span></span>

<span data-ttu-id="b5092-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5092-139">For example:</span></span>

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a><span data-ttu-id="b5092-140">-Modules \<Module-Name\> |\<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="b5092-140">-Modules \<Module-Name\> | \<Hashtable\></span></span>

<span data-ttu-id="b5092-141">Указывает модули PowerShell, необходимые для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5092-141">Specifies PowerShell modules that the script requires.</span></span> <span data-ttu-id="b5092-142">Введите имя модуля и номер необязательной версии.</span><span class="sxs-lookup"><span data-stu-id="b5092-142">Enter the module name and an optional version number.</span></span>

<span data-ttu-id="b5092-143">Если необходимые модули не находятся в текущем сеансе, PowerShell импортирует их.</span><span class="sxs-lookup"><span data-stu-id="b5092-143">If the required modules aren't in the current session, PowerShell imports them.</span></span>
<span data-ttu-id="b5092-144">Если не удается импортировать модули, PowerShell выдает ошибку, завершающуюся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b5092-144">If the modules can't be imported, PowerShell throws a terminating error.</span></span>

<span data-ttu-id="b5092-145">Для каждого модуля введите имя модуля ( \<String\> ) или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="b5092-145">For each module, type the module name (\<String\>) or a hash table.</span></span> <span data-ttu-id="b5092-146">Значение может быть сочетанием строк и хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="b5092-146">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="b5092-147">Хэш-таблица содержит следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="b5092-147">The hash table has the following keys.</span></span>

- <span data-ttu-id="b5092-148">`ModuleName` - **Обязательное требование** Указывает имя модуля.</span><span class="sxs-lookup"><span data-stu-id="b5092-148">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="b5092-149">`GUID` - **Необязательно** Указывает идентификатор GUID модуля.</span><span class="sxs-lookup"><span data-stu-id="b5092-149">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="b5092-150">**Также необходимо** указать один из трех указанных ниже ключей.</span><span class="sxs-lookup"><span data-stu-id="b5092-150">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="b5092-151">Эти ключи нельзя использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="b5092-151">These keys can't be used together.</span></span>
  - <span data-ttu-id="b5092-152">`ModuleVersion` — Указывает минимальную допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="b5092-152">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="b5092-153">`RequiredVersion` — Указывает точную, требуемую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="b5092-153">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="b5092-154">`MaximumVersion` — Указывает максимально допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="b5092-154">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="b5092-155">`RequiredVersion` был добавлен в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="b5092-155">`RequiredVersion` was added in Windows PowerShell 5.0.</span></span>
> <span data-ttu-id="b5092-156">`MaximumVersion` был добавлен в Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="b5092-156">`MaximumVersion` was added in Windows PowerShell 5.1.</span></span>

<span data-ttu-id="b5092-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5092-157">For example:</span></span>

<span data-ttu-id="b5092-158">Требовать `AzureRM.Netcore` установки (версии `0.12.0` или выше).</span><span class="sxs-lookup"><span data-stu-id="b5092-158">Require that `AzureRM.Netcore` (version `0.12.0` or greater) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; ModuleVersion="0.12.0" }
```

<span data-ttu-id="b5092-159">Требовать `AzureRM.Netcore` установку **только** версии `0.12.0` .</span><span class="sxs-lookup"><span data-stu-id="b5092-159">Require that `AzureRM.Netcore` (**only** version `0.12.0`) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12.0" }
```

<span data-ttu-id="b5092-160">Требует `AzureRM.Netcore` установки (версии `0.12.0` или меньше).</span><span class="sxs-lookup"><span data-stu-id="b5092-160">Requires that `AzureRM.Netcore` (version `0.12.0` or lesser) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; MaximumVersion="0.12.0" }
```

<span data-ttu-id="b5092-161">Требовать установки любой версии `AzureRM.Netcore` и `PowerShellGet` .</span><span class="sxs-lookup"><span data-stu-id="b5092-161">Require that any version of `AzureRM.Netcore` and `PowerShellGet` is installed.</span></span>

```powershell
#Requires -Modules AzureRM.Netcore, PowerShellGet
```

<span data-ttu-id="b5092-162">При использовании `RequiredVersion` ключа убедитесь, что строка версии точно соответствует требуемой строке версии.</span><span class="sxs-lookup"><span data-stu-id="b5092-162">When using the `RequiredVersion` key, ensure your version string exactly matches the version string you require.</span></span>

```powershell
Get-Module AzureRM.Netcore -ListAvailable
```

```Output
    Directory: /home/azureuser/.local/share/powershell/Modules

ModuleType Version Name            PSEdition ExportedCommands
---------- ------- ----            --------- ----------------
Script     0.12.0  AzureRM.Netcore Core
```

<span data-ttu-id="b5092-163">В следующем примере происходит сбой, так как **0,12** не полностью соответствует **0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="b5092-163">The following example fails because **0.12** doesn't exactly match **0.12.0**.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12" }
```

#### <a name="-psedition-psedition-name"></a><span data-ttu-id="b5092-164">-PSEdition \<PSEdition-Name\></span><span class="sxs-lookup"><span data-stu-id="b5092-164">-PSEdition \<PSEdition-Name\></span></span>

<span data-ttu-id="b5092-165">Указывает выпуск PowerShell, который требуется для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5092-165">Specifies a PowerShell edition that the script requires.</span></span> <span data-ttu-id="b5092-166">Допустимые значения: **Core** для PowerShell Core и **Desktop** для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5092-166">Valid values are **Core** for PowerShell Core and **Desktop** for Windows PowerShell.</span></span>

<span data-ttu-id="b5092-167">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5092-167">For example:</span></span>

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a><span data-ttu-id="b5092-168">-Шеллид</span><span class="sxs-lookup"><span data-stu-id="b5092-168">-ShellId</span></span>

<span data-ttu-id="b5092-169">Указывает оболочку, требуемую для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5092-169">Specifies the shell that the script requires.</span></span> <span data-ttu-id="b5092-170">Введите идентификатор оболочки.</span><span class="sxs-lookup"><span data-stu-id="b5092-170">Enter the shell ID.</span></span> <span data-ttu-id="b5092-171">При использовании параметра **шеллид** необходимо также включить параметр **PSSnapin** .</span><span class="sxs-lookup"><span data-stu-id="b5092-171">If you use the **ShellId** parameter, you must also include the **PSSnapin** parameter.</span></span>
<span data-ttu-id="b5092-172">Текущую **шеллид** можно найти, запросив `$ShellId` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="b5092-172">You can find the current **ShellId** by querying the `$ShellId` automatic variable.</span></span>

<span data-ttu-id="b5092-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5092-173">For example:</span></span>

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> <span data-ttu-id="b5092-174">Этот параметр предназначен для использования в мини-оболочках, которые являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="b5092-174">This parameter is intended for use in mini-shells, which have been deprecated.</span></span>

#### <a name="-runasadministrator"></a><span data-ttu-id="b5092-175">-Рунасадминистратор</span><span class="sxs-lookup"><span data-stu-id="b5092-175">-RunAsAdministrator</span></span>

<span data-ttu-id="b5092-176">Когда этот параметр Switch добавляется к `#Requires` оператору, он указывает, что сеанс PowerShell, в котором выполняется скрипт, должен быть запущен с повышенными правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5092-176">When this switch parameter is added to your `#Requires` statement, it specifies that the PowerShell session in which you're running the script must be started with elevated user rights.</span></span> <span data-ttu-id="b5092-177">Параметр **рунасадминистратор** игнорируется в операционной системе, отличной от Windows.</span><span class="sxs-lookup"><span data-stu-id="b5092-177">The **RunAsAdministrator** parameter is ignored on a non-Windows operating system.</span></span> <span data-ttu-id="b5092-178">Параметр **рунасадминистратор** появился в PowerShell 4,0.</span><span class="sxs-lookup"><span data-stu-id="b5092-178">The **RunAsAdministrator** parameter was introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="b5092-179">Пример:</span><span class="sxs-lookup"><span data-stu-id="b5092-179">For example:</span></span>

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a><span data-ttu-id="b5092-180">Примеры</span><span class="sxs-lookup"><span data-stu-id="b5092-180">Examples</span></span>

<span data-ttu-id="b5092-181">Следующий скрипт содержит две `#Requires` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b5092-181">The following script has two `#Requires` statements.</span></span> <span data-ttu-id="b5092-182">Если требования, указанные в обоих инструкциях, не выполняются, скрипт не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b5092-182">If the requirements specified in both statements aren't met, the script doesn't run.</span></span> <span data-ttu-id="b5092-183">Каждая `#Requires` инструкция должна быть первым элементом в строке:</span><span class="sxs-lookup"><span data-stu-id="b5092-183">Each `#Requires` statement must be the first item on a line:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b5092-184">См. также</span><span class="sxs-lookup"><span data-stu-id="b5092-184">See also</span></span>

[<span data-ttu-id="b5092-185">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="b5092-185">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="b5092-186">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="b5092-186">about_Language_Keywords</span></span>](about_Language_Keywords.md)
