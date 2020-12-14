---
title: Новые возможности в PowerShell Core 6.2
description: Новые возможности и изменения в PowerShell Core 6.2
ms.date: 03/28/2019
ms.openlocfilehash: 98dd97b064e11509bf97e68e0a312e6b34b5d2bc
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2020
ms.locfileid: "96833815"
---
# <a name="whats-new-in-powershell-core-62"></a><span data-ttu-id="d326a-103">Новые возможности в PowerShell Core 6.2</span><span class="sxs-lookup"><span data-stu-id="d326a-103">What's New in PowerShell Core 6.2</span></span>

<span data-ttu-id="d326a-104">В выпуске PowerShell Core 6.2 основное внимание уделено повышению производительности, исправлению ошибок, а также небольшим усовершенствованиям командлетов и языка, улучшающим качество.</span><span class="sxs-lookup"><span data-stu-id="d326a-104">The PowerShell Core 6.2 release focused on performance improvements, bug fixes, and smaller cmdlet and language enhancements that improve the quality.</span></span> <span data-ttu-id="d326a-105">Полный список улучшений можно увидеть в наших подробных [журналах изменений](https://github.com/PowerShell/PowerShell/releases) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="d326a-105">To see a full list of improvements, check out our detailed [changelogs](https://github.com/PowerShell/PowerShell/releases) on GitHub.</span></span>

## <a name="experimental-features"></a><span data-ttu-id="d326a-106">Экспериментальные возможности</span><span class="sxs-lookup"><span data-stu-id="d326a-106">Experimental Features</span></span>

<span data-ttu-id="d326a-107">Ранее мы добавили поддержку [Экспериментальные возможности][].</span><span class="sxs-lookup"><span data-stu-id="d326a-107">Previously, we enabled support for [Experimental Features][].</span></span> <span data-ttu-id="d326a-108">В выпуске 6.2 имеются четыре экспериментальные возможности. Оставьте отзыв по этим возможностям, чтобы мы могли внести улучшения и решить, стоит ли переводить их в статус базовых.</span><span class="sxs-lookup"><span data-stu-id="d326a-108">In the 6.2 release, we have four experimental features to try out. Please provide feedback so we can make improvements and to decide whether the feature is worth promoting to mainstream status.</span></span>

<span data-ttu-id="d326a-109">Используйте командлет `Get-ExperimentalFeature`, чтобы получить список доступных экспериментальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="d326a-109">Use `Get-ExperimentalFeature` to get a list of available experimental features.</span></span> <span data-ttu-id="d326a-110">Их можно включить и отключить с помощью `Enable-ExperimentalFeature` и `Disable-ExperimentalFeature` соответственно.</span><span class="sxs-lookup"><span data-stu-id="d326a-110">You can enable or disable these features with `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature`.</span></span>

### <a name="command-not-found-suggestions"></a><span data-ttu-id="d326a-111">Предложения "Команда не найдена"</span><span class="sxs-lookup"><span data-stu-id="d326a-111">Command Not Found Suggestions</span></span>

<span data-ttu-id="d326a-112">Эта возможность использует нечеткое соответствие, чтобы найти предложения для команд или командлетов, в которых вы, возможно, допустили опечатку.</span><span class="sxs-lookup"><span data-stu-id="d326a-112">This feature uses fuzzy matching to find suggestions for commands or cmdlets you may have mistyped.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSCommandNotFoundSuggestion
```

#### <a name="example"></a><span data-ttu-id="d326a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d326a-113">Example</span></span>

<span data-ttu-id="d326a-114">В этом примере имя командлета с ошибками нечетко соответствует нескольким предложениям от наиболее до наименее вероятных.</span><span class="sxs-lookup"><span data-stu-id="d326a-114">In this example, the misspelled cmdlet name is fuzzy matched to several suggestions from most likely to least likely.</span></span>

```powershell
Get-Commnd
```

```Output
Get-Commnd : The term 'Get-Commnd' is not recognized as the name of a cmdlet, function, script file, or operable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-Commnd
+ ~~~~~~~~~~
+ CategoryInfo          : ObjectNotFound: (Get-Commnd:String) [], CommandNotFoundException
+ FullyQualifiedErrorId : CommandNotFoundException


Suggestion [4,General]: The most similar commands are: Get-Command, Get-Content, Get-Job, Get-Module, Get-Event, Get-Host, Get-Member, Get-Item, Set-Content.
```

### <a name="implicit-remoting-batching"></a><span data-ttu-id="d326a-115">Пакетная обработка неявного удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="d326a-115">Implicit Remoting Batching</span></span>

<span data-ttu-id="d326a-116">При использовании [неявного удаленного взаимодействия](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) в конвейере PowerShell обрабатывает каждую команду в конвейере независимо.</span><span class="sxs-lookup"><span data-stu-id="d326a-116">When using [implicit remoting](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) in a pipeline, PowerShell treats each command in the pipeline independently.</span></span> <span data-ttu-id="d326a-117">Во время работы конвейера объекты периодически сериализуются и десериализуются (`de-serialized`) между клиентом и удаленной системой.</span><span class="sxs-lookup"><span data-stu-id="d326a-117">Objects are repeatedly serialized and `de-serialized` between the client and remote system over the execution of the pipeline.</span></span>

<span data-ttu-id="d326a-118">С помощью этой возможности PowerShell анализирует конвейер, чтобы определить, является ли команда безопасной для выполнения и существует ли она в целевой системе.</span><span class="sxs-lookup"><span data-stu-id="d326a-118">With this feature, PowerShell analyzes the pipeline to determine if the command is safe to run and it exists on the target system.</span></span> <span data-ttu-id="d326a-119">Если значение TRUE, PowerShell выполняет весь конвейер удаленно и сериализует и десериализует (`de-serializes`) обратно в клиент только результаты.</span><span class="sxs-lookup"><span data-stu-id="d326a-119">When true, PowerShell executes the entire pipeline remotely and only serializes and `de-serializes` the results back to the client.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSImplicitRemotingBatching
```

<span data-ttu-id="d326a-120">Реальное тестирование `Get-Process | Sort-Object` через localhost уменьшается с 10–15 секунд до 20–30 **миллисекунд**.</span><span class="sxs-lookup"><span data-stu-id="d326a-120">A real-world test of `Get-Process | Sort-Object` over localhost decreases from 10-15 seconds to 20-30 **milliseconds**.</span></span> <span data-ttu-id="d326a-121">Эта возможность должна быть включена только в клиенте.</span><span class="sxs-lookup"><span data-stu-id="d326a-121">The feature only needs to be enabled on the client.</span></span> <span data-ttu-id="d326a-122">Изменения на сервере не требуются.</span><span class="sxs-lookup"><span data-stu-id="d326a-122">No changes are required on the server.</span></span>

### <a name="temp-drive"></a><span data-ttu-id="d326a-123">Временной диск</span><span class="sxs-lookup"><span data-stu-id="d326a-123">Temp Drive</span></span>

```powershell
Enable-ExperimentalFeature -Name PSTempDrive
```

<span data-ttu-id="d326a-124">Если вы используете PowerShell Core в различных операционных системах, вы обнаружите, что переменная среды для поиска временного каталога отличается в Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="d326a-124">If you're using PowerShell Core on different operating systems, you'll discover that the environment variable for finding the temporary directory is different on Windows, macOS, and Linux!</span></span> <span data-ttu-id="d326a-125">Благодаря этой возможности вы получаете диск [PSDrive][] с именем `Temp:`, который автоматически сопоставляется с временной папкой для используемой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d326a-125">With this feature, you get a [PSDrive][] called `Temp:` that is automatically mapped to the temporary folder for the operating system you are using.</span></span>

#### <a name="example"></a><span data-ttu-id="d326a-126">Пример</span><span class="sxs-lookup"><span data-stu-id="d326a-126">Example</span></span>

```powershell
PS> "Hello World!" > Temp:/hello.txt
PS> Get-Content Temp:/hello.txt
Hello World!
```

<span data-ttu-id="d326a-127">Имейте в виду, что исходным системным командам с файлами (например, `ls` в Linux) неизвестно о дисках PSDrive и для них этот диск `Temp:` не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="d326a-127">Be aware that native file commands (like `ls` on Linux) are not aware of PSDrives and won't see this `Temp:` drive.</span></span>

### <a name="abbreviation-expansion"></a><span data-ttu-id="d326a-128">Расширение сокращения</span><span class="sxs-lookup"><span data-stu-id="d326a-128">Abbreviation Expansion</span></span>

<span data-ttu-id="d326a-129">Командлеты PowerShell должны иметь описательные существительные.</span><span class="sxs-lookup"><span data-stu-id="d326a-129">PowerShell cmdlets are expected to have descriptive nouns.</span></span> <span data-ttu-id="d326a-130">Из-за этого у них длинные имена, которые сложнее вводить.</span><span class="sxs-lookup"><span data-stu-id="d326a-130">This results in long names that are more difficult to type.</span></span> <span data-ttu-id="d326a-131">Эта возможность позволяет вам просто вводить командлет прописными символами и использовать заполнение нажатием клавиши TAB для поиска совпадений.</span><span class="sxs-lookup"><span data-stu-id="d326a-131">This feature allows you to just type the uppercase characters of the cmdlet and use tab-completion to find a match.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSUseAbbreviationExpansion
```

#### <a name="example"></a><span data-ttu-id="d326a-132">Пример</span><span class="sxs-lookup"><span data-stu-id="d326a-132">Example</span></span>

```powershell
PS> i-arsavsf
```

<span data-ttu-id="d326a-133">Если вы нажмете клавишу TAB при наличии установленного модуля Azure PowerShell [Az](https://www.powershellgallery.com/packages/Az), автоматически подставится такое:</span><span class="sxs-lookup"><span data-stu-id="d326a-133">If you hit tab, and have the Azure PowerShell [Az](https://www.powershellgallery.com/packages/Az) module installed, it will autocomplete to:</span></span>

```Output
PS> Import-AzRecoveryServicesAsrVaultSettingsFile
```

> [!NOTE]
> <span data-ttu-id="d326a-134">Эта возможность предназначена для интерактивного использования.</span><span class="sxs-lookup"><span data-stu-id="d326a-134">This feature is intended to be used interactively.</span></span> <span data-ttu-id="d326a-135">Сокращенные формы командлетов выполнить невозможно.</span><span class="sxs-lookup"><span data-stu-id="d326a-135">Abbreviated forms of cmdlets can't be executed.</span></span>
> <span data-ttu-id="d326a-136">Эта возможность не используется в качестве замены псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="d326a-136">This feature is not a replacement for aliases.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="d326a-137">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="d326a-137">Breaking Changes</span></span>

- <span data-ttu-id="d326a-138">Поведение командлета `-NoEnumerate` в `Write-Output` исправлено для согласованности с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d326a-138">Fix `-NoEnumerate` behavior in `Write-Output` to be consistent with Windows PowerShell.</span></span> <span data-ttu-id="d326a-139">(№ 9069)</span><span class="sxs-lookup"><span data-stu-id="d326a-139">(#9069)</span></span>
- <span data-ttu-id="d326a-140">Результат `Join-String -InputObject 1,2,3` стал равным результату `1,2,3 | Join-String` (№ 8611). (Выражаем благодарность @sethvs.)</span><span class="sxs-lookup"><span data-stu-id="d326a-140">Make `Join-String -InputObject 1,2,3` result equal to `1,2,3 | Join-String` result (#8611) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="d326a-141">К командлету `Sort-Object` и связанным тестам добавлен параметр `-Stable` к (№ 7862). (Выражаем благодарность @KirkMunro.)</span><span class="sxs-lookup"><span data-stu-id="d326a-141">Add `-Stable` to `Sort-Object` and related tests (#7862) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="d326a-142">Командлет `Start-Sleep` улучшен для принятия долей секунд (№ 8537). (Выражаем благодарность @Prototyyppi.)</span><span class="sxs-lookup"><span data-stu-id="d326a-142">Improve `Start-Sleep` cmdlet to accept fractional seconds (#8537) (Thanks @Prototyyppi!)</span></span>
- <span data-ttu-id="d326a-143">Хэш-таблица изменена для использования параметра OrdinalIgnoreCase со значением `case-insensitive` на всех языках (№ 8566).</span><span class="sxs-lookup"><span data-stu-id="d326a-143">Change hashtable to use OrdinalIgnoreCase to be `case-insensitive` in all Cultures (#8566)</span></span>
- <span data-ttu-id="d326a-144">Параметр **LiteralPath** в командлете `Import-Csv` теперь привязан к выходным данным `Get-ChildItem` (№ 8277). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-144">Fix **LiteralPath** in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-145">Столбец без имени больше не пропускается, если в командлете `Import-Csv` используется разделитель двойными кавычками (№ 7899). (Выражаем благодарность @Topping.)</span><span class="sxs-lookup"><span data-stu-id="d326a-145">No longer skips a column without name if double quote delimiter is used in `Import-Csv` (#7899) (Thanks @Topping!)</span></span>
- <span data-ttu-id="d326a-146">Командлет `Get-ExperimentalFeature` больше не имеет параметр `-ListAvailable` (№ 8318).</span><span class="sxs-lookup"><span data-stu-id="d326a-146">`Get-ExperimentalFeature` no longer has `-ListAvailable` switch (#8318)</span></span>
- <span data-ttu-id="d326a-147">Параметр Debug теперь задает значение **Continue** вместо **Inquire** для переменной `$DebugPreference` (№ 8195). (Выражаем благодарность @KirkMunro.)</span><span class="sxs-lookup"><span data-stu-id="d326a-147">Debug parameter now sets `$DebugPreference` to **Continue** instead of **Inquire** (#8195) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="d326a-148">Параметр `-OutputFormat` учитывается, если указан в неинтерактивной, перенаправленной, закодированной команде, используемой с pwsh (№ 8115).</span><span class="sxs-lookup"><span data-stu-id="d326a-148">Honor `-OutputFormat` if specified in non-interactive, redirected, encoded command used with pwsh (#8115)</span></span>
- <span data-ttu-id="d326a-149">Сборка загружается из базового пути к модулю перед попыткой загрузить из глобального кэша сборок (№ 8073).</span><span class="sxs-lookup"><span data-stu-id="d326a-149">Load assembly from module base path before trying to load from the GAC (#8073)</span></span>
- <span data-ttu-id="d326a-150">Удалена тильда из предварительной версии пакетов Linux (№ 8244).</span><span class="sxs-lookup"><span data-stu-id="d326a-150">Remove tilde from Linux preview packages (#8244)</span></span>
- <span data-ttu-id="d326a-151">Обработка `-WorkingDirectory` теперь выполняется перед обработкой профилей (№ 8079).</span><span class="sxs-lookup"><span data-stu-id="d326a-151">Move processing of `-WorkingDirectory` before processing of profiles (#8079)</span></span>
- <span data-ttu-id="d326a-152">Переменная среды `PATHEXT` не добавлена в Unix (№ 7697). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-152">Do not add `PATHEXT` environment variable on Unix (#7697) (Thanks @iSazonov!)</span></span>

## <a name="known-issues"></a><span data-ttu-id="d326a-153">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="d326a-153">Known Issues</span></span>

- <span data-ttu-id="d326a-154">При удаленном взаимодействии на платформах ARM Windows IоT возникает проблема с загрузкой модулей.</span><span class="sxs-lookup"><span data-stu-id="d326a-154">Remoting on Windows IOT ARM platforms has an issue loading modules.</span></span> <span data-ttu-id="d326a-155">См. № 8053.</span><span class="sxs-lookup"><span data-stu-id="d326a-155">See (#8053)</span></span>

## <a name="general-updates-and-fixes"></a><span data-ttu-id="d326a-156">Общие обновления и исправления</span><span class="sxs-lookup"><span data-stu-id="d326a-156">General Updates and Fixes</span></span>

- <span data-ttu-id="d326a-157">Разрешено заполнение нажатием клавиши TAB без учета регистра для файлов и папок в файловой системе с учетом регистра (№ 8128).</span><span class="sxs-lookup"><span data-stu-id="d326a-157">Enable case-insensitive tab completion for files and folders on case-sensitive filesystem (#8128)</span></span>
- <span data-ttu-id="d326a-158">PSVersionInfo.PSVersion и PSVersionInfo.PSEdition стали общедоступными (№ 8054). (Выражаем благодарность @KirkMunro.)</span><span class="sxs-lookup"><span data-stu-id="d326a-158">Make PSVersionInfo.PSVersion and PSVersionInfo.PSEdition public (#8054) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="d326a-159">Добавлено определение типа для `$_` / `$PSItem` в блоках `catch{ }` (№ 8020). (Выражаем благодарность @vexx32.)</span><span class="sxs-lookup"><span data-stu-id="d326a-159">Add Type Inference for `$_` / `$PSItem` in `catch{ }` blocks (#8020) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="d326a-160">Исправлено определение типа вызова статического метода (№ 8018). (Выражаем благодарность @SeeminglyScience.)</span><span class="sxs-lookup"><span data-stu-id="d326a-160">Fix static method invocation type inference (#8018) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="d326a-161">Созданы выводимые типы для `Select-Object`, `Group-Object`, **PSObject** и **Hashtable** (№ 7231). (Выражаем благодарность @powercode.)</span><span class="sxs-lookup"><span data-stu-id="d326a-161">Create inferred types for `Select-Object`, `Group-Object`, **PSObject** and **Hashtable** (#7231) (Thanks @powercode!)</span></span>
- <span data-ttu-id="d326a-162">Предоставлена поддержка вызова метода с параметрами типа `ByRef-like` (№ 7721).</span><span class="sxs-lookup"><span data-stu-id="d326a-162">Support calling method with `ByRef-like` type parameters (#7721)</span></span>
- <span data-ttu-id="d326a-163">Добавлена обработка случая, когда путь к модулю Windows PowerShell уже находится в PSModulePath среды (№ 7727).</span><span class="sxs-lookup"><span data-stu-id="d326a-163">Handle the case where the Windows PowerShell module path is already in the environment's PSModulePath (#7727)</span></span>
- <span data-ttu-id="d326a-164">Включены командлеты `SecureString` для отличающихся от Windows продуктов с сохранением обычного текста (№ 9199).</span><span class="sxs-lookup"><span data-stu-id="d326a-164">Enable `SecureString` cmdlets for non-Windows by storing the plain text (#9199)</span></span>
- <span data-ttu-id="d326a-165">Улучшено сообщение об ошибке в отличающихся от Windows продуктах при импорте CLIXML-файла с использованием securestring (№ 7997).</span><span class="sxs-lookup"><span data-stu-id="d326a-165">Improve error message on non-Windows when importing clixml with securestring (#7997)</span></span>
- <span data-ttu-id="d326a-166">Добавлен параметр ReplyTo в командлет `Send-MailMessage` (№ 8727). (Выражаем благодарность @replicaJunction.)</span><span class="sxs-lookup"><span data-stu-id="d326a-166">Adding parameter ReplyTo to `Send-MailMessage` (#8727) (Thanks @replicaJunction!)</span></span>
- <span data-ttu-id="d326a-167">Добавлено сообщение об устаревшем объекте для параметра `Send-MailMessage` (№ 9178).</span><span class="sxs-lookup"><span data-stu-id="d326a-167">Add Obsolete message to `Send-MailMessage` (#9178)</span></span>
- <span data-ttu-id="d326a-168">Исправлена ошибка с командлетом `Restart-Computer`: теперь он работает с `localhost` при отсутствии WinRM (№ 9160).</span><span class="sxs-lookup"><span data-stu-id="d326a-168">Fix `Restart-Computer` to work on `localhost` when WinRM is not present (#9160)</span></span>
- <span data-ttu-id="d326a-169">Теперь командлет `Start-Job` возвращает критическую ошибку при размещении PowerShell (№ 9128).</span><span class="sxs-lookup"><span data-stu-id="d326a-169">Make `Start-Job` throw terminating error when PowerShell is being hosted (#9128)</span></span>
- <span data-ttu-id="d326a-170">Добавлены ускорители типов стиля C# и суффиксы для литералов ushort, uint, ulong и short (№ 7813). (Выражаем благодарность @vexx32.)</span><span class="sxs-lookup"><span data-stu-id="d326a-170">Add C# style type accelerators and suffixes for ushort, uint, ulong, and short literals (#7813) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="d326a-171">Добавлены новые суффиксы для числовых литералов (№ 7901). См. [сведения о числовых литералах][]. (Выражаем благодарность @vexx32.)</span><span class="sxs-lookup"><span data-stu-id="d326a-171">Added new suffixes for numeric literals - see [about_Numeric_Literals][] (#7901) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="d326a-172">Теперь уровень влияния правильно сообщается, когда для параметра SupportsShouldProcess не установлено значение true (№ 8209). (Выражаем благодарность @vexx32.)</span><span class="sxs-lookup"><span data-stu-id="d326a-172">Correctly Report impact level when SupportsShouldProcess is not set to 'true' (#8209) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="d326a-173">Исправлены проблемы с кодировкой запросов в веб-командлетах (№ 8742). (Выражаем благодарность @markekraus.)</span><span class="sxs-lookup"><span data-stu-id="d326a-173">Fix Request Charset Issues in Web Cmdlets (#8742) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="d326a-174">Исправлена проблема с ожиданием `100-continue` для веб-командлетов (№ 8679). (Выражаем благодарность @markekraus.)</span><span class="sxs-lookup"><span data-stu-id="d326a-174">Fix Expect `100-continue` issue with Web Cmdlets (#8679) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="d326a-175">Исправлена проблема блокировки файла для веб-командлетов (№ 7676.) (Выражаем благодарность @Claustn.)</span><span class="sxs-lookup"><span data-stu-id="d326a-175">Fix file blocking issue with web cmdlets (#7676) (Thanks @Claustn!)</span></span>
- <span data-ttu-id="d326a-176">Исправлена проблема с анализом кодовой страницы в `Invoke-RestMethod` (№ 8694). (Выражаем благодарность @markekraus.)</span><span class="sxs-lookup"><span data-stu-id="d326a-176">Fix code page parsing issue in `Invoke-RestMethod` (#8694) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="d326a-177">Выполнен рефакторинг командлета `ConvertTo-Json` для предоставления JsonObject.ConvertToJson в качестве общедоступного API (№ 8682).</span><span class="sxs-lookup"><span data-stu-id="d326a-177">Refactor `ConvertTo-Json` to expose JsonObject.ConvertToJson as a public API (#8682)</span></span>
- <span data-ttu-id="d326a-178">Добавлена настраиваемая максимальная глубина в командлете `ConvertFrom-Json` с помощью параметра -Depth (№ 8199). (Выражаем благодарность @louistio).</span><span class="sxs-lookup"><span data-stu-id="d326a-178">Add configurable maximum depth in `ConvertFrom-Json` with -Depth (#8199) (Thanks @louistio!)</span></span>
- <span data-ttu-id="d326a-179">Добавлен параметр EscapeHandling в командлет `ConvertTo-Json` (№ 7775). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-179">Add EscapeHandling parameter in `ConvertTo-Json` cmdlet (#7775) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-180">Добавлен параметр `-CustomPipeName` в pwsh и `Enter-PSHostProcess` (№ 8889).</span><span class="sxs-lookup"><span data-stu-id="d326a-180">Add `-CustomPipeName` to pwsh and `Enter-PSHostProcess` (#8889)</span></span>
- <span data-ttu-id="d326a-181">Добавлена возможность создания относительных символических ссылок в Windows с помощью `New-Item` (№ 8783).</span><span class="sxs-lookup"><span data-stu-id="d326a-181">Enable creating relative symbolic links on Windows with `New-Item` (#8783)</span></span>
- <span data-ttu-id="d326a-182">Пользователям Windows разрешено в режиме разработчика создавать символические ссылки без повышения прав (№ 8534).</span><span class="sxs-lookup"><span data-stu-id="d326a-182">Allow Windows users in developer mode to create symlinks without elevation (#8534)</span></span>
- <span data-ttu-id="d326a-183">Теперь командлет `Write-Information` принимает `$null` (№ 8774).</span><span class="sxs-lookup"><span data-stu-id="d326a-183">Enable `Write-Information` to accept `$null` (#8774)</span></span>
- <span data-ttu-id="d326a-184">Командлет `Get-Help` исправлен для расширенных функций с содержимым справки MAML (№ 8353).</span><span class="sxs-lookup"><span data-stu-id="d326a-184">Fix `Get-Help` for advanced functions with MAML help content (#8353)</span></span>
- <span data-ttu-id="d326a-185">Исправлена проблема PSTypeName `Get-Help` с -Parameter, когда объявлялся только один параметр (№ 8754). (Выражаем благодарность @pougetat.)</span><span class="sxs-lookup"><span data-stu-id="d326a-185">Fix `Get-Help` PSTypeName issue with -Parameter when only one parameter is declared (#8754) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="d326a-186">Исправлено вычисление токена для командлета `Get-Help`, выполненного в ScriptBlock для справки в комментариях</span><span class="sxs-lookup"><span data-stu-id="d326a-186">Token calculation fix for `Get-Help` executed on ScriptBlock for comment help.</span></span> <span data-ttu-id="d326a-187">(№ 8238). (Выражаем благодарность @hubuk.)</span><span class="sxs-lookup"><span data-stu-id="d326a-187">(#8238) (Thanks @hubuk!)</span></span>
- <span data-ttu-id="d326a-188">Изменен параметр -Parameter командлета `Get-Help` для принятия строкового массива (№ 8454). (Выражаем благодарность @sethvs.)</span><span class="sxs-lookup"><span data-stu-id="d326a-188">Change `Get-Help` cmdlet -Parameter parameter so it accepts string arrays (#8454) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="d326a-189">Теперь PAGER разрешается, если его путь содержит пробелы (№ 8571). (Выражаем благодарность @pougetat.)</span><span class="sxs-lookup"><span data-stu-id="d326a-189">Resolve PAGER if its path contains spaces (#8571) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="d326a-190">Добавлен запрос при использовании `less` в функции help, чтобы указать пользователю, как выйти (№ 7998).</span><span class="sxs-lookup"><span data-stu-id="d326a-190">Add prompt to the use of `less` in the function 'help' to instruct user how to quit (#7998)</span></span>
- <span data-ttu-id="d326a-191">Добавлено перечисление поддержки и типы char в командлете `Format-Hex` (№ 8191). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-191">Add support enum and char types in `Format-Hex` cmdlet (#8191) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-192">Удален параметр ShouldProcess из командлета `Format-Hex` (№ 8178).</span><span class="sxs-lookup"><span data-stu-id="d326a-192">Remove ShouldProcess from `Format-Hex` (#8178)</span></span>
- <span data-ttu-id="d326a-193">Добавлены новые параметры Offset и Count в командлет `Format-Hex` и выполнен его рефакторинг (№ 7877). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-193">Add new Offset and Count parameters to `Format-Hex` and refactor the cmdlet (#7877) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-194">Атрибут name разрешен в качестве ключа псевдонима для label в командлете `ConvertTo-Html`, и запись width может быть целым числом (№ 8426). (Выражаем благодарность @mklement0.)</span><span class="sxs-lookup"><span data-stu-id="d326a-194">Allow 'name' as an alias key for 'label' in `ConvertTo-Html`, allow the 'width' entry to be an integer (#8426) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="d326a-195">Вычисляемые свойства на основе ScriptBlock снова работают в командлете `ConvertTo-Html` (№ 8427). (Выражаем благодарность @mklement0.)</span><span class="sxs-lookup"><span data-stu-id="d326a-195">Make scriptblock based calculated properties work again in `ConvertTo-Html` (#8427) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="d326a-196">Добавлен командлет `Join-String` для создания текста из входных данных конвейера (№ 7660.) (Выражаем благодарность @powercode.)</span><span class="sxs-lookup"><span data-stu-id="d326a-196">Add cmdlet `Join-String` for creating text from pipeline input (#7660) (Thanks @powercode!)</span></span>
- <span data-ttu-id="d326a-197">Исправлена логика параметра FormatString командлета `Join-String` (№ 8449). (Выражаем благодарность @sethvs.)</span><span class="sxs-lookup"><span data-stu-id="d326a-197">Fix `Join-String` cmdlet FormatString parameter logic (#8449) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="d326a-198">Функция `Clear-Host` снова использует `$RAWUI` и работает через удаленное взаимодействие (№ 8609).</span><span class="sxs-lookup"><span data-stu-id="d326a-198">Change `Clear-Host` back to using `$RAWUI` and clear to work over remoting (#8609)</span></span>
- <span data-ttu-id="d326a-199">Название функции `Clear-Host` изменено на простое имя `[console]::clear`, и псевдоним clear удален из Unix (№ 8603).</span><span class="sxs-lookup"><span data-stu-id="d326a-199">Change `Clear-Host` to simply called `[console]::clear` and remove clear alias from Unix (#8603)</span></span>
- <span data-ttu-id="d326a-200">Параметр LiteralPath в командлете `Import-Csv` теперь привязан к выходным данным `Get-ChildItem` (№ 8277). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-200">Fix LiteralPath in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-201">Функция справки не должна использовать пейджер для AliasHelpInfo (№ 8552).</span><span class="sxs-lookup"><span data-stu-id="d326a-201">help function shouldn't use pager for AliasHelpInfo (#8552)</span></span>
- <span data-ttu-id="d326a-202">В командлет `Start-Transcript` добавлен параметр `-UseMinimalHeader`, чтобы свернуть заголовок записи (№ 8402). (выражаем благодарность @lukexjeremy.)</span><span class="sxs-lookup"><span data-stu-id="d326a-202">Add `-UseMinimalHeader` to `Start-Transcript` to minimize transcript header (#8402) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="d326a-203">Добавлены командлеты `Enable-ExperimentalFeature` и `Disable-ExperimentalFeature` (№ 8318).</span><span class="sxs-lookup"><span data-stu-id="d326a-203">Add `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature` cmdlets (#8318)</span></span>
- <span data-ttu-id="d326a-204">Теперь все командлеты из **PSDiagnostics** предоставлены, если доступно средство logman.exe (№ 8366).</span><span class="sxs-lookup"><span data-stu-id="d326a-204">Expose all cmdlets from **PSDiagnostics** if logman.exe is available (#8366)</span></span>
- <span data-ttu-id="d326a-205">Удален параметр **Persist** из командлета `New-PSDrive` на платформе `non-Windows` (№ 8291.) (Выражаем благодарность @lukexjeremy.)</span><span class="sxs-lookup"><span data-stu-id="d326a-205">Remove **Persist** parameter from `New-PSDrive` on `non-Windows` platform (#8291) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="d326a-206">Добавлена поддержка для `cd +` (№ 7206). (Выражаем благодарность @bergmeister.)</span><span class="sxs-lookup"><span data-stu-id="d326a-206">Add support for `cd +` (#7206) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="d326a-207">Теперь `Set-Location -LiteralPath` работает с папками с именами "-" и "+" (№ 8089).</span><span class="sxs-lookup"><span data-stu-id="d326a-207">Enable `Set-Location -LiteralPath` to work with folders named - and + (#8089)</span></span>
- <span data-ttu-id="d326a-208">`Test-Path` возвращает значение `$false`, когда дано пустое значение пути или `$null` (№ 8080). (Выражаем благодарность @vexx32.)</span><span class="sxs-lookup"><span data-stu-id="d326a-208">`Test-Path` returns `$false` when given an empty or `$null` path value (#8080) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="d326a-209">Разрешен возврат динамического параметра, даже если путь не соответствует ни одному поставщику (№ 7957).</span><span class="sxs-lookup"><span data-stu-id="d326a-209">Allow dynamic parameter to be returned even if path does not match any provider (#7957)</span></span>
- <span data-ttu-id="d326a-210">Предоставлена поддержка командлетов `Get-PSHostProcessInfo` и `Enter-PSHostProcess` на платформах Unix (№ 8232).</span><span class="sxs-lookup"><span data-stu-id="d326a-210">Support `Get-PSHostProcessInfo` and `Enter-PSHostProcess` on Unix platforms (#8232)</span></span>
- <span data-ttu-id="d326a-211">Уменьшено количество выделений в командлете `Get-Content` (№ 8103). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-211">Reduce allocations in `Get-Content` cmdlet (#8103) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-212">Теперь командлет `Add-Content` предоставляет общий доступ на чтение другим инструментам во время записи содержимого (№ 8091).</span><span class="sxs-lookup"><span data-stu-id="d326a-212">Enable `Add-Content` to share read access with other tools while writing content (#8091)</span></span>
- <span data-ttu-id="d326a-213">`Get/Add-Content` выдает улучшенную ошибку при выборе контейнера (№ 7823). (Выражаем благодарность @kvprasoon.)</span><span class="sxs-lookup"><span data-stu-id="d326a-213">`Get/Add-Content` throws improved error when targeting a container (#7823) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="d326a-214">Добавлены параметры `-Name`, `-NoUserOverrides` и `-ListAvailable` в командлет `Get-Culture` (№ 7702). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-214">Add `-Name`, `-NoUserOverrides` and `-ListAvailable` parameters to `Get-Culture` cmdlet (#7702) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-215">Добавлен унифицированный атрибут для завершения для параметра **Encoding**</span><span class="sxs-lookup"><span data-stu-id="d326a-215">Add unified attribute for completion for **Encoding** parameter.</span></span> <span data-ttu-id="d326a-216">(№ 7732). (Выражаем благодарность @ThreeFive-O.)</span><span class="sxs-lookup"><span data-stu-id="d326a-216">(#7732) (Thanks @ThreeFive-O!)</span></span>
- <span data-ttu-id="d326a-217">Разрешены числовые ИД и имя зарегистрированных кодовых страниц в параметрах **Encoding** (№ 7636). (Выражаем благодарность @iSazonov.)</span><span class="sxs-lookup"><span data-stu-id="d326a-217">Allow numeric Ids and name of registered code pages in **Encoding** parameters (#7636) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="d326a-218">Исправлен `Rename-Item -Path` с использованием подстановочного знака char (№ 7398). (Выражаем благодарность @kwkam.)</span><span class="sxs-lookup"><span data-stu-id="d326a-218">Fix `Rename-Item -Path` with wildcard char (#7398) (Thanks @kwkam!)</span></span>
- <span data-ttu-id="d326a-219">Когда командлет `Start-Transcript` применяется при существовании файла, используется пустой файл, а не удаление (№ 8131). (Выражаем благодарность @paalbra.)</span><span class="sxs-lookup"><span data-stu-id="d326a-219">When using `Start-Transcript` and file exists, empty file rather than deleting (#8131) (Thanks @paalbra!)</span></span>
- <span data-ttu-id="d326a-220">Командлет `Add-Type` явно открывает исходные файлы с доступом **FileAccess.Read** и **FileShare.Read** (№ 7915). (Выражаем благодарность @IISResetMe.)</span><span class="sxs-lookup"><span data-stu-id="d326a-220">Make `Add-Type` open source files with **FileAccess.Read** and **FileShare.Read** explicitly (#7915) (Thanks @IISResetMe!)</span></span>
- <span data-ttu-id="d326a-221">Исправлена команда `Enter-PSSession -ContainerId` для последней версии Windows (№ 7883).</span><span class="sxs-lookup"><span data-stu-id="d326a-221">Fix `Enter-PSSession -ContainerId` for the latest Windows (#7883)</span></span>
- <span data-ttu-id="d326a-222">Теперь командлет `Test-ModuleManifest` заполняет свойство **NestedModules** (№ 7859).</span><span class="sxs-lookup"><span data-stu-id="d326a-222">Ensure **NestedModules** property gets populated by `Test-ModuleManifest` (#7859)</span></span>
- <span data-ttu-id="d326a-223">Добавлено условие `%F` к `Get-Date` -UFormat (№ 7630). (Выражаем благодарность @britishben.)</span><span class="sxs-lookup"><span data-stu-id="d326a-223">Add `%F` case to `Get-Date` -UFormat (#7630) (Thanks @britishben!)</span></span>
- <span data-ttu-id="d326a-224">Командлет `Set-Service -Status Stopped` исправлен для остановки служб с зависимостями (№ 5525). (Выражаем благодарность @zhenggu.)</span><span class="sxs-lookup"><span data-stu-id="d326a-224">Fix `Set-Service -Status Stopped` to stop services with dependencies (#5525) (Thanks @zhenggu!)</span></span>

<!-- Link references -->
[Сведения о числовых литералах]: /powershell/module/Microsoft.PowerShell.Core/About/about_numeric_literals
[about_Numeric_Literals]: /powershell/module/Microsoft.PowerShell.Core/About/about_numeric_literals
[Экспериментальные возможности]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[Experimental Features]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[PSDrive]: /powershell/module/microsoft.powershell.management/new-psdrive
