---
description: Файлы конфигурации для PowerShell Core, замена конфигурации реестра.
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: 7190484832958e778a21e6d2cc91771587bffdbf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604430"
---
# <a name="about-powershell-config"></a><span data-ttu-id="c9556-103">О конфигурации PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9556-103">About PowerShell Config</span></span>

## <a name="short-description"></a><span data-ttu-id="c9556-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c9556-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c9556-105">Файлы конфигурации для PowerShell Core, замена конфигурации реестра.</span><span class="sxs-lookup"><span data-stu-id="c9556-105">Configuration files for PowerShell Core, replacing Registry configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="c9556-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c9556-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="c9556-107">`powershell.config.json`Файл содержит параметры конфигурации для PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="c9556-107">The `powershell.config.json` file contains configuration settings for PowerShell Core.</span></span> <span data-ttu-id="c9556-108">PowerShell загружает эту конфигурацию при запуске.</span><span class="sxs-lookup"><span data-stu-id="c9556-108">PowerShell loads this configuration at startup.</span></span> <span data-ttu-id="c9556-109">Параметры также можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9556-109">The settings can also be modified at runtime.</span></span> <span data-ttu-id="c9556-110">Ранее эти параметры хранились в реестре Windows для PowerShell, но теперь содержатся в файле для включения настройки в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="c9556-110">Previously, these settings were stored in the Windows Registry for PowerShell, but are now contained in a file to enable configuration on macOS and Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="c9556-111">Если `powershell.config.json` файл содержит недопустимый JSON PowerShell, невозможно запустить интерактивный сеанс.</span><span class="sxs-lookup"><span data-stu-id="c9556-111">If the `powershell.config.json` file contains invalid JSON PowerShell cannot start an interactive session.</span></span>
> <span data-ttu-id="c9556-112">В этом случае необходимо исправить файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9556-112">If this occurs, you must fix the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="c9556-113">Нераспознанные ключи или недопустимые значения в файле конфигурации будут игнорироваться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="c9556-113">Unrecognized keys or invalid values in the configuration file will be silently ignored.</span></span>

### <a name="allusers-shared-configuration"></a><span data-ttu-id="c9556-114">Конфигурация AllUsers (общая)</span><span class="sxs-lookup"><span data-stu-id="c9556-114">AllUsers (shared) configuration</span></span>

<span data-ttu-id="c9556-115">`powershell.config.json`Файл в `$PSHOME` каталоге определяет конфигурацию всех сеансов PowerShell Core, выполняемых из этой установки PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="c9556-115">A `powershell.config.json` file in the `$PSHOME` directory defines the configuration for all PowerShell Core sessions running from that PowerShell Core installation.</span></span>

> [!NOTE]
> <span data-ttu-id="c9556-116">`$PSHOME`Расположение определяется в том же каталоге, что и исполняемая System.Management.Automation.dll сборка.</span><span class="sxs-lookup"><span data-stu-id="c9556-116">The `$PSHOME` location is defined as the same directory as the executing System.Management.Automation.dll assembly.</span></span> <span data-ttu-id="c9556-117">Это относится и к размещенным экземплярам пакета SDK для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-117">This applies to hosted PowerShell SDK instances as well.</span></span>

### <a name="currentuser-per-user-configurations"></a><span data-ttu-id="c9556-118">Конфигурации CurrentUser (на пользователя)</span><span class="sxs-lookup"><span data-stu-id="c9556-118">CurrentUser (per-user) configurations</span></span>

<span data-ttu-id="c9556-119">Вы также можете настроить PowerShell для отдельных пользователей, поместив файл в каталог конфигурации области пользователя.</span><span class="sxs-lookup"><span data-stu-id="c9556-119">You can also configure PowerShell on a per-user basis by placing the file in the user-scope configuration directory.</span></span> <span data-ttu-id="c9556-120">Каталог конфигурации пользователя можно найти на разных платформах с помощью команды `Split-Path $PROFILE.CurrentUserCurrentHost` .</span><span class="sxs-lookup"><span data-stu-id="c9556-120">The user configuration directory can be found across platforms with the command `Split-Path $PROFILE.CurrentUserCurrentHost`.</span></span>

## <a name="general-configuration-settings"></a><span data-ttu-id="c9556-121">Общие параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="c9556-121">General configuration settings</span></span>

### <a name="executionpolicy"></a><span data-ttu-id="c9556-122">ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="c9556-122">ExecutionPolicy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9556-123">Эта конфигурация применяется только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="c9556-123">This configuration only applies on Windows platforms.</span></span>

<span data-ttu-id="c9556-124">Настраивает политику выполнения для сеансов PowerShell, определяя, какие скрипты можно запускать.</span><span class="sxs-lookup"><span data-stu-id="c9556-124">Configures the execution policy for PowerShell sessions, determining what scripts can be run.</span></span> <span data-ttu-id="c9556-125">По умолчанию PowerShell использует существующую политику выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9556-125">By default, PowerShell uses the existing execution policy.</span></span>

<span data-ttu-id="c9556-126">Для конфигураций AllUsers этот параметр задает политику выполнения **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="c9556-126">For AllUsers configurations, this sets the **LocalMachine** execution policy.</span></span>
<span data-ttu-id="c9556-127">Для конфигураций CurrentUser этот параметр задает политику выполнения **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="c9556-127">For CurrentUser configurations, this sets the **CurrentUser** execution policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c9556-128">[`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)Командлет изменяет этот параметр в файле конфигурации ALLUSERS при вызове с параметром `-Scope LocalMachine` и изменяет его в файле конфигурации CurrentUser при вызове с помощью `-Scope CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="c9556-128">The [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifies this setting in the AllUsers configuration file when invoked with `-Scope LocalMachine`, and modifies this setting in the CurrentUser configuration file when invoked with `-Scope CurrentUser`.</span></span>

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

<span data-ttu-id="c9556-129">Где:</span><span class="sxs-lookup"><span data-stu-id="c9556-129">Where:</span></span>

- <span data-ttu-id="c9556-130">`<shell-id>` Указывает идентификатор текущего узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-130">`<shell-id>` refers to the ID of the current PowerShell host.</span></span>
  <span data-ttu-id="c9556-131">Для обычной среды PowerShell Core это `Microsoft.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="c9556-131">For normal PowerShell Core, this is `Microsoft.PowerShell`.</span></span>
  <span data-ttu-id="c9556-132">В любом сеансе PowerShell его можно обнаружить с помощью `$ShellId` .</span><span class="sxs-lookup"><span data-stu-id="c9556-132">In any PowerShell session, you can discover it with `$ShellId`.</span></span>
- <span data-ttu-id="c9556-133">`<execution-policy>` Указывает на допустимое имя политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9556-133">`<execution-policy>` refers to a valid execution policy name.</span></span>

<span data-ttu-id="c9556-134">В следующем примере для политики выполнения PowerShell задается значение `RemoteSigned` .</span><span class="sxs-lookup"><span data-stu-id="c9556-134">The following example sets the execution policy of PowerShell to `RemoteSigned`.</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

<span data-ttu-id="c9556-135">В Windows эквивалентные разделы реестра можно найти в `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` разделах `HKEY_LOCAL_MACHINE` и `HKEY_CURRENT_USER` .</span><span class="sxs-lookup"><span data-stu-id="c9556-135">In Windows, the equivalent registry keys can be found in `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` under `HKEY_LOCAL_MACHINE` and `HKEY_CURRENT_USER`.</span></span>

### <a name="psmodulepath"></a><span data-ttu-id="c9556-136">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="c9556-136">PSModulePath</span></span>

<span data-ttu-id="c9556-137">Переопределяет компонент PSModulePath для этого сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-137">Overrides a PSModulePath component for this PowerShell session.</span></span> <span data-ttu-id="c9556-138">Если конфигурация предназначена для текущего пользователя, задает путь к модулю CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="c9556-138">If the configuration is for the current user, sets the CurrentUser module path.</span></span> <span data-ttu-id="c9556-139">Если конфигурация предназначена для всех пользователей, задает путь к модулю Аллусер.</span><span class="sxs-lookup"><span data-stu-id="c9556-139">If the configuration is for all users, sets the AllUser module path.</span></span>

> [!WARNING]
> <span data-ttu-id="c9556-140">Настройка пути к модулю AllUsers или CurrentUser не приведет к изменению расположения установки с областью действия для модулей PowerShellGet, таких как [Install-Module](/powershell/module/powershellget/install-module).</span><span class="sxs-lookup"><span data-stu-id="c9556-140">Configuring an AllUsers or CurrentUser module path here will not change the scoped installation location for PowerShellGet modules like [Install-Module](/powershell/module/powershellget/install-module).</span></span>
> <span data-ttu-id="c9556-141">Эти командлеты всегда используют пути модулей *по умолчанию* .</span><span class="sxs-lookup"><span data-stu-id="c9556-141">These cmdlets always use the *default* module paths.</span></span>

<span data-ttu-id="c9556-142">Если значение не задано, будет использоваться значение по умолчанию для соответствующего компонента пути к модулю.</span><span class="sxs-lookup"><span data-stu-id="c9556-142">If no value is set, the default value for the respective module path component will be used.</span></span> <span data-ttu-id="c9556-143">Дополнительные сведения об этих значениях по умолчанию см. в разделе [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) .</span><span class="sxs-lookup"><span data-stu-id="c9556-143">See [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) for more details on these defaults.</span></span>

<span data-ttu-id="c9556-144">Этот параметр позволяет использовать переменные среды, внедряя их между `%` символами, например, так `"%HOME%\Documents\PowerShell\Modules"` же, как и команда cmd.</span><span class="sxs-lookup"><span data-stu-id="c9556-144">This setting allows environment variables to be used by embedding them between `%` characters, like `"%HOME%\Documents\PowerShell\Modules"`, in the same way as CMD allows.</span></span> <span data-ttu-id="c9556-145">Этот синтаксис также применим в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="c9556-145">This syntax also applies on Linux and macOS.</span></span> <span data-ttu-id="c9556-146">Примеры см. ниже.</span><span class="sxs-lookup"><span data-stu-id="c9556-146">See below for examples.</span></span>

```Schema
"PSModulePath": "<ps-module-path>"
```

<span data-ttu-id="c9556-147">Где:</span><span class="sxs-lookup"><span data-stu-id="c9556-147">Where:</span></span>

- <span data-ttu-id="c9556-148">`<ps-module-path>` абсолютный путь к каталогу модуля.</span><span class="sxs-lookup"><span data-stu-id="c9556-148">`<ps-module-path>` is the absolute path to a module directory.</span></span> <span data-ttu-id="c9556-149">Для всех пользовательских конфигураций это каталог общего модуля AllUsers.</span><span class="sxs-lookup"><span data-stu-id="c9556-149">For all user configurations, this is the AllUsers shared module directory.</span></span> <span data-ttu-id="c9556-150">Для текущих пользовательских конфигураций это каталог модулей CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="c9556-150">For current user configurations, this is CurrentUser module directory.</span></span>

<span data-ttu-id="c9556-151">В этом примере показана конфигурация PSModulePath для среды Windows:</span><span class="sxs-lookup"><span data-stu-id="c9556-151">This example shows a PSModulePath configuration for a Windows environment:</span></span>

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

<span data-ttu-id="c9556-152">В этом примере показана конфигурация PSModulePath для среды macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="c9556-152">This example shows a PSModulePath configuration for a macOS or Linux environment:</span></span>

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

<span data-ttu-id="c9556-153">В этом примере показано, как внедрить переменную среды в конфигурацию PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="c9556-153">This example shows embedding an environment variable in a PSModulePath configuration.</span></span> <span data-ttu-id="c9556-154">Обратите внимание, что `HOME` при использовании переменной среды и `/` разделителя каталогов это будет работать в Windows, MacOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="c9556-154">Note that using the `HOME` environment variable and the `/` directory separator, this will work on Windows, macOS and Linux.</span></span>

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

<span data-ttu-id="c9556-155">В этом примере показано, как внедрить переменную среды в конфигурацию PSModulePath, которая будет работать только в macOS и Linux:</span><span class="sxs-lookup"><span data-stu-id="c9556-155">This example shows embedding an environment variable in a PSModulePath configuration that will only work on macOS and Linux:</span></span>

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> <span data-ttu-id="c9556-156">Переменные PowerShell не могут быть внедрены в конфигурации PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="c9556-156">PowerShell variables cannot be embedded in PSModulePath configurations.</span></span>
> <span data-ttu-id="c9556-157">В конфигурациях PSModulePath в Linux и macOS учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c9556-157">PSModulePath configurations on Linux and macOS are case-sensitive.</span></span> <span data-ttu-id="c9556-158">Конфигурация PSModulePath должна использовать допустимые разделители каталогов для платформы.</span><span class="sxs-lookup"><span data-stu-id="c9556-158">A PSModulePath configuration must use valid directory separators for the platform.</span></span> <span data-ttu-id="c9556-159">В macOS и Linux это означает `/` .</span><span class="sxs-lookup"><span data-stu-id="c9556-159">On macOS and Linux, this means `/`.</span></span> <span data-ttu-id="c9556-160">В Windows обе `/` и `\` будут работать.</span><span class="sxs-lookup"><span data-stu-id="c9556-160">On Windows, both `/` and `\` will work.</span></span>

### <a name="experimentalfeatures"></a><span data-ttu-id="c9556-161">експерименталфеатурес</span><span class="sxs-lookup"><span data-stu-id="c9556-161">ExperimentalFeatures</span></span>

<span data-ttu-id="c9556-162">Имена экспериментальных функций, которые необходимо включить в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-162">The names of the experimental features to enable in PowerShell.</span></span>
<span data-ttu-id="c9556-163">По умолчанию экспериментальные функции не включены.</span><span class="sxs-lookup"><span data-stu-id="c9556-163">By default, no experimental features are enabled.</span></span>
<span data-ttu-id="c9556-164">Значение по умолчанию — пустой массив.</span><span class="sxs-lookup"><span data-stu-id="c9556-164">The default value is an empty array.</span></span>

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

<span data-ttu-id="c9556-165">Где:</span><span class="sxs-lookup"><span data-stu-id="c9556-165">Where:</span></span>

- <span data-ttu-id="c9556-166">`<experimental-feature-name>` имя экспериментальной функции, которую необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="c9556-166">`<experimental-feature-name>` is the name of an experimental feature to enable.</span></span>

<span data-ttu-id="c9556-167">В следующем примере включаются экспериментальные функции **псимплиЦитремотинг** и **Псусеаббревиатионекспансион** при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-167">The following example enables the **PSImplicitRemoting** and **PSUseAbbreviationExpansion** experimental features when PowerShell starts up.</span></span>

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

<span data-ttu-id="c9556-168">Дополнительные сведения о экспериментальных функциях см. в разделе [POWERSHELL RFC 29][RFC0029].</span><span class="sxs-lookup"><span data-stu-id="c9556-168">For more information on experimental features, see [PowerShell RFC 29][RFC0029].</span></span>

## <a name="non-windows-logging-configuration"></a><span data-ttu-id="c9556-169">Конфигурация ведения журнала не Windows</span><span class="sxs-lookup"><span data-stu-id="c9556-169">Non-Windows logging configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9556-170">Параметры конфигурации в этом разделе применимы только к macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="c9556-170">The configuration options in this section only apply to macOS and Linux.</span></span>
> <span data-ttu-id="c9556-171">Ведение журнала для Windows осуществляется с помощью Просмотр событий Windows.</span><span class="sxs-lookup"><span data-stu-id="c9556-171">Logging for Windows is managed by the Windows Event Viewer.</span></span>

<span data-ttu-id="c9556-172">Ведение журнала PowerShell в macOS и Linux можно настроить в файле конфигурации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-172">PowerShell's logging on macOS and Linux can be configured in the PowerShell configuration file.</span></span> <span data-ttu-id="c9556-173">Полное описание ведения журнала PowerShell для систем, отличных от Windows, см. в статье [о ведении журнала](./about_Logging_Non-Windows.md).</span><span class="sxs-lookup"><span data-stu-id="c9556-173">For a full description of PowerShell logging for non-Windows systems, see [About Logging](./about_Logging_Non-Windows.md).</span></span>

### <a name="logidentity"></a><span data-ttu-id="c9556-174">логидентити</span><span class="sxs-lookup"><span data-stu-id="c9556-174">LogIdentity</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9556-175">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="c9556-175">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="c9556-176">Задает имя удостоверения, используемое для записи в системный журнал.</span><span class="sxs-lookup"><span data-stu-id="c9556-176">Sets the identity name used to write to the system log.</span></span> <span data-ttu-id="c9556-177">Значение по умолчанию — "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="c9556-177">The default value is "powershell".</span></span>

```Schema
"LogIdentity": "<log-identity>"
```

<span data-ttu-id="c9556-178">Где:</span><span class="sxs-lookup"><span data-stu-id="c9556-178">Where:</span></span>

- <span data-ttu-id="c9556-179">`<log-identity>` — Это строковое удостоверение, которое PowerShell должно использовать для записи в системный журнал.</span><span class="sxs-lookup"><span data-stu-id="c9556-179">`<log-identity>` is the string identity that PowerShell should use for writing to syslog.</span></span>

> [!NOTE]
> <span data-ttu-id="c9556-180">Вы можете использовать разные значения **логидентити** для каждого установленного экземпляра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-180">You may want to have different **LogIdentity** values for each different instance of PowerShell you have installed.</span></span>

<span data-ttu-id="c9556-181">В этом примере мы настроим **логидентити** для предварительной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-181">In this example, we are configuring the **LogIdentity** for a preview release of PowerShell.</span></span>

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a><span data-ttu-id="c9556-182">LogLevel</span><span class="sxs-lookup"><span data-stu-id="c9556-182">LogLevel</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9556-183">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="c9556-183">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="c9556-184">Задает минимальный уровень серьезности, при котором PowerShell должен вести журнал.</span><span class="sxs-lookup"><span data-stu-id="c9556-184">Specifies the minimum severity level at which PowerShell should log.</span></span>

```Schema
"LogLevel": "<log-level>|default"
```

<span data-ttu-id="c9556-185">Где:</span><span class="sxs-lookup"><span data-stu-id="c9556-185">Where:</span></span>

- <span data-ttu-id="c9556-186">`<log-level>` может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c9556-186">`<log-level>` is one of:</span></span>
  - <span data-ttu-id="c9556-187">Всегда</span><span class="sxs-lookup"><span data-stu-id="c9556-187">Always</span></span>
  - <span data-ttu-id="c9556-188">Критически важно</span><span class="sxs-lookup"><span data-stu-id="c9556-188">Critical</span></span>
  - <span data-ttu-id="c9556-189">Ошибка</span><span class="sxs-lookup"><span data-stu-id="c9556-189">Error</span></span>
  - <span data-ttu-id="c9556-190">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="c9556-190">Warning</span></span>
  - <span data-ttu-id="c9556-191">Informational</span><span class="sxs-lookup"><span data-stu-id="c9556-191">Informational</span></span>
  - <span data-ttu-id="c9556-192">Подробный</span><span class="sxs-lookup"><span data-stu-id="c9556-192">Verbose</span></span>
  - <span data-ttu-id="c9556-193">Отладка</span><span class="sxs-lookup"><span data-stu-id="c9556-193">Debug</span></span>

> [!NOTE]
> <span data-ttu-id="c9556-194">Задание уровня ведения журнала включает все уровни журнала, расположенные выше.</span><span class="sxs-lookup"><span data-stu-id="c9556-194">Setting a the log level enables all log levels above it.</span></span>

<span data-ttu-id="c9556-195">При выборе значения **по умолчанию** для этого параметра будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c9556-195">Setting this setting to **default** will be interpreted as the default value.</span></span>
<span data-ttu-id="c9556-196">Значение по умолчанию — **информационное**.</span><span class="sxs-lookup"><span data-stu-id="c9556-196">The default value is **Informational**.</span></span>

<span data-ttu-id="c9556-197">В следующем примере задается значение **verbose**.</span><span class="sxs-lookup"><span data-stu-id="c9556-197">The following example sets the value to **Verbose**.</span></span>

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a><span data-ttu-id="c9556-198">логчаннелс</span><span class="sxs-lookup"><span data-stu-id="c9556-198">LogChannels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9556-199">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="c9556-199">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="c9556-200">Определяет, какие каналы ведения журнала включены.</span><span class="sxs-lookup"><span data-stu-id="c9556-200">Determines which logging channels are enabled.</span></span>

```Schema
"LogChannels": "<log-channel>,..."
```

<span data-ttu-id="c9556-201">Где:</span><span class="sxs-lookup"><span data-stu-id="c9556-201">Where:</span></span>

- <span data-ttu-id="c9556-202">`<log-channel>` может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c9556-202">`<log-channel>` is one of:</span></span>
  - <span data-ttu-id="c9556-203">Операционные — записывает основные сведения о действиях PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9556-203">Operational - logs basic information about PowerShell activities</span></span>
  - <span data-ttu-id="c9556-204">Аналитическая — журналы более подробные диагностические сведения</span><span class="sxs-lookup"><span data-stu-id="c9556-204">Analytic - logs more detailed diagnostic information</span></span>

<span data-ttu-id="c9556-205">Значение по умолчанию — " **работает**".</span><span class="sxs-lookup"><span data-stu-id="c9556-205">The default value is **Operational**.</span></span> <span data-ttu-id="c9556-206">Чтобы включить оба канала, включите оба значения в одну строку с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="c9556-206">To enable both channels, include both values as a single comma-separated string.</span></span> <span data-ttu-id="c9556-207">Пример:</span><span class="sxs-lookup"><span data-stu-id="c9556-207">For example:</span></span>

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a><span data-ttu-id="c9556-208">логкэйвордс</span><span class="sxs-lookup"><span data-stu-id="c9556-208">LogKeywords</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9556-209">Этот параметр можно использовать только в macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="c9556-209">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="c9556-210">Определяет, какие части PowerShell регистрируются в журнале.</span><span class="sxs-lookup"><span data-stu-id="c9556-210">Determines which parts of PowerShell are logged.</span></span> <span data-ttu-id="c9556-211">По умолчанию все ключевые слова журнала включены.</span><span class="sxs-lookup"><span data-stu-id="c9556-211">By default, all log keywords are enabled.</span></span> <span data-ttu-id="c9556-212">Чтобы включить несколько ключевых слов, перечислите значения в одной строке с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="c9556-212">To enable multiple keywords, list the values in a single comma-separated string.</span></span>

```Schema
"LogKeywords": "<log-keyword>,..."
```

<span data-ttu-id="c9556-213">Где:</span><span class="sxs-lookup"><span data-stu-id="c9556-213">Where:</span></span>

- <span data-ttu-id="c9556-214">`<log-keyword>` может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c9556-214">`<log-keyword>` is one of:</span></span>
  - <span data-ttu-id="c9556-215">Пространство выполнения — управление пространством выполнения</span><span class="sxs-lookup"><span data-stu-id="c9556-215">Runspace - runspace management</span></span>
  - <span data-ttu-id="c9556-216">Конвейер — операции конвейера</span><span class="sxs-lookup"><span data-stu-id="c9556-216">Pipeline - pipeline operations</span></span>
  - <span data-ttu-id="c9556-217">Обработка протокола связи с протоколом, например PSRP</span><span class="sxs-lookup"><span data-stu-id="c9556-217">Protocol - communication protocol handling, such as PSRP</span></span>
  - <span data-ttu-id="c9556-218">Транспорт — поддержка транспортного уровня, например SSH</span><span class="sxs-lookup"><span data-stu-id="c9556-218">Transport - transport layer support, such as SSH</span></span>
  - <span data-ttu-id="c9556-219">Хост-функции узла PowerShell, например взаимодействие с консолью</span><span class="sxs-lookup"><span data-stu-id="c9556-219">Host - PowerShell host functionality, for example console interaction</span></span>
  - <span data-ttu-id="c9556-220">Командлеты — встроенные командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9556-220">Cmdlets -PowerShell builtin cmdlets</span></span>
  - <span data-ttu-id="c9556-221">Сериализатор — логика сериализации</span><span class="sxs-lookup"><span data-stu-id="c9556-221">Serializer - serialization logic</span></span>
  - <span data-ttu-id="c9556-222">Сеанс — состояние сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9556-222">Session - PowerShell session state</span></span>
  - <span data-ttu-id="c9556-223">Манажедплугин — подключаемый модуль WSMan</span><span class="sxs-lookup"><span data-stu-id="c9556-223">ManagedPlugin - WSMan plugin</span></span>

> [!NOTE]
> <span data-ttu-id="c9556-224">Обычно рекомендуется оставить это значение неустановленным, если вы не пытаетесь диагностировать определенное поведение в известной части PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9556-224">It is generally advised to leave this value unset unless you are trying to diagnose a specific behavior in a known part of PowerShell.</span></span>
> <span data-ttu-id="c9556-225">Изменение этого значения уменьшает только объем записываемых данных.</span><span class="sxs-lookup"><span data-stu-id="c9556-225">Changing this value only decreases the amount of information logged.</span></span>

<span data-ttu-id="c9556-226">В этом примере ограничивается ведение журнала операциями с пространством выполнения, логикой конвейера и командлетом.</span><span class="sxs-lookup"><span data-stu-id="c9556-226">This example limits the logging to runspace operations, pipeline logic, and cmdlet use.</span></span> <span data-ttu-id="c9556-227">Все остальные журналы будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="c9556-227">All other logging will be omitted.</span></span>

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

## <a name="more-example-configurations"></a><span data-ttu-id="c9556-228">Дополнительные примеры конфигураций</span><span class="sxs-lookup"><span data-stu-id="c9556-228">More example configurations</span></span>

### <a name="example-windows-configuration"></a><span data-ttu-id="c9556-229">Пример конфигурации Windows</span><span class="sxs-lookup"><span data-stu-id="c9556-229">Example Windows configuration</span></span>

<span data-ttu-id="c9556-230">Для этой конфигурации заданы дополнительные параметры:</span><span class="sxs-lookup"><span data-stu-id="c9556-230">This configuration has more settings explicitly set:</span></span>

- <span data-ttu-id="c9556-231">Политика выполнения для этой установки PowerShell `AllSigned`</span><span class="sxs-lookup"><span data-stu-id="c9556-231">Execution policy for this PowerShell installation is `AllSigned`</span></span>
- <span data-ttu-id="c9556-232">Путь к модулю CurrentUser задается как каталог модуля на общем диске</span><span class="sxs-lookup"><span data-stu-id="c9556-232">The CurrentUser module path is set to a module directory on a shared drive</span></span>
- <span data-ttu-id="c9556-233">`PSImplicitRemotingBatching`Экспериментальная функция включена</span><span class="sxs-lookup"><span data-stu-id="c9556-233">The `PSImplicitRemotingBatching` experimental feature is enabled</span></span>

> [!NOTE]
> <span data-ttu-id="c9556-234">`ExecutionPolicy`Параметры и `PSModulePath` здесь будут работать только на платформе Windows, так как путь к модулю использует `\` `;` символы-разделители и не является политикой выполнения `Unrestricted` (единственная допустимая политика на платформах, подобных Unix).</span><span class="sxs-lookup"><span data-stu-id="c9556-234">The `ExecutionPolicy` and `PSModulePath` settings here would only work on a Windows platform, since the module path uses `\` and `;` separator characters and the execution policy is not `Unrestricted` (the only policy allowed on UNIX-like platforms).</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a><span data-ttu-id="c9556-235">Пример конфигурации, отличной от Windows</span><span class="sxs-lookup"><span data-stu-id="c9556-235">Example non-Windows configuration</span></span>

<span data-ttu-id="c9556-236">Эта конфигурация задает ряд параметров, которые работают только в macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="c9556-236">This configuration sets a number of options that only work in macOS or Linux:</span></span>

- <span data-ttu-id="c9556-237">Путь к модулю CurrentUser задается в пользовательском каталоге модуля в `$HOME`</span><span class="sxs-lookup"><span data-stu-id="c9556-237">The CurrentUser module path is set to a custom module directory in `$HOME`</span></span>
- <span data-ttu-id="c9556-238">Включен экспериментальный компонент **псимплиЦитремотингбатчинг**</span><span class="sxs-lookup"><span data-stu-id="c9556-238">The **PSImplicitRemotingBatching** experimental feature is enabled</span></span>
- <span data-ttu-id="c9556-239">В качестве уровня ведения журнала PowerShell задано **подробное** протоколирование.</span><span class="sxs-lookup"><span data-stu-id="c9556-239">The PowerShell logging level is set to **Verbose**, for more logging</span></span>
- <span data-ttu-id="c9556-240">Эта установка PowerShell выполняет запись в журналы, используя удостоверение **Home-PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="c9556-240">This PowerShell installation writes to the logs using the **home-powershell** identity.</span></span>

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a><span data-ttu-id="c9556-241">См. также</span><span class="sxs-lookup"><span data-stu-id="c9556-241">See also</span></span>

[<span data-ttu-id="c9556-242">Общие сведения о политиках выполнения</span><span class="sxs-lookup"><span data-stu-id="c9556-242">About Execution Policies</span></span>](./about_Execution_Policies.md)

[<span data-ttu-id="c9556-243">Сведения об автоматических переменных</span><span class="sxs-lookup"><span data-stu-id="c9556-243">About Automatic Variables</span></span>](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md

