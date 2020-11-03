---
description: Описание параметров групповая политика для PowerShell
keywords: powershell,командлет
Locale: en-US
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: df2a3e9349dd3afbe621bd11b92ac5cdf552492a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231114"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="648da-104">Сведения о параметрах групповая политика</span><span class="sxs-lookup"><span data-stu-id="648da-104">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="648da-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="648da-105">Short description</span></span>
<span data-ttu-id="648da-106">Описание параметров групповая политика для PowerShell</span><span class="sxs-lookup"><span data-stu-id="648da-106">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="648da-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="648da-107">Long description</span></span>

<span data-ttu-id="648da-108">В PowerShell имеются групповая политика параметры, помогающие определить единообразные значения конфигурации для компьютеров Windows в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="648da-108">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="648da-109">Параметры групповая политика PowerShell находятся в следующих групповая политика путях:</span><span class="sxs-lookup"><span data-stu-id="648da-109">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    PowerShell Core

User Configuration\
  Administrative Templates\
    PowerShell Core
```

<span data-ttu-id="648da-110">Параметры групповой политики в пути конфигурации пользователя имеют приоритет над параметрами групповая политика в пути конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="648da-110">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="648da-111">В PowerShell 7 предусмотрены шаблоны групповой политики и скрипт установки в `$PSHOME`.</span><span class="sxs-lookup"><span data-stu-id="648da-111">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="648da-112">Инструменты групповой политики используют файлы административных шаблонов (с расширениями `.admx`, `.adml`) для заполнения параметров политики в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="648da-112">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="648da-113">Это позволяет администраторам управлять параметрами политики на основе реестра.</span><span class="sxs-lookup"><span data-stu-id="648da-113">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="648da-114">`InstallPSCorePolicyDefinitions.ps1`Сценарий устанавливает **PowerShell Core административные шаблоны** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="648da-114">The `InstallPSCorePolicyDefinitions.ps1` script installs **PowerShell Core Administrative Templates** on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode       LastWriteTime         Length Name
----       -------------         ------ ----
-a---      2/27/2020 12:38 AM     15861 InstallPSCorePolicyDefinitions.ps1
-a---      2/27/2020 12:28 AM      9675 PowerShellCoreExecutionPolicy.adml
-a---      2/27/2020 12:28 AM      6201 PowerShellCoreExecutionPolicy.admx
```

<span data-ttu-id="648da-115">После установки шаблонов эти параметры можно изменить в редакторе групповая политика ( `gpedit.msc` ).</span><span class="sxs-lookup"><span data-stu-id="648da-115">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="648da-116">Существуют следующие политики.</span><span class="sxs-lookup"><span data-stu-id="648da-116">The policies are as follows:</span></span>

- <span data-ttu-id="648da-117">Конфигурация сеанса консоли — задает конечную точку конфигурации, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="648da-117">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="648da-118">Включить ведение журнала модуля: задает свойство **LogPipelineExecutionDetails** модулей.</span><span class="sxs-lookup"><span data-stu-id="648da-118">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="648da-119">"Включить регистрацию блоков сценариев PowerShell" — включает подробное ведение журнала всех скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="648da-119">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="648da-120">"Включить выполнение сценариев" — задает политику выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="648da-120">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="648da-121">"Включить транскрипции PowerShell" — включает запись входных и выходных данных команд PowerShell в виде текстовых расшифровок</span><span class="sxs-lookup"><span data-stu-id="648da-121">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="648da-122">Задайте исходный путь по умолчанию для `Update-Help` : задает для обновляемой справки каталог, а не Интернет.</span><span class="sxs-lookup"><span data-stu-id="648da-122">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="648da-123">Каждый параметр групповая политика PowerShell имеет параметр ("использовать параметр политики Windows PowerShell") для использования значения из аналогичного параметра групповая политика Windows PowerShell, расположенного по следующим групповая политика путям:</span><span class="sxs-lookup"><span data-stu-id="648da-123">Each PowerShell Group Policy setting has an option ('Use Windows PowerShell Policy setting' field) to use the value from a similar Windows PowerShell Group Policy setting that is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

> [!NOTE]
> <span data-ttu-id="648da-124">Эти **Административные шаблоны PowerShell Core** не включают параметры для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="648da-124">These **PowerShell Core Administrative Templates** do not include settings for Windows PowerShell.</span></span> <span data-ttu-id="648da-125">Дополнительные сведения о получении других шаблонов и настройке групповой политики см. в статье [Создание центрального хранилища для групповая политика административные шаблоны в Windows и управление им][gpstore].</span><span class="sxs-lookup"><span data-stu-id="648da-125">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="console-session-configuration"></a><span data-ttu-id="648da-126">Конфигурация сеанса консоли</span><span class="sxs-lookup"><span data-stu-id="648da-126">Console session configuration</span></span>

<span data-ttu-id="648da-127">Параметр политики **конфигурации сеанса консоли** задает конечную точку конфигурации, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="648da-127">The **Console session configuration** policy setting specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="648da-128">Это может быть любая конечная точка, зарегистрированная на локальном компьютере, включая конечные точки удаленного взаимодействия PowerShell по умолчанию или пользовательскую конечную точку с конкретными возможностями роли пользователя.</span><span class="sxs-lookup"><span data-stu-id="648da-128">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="648da-129">Включить ведение журнала модуля</span><span class="sxs-lookup"><span data-stu-id="648da-129">Turn on module logging</span></span>

<span data-ttu-id="648da-130">Параметр политики **включить ведение журнала модуля** включает ведение журнала для выбранных модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="648da-130">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="648da-131">Этот параметр действует во всех сеансах на всех затронутых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="648da-131">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="648da-132">Если включить этот параметр политики и указать один или несколько модулей, события выполнения конвейера для указанных модулей записываются в журнал Windows PowerShell в Просмотр событий.</span><span class="sxs-lookup"><span data-stu-id="648da-132">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="648da-133">Если отключить этот параметр политики, ведение журнала событий выполнения будет отключено для всех модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="648da-133">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="648da-134">Если этот параметр политики не настроен, свойство **LogPipelineExecutionDetails** каждого модуля определяет, регистрируются ли события выполнения модуля.</span><span class="sxs-lookup"><span data-stu-id="648da-134">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="648da-135">По умолчанию свойство **LogPipelineExecutionDetails** всех модулей имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="648da-135">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="648da-136">Чтобы включить ведение журнала модуля для модуля, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="648da-136">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="648da-137">Модуль должен быть импортирован в сеанс, и параметр действует только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="648da-137">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="648da-138">Чтобы включить ведение журнала модуля для всех сеансов на определенном компьютере, добавьте предыдущие команды в профиль PowerShell "все пользователи ( `$Profile.AllUsersAllHosts` )".</span><span class="sxs-lookup"><span data-stu-id="648da-138">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="648da-139">Дополнительные сведения о ведении журнала модулей см. в разделе [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="648da-139">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="648da-140">Включить ведение журнала блоков сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="648da-140">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="648da-141">Параметр политики **включить ведение журнала блока сценариев PowerShell** включает ведение журнала всех входных данных сценария PowerShell в журнал событий Microsoft-Windows-PowerShell/операционный.</span><span class="sxs-lookup"><span data-stu-id="648da-141">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="648da-142">Если этот параметр политики включен, PowerShell Core будет записывать в журнал обработку команд, блоков скриптов, функций и сценариев, которые будут вызываться в интерактивном режиме или с помощью службы автоматизации.</span><span class="sxs-lookup"><span data-stu-id="648da-142">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="648da-143">Если этот параметр политики отключен, регистрация ввода сценариев PowerShell отключена.</span><span class="sxs-lookup"><span data-stu-id="648da-143">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="648da-144">Если регистрация вызова блоков сценариев включена, PowerShell также регистрирует события при запуске или остановке вызова команд, блоков сценариев, функций или сценариев.</span><span class="sxs-lookup"><span data-stu-id="648da-144">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="648da-145">Включение регистрации вызовов ведет к созданию большого количества журналов событий.</span><span class="sxs-lookup"><span data-stu-id="648da-145">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="648da-146">Включить выполнение скрипта</span><span class="sxs-lookup"><span data-stu-id="648da-146">Turn on script execution</span></span>

<span data-ttu-id="648da-147">Параметр политики **включить выполнение скрипта** задает политику выполнения для компьютеров и пользователей, которые определяют, какие скрипты разрешено запускать.</span><span class="sxs-lookup"><span data-stu-id="648da-147">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="648da-148">При включении параметра политики можно выбрать следующие параметры политики.</span><span class="sxs-lookup"><span data-stu-id="648da-148">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="648da-149">**Разрешение только подписанных скриптов** позволяет выполнять сценарии только в том случае, если они подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="648da-149">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="648da-150">Этот параметр политики эквивалентен политике выполнения AllSigned.</span><span class="sxs-lookup"><span data-stu-id="648da-150">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="648da-151">**Разрешить локальным сценариям и удаленно подписанным сценариям** выполнять все локальные скрипты.</span><span class="sxs-lookup"><span data-stu-id="648da-151">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="648da-152">Сценарии, созданные из Интернета, должны быть подписаны доверенным издателем.</span><span class="sxs-lookup"><span data-stu-id="648da-152">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="648da-153">Этот параметр политики эквивалентен политике выполнения RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="648da-153">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="648da-154">**Разрешить всем сценариям** выполнять все сценарии.</span><span class="sxs-lookup"><span data-stu-id="648da-154">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="648da-155">Этот параметр политики эквивалентен политике неограниченного выполнения.</span><span class="sxs-lookup"><span data-stu-id="648da-155">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="648da-156">Если этот параметр политики отключен, выполнение скриптов запрещено.</span><span class="sxs-lookup"><span data-stu-id="648da-156">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="648da-157">Этот параметр политики эквивалентен политике ограниченного выполнения.</span><span class="sxs-lookup"><span data-stu-id="648da-157">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="648da-158">Если вы отключаете или не настраиваете этот параметр политики, политика выполнения, заданная для компьютера или пользователя `Set-ExecutionPolicy` командлетом, определяет, разрешено ли выполнение скриптов.</span><span class="sxs-lookup"><span data-stu-id="648da-158">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="648da-159">По умолчанию используется значение Restricted.</span><span class="sxs-lookup"><span data-stu-id="648da-159">The default value is Restricted.</span></span>

<span data-ttu-id="648da-160">Подробнее см. в разделе [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="648da-160">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="648da-161">Включить транскрипцию PowerShell</span><span class="sxs-lookup"><span data-stu-id="648da-161">Turn on powershell transcription</span></span>

<span data-ttu-id="648da-162">Параметр политики включить запись в **PowerShell** позволяет записывать входные и выходные данные команд PowerShell Core в текстовые записи.</span><span class="sxs-lookup"><span data-stu-id="648da-162">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="648da-163">Если этот параметр политики включен, PowerShell Core включит ведение журнала регистрации для PowerShell Core и любых других приложений, использующих ядро PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="648da-163">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="648da-164">По умолчанию PowerShell Core будет записывать выходные данные записи в каталог "Мои документы" каждого пользователя с именем файла, включающего "PowerShell_transcript", а также имя компьютера и время запуска.</span><span class="sxs-lookup"><span data-stu-id="648da-164">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="648da-165">Включение этой политики равнозначно вызову командлета Start-Transcript в каждом сеансе PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="648da-165">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="648da-166">Если вы отключаете этот параметр политики, ведение журнала для приложений на основе PowerShell по умолчанию отключено, хотя запись по-прежнему может быть включена с помощью командлета Start-Transcript.</span><span class="sxs-lookup"><span data-stu-id="648da-166">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="648da-167">Если вы используете параметр OutputDirectory, чтобы включить ведение журнала записи в общую папку, ограничьте доступ к этому каталогу, чтобы пользователи не могли просматривать запись других пользователей или компьютеров.</span><span class="sxs-lookup"><span data-stu-id="648da-167">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="648da-168">Задайте путь к источнику по умолчанию для Update-Help</span><span class="sxs-lookup"><span data-stu-id="648da-168">Set the default source path for Update-Help</span></span>

<span data-ttu-id="648da-169">В параметре **задать путь к источнику по умолчанию для параметра политика обновления — Справка** задается значение по умолчанию для параметра **SourcePath** `Update-Help` командлета.</span><span class="sxs-lookup"><span data-stu-id="648da-169">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="648da-170">Этот параметр запрещает пользователям использовать `Update-Help` командлет для скачивания файлов справки из Интернета.</span><span class="sxs-lookup"><span data-stu-id="648da-170">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="648da-171">Этот параметр групповая политика отображается в разделе **Конфигурация компьютера** и **Конфигурация пользователя**.</span><span class="sxs-lookup"><span data-stu-id="648da-171">This Group Policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="648da-172">Однако действует только параметр групповая политика в разделе **Конфигурация компьютера** .</span><span class="sxs-lookup"><span data-stu-id="648da-172">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="648da-173">Параметр групповая политика в разделе **Конфигурация пользователя** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="648da-173">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="648da-174">`Update-Help`Командлет загрузит и установит новейшие файлы справки для модулей PowerShell и установит их на компьютере.</span><span class="sxs-lookup"><span data-stu-id="648da-174">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="648da-175">По умолчанию `Update-Help` скачивает новые файлы справки из расположения в Интернете, указанного модулем.</span><span class="sxs-lookup"><span data-stu-id="648da-175">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="648da-176">Однако с помощью `Save-Help` командлета можно скачать самые новые файлы справки в расположение файловой системы, например в общую сетевую папку, а затем использовать `Update-Help` командлет для получения файлов справки из расположения файловой системы и установки их на компьютер.</span><span class="sxs-lookup"><span data-stu-id="648da-176">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="648da-177">Параметр **SourcePath** `Update-Help` командлета задает расположение файловой системы.</span><span class="sxs-lookup"><span data-stu-id="648da-177">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="648da-178">Указав значение по умолчанию для параметра **SourcePath** , этот групповая политика неявно добавляет параметр **SourcePath** ко всем `Update-Help` командам.</span><span class="sxs-lookup"><span data-stu-id="648da-178">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="648da-179">Пользователи могут переопределить определенное расположение файловой системы, указанное в качестве значения по умолчанию, введя другое расположение файловой системы.</span><span class="sxs-lookup"><span data-stu-id="648da-179">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="648da-180">Но они не могут удалить параметр **SourcePath** из `Update-Help` команды.</span><span class="sxs-lookup"><span data-stu-id="648da-180">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="648da-181">Если этот параметр политики включен, можно указать значение по умолчанию для параметра **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="648da-181">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="648da-182">Введите расположение файловой системы.</span><span class="sxs-lookup"><span data-stu-id="648da-182">Enter a file system location.</span></span>

<span data-ttu-id="648da-183">Если этот параметр политики отключен или не настроен, значение по умолчанию для параметра **SourcePath** `Update-Help` командлета отсутствует.</span><span class="sxs-lookup"><span data-stu-id="648da-183">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="648da-184">Пользователи могут загружать справку из Интернета или из любого расположения файловой системы.</span><span class="sxs-lookup"><span data-stu-id="648da-184">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="648da-185">Дополнительные сведения см. в разделе [about_Updatable_Help](about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="648da-185">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="648da-186">Keywords</span><span class="sxs-lookup"><span data-stu-id="648da-186">Keywords</span></span>

<span data-ttu-id="648da-187">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="648da-187">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="648da-188">См. также статью</span><span class="sxs-lookup"><span data-stu-id="648da-188">See also</span></span>

[<span data-ttu-id="648da-189">RFC основной политики PowerShell</span><span class="sxs-lookup"><span data-stu-id="648da-189">PowerShell Core Policy RFC</span></span>](https://github.com/PowerShell/PowerShell-RFC/blob/master/4-Experimental-Accepted/RFC0041-Policy.md)

[<span data-ttu-id="648da-190">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="648da-190">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="648da-191">about_Modules</span><span class="sxs-lookup"><span data-stu-id="648da-191">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="648da-192">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="648da-192">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="648da-193">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="648da-193">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="648da-194">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="648da-194">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="648da-195">Get-Module</span><span class="sxs-lookup"><span data-stu-id="648da-195">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="648da-196">Update-Help</span><span class="sxs-lookup"><span data-stu-id="648da-196">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="648da-197">Save-Help</span><span class="sxs-lookup"><span data-stu-id="648da-197">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759

