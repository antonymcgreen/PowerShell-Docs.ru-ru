---
ms.date: 04/28/2020
title: Использование экспериментальных функций в PowerShell
description: Список доступных в настоящее время экспериментальных функций и их использование.
ms.openlocfilehash: 72a4309d6eeede4cd2ff7c38ce8e99ce3ace30eb
ms.sourcegitcommit: e6a9b13a4799667b74e0ba0f742dded4511d32b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82630773"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="c071f-103">Использование экспериментальных функций в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c071f-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="c071f-104">Поддержка экспериментальных функций в PowerShell обеспечивает механизм для сосуществования экспериментальных функций с имеющимися стабильными функциями в модулях PowerShell или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c071f-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="c071f-105">Экспериментальной функцией называется та, которая находится на этапе проектирования.</span><span class="sxs-lookup"><span data-stu-id="c071f-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="c071f-106">Эта функция доступна пользователям для тестирования и предоставления отзывов о ней.</span><span class="sxs-lookup"><span data-stu-id="c071f-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="c071f-107">Как только процесс разработки экспериментальной функции будет завершен, изменения на этапе проектирования станут критическими.</span><span class="sxs-lookup"><span data-stu-id="c071f-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="c071f-108">Экспериментальные функции не предназначены для использования в рабочей среде, так как изменения могут привести к нарушению работы.</span><span class="sxs-lookup"><span data-stu-id="c071f-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="c071f-109">Экспериментальные функции официально не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c071f-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="c071f-110">Тем не менее мы будем признательны вам за любые отзывы и отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c071f-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="c071f-111">Сообщить о проблеме можно в [исходном репозитории GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).</span><span class="sxs-lookup"><span data-stu-id="c071f-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="c071f-112">Дополнительные сведения о включении или отключении этих функций см. в статье [Экспериментальные функции](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span><span class="sxs-lookup"><span data-stu-id="c071f-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="c071f-113">Доступные функции</span><span class="sxs-lookup"><span data-stu-id="c071f-113">Available features</span></span>

<span data-ttu-id="c071f-114">В этой статье описываются доступные экспериментальные функции и сведения об их использовании.</span><span class="sxs-lookup"><span data-stu-id="c071f-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="c071f-115">Имя</span><span class="sxs-lookup"><span data-stu-id="c071f-115">Name</span></span>                            |   <span data-ttu-id="c071f-116">6.2</span><span class="sxs-lookup"><span data-stu-id="c071f-116">6.2</span></span>   |   <span data-ttu-id="c071f-117">7.0</span><span class="sxs-lookup"><span data-stu-id="c071f-117">7.0</span></span>   | <span data-ttu-id="c071f-118">7.1 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c071f-118">7.1 (preview)</span></span> |
| ---------------------------------------------------------- | :-----: | :-----: | :-----------: |
| <span data-ttu-id="c071f-119">PSTempDrive (основная фаза в PS 7.0 и выше)</span><span class="sxs-lookup"><span data-stu-id="c071f-119">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |               |
| <span data-ttu-id="c071f-120">PSUseAbbreviationExpansion (основная фаза в PS 7.0 и выше)</span><span class="sxs-lookup"><span data-stu-id="c071f-120">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |               |
| <span data-ttu-id="c071f-121">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="c071f-121">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; |    &check;    |
| <span data-ttu-id="c071f-122">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="c071f-122">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; |    &check;    |
| <span data-ttu-id="c071f-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="c071f-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; |    &check;    |
| <span data-ttu-id="c071f-124">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="c071f-124">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; |    &check;    |
| <span data-ttu-id="c071f-125">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="c071f-125">PSNullConditionalOperators</span></span>                                 |         | &check; |    &check;    |
| <span data-ttu-id="c071f-126">PSUnixFileStat (только не на базе Windows)</span><span class="sxs-lookup"><span data-stu-id="c071f-126">PSUnixFileStat (non-Windows only)</span></span>                          |         | &check; |    &check;    |
| <span data-ttu-id="c071f-127">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="c071f-127">PSNativePSPathResolution</span></span>                                   |         |         |    &check;    |
| <span data-ttu-id="c071f-128">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="c071f-128">PSCultureInvariantReplaceOperator</span></span>                          |         |         |    &check;    |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="c071f-129">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="c071f-129">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="c071f-130">Эта функция включает параметр **BreakAll** в командлетах `Debug-Runspace` и `Debug-Job`, чтобы пользователи могли принять решение, стоит ли PowerShell немедленно остановиться в текущем расположении при подключении отладчика.</span><span class="sxs-lookup"><span data-stu-id="c071f-130">Enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="c071f-131">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="c071f-131">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="c071f-132">Рекомендует потенциальные команды на основе поиска нечетких соответствий после **CommandNotFoundException**.</span><span class="sxs-lookup"><span data-stu-id="c071f-132">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="c071f-133">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="c071f-133">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="c071f-134">Когда левый операнд в инструкции оператора `-replace` не является строкой, он преобразуется в строку.</span><span class="sxs-lookup"><span data-stu-id="c071f-134">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="c071f-135">Когда эта функция отключена, оператор `-replace` выполняет преобразование строк с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c071f-135">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="c071f-136">Например, если для языка и региональных параметров настроен французский язык (fr), значение `1.2` преобразуется в строку `1,2`.</span><span class="sxs-lookup"><span data-stu-id="c071f-136">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="c071f-137">С включенной функцией:</span><span class="sxs-lookup"><span data-stu-id="c071f-137">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="c071f-138">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="c071f-138">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="c071f-139">Эта функция включает компиляцию в MOF в системах, отличных от Windows, и позволяет использовать `Invoke-DSCResource` без LCM.</span><span class="sxs-lookup"><span data-stu-id="c071f-139">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="c071f-140">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="c071f-140">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="c071f-141">Эта функция проверяет команду, введенную в оболочке. Если все команды являются командами прокси-сервера неявного удаленного взаимодействия, которые образуют простой конвейер, то эти команды объединяются и вызываются как один удаленный конвейер.</span><span class="sxs-lookup"><span data-stu-id="c071f-141">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="c071f-142">Пример</span><span class="sxs-lookup"><span data-stu-id="c071f-142">Example:</span></span>

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

<span data-ttu-id="c071f-143">Как показано выше, при включенной функции пакетирования все три команды прокси-сервера неявного удаленного доступа (`Get-AllProcesses`, `Select-Custom`, `Group-Stuff`) выполняются в удаленном сеансе, а результат из конвейера — это единственные данные, которые возвращаются клиенту.</span><span class="sxs-lookup"><span data-stu-id="c071f-143">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="c071f-144">Это приводит к уменьшению объема данных, передаваемых между клиентом и удаленным сеансом. Это также уменьшает количество процессов сериализации и десериализации объекта.</span><span class="sxs-lookup"><span data-stu-id="c071f-144">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="c071f-145">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="c071f-145">PSNativePSPathResolution</span></span>

<span data-ttu-id="c071f-146">Если путь PSDrive, использующий поставщик FileSystem, передается собственной команде, то и разрешенный путь к файлу передается собственной команде.</span><span class="sxs-lookup"><span data-stu-id="c071f-146">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="c071f-147">Это означает, что такая команда, как `code temp:/test.txt`, сейчас работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="c071f-147">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="c071f-148">Кроме того, если в Windows путь начинается с `~`, он преобразуется в полный путь и передается собственной команде.</span><span class="sxs-lookup"><span data-stu-id="c071f-148">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="c071f-149">В обоих случаях путь нормализуется к разделителям каталогов для соответствующей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c071f-149">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="c071f-150">Если путь не является PSDrive или `~` (в Windows), то нормализация пути не происходит.</span><span class="sxs-lookup"><span data-stu-id="c071f-150">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="c071f-151">Если путь указан в одинарных кавычках, он не разрешается и рассматривается в качестве литерала.</span><span class="sxs-lookup"><span data-stu-id="c071f-151">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="c071f-152">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="c071f-152">PSNullConditionalOperators</span></span>

<span data-ttu-id="c071f-153">Эта функция вводит новые операторы для операторов доступа к членам, определяемого условием NULL: `?.` и `?[]`.</span><span class="sxs-lookup"><span data-stu-id="c071f-153">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="c071f-154">Операторы доступа к членам, определяемого условием NULL, могут использоваться для скалярных типов и типов массивов.</span><span class="sxs-lookup"><span data-stu-id="c071f-154">Null member access operators can used on scalar types and array types.</span></span> <span data-ttu-id="c071f-155">Возвращает значение члена, к которому был получен доступ, если переменная не равна значению NULL.</span><span class="sxs-lookup"><span data-stu-id="c071f-155">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="c071f-156">Если значение переменной равно значению NULL, тогда возвращается NULL.</span><span class="sxs-lookup"><span data-stu-id="c071f-156">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="c071f-157">Доступ к свойству `propname` и его значение возвращаются, только если `$x` не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="c071f-157">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="c071f-158">Аналогичным образом индексатор используется, только если `$x` не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="c071f-158">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="c071f-159">Если `$x` равно NULL, то возвращается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c071f-159">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="c071f-160">Операторы `?.` и `?[]` являются операторами доступа к членам и не допускают пробела между именем переменной и оператором.</span><span class="sxs-lookup"><span data-stu-id="c071f-160">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="c071f-161">Так как PowerShell допускает `?` в качестве части имени переменной, когда операторы используются без пробела между именем переменной и оператором, требуется устранение неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="c071f-161">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="c071f-162">Чтобы устранить неоднозначность, переменные должны заключить имя переменной в скобки `{}`, например: `${x?}?.propertyName` или `${y}?[0]`.</span><span class="sxs-lookup"><span data-stu-id="c071f-162">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="c071f-163">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="c071f-163">PSTempDrive</span></span>

<span data-ttu-id="c071f-164">Создает `TEMP:` PSDrive, сопоставленный с временным каталогом пользователя.</span><span class="sxs-lookup"><span data-stu-id="c071f-164">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="c071f-165">Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="c071f-165">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="c071f-166">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="c071f-166">PSUnixFileStat</span></span>

<span data-ttu-id="c071f-167">Эта функция обеспечивает новые возможности для включения данных из API функции **stat** Unix в выходные данные поставщика файловой системы, чтобы упростить более похожий на Unix список файлов.</span><span class="sxs-lookup"><span data-stu-id="c071f-167">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="c071f-168">Она добавляет новое свойство примечания в поставщик файловой системы с именем **UnixStat**, которое включает в себя общее выражение API `stat(2)` из базовой системы типов Unix.</span><span class="sxs-lookup"><span data-stu-id="c071f-168">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="c071f-169">Результат `Get-ChildItem` должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c071f-169">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
PS> dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="c071f-170">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="c071f-170">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="c071f-171">Эта функция позволяет выполнять заполнение сокращенных командлетов и функций нажатием клавиши TAB:</span><span class="sxs-lookup"><span data-stu-id="c071f-171">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="c071f-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="c071f-172">For example:</span></span>

- <span data-ttu-id="c071f-173">`i-psdf<tab>` возвращает `Import-PowerShellDataFile`.</span><span class="sxs-lookup"><span data-stu-id="c071f-173">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="c071f-174">`u-akvmssdr<tab>` возвращает `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span><span class="sxs-lookup"><span data-stu-id="c071f-174">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="c071f-175">Эта функция работает только для заполнения нажатием клавиши TAB (интерактивное использование), поэтому `i-psdf` — недопустимое имя командлета в скрипте.</span><span class="sxs-lookup"><span data-stu-id="c071f-175">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="c071f-176">Эта функция вышла из экспериментального режима и является основной функцией в PowerShell 7 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="c071f-176">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>
