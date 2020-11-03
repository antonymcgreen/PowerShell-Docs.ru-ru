---
description: Файлы конфигурации для PowerShell Core, замена конфигурации реестра.
keywords: powershell
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: e1eabd71dde71f0191ca8bb991b5bee8f615c312
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231354"
---
# <a name="about-powershell-config"></a><span data-ttu-id="2ac27-104">О конфигурации PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ac27-104">About PowerShell Config</span></span>

## <a name="short-description"></a><span data-ttu-id="2ac27-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="2ac27-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2ac27-106">Файлы конфигурации для PowerShell Core, замена конфигурации реестра.</span><span class="sxs-lookup"><span data-stu-id="2ac27-106">Configuration files for PowerShell Core, replacing Registry configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="2ac27-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="2ac27-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2ac27-108">`powershell.config.json`Файл содержит параметры конфигурации для PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="2ac27-108">The `powershell.config.json` file contains configuration settings for PowerShell Core.</span></span> <span data-ttu-id="2ac27-109">PowerShell загружает эту конфигурацию при запуске.</span><span class="sxs-lookup"><span data-stu-id="2ac27-109">PowerShell loads this configuration at startup.</span></span> <span data-ttu-id="2ac27-110">Параметры также можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2ac27-110">The settings can also be modified at runtime.</span></span> <span data-ttu-id="2ac27-111">Ранее эти параметры хранились в реестре Windows для PowerShell, но теперь содержатся в файле для включения настройки в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2ac27-111">Previously, these settings were stored in the Windows Registry for PowerShell, but are now contained in a file to enable configuration on macOS and Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="2ac27-112">Если `powershell.config.json` файл содержит недопустимый JSON PowerShell, невозможно запустить интерактивный сеанс.</span><span class="sxs-lookup"><span data-stu-id="2ac27-112">If the `powershell.config.json` file contains invalid JSON PowerShell cannot start an interactive session.</span></span>
> <span data-ttu-id="2ac27-113">В этом случае необходимо исправить файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2ac27-113">If this occurs, you must fix the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac27-114">Нераспознанные ключи или недопустимые значения в файле конфигурации будут игнорироваться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="2ac27-114">Unrecognized keys or invalid values in the configuration file will be silently ignored.</span></span>

### <a name="allusers-shared-configuration"></a><span data-ttu-id="2ac27-115">Конфигурация AllUsers (общая)</span><span class="sxs-lookup"><span data-stu-id="2ac27-115">AllUsers (shared) configuration</span></span>

<span data-ttu-id="2ac27-116">`powershell.config.json`Файл в `$PSHOME` каталоге определяет конфигурацию всех сеансов PowerShell Core, выполняемых из этой установки PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="2ac27-116">A `powershell.config.json` file in the `$PSHOME` directory defines the configuration for all PowerShell Core sessions running from that PowerShell Core installation.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac27-117">`$PSHOME`Расположение определяется в том же каталоге, что и исполняемая System.Management.Automation.dll сборка.</span><span class="sxs-lookup"><span data-stu-id="2ac27-117">The `$PSHOME` location is defined as the same directory as the executing System.Management.Automation.dll assembly.</span></span> <span data-ttu-id="2ac27-118">Это относится и к размещенным экземплярам пакета SDK для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-118">This applies to hosted PowerShell SDK instances as well.</span></span>

### <a name="currentuser-per-user-configurations"></a><span data-ttu-id="2ac27-119">Конфигурации CurrentUser (на пользователя)</span><span class="sxs-lookup"><span data-stu-id="2ac27-119">CurrentUser (per-user) configurations</span></span>

<span data-ttu-id="2ac27-120">Вы также можете настроить PowerShell для отдельных пользователей, поместив файл в каталог конфигурации области пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ac27-120">You can also configure PowerShell on a per-user basis by placing the file in the user-scope configuration directory.</span></span> <span data-ttu-id="2ac27-121">Каталог конфигурации пользователя можно найти на разных платформах с помощью команды `Split-Path $PROFILE.CurrentUserCurrentHost` .</span><span class="sxs-lookup"><span data-stu-id="2ac27-121">The user configuration directory can be found across platforms with the command `Split-Path $PROFILE.CurrentUserCurrentHost`.</span></span>

## <a name="general-configuration-settings"></a><span data-ttu-id="2ac27-122">Общие параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="2ac27-122">General configuration settings</span></span>

### <a name="executionpolicy"></a><span data-ttu-id="2ac27-123">ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="2ac27-123">ExecutionPolicy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ac27-124">Эта конфигурация применяется только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="2ac27-124">This configuration only applies on Windows platforms.</span></span>

<span data-ttu-id="2ac27-125">Настраивает политику выполнения для сеансов PowerShell, определяя, какие скрипты можно запускать.</span><span class="sxs-lookup"><span data-stu-id="2ac27-125">Configures the execution policy for PowerShell sessions, determining what scripts can be run.</span></span> <span data-ttu-id="2ac27-126">По умолчанию PowerShell использует существующую политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="2ac27-126">By default, PowerShell uses the existing execution policy.</span></span>

<span data-ttu-id="2ac27-127">Для конфигураций AllUsers этот параметр задает политику выполнения **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="2ac27-127">For AllUsers configurations, this sets the **LocalMachine** execution policy.</span></span>
<span data-ttu-id="2ac27-128">Для конфигураций CurrentUser этот параметр задает политику выполнения **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="2ac27-128">For CurrentUser configurations, this sets the **CurrentUser** execution policy.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac27-129">[`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)Командлет изменяет этот параметр в файле конфигурации ALLUSERS при вызове с параметром `-Scope LocalMachine` и изменяет его в файле конфигурации CurrentUser при вызове с помощью `-Scope CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="2ac27-129">The [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifies this setting in the AllUsers configuration file when invoked with `-Scope LocalMachine`, and modifies this setting in the CurrentUser configuration file when invoked with `-Scope CurrentUser`.</span></span>

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

<span data-ttu-id="2ac27-130">Где:</span><span class="sxs-lookup"><span data-stu-id="2ac27-130">Where:</span></span>

- <span data-ttu-id="2ac27-131">`<shell-id>` Указывает идентификатор текущего узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-131">`<shell-id>` refers to the ID of the current PowerShell host.</span></span>
  <span data-ttu-id="2ac27-132">Для обычной среды PowerShell Core это `Microsoft.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="2ac27-132">For normal PowerShell Core, this is `Microsoft.PowerShell`.</span></span>
  <span data-ttu-id="2ac27-133">В любом сеансе PowerShell его можно обнаружить с помощью `$ShellId` .</span><span class="sxs-lookup"><span data-stu-id="2ac27-133">In any PowerShell session, you can discover it with `$ShellId`.</span></span>
- <span data-ttu-id="2ac27-134">`<execution-policy>` Указывает на допустимое имя политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="2ac27-134">`<execution-policy>` refers to a valid execution policy name.</span></span>

<span data-ttu-id="2ac27-135">В следующем примере для политики выполнения PowerShell задается значение `RemoteSigned` .</span><span class="sxs-lookup"><span data-stu-id="2ac27-135">The following example sets the execution policy of PowerShell to `RemoteSigned`.</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

<span data-ttu-id="2ac27-136">В Windows эквивалентные разделы реестра можно найти в `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` разделах `HKEY_LOCAL_MACHINE` и `HKEY_CURRENT_USER` .</span><span class="sxs-lookup"><span data-stu-id="2ac27-136">In Windows, the equivalent registry keys can be found in `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` under `HKEY_LOCAL_MACHINE` and `HKEY_CURRENT_USER`.</span></span>

### <a name="psmodulepath"></a><span data-ttu-id="2ac27-137">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="2ac27-137">PSModulePath</span></span>

<span data-ttu-id="2ac27-138">Переопределяет компонент PSModulePath для этого сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-138">Overrides a PSModulePath component for this PowerShell session.</span></span> <span data-ttu-id="2ac27-139">Если конфигурация предназначена для текущего пользователя, задает путь к модулю CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="2ac27-139">If the configuration is for the current user, sets the CurrentUser module path.</span></span> <span data-ttu-id="2ac27-140">Если конфигурация предназначена для всех пользователей, задает путь к модулю Аллусер.</span><span class="sxs-lookup"><span data-stu-id="2ac27-140">If the configuration is for all users, sets the AllUser module path.</span></span>

> [!WARNING]
> <span data-ttu-id="2ac27-141">Настройка пути к модулю AllUsers или CurrentUser не приведет к изменению расположения установки с областью действия для модулей PowerShellGet, таких как [Install-Module](/powershell/module/powershellget/install-module).</span><span class="sxs-lookup"><span data-stu-id="2ac27-141">Configuring an AllUsers or CurrentUser module path here will not change the scoped installation location for PowerShellGet modules like [Install-Module](/powershell/module/powershellget/install-module).</span></span>
> <span data-ttu-id="2ac27-142">Эти командлеты всегда используют пути модулей *по умолчанию* .</span><span class="sxs-lookup"><span data-stu-id="2ac27-142">These cmdlets always use the *default* module paths.</span></span>

<span data-ttu-id="2ac27-143">Если значение не задано, будет использоваться значение по умолчанию для соответствующего компонента пути к модулю.</span><span class="sxs-lookup"><span data-stu-id="2ac27-143">If no value is set, the default value for the respective module path component will be used.</span></span> <span data-ttu-id="2ac27-144">Дополнительные сведения об этих значениях по умолчанию см. в разделе [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) .</span><span class="sxs-lookup"><span data-stu-id="2ac27-144">See [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) for more details on these defaults.</span></span>

<span data-ttu-id="2ac27-145">Этот параметр позволяет использовать переменные среды, внедряя их между `%` символами, например, так `"%HOME%\Documents\PowerShell\Modules"` же, как и команда cmd.</span><span class="sxs-lookup"><span data-stu-id="2ac27-145">This setting allows environment variables to be used by embedding them between `%` characters, like `"%HOME%\Documents\PowerShell\Modules"`, in the same way as CMD allows.</span></span> <span data-ttu-id="2ac27-146">Этот синтаксис также применим в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="2ac27-146">This syntax also applies on Linux and macOS.</span></span> <span data-ttu-id="2ac27-147">Примеры см. ниже.</span><span class="sxs-lookup"><span data-stu-id="2ac27-147">See below for examples.</span></span>

```Schema
"PSModulePath": "<ps-module-path>"
```

<span data-ttu-id="2ac27-148">Где:</span><span class="sxs-lookup"><span data-stu-id="2ac27-148">Where:</span></span>

- <span data-ttu-id="2ac27-149">`<ps-module-path>` абсолютный путь к каталогу модуля.</span><span class="sxs-lookup"><span data-stu-id="2ac27-149">`<ps-module-path>` is the absolute path to a module directory.</span></span> <span data-ttu-id="2ac27-150">Для всех пользовательских конфигураций это каталог общего модуля AllUsers.</span><span class="sxs-lookup"><span data-stu-id="2ac27-150">For all user configurations, this is the AllUsers shared module directory.</span></span> <span data-ttu-id="2ac27-151">Для текущих пользовательских конфигураций это каталог модулей CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="2ac27-151">For current user configurations, this is CurrentUser module directory.</span></span>

<span data-ttu-id="2ac27-152">В этом примере показана конфигурация PSModulePath для среды Windows:</span><span class="sxs-lookup"><span data-stu-id="2ac27-152">This example shows a PSModulePath configuration for a Windows environment:</span></span>

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

<span data-ttu-id="2ac27-153">В этом примере показана конфигурация PSModulePath для среды macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="2ac27-153">This example shows a PSModulePath configuration for a macOS or Linux environment:</span></span>

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

<span data-ttu-id="2ac27-154">В этом примере показано, как внедрить переменную среды в конфигурацию PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="2ac27-154">This example shows embedding an environment variable in a PSModulePath configuration.</span></span> <span data-ttu-id="2ac27-155">Обратите внимание, что `HOME` при использовании переменной среды и `/` разделителя каталогов это будет работать в Windows, MacOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2ac27-155">Note that using the `HOME` environment variable and the `/` directory separator, this will work on Windows, macOS and Linux.</span></span>

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

<span data-ttu-id="2ac27-156">В этом примере показано, как внедрить переменную среды в конфигурацию PSModulePath, которая будет работать только в macOS и Linux:</span><span class="sxs-lookup"><span data-stu-id="2ac27-156">This example shows embedding an environment variable in a PSModulePath configuration that will only work on macOS and Linux:</span></span>

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> <span data-ttu-id="2ac27-157">Переменные PowerShell не могут быть внедрены в конфигурации PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="2ac27-157">PowerShell variables cannot be embedded in PSModulePath configurations.</span></span>
> <span data-ttu-id="2ac27-158">В конфигурациях PSModulePath в Linux и macOS учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="2ac27-158">PSModulePath configurations on Linux and macOS are case-sensitive.</span></span> <span data-ttu-id="2ac27-159">Конфигурация PSModulePath должна использовать допустимые разделители каталогов для платформы.</span><span class="sxs-lookup"><span data-stu-id="2ac27-159">A PSModulePath configuration must use valid directory separators for the platform.</span></span> <span data-ttu-id="2ac27-160">В macOS и Linux это означает `/` .</span><span class="sxs-lookup"><span data-stu-id="2ac27-160">On macOS and Linux, this means `/`.</span></span> <span data-ttu-id="2ac27-161">В Windows обе `/` и `\` будут работать.</span><span class="sxs-lookup"><span data-stu-id="2ac27-161">On Windows, both `/` and `\` will work.</span></span>

### <a name="experimentalfeatures"></a><span data-ttu-id="2ac27-162">експерименталфеатурес</span><span class="sxs-lookup"><span data-stu-id="2ac27-162">ExperimentalFeatures</span></span>

<span data-ttu-id="2ac27-163">Имена экспериментальных функций, которые необходимо включить в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-163">The names of the experimental features to enable in PowerShell.</span></span>
<span data-ttu-id="2ac27-164">По умолчанию экспериментальные функции не включены.</span><span class="sxs-lookup"><span data-stu-id="2ac27-164">By default, no experimental features are enabled.</span></span>
<span data-ttu-id="2ac27-165">Значение по умолчанию — пустой массив.</span><span class="sxs-lookup"><span data-stu-id="2ac27-165">The default value is an empty array.</span></span>

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

<span data-ttu-id="2ac27-166">Где:</span><span class="sxs-lookup"><span data-stu-id="2ac27-166">Where:</span></span>

- <span data-ttu-id="2ac27-167">`<experimental-feature-name>` имя экспериментальной функции, которую необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="2ac27-167">`<experimental-feature-name>` is the name of an experimental feature to enable.</span></span>

<span data-ttu-id="2ac27-168">В следующем примере включаются экспериментальные функции **псимплиЦитремотинг** и **Псусеаббревиатионекспансион** при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-168">The following example enables the **PSImplicitRemoting** and **PSUseAbbreviationExpansion** experimental features when PowerShell starts up.</span></span>

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

<span data-ttu-id="2ac27-169">Дополнительные сведения о экспериментальных функциях см. в разделе [POWERSHELL RFC 29][RFC0029].</span><span class="sxs-lookup"><span data-stu-id="2ac27-169">For more information on experimental features, see [PowerShell RFC 29][RFC0029].</span></span>

## <a name="non-windows-logging-configuration"></a><span data-ttu-id="2ac27-170">Конфигурация ведения журнала не Windows</span><span class="sxs-lookup"><span data-stu-id="2ac27-170">Non-Windows logging configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ac27-171">Параметры конфигурации в этом разделе применимы только к macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2ac27-171">The configuration options in this section only apply to macOS and Linux.</span></span>
> <span data-ttu-id="2ac27-172">Ведение журнала для Windows осуществляется с помощью Просмотр событий Windows.</span><span class="sxs-lookup"><span data-stu-id="2ac27-172">Logging for Windows is managed by the Windows Event Viewer.</span></span>

<span data-ttu-id="2ac27-173">Ведение журнала PowerShell в macOS и Linux можно настроить в файле конфигурации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-173">PowerShell's logging on macOS and Linux can be configured in the PowerShell configuration file.</span></span> <span data-ttu-id="2ac27-174">Полное описание ведения журнала PowerShell для систем, отличных от Windows, см. в статье [о ведении журнала](./about_Logging_Non-Windows.md).</span><span class="sxs-lookup"><span data-stu-id="2ac27-174">For a full description of PowerShell logging for non-Windows systems, see [About Logging](./about_Logging_Non-Windows.md).</span></span>

### <a name="logidentity"></a><span data-ttu-id="2ac27-175">логидентити</span><span class="sxs-lookup"><span data-stu-id="2ac27-175">LogIdentity</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ac27-176">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2ac27-176">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="2ac27-177">Задает имя удостоверения, используемое для записи в системный журнал.</span><span class="sxs-lookup"><span data-stu-id="2ac27-177">Sets the identity name used to write to the system log.</span></span> <span data-ttu-id="2ac27-178">Значение по умолчанию — "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="2ac27-178">The default value is "powershell".</span></span>

```Schema
"LogIdentity": "<log-identity>"
```

<span data-ttu-id="2ac27-179">Где:</span><span class="sxs-lookup"><span data-stu-id="2ac27-179">Where:</span></span>

- <span data-ttu-id="2ac27-180">`<log-identity>` — Это строковое удостоверение, которое PowerShell должно использовать для записи в системный журнал.</span><span class="sxs-lookup"><span data-stu-id="2ac27-180">`<log-identity>` is the string identity that PowerShell should use for writing to syslog.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac27-181">Вы можете использовать разные значения **логидентити** для каждого установленного экземпляра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-181">You may want to have different **LogIdentity** values for each different instance of PowerShell you have installed.</span></span>

<span data-ttu-id="2ac27-182">В этом примере мы настроим **логидентити** для предварительной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-182">In this example, we are configuring the **LogIdentity** for a preview release of PowerShell.</span></span>

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a><span data-ttu-id="2ac27-183">LogLevel</span><span class="sxs-lookup"><span data-stu-id="2ac27-183">LogLevel</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ac27-184">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2ac27-184">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="2ac27-185">Задает минимальный уровень серьезности, при котором PowerShell должен вести журнал.</span><span class="sxs-lookup"><span data-stu-id="2ac27-185">Specifies the minimum severity level at which PowerShell should log.</span></span>

```Schema
"LogLevel": "<log-level>|default"
```

<span data-ttu-id="2ac27-186">Где:</span><span class="sxs-lookup"><span data-stu-id="2ac27-186">Where:</span></span>

- <span data-ttu-id="2ac27-187">`<log-level>` является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="2ac27-187">`<log-level>` is one of:</span></span>
  - <span data-ttu-id="2ac27-188">Всегда</span><span class="sxs-lookup"><span data-stu-id="2ac27-188">Always</span></span>
  - <span data-ttu-id="2ac27-189">Критически важно</span><span class="sxs-lookup"><span data-stu-id="2ac27-189">Critical</span></span>
  - <span data-ttu-id="2ac27-190">Ошибка</span><span class="sxs-lookup"><span data-stu-id="2ac27-190">Error</span></span>
  - <span data-ttu-id="2ac27-191">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="2ac27-191">Warning</span></span>
  - <span data-ttu-id="2ac27-192">Informational</span><span class="sxs-lookup"><span data-stu-id="2ac27-192">Informational</span></span>
  - <span data-ttu-id="2ac27-193">Подробный</span><span class="sxs-lookup"><span data-stu-id="2ac27-193">Verbose</span></span>
  - <span data-ttu-id="2ac27-194">Отладка</span><span class="sxs-lookup"><span data-stu-id="2ac27-194">Debug</span></span>

> [!NOTE]
> <span data-ttu-id="2ac27-195">Задание уровня ведения журнала включает все уровни журнала, расположенные выше.</span><span class="sxs-lookup"><span data-stu-id="2ac27-195">Setting a the log level enables all log levels above it.</span></span>

<span data-ttu-id="2ac27-196">При выборе значения **по умолчанию** для этого параметра будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ac27-196">Setting this setting to **default** will be interpreted as the default value.</span></span>
<span data-ttu-id="2ac27-197">Значение по умолчанию — **информационное** .</span><span class="sxs-lookup"><span data-stu-id="2ac27-197">The default value is **Informational** .</span></span>

<span data-ttu-id="2ac27-198">В следующем примере задается значение **verbose** .</span><span class="sxs-lookup"><span data-stu-id="2ac27-198">The following example sets the value to **Verbose** .</span></span>

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a><span data-ttu-id="2ac27-199">логчаннелс</span><span class="sxs-lookup"><span data-stu-id="2ac27-199">LogChannels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ac27-200">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2ac27-200">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="2ac27-201">Определяет, какие каналы ведения журнала включены.</span><span class="sxs-lookup"><span data-stu-id="2ac27-201">Determines which logging channels are enabled.</span></span>

```Schema
"LogChannels": "<log-channel>,..."
```

<span data-ttu-id="2ac27-202">Где:</span><span class="sxs-lookup"><span data-stu-id="2ac27-202">Where:</span></span>

- <span data-ttu-id="2ac27-203">`<log-channel>` является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="2ac27-203">`<log-channel>` is one of:</span></span>
  - <span data-ttu-id="2ac27-204">Операционные — записывает основные сведения о действиях PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ac27-204">Operational - logs basic information about PowerShell activities</span></span>
  - <span data-ttu-id="2ac27-205">Аналитическая — журналы более подробные диагностические сведения</span><span class="sxs-lookup"><span data-stu-id="2ac27-205">Analytic - logs more detailed diagnostic information</span></span>

<span data-ttu-id="2ac27-206">Значение по умолчанию — " **работает** ".</span><span class="sxs-lookup"><span data-stu-id="2ac27-206">The default value is **Operational** .</span></span> <span data-ttu-id="2ac27-207">Чтобы включить оба канала, включите оба значения в одну строку с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="2ac27-207">To enable both channels, include both values as a single comma-separated string.</span></span> <span data-ttu-id="2ac27-208">Пример:</span><span class="sxs-lookup"><span data-stu-id="2ac27-208">For example:</span></span>

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a><span data-ttu-id="2ac27-209">логкэйвордс</span><span class="sxs-lookup"><span data-stu-id="2ac27-209">LogKeywords</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ac27-210">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="2ac27-210">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="2ac27-211">Определяет, какие части PowerShell регистрируются в журнале.</span><span class="sxs-lookup"><span data-stu-id="2ac27-211">Determines which parts of PowerShell are logged.</span></span> <span data-ttu-id="2ac27-212">По умолчанию все ключевые слова журнала включены.</span><span class="sxs-lookup"><span data-stu-id="2ac27-212">By default, all log keywords are enabled.</span></span> <span data-ttu-id="2ac27-213">Чтобы включить несколько ключевых слов, перечислите значения в одной строке с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="2ac27-213">To enable multiple keywords, list the values in a single comma-separated string.</span></span>

```Schema
"LogKeywords": "<log-keyword>,..."
```

<span data-ttu-id="2ac27-214">Где:</span><span class="sxs-lookup"><span data-stu-id="2ac27-214">Where:</span></span>

- <span data-ttu-id="2ac27-215">`<log-keyword>` является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="2ac27-215">`<log-keyword>` is one of:</span></span>
  - <span data-ttu-id="2ac27-216">Пространство выполнения — управление пространством выполнения</span><span class="sxs-lookup"><span data-stu-id="2ac27-216">Runspace - runspace management</span></span>
  - <span data-ttu-id="2ac27-217">Конвейер — операции конвейера</span><span class="sxs-lookup"><span data-stu-id="2ac27-217">Pipeline - pipeline operations</span></span>
  - <span data-ttu-id="2ac27-218">Обработка протокола связи с протоколом, например PSRP</span><span class="sxs-lookup"><span data-stu-id="2ac27-218">Protocol - communication protocol handling, such as PSRP</span></span>
  - <span data-ttu-id="2ac27-219">Транспорт — поддержка транспортного уровня, например SSH</span><span class="sxs-lookup"><span data-stu-id="2ac27-219">Transport - transport layer support, such as SSH</span></span>
  - <span data-ttu-id="2ac27-220">Хост-функции узла PowerShell, например взаимодействие с консолью</span><span class="sxs-lookup"><span data-stu-id="2ac27-220">Host - PowerShell host functionality, for example console interaction</span></span>
  - <span data-ttu-id="2ac27-221">Командлеты — встроенные командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ac27-221">Cmdlets -PowerShell builtin cmdlets</span></span>
  - <span data-ttu-id="2ac27-222">Сериализатор — логика сериализации</span><span class="sxs-lookup"><span data-stu-id="2ac27-222">Serializer - serialization logic</span></span>
  - <span data-ttu-id="2ac27-223">Сеанс — состояние сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ac27-223">Session - PowerShell session state</span></span>
  - <span data-ttu-id="2ac27-224">Манажедплугин — подключаемый модуль WSMan</span><span class="sxs-lookup"><span data-stu-id="2ac27-224">ManagedPlugin - WSMan plugin</span></span>

> [!NOTE]
> <span data-ttu-id="2ac27-225">Обычно рекомендуется оставить это значение неустановленным, если вы не пытаетесь диагностировать определенное поведение в известной части PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ac27-225">It is generally advised to leave this value unset unless you are trying to diagnose a specific behavior in a known part of PowerShell.</span></span>
> <span data-ttu-id="2ac27-226">Изменение этого значения уменьшает только объем записываемых данных.</span><span class="sxs-lookup"><span data-stu-id="2ac27-226">Changing this value only decreases the amount of information logged.</span></span>

<span data-ttu-id="2ac27-227">В этом примере ограничивается ведение журнала операциями с пространством выполнения, логикой конвейера и командлетом.</span><span class="sxs-lookup"><span data-stu-id="2ac27-227">This example limits the logging to runspace operations, pipeline logic, and cmdlet use.</span></span> <span data-ttu-id="2ac27-228">Все остальные журналы будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="2ac27-228">All other logging will be omitted.</span></span>

```json
"LogKeywords": "Runspace,Pipeline,Cmdlets"
```

<!--

## Group policy configuration

### ScriptExecution

### ScriptBlockLogging

### ProtectedEventLogging

### Transcription

### UpdateableHelp

### ConsoleSessionConfiguration

-->

## <a name="more-example-configurations"></a><span data-ttu-id="2ac27-229">Дополнительные примеры конфигураций</span><span class="sxs-lookup"><span data-stu-id="2ac27-229">More example configurations</span></span>

### <a name="example-windows-configuration"></a><span data-ttu-id="2ac27-230">Пример конфигурации Windows</span><span class="sxs-lookup"><span data-stu-id="2ac27-230">Example Windows configuration</span></span>

<span data-ttu-id="2ac27-231">Для этой конфигурации заданы дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="2ac27-231">This configuration has more settings explicitly set:</span></span>

- <span data-ttu-id="2ac27-232">Политика выполнения для этой установки PowerShell `AllSigned`</span><span class="sxs-lookup"><span data-stu-id="2ac27-232">Execution policy for this PowerShell installation is `AllSigned`</span></span>
- <span data-ttu-id="2ac27-233">Путь к модулю CurrentUser задается как каталог модуля на общем диске</span><span class="sxs-lookup"><span data-stu-id="2ac27-233">The CurrentUser module path is set to a module directory on a shared drive</span></span>
- <span data-ttu-id="2ac27-234">`PSImplicitRemotingBatching`Экспериментальная функция включена</span><span class="sxs-lookup"><span data-stu-id="2ac27-234">The `PSImplicitRemotingBatching` experimental feature is enabled</span></span>

> [!NOTE]
> <span data-ttu-id="2ac27-235">`ExecutionPolicy`Параметры и `PSModulePath` здесь будут работать только на платформе Windows, так как путь к модулю использует `\` `;` символы-разделители и не является политикой выполнения `Unrestricted` (единственная допустимая политика на платформах, подобных Unix).</span><span class="sxs-lookup"><span data-stu-id="2ac27-235">The `ExecutionPolicy` and `PSModulePath` settings here would only work on a Windows platform, since the module path uses `\` and `;` separator characters and the execution policy is not `Unrestricted` (the only policy allowed on UNIX-like platforms).</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a><span data-ttu-id="2ac27-236">Пример конфигурации, отличной от Windows</span><span class="sxs-lookup"><span data-stu-id="2ac27-236">Example non-Windows configuration</span></span>

<span data-ttu-id="2ac27-237">Эта конфигурация задает ряд параметров, которые работают только в macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="2ac27-237">This configuration sets a number of options that only work in macOS or Linux:</span></span>

- <span data-ttu-id="2ac27-238">Путь к модулю CurrentUser задается в пользовательском каталоге модуля в `$HOME`</span><span class="sxs-lookup"><span data-stu-id="2ac27-238">The CurrentUser module path is set to a custom module directory in `$HOME`</span></span>
- <span data-ttu-id="2ac27-239">Включен экспериментальный компонент **псимплиЦитремотингбатчинг**</span><span class="sxs-lookup"><span data-stu-id="2ac27-239">The **PSImplicitRemotingBatching** experimental feature is enabled</span></span>
- <span data-ttu-id="2ac27-240">В качестве уровня ведения журнала PowerShell задано **подробное** протоколирование.</span><span class="sxs-lookup"><span data-stu-id="2ac27-240">The PowerShell logging level is set to **Verbose** , for more logging</span></span>
- <span data-ttu-id="2ac27-241">Эта установка PowerShell выполняет запись в журналы, используя удостоверение **Home-PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="2ac27-241">This PowerShell installation writes to the logs using the **home-powershell** identity.</span></span>

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a><span data-ttu-id="2ac27-242">См. также статью</span><span class="sxs-lookup"><span data-stu-id="2ac27-242">See also</span></span>

[<span data-ttu-id="2ac27-243">Общие сведения о политиках выполнения</span><span class="sxs-lookup"><span data-stu-id="2ac27-243">About Execution Policies</span></span>](./about_Execution_Policies.md)

[<span data-ttu-id="2ac27-244">Сведения об автоматических переменных</span><span class="sxs-lookup"><span data-stu-id="2ac27-244">About Automatic Variables</span></span>](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md
