---
description: Описывает, как получить доступ к переменным среды Windows в PowerShell.
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Environment_Variables
ms.openlocfilehash: 66d2bcd76651a7231a670ee5b02b99d6edd63a72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600197"
---
# <a name="about-environment-variables"></a><span data-ttu-id="631e4-103">Сведения о переменных среды</span><span class="sxs-lookup"><span data-stu-id="631e4-103">About Environment Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="631e4-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="631e4-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="631e4-105">Описывает, как получить доступ к переменным среды Windows в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631e4-105">Describes how to access Windows environment variables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="631e4-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="631e4-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="631e4-107">Переменные среды хранят сведения о среде операционной системы.</span><span class="sxs-lookup"><span data-stu-id="631e4-107">Environment variables store information about the operating system environment.</span></span> <span data-ttu-id="631e4-108">Эти сведения включают в себя такие сведения, как путь операционной системы, количество процессоров, используемых операционной системой, и расположение временных папок.</span><span class="sxs-lookup"><span data-stu-id="631e4-108">This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders.</span></span>

<span data-ttu-id="631e4-109">Переменные среды хранят данные, используемые операционной системой и другими программами.</span><span class="sxs-lookup"><span data-stu-id="631e4-109">The environment variables store data that is used by the operating system and other programs.</span></span> <span data-ttu-id="631e4-110">Например, `WINDIR` переменная среды содержит расположение каталога установки Windows.</span><span class="sxs-lookup"><span data-stu-id="631e4-110">For example, the `WINDIR` environment variable contains the location of the Windows installation directory.</span></span> <span data-ttu-id="631e4-111">Программы могут запрашивать значение этой переменной, чтобы определить, где находятся файлы операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="631e4-111">Programs can query the value of this variable to determine where Windows operating system files are located.</span></span>

<span data-ttu-id="631e4-112">PowerShell может обращаться к переменным среды и управлять ими на любой из поддерживаемых платформ операционной системы.</span><span class="sxs-lookup"><span data-stu-id="631e4-112">PowerShell can access and manage environment variables in any of the supported operating system platforms.</span></span> <span data-ttu-id="631e4-113">Поставщик среды PowerShell упрощает этот процесс, облегчая просмотр и изменение переменных среды.</span><span class="sxs-lookup"><span data-stu-id="631e4-113">The PowerShell environment provider simplifies this process by making it easy to view and change environment variables.</span></span>

<span data-ttu-id="631e4-114">Переменные среды, в отличие от других типов переменных в PowerShell, наследуются дочерними процессами, такими как локальные фоновые задания и сеансы, в которых выполняются элементы модуля.</span><span class="sxs-lookup"><span data-stu-id="631e4-114">Environment variables, unlike other types of variables in PowerShell, are inherited by child processes, such as local background jobs and the sessions in which module members run.</span></span> <span data-ttu-id="631e4-115">Это делает переменные среды наиболее подходящими для хранения значений, необходимых как в родительских, так и в дочерних процессах.</span><span class="sxs-lookup"><span data-stu-id="631e4-115">This makes environment variables well suited to storing values that are needed in both parent and child processes.</span></span>

## <a name="using-and-changing-environment-variables"></a><span data-ttu-id="631e4-116">Использование и изменение переменных среды</span><span class="sxs-lookup"><span data-stu-id="631e4-116">Using and changing environment variables</span></span>

<span data-ttu-id="631e4-117">В Windows переменные среды могут быть определены в трех областях:</span><span class="sxs-lookup"><span data-stu-id="631e4-117">On Windows, environment variables can be defined in three scopes:</span></span>

- <span data-ttu-id="631e4-118">Область компьютера (или системы)</span><span class="sxs-lookup"><span data-stu-id="631e4-118">Machine (or System) scope</span></span>
- <span data-ttu-id="631e4-119">Область пользователей</span><span class="sxs-lookup"><span data-stu-id="631e4-119">User scope</span></span>
- <span data-ttu-id="631e4-120">Область процесса</span><span class="sxs-lookup"><span data-stu-id="631e4-120">Process scope</span></span>

<span data-ttu-id="631e4-121">Область _процесса_ содержит переменные среды, доступные в текущем процессе, или сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631e4-121">The _Process_ scope contains the environment variables available in the current process, or PowerShell session.</span></span> <span data-ttu-id="631e4-122">Этот список переменных наследуется от родительского процесса и создается из переменных в областях _компьютера_ и _пользователя_ .</span><span class="sxs-lookup"><span data-stu-id="631e4-122">This list of variables is inherited from the parent process and is constructed from the variables in the _Machine_ and _User_ scopes.</span></span> <span data-ttu-id="631e4-123">Платформы на базе UNIX имеют только область _процесса_ .</span><span class="sxs-lookup"><span data-stu-id="631e4-123">Unix-based platforms only have the _Process_ scope.</span></span>

<span data-ttu-id="631e4-124">Можно отображать и изменять значения переменных среды без использования командлета с помощью переменных синтаксиса в поставщике среды.</span><span class="sxs-lookup"><span data-stu-id="631e4-124">You can display and change the values of environment variables without using a cmdlet by using a variable syntax with the environment provider.</span></span> <span data-ttu-id="631e4-125">Чтобы отобразить значение переменной среды, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="631e4-125">To display the value of an environment variable, use the following syntax:</span></span>

```
$Env:<variable-name>
```

<span data-ttu-id="631e4-126">Например, чтобы отобразить значение `WINDIR` переменной среды, введите в командной строке PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="631e4-126">For example, to display the value of the `WINDIR` environment variable, type the following command at the PowerShell command prompt:</span></span>

```powershell
$Env:windir
```

<span data-ttu-id="631e4-127">В этом синтаксисе знак доллара ( `$` ) указывает на переменную, а имя диска ( `Env:` ) указывает на переменную среды, за которой следует имя переменной ( `windir` ).</span><span class="sxs-lookup"><span data-stu-id="631e4-127">In this syntax, the dollar sign (`$`) indicates a variable, and the drive name (`Env:`) indicates an environment variable followed by the variable name (`windir`).</span></span>

<span data-ttu-id="631e4-128">Изменение переменных среды в PowerShell влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="631e4-128">When you change environment variables in PowerShell, the change affects only the current session.</span></span> <span data-ttu-id="631e4-129">Это поведение напоминает поведение `Set` команды в командной оболочке Windows и `Setenv` команду в средах на базе UNIX.</span><span class="sxs-lookup"><span data-stu-id="631e4-129">This behavior resembles the behavior of the `Set` command in the Windows Command Shell and the `Setenv` command in UNIX-based environments.</span></span> <span data-ttu-id="631e4-130">Чтобы изменить значения в областях компьютера или пользователя, необходимо использовать методы класса **System. Environment** .</span><span class="sxs-lookup"><span data-stu-id="631e4-130">To change values in the Machine or User scopes, you must use the methods of the **System.Environment** class.</span></span>

<span data-ttu-id="631e4-131">Чтобы внести изменения в переменные на уровне компьютера, необходимо также иметь разрешение.</span><span class="sxs-lookup"><span data-stu-id="631e4-131">To make changes to Machine-scoped variables, must also have permission.</span></span> <span data-ttu-id="631e4-132">Если вы попытаетесь изменить значение без достаточных разрешений, команда завершится ошибкой, и в PowerShell отобразится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="631e4-132">If you try to change a value without sufficient permission, the command fails and PowerShell displays an error.</span></span>

<span data-ttu-id="631e4-133">Можно изменить значения переменных без использования командлета, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="631e4-133">You can change the values of variables without using a cmdlet using the following syntax:</span></span>

```powershell
$Env:<variable-name> = "<new-value>"
```

<span data-ttu-id="631e4-134">Например, чтобы добавить `;c:\temp` к значению `Path` переменной среды, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="631e4-134">For example, to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
$Env:Path += ";c:\temp"
```

<span data-ttu-id="631e4-135">В Linux или MacOS двоеточие ( `:` ) в команде отделяет новый путь от пути, расположенного перед ним в списке.</span><span class="sxs-lookup"><span data-stu-id="631e4-135">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

```powershell
$Env:PATH += ":/usr/local/temp"
```

<span data-ttu-id="631e4-136">Можно также использовать командлеты Item, такие как `Set-Item` , `Remove-Item` и, `Copy-Item` чтобы изменить значения переменных среды.</span><span class="sxs-lookup"><span data-stu-id="631e4-136">You can also use the Item cmdlets, such as `Set-Item`, `Remove-Item`, and `Copy-Item` to change the values of environment variables.</span></span> <span data-ttu-id="631e4-137">Например, чтобы использовать `Set-Item` командлет для добавления `;c:\temp` к значению `Path` переменной среды, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="631e4-137">For example, to use the `Set-Item` cmdlet to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
Set-Item -Path Env:Path -Value ($Env:Path + ";C:\Temp")
```

<span data-ttu-id="631e4-138">В этой команде значение заключается в круглые скобки, чтобы интерпретироваться как единое целое.</span><span class="sxs-lookup"><span data-stu-id="631e4-138">In this command, the value is enclosed in parentheses so that it is interpreted as a unit.</span></span>

## <a name="environment-variables-that-store-preferences"></a><span data-ttu-id="631e4-139">Переменные среды, в которых хранятся настройки</span><span class="sxs-lookup"><span data-stu-id="631e4-139">Environment variables that store preferences</span></span>

<span data-ttu-id="631e4-140">Функции PowerShell могут использовать переменные среды для хранения настроек пользователя.</span><span class="sxs-lookup"><span data-stu-id="631e4-140">PowerShell features can use environment variables to store user preferences.</span></span>
<span data-ttu-id="631e4-141">Эти переменные работают подобно переменным предпочтений, но они наследуются дочерними сеансами сеансов, в которых они созданы.</span><span class="sxs-lookup"><span data-stu-id="631e4-141">These variables work like preference variables, but they are inherited by child sessions of the sessions in which they are created.</span></span> <span data-ttu-id="631e4-142">Дополнительные сведения о переменных предпочтений см. в разделе [about_preference_variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="631e4-142">For more information about preference variables, see [about_preference_variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="631e4-143">Ниже перечислены переменные среды, в которых хранятся настройки.</span><span class="sxs-lookup"><span data-stu-id="631e4-143">The environment variables that store preferences include:</span></span>

- <span data-ttu-id="631e4-144">PSExecutionPolicyPreference</span><span class="sxs-lookup"><span data-stu-id="631e4-144">PSExecutionPolicyPreference</span></span>

  <span data-ttu-id="631e4-145">Хранит политику выполнения, заданную для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="631e4-145">Stores the execution policy set for the current session.</span></span> <span data-ttu-id="631e4-146">Эта переменная среды существует только в том случае, если задана политика выполнения для одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="631e4-146">This environment variable exists only when you set an execution policy for a single session.</span></span>
  <span data-ttu-id="631e4-147">Это можно сделать двумя разными способами.</span><span class="sxs-lookup"><span data-stu-id="631e4-147">You can do this in two different ways.</span></span>

  - <span data-ttu-id="631e4-148">Запустите сеанс из командной строки с помощью параметра **ExecutionPolicy** , чтобы задать политику выполнения для сеанса.</span><span class="sxs-lookup"><span data-stu-id="631e4-148">Start a session from the command line using the **ExecutionPolicy** parameter to set the execution policy for the session.</span></span>

  - <span data-ttu-id="631e4-149">Используйте командлет `Set-ExecutionPolicy`.</span><span class="sxs-lookup"><span data-stu-id="631e4-149">Use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="631e4-150">Используйте параметр Scope со значением "Process".</span><span class="sxs-lookup"><span data-stu-id="631e4-150">Use the Scope parameter with a value of "Process".</span></span>

    <span data-ttu-id="631e4-151">Подробнее см. в разделе [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="631e4-151">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

- <span data-ttu-id="631e4-152">псмодулеаналисискачепас</span><span class="sxs-lookup"><span data-stu-id="631e4-152">PSModuleAnalysisCachePath</span></span>

  <span data-ttu-id="631e4-153">PowerShell обеспечивает контроль над файлом, используемым для кэширования данных о модулях и их командлетах.</span><span class="sxs-lookup"><span data-stu-id="631e4-153">PowerShell provides control over the file that is used to cache data about modules and their cmdlets.</span></span> <span data-ttu-id="631e4-154">Кэш считывается при запуске во время поиска команды и записывается в фоновом потоке после импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="631e4-154">The cache is read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

  <span data-ttu-id="631e4-155">Расположение кэша по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="631e4-155">Default location of the cache is:</span></span>

  - <span data-ttu-id="631e4-156">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="631e4-156">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span></span>
  - <span data-ttu-id="631e4-157">PowerShell 6,0 и более поздние версии: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="631e4-157">PowerShell 6.0 and higher: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span></span>
  - <span data-ttu-id="631e4-158">По умолчанию не для Windows: `~/.cache/powershell`</span><span class="sxs-lookup"><span data-stu-id="631e4-158">Non-Windows default: `~/.cache/powershell`</span></span>

  <span data-ttu-id="631e4-159">По умолчанию для кэша используется имя файла `ModuleAnalysisCache` .</span><span class="sxs-lookup"><span data-stu-id="631e4-159">The default filename for the cache is `ModuleAnalysisCache`.</span></span> <span data-ttu-id="631e4-160">Если установлено несколько экземпляров PowerShell, имя файла включает в себя шестнадцатеричный суффикс, чтобы для каждой установки существовало уникальное имя файла.</span><span class="sxs-lookup"><span data-stu-id="631e4-160">When you have multiple instances of PowerShell installed, the filename includes a hexadecimal suffix so that there is a a unique filename per installation.</span></span>

  > [!NOTE]
  > <span data-ttu-id="631e4-161">Если обнаружение команд работает неправильно, например, в IntelliSense отображаются несуществующие команды, можно удалить файл кэша.</span><span class="sxs-lookup"><span data-stu-id="631e4-161">If command discovery isn't working correctly, for example Intellisense shows commands that don't exist, you can delete the cache file.</span></span> <span data-ttu-id="631e4-162">Кэш создается повторно при следующем запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631e4-162">The cache is recreated the next time you start PowerShell.</span></span>

  <span data-ttu-id="631e4-163">Чтобы изменить расположение кэша по умолчанию, задайте переменную среды перед запуском PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631e4-163">To change the default location of the cache, set the environment variable before starting PowerShell.</span></span> <span data-ttu-id="631e4-164">Изменения этой переменной среды влияют только на дочерние процессы.</span><span class="sxs-lookup"><span data-stu-id="631e4-164">Changes to this environment variable only affect child processes.</span></span> <span data-ttu-id="631e4-165">Значение должно быть полным путем (включая имя файла), на создание и запись файлов по которому у среды PowerShell есть разрешение.</span><span class="sxs-lookup"><span data-stu-id="631e4-165">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span>

  <span data-ttu-id="631e4-166">Чтобы отключить файловый кэш, укажите в качестве этого значения недопустимое расположение, например:</span><span class="sxs-lookup"><span data-stu-id="631e4-166">To disable the file cache, set this value to an invalid location, for example:</span></span>

  ```powershell
  # `NUL` here is a special device on Windows that cannot be written to,
  # on non-Windows you would use `/dev/null`
  $env:PSModuleAnalysisCachePath = 'NUL'
  ```

  <span data-ttu-id="631e4-167">Это задает путь к устройству **NUL** .</span><span class="sxs-lookup"><span data-stu-id="631e4-167">This sets the path to the **NUL** device.</span></span> <span data-ttu-id="631e4-168">PowerShell не удается выполнить запись в путь, но ошибка не возвращается.</span><span class="sxs-lookup"><span data-stu-id="631e4-168">PowerShell can't write to the path but no error is returned.</span></span> <span data-ttu-id="631e4-169">Вы можете увидеть ошибки, о которых сообщили с помощью трассировки:</span><span class="sxs-lookup"><span data-stu-id="631e4-169">You can see the errors reported using a tracer:</span></span>

  ```powershell
  Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
  ```

- <span data-ttu-id="631e4-170">псдисаблемодулеаналисискачеклеануп</span><span class="sxs-lookup"><span data-stu-id="631e4-170">PSDisableModuleAnalysisCacheCleanup</span></span>

  <span data-ttu-id="631e4-171">При вызаписи кэша анализа модуля PowerShell проверяет наличие модулей, которые больше не существуют, чтобы избежать необязательного большого объема кэша.</span><span class="sxs-lookup"><span data-stu-id="631e4-171">When writing out the module analysis cache, PowerShell checks for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="631e4-172">Иногда эти проверки нежелательны. в этом случае их можно отключить, задав для этого значения переменной среды значение `1` .</span><span class="sxs-lookup"><span data-stu-id="631e4-172">Sometimes these checks are not desirable, in which case you can turn them off by setting this environment variable value to `1`.</span></span>

  <span data-ttu-id="631e4-173">Установка этой переменной среды вступает в силу немедленно в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="631e4-173">Setting this environment variable takes effect immediately in the current process.</span></span>

- <span data-ttu-id="631e4-174">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="631e4-174">PSModulePath</span></span>

  <span data-ttu-id="631e4-175">`$env:PSModulePath`Переменная среды содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="631e4-175">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

  <span data-ttu-id="631e4-176">По умолчанию действующие расположения, назначенные, `$env:PSModulePath` являются:</span><span class="sxs-lookup"><span data-stu-id="631e4-176">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

  - <span data-ttu-id="631e4-177">Расположения на уровне системы. Эти папки содержат модули, поставляемые с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631e4-177">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="631e4-178">Модули хранятся в `$PSHOME\Modules` расположении.</span><span class="sxs-lookup"><span data-stu-id="631e4-178">The modules are store in the `$PSHOME\Modules` location.</span></span> <span data-ttu-id="631e4-179">Кроме того, это расположение, в котором устанавливаются модули управления Windows.</span><span class="sxs-lookup"><span data-stu-id="631e4-179">Also, This is the location where the Windows management modules are installed.</span></span>

  - <span data-ttu-id="631e4-180">Модули, установленные пользователем: это модули, установленные пользователем.</span><span class="sxs-lookup"><span data-stu-id="631e4-180">User-installed modules: These are modules installed by the user.</span></span>
    <span data-ttu-id="631e4-181">`Install-Module` имеет параметр **области** , который позволяет указать, установлен ли модуль для текущего пользователя или для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="631e4-181">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="631e4-182">Дополнительные сведения см. в разделе [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="631e4-182">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

    - <span data-ttu-id="631e4-183">В Windows расположением определяемой пользователем области **CurrentUser** является `$HOME\Documents\PowerShell\Modules` Папка.</span><span class="sxs-lookup"><span data-stu-id="631e4-183">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="631e4-184">Областью **ALLUSERS** является расположение `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="631e4-184">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
    - <span data-ttu-id="631e4-185">В системах, отличных от Windows, расположением определяемой пользователем области **CurrentUser** является `$HOME/.local/share/powershell/Modules` Папка.</span><span class="sxs-lookup"><span data-stu-id="631e4-185">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="631e4-186">Областью **ALLUSERS** является расположение `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="631e4-186">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

  <span data-ttu-id="631e4-187">Кроме того, программы установки, устанавливающие модули в других каталогах, например каталог Program Files, могут добавлять свои расположения к значению `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="631e4-187">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

  <span data-ttu-id="631e4-188">Дополнительные сведения см. в разделе [about_PSModulePath](about_PSModulePath.md).</span><span class="sxs-lookup"><span data-stu-id="631e4-188">For more information, see [about_PSModulePath](about_PSModulePath.md).</span></span>

## <a name="managing-environment-variables"></a><span data-ttu-id="631e4-189">Управление переменными среды</span><span class="sxs-lookup"><span data-stu-id="631e4-189">Managing environment variables</span></span>

<span data-ttu-id="631e4-190">PowerShell предоставляет несколько различных методов для управления переменными среды.</span><span class="sxs-lookup"><span data-stu-id="631e4-190">PowerShell provides several different methods for managing environment variables.</span></span>

- <span data-ttu-id="631e4-191">Диск поставщика среды</span><span class="sxs-lookup"><span data-stu-id="631e4-191">The Environment provider drive</span></span>
- <span data-ttu-id="631e4-192">Командлеты элементов</span><span class="sxs-lookup"><span data-stu-id="631e4-192">The Item cmdlets</span></span>
- <span data-ttu-id="631e4-193">Класс .NET **System. Environment**</span><span class="sxs-lookup"><span data-stu-id="631e4-193">The .NET **System.Environment** class</span></span>
- <span data-ttu-id="631e4-194">В Windows Панель управления системы</span><span class="sxs-lookup"><span data-stu-id="631e4-194">On Windows, the System Control Panel</span></span>

### <a name="using-the-environment-provider"></a><span data-ttu-id="631e4-195">Использование поставщика среды</span><span class="sxs-lookup"><span data-stu-id="631e4-195">Using the Environment provider</span></span>

<span data-ttu-id="631e4-196">Каждая переменная среды представлена экземпляром класса **System. Collections. DictionaryEntry** .</span><span class="sxs-lookup"><span data-stu-id="631e4-196">Each environment variable is represented by an instance of the **System.Collections.DictionaryEntry** class.</span></span> <span data-ttu-id="631e4-197">В каждом объекте **DictionaryEntry** имя переменной среды является ключом словаря.</span><span class="sxs-lookup"><span data-stu-id="631e4-197">In each **DictionaryEntry** object, the name of the environment variable is the dictionary key.</span></span> <span data-ttu-id="631e4-198">Значением переменной является значение словаря.</span><span class="sxs-lookup"><span data-stu-id="631e4-198">The value of the variable is the dictionary value.</span></span>

<span data-ttu-id="631e4-199">Чтобы отобразить свойства и методы объекта, представляющего переменную среды в PowerShell, используйте `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="631e4-199">To display the properties and methods of the object that represents an environment variable in PowerShell, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="631e4-200">Например, чтобы отобразить методы и свойства всех объектов на `Env:` диске, введите:</span><span class="sxs-lookup"><span data-stu-id="631e4-200">For example, to display the methods and properties of all the objects in the `Env:` drive, type:</span></span>

```powershell
Get-Item -Path Env:* | Get-Member
```

<span data-ttu-id="631e4-201">Поставщик среды PowerShell позволяет получить доступ к переменным среды на диске PowerShell ( `Env:` диск).</span><span class="sxs-lookup"><span data-stu-id="631e4-201">The PowerShell Environment provider lets you access environment variables in a PowerShell drive (the `Env:` drive).</span></span> <span data-ttu-id="631e4-202">Этот диск выглядит примерно так же, как диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="631e4-202">This drive looks much like a file system drive.</span></span> <span data-ttu-id="631e4-203">Чтобы открыть `Env:` диск, введите:</span><span class="sxs-lookup"><span data-stu-id="631e4-203">To go to the `Env:` drive, type:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="631e4-204">Используйте командлеты Content, чтобы получить или задать значения переменной среды.</span><span class="sxs-lookup"><span data-stu-id="631e4-204">Use the Content cmdlets to get or set the values of an environment variable.</span></span>

```powershell
PS Env:\> Set-Content -Path Test -Value 'Test value'
PS Env:\> Get-Content -Path Test
Test value
```

<span data-ttu-id="631e4-205">Можно просмотреть переменные среды на `Env:` диске с любого другого диска PowerShell, а также можно перейти на `Env:` диск, чтобы просмотреть и изменить переменные среды.</span><span class="sxs-lookup"><span data-stu-id="631e4-205">You can view the environment variables in the `Env:` drive from any other PowerShell drive, and you can go into the `Env:` drive to view and change the environment variables.</span></span>

### <a name="using-item-cmdlets"></a><span data-ttu-id="631e4-206">Использование командлетов Item</span><span class="sxs-lookup"><span data-stu-id="631e4-206">Using Item cmdlets</span></span>

<span data-ttu-id="631e4-207">При ссылке на переменную среды введите `Env:` имя диска, за которым следует имя переменной.</span><span class="sxs-lookup"><span data-stu-id="631e4-207">When you refer to an environment variable, type the `Env:` drive name followed by the name of the variable.</span></span> <span data-ttu-id="631e4-208">Например, чтобы отобразить значение `COMPUTERNAME` переменной среды, введите:</span><span class="sxs-lookup"><span data-stu-id="631e4-208">For example, to display the value of the `COMPUTERNAME` environment variable, type:</span></span>

```powershell
Get-ChildItem Env:Computername
```

<span data-ttu-id="631e4-209">Чтобы отобразить значения всех переменных среды, введите:</span><span class="sxs-lookup"><span data-stu-id="631e4-209">To display the values of all the environment variables, type:</span></span>

```powershell
Get-ChildItem Env:
```

<span data-ttu-id="631e4-210">Так как переменные среды не имеют дочерних элементов, выходные данные `Get-Item` и `Get-ChildItem` одинаковы.</span><span class="sxs-lookup"><span data-stu-id="631e4-210">Because environment variables do not have child items, the output of `Get-Item` and `Get-ChildItem` is the same.</span></span>

<span data-ttu-id="631e4-211">По умолчанию PowerShell отображает переменные среды в том порядке, в котором они извлекаются.</span><span class="sxs-lookup"><span data-stu-id="631e4-211">By default, PowerShell displays the environment variables in the order in which it retrieves them.</span></span> <span data-ttu-id="631e4-212">Чтобы отсортировать список переменных среды по имени переменной, необходимо передать выходные данные `Get-ChildItem` команды в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="631e4-212">To sort the list of environment variables by variable name, pipe the output of a `Get-ChildItem` command to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="631e4-213">Например, с любого диска PowerShell введите:</span><span class="sxs-lookup"><span data-stu-id="631e4-213">For example, from any PowerShell drive, type:</span></span>

```powershell
Get-ChildItem Env: | Sort Name
```

<span data-ttu-id="631e4-214">Вы также можете войти на `Env:` диск с помощью `Set-Location` командлета:</span><span class="sxs-lookup"><span data-stu-id="631e4-214">You can also go into the `Env:` drive by using the `Set-Location` cmdlet:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="631e4-215">Если вы используете `Env:` диск, можно опустить `Env:` имя диска из пути.</span><span class="sxs-lookup"><span data-stu-id="631e4-215">When you are in the `Env:` drive, you can omit the `Env:` drive name from the path.</span></span> <span data-ttu-id="631e4-216">Например, чтобы отобразить все переменные среды, введите:</span><span class="sxs-lookup"><span data-stu-id="631e4-216">For example, to display all the environment variables, type:</span></span>

```powershell
PS Env:\> Get-ChildItem
```

<span data-ttu-id="631e4-217">Чтобы отобразить значение `COMPUTERNAME` переменной в пределах `Env:` диска, введите:</span><span class="sxs-lookup"><span data-stu-id="631e4-217">To display the value of the `COMPUTERNAME` variable from within the `Env:` drive, type:</span></span>

```powershell
PS Env:\> Get-ChildItem ComputerName
```

### <a name="saving-changes-to-environment-variables"></a><span data-ttu-id="631e4-218">Сохранение изменений в переменных среды</span><span class="sxs-lookup"><span data-stu-id="631e4-218">Saving changes to environment variables</span></span>

<span data-ttu-id="631e4-219">Чтобы внести постоянное изменение в переменную среды в Windows, используйте панель управления "система".</span><span class="sxs-lookup"><span data-stu-id="631e4-219">To make a persistent change to an environment variable on Windows, use the System Control Panel.</span></span> <span data-ttu-id="631e4-220">Выберите **Дополнительные параметры системы**.</span><span class="sxs-lookup"><span data-stu-id="631e4-220">Select **Advanced System Settings**.</span></span> <span data-ttu-id="631e4-221">На вкладке **Дополнительно** щелкните **переменная среды...**. Можно добавлять или изменять существующие переменные среды в области **пользователя** и **системы** (компьютера).</span><span class="sxs-lookup"><span data-stu-id="631e4-221">On the **Advanced** tab, click **Environment Variable...**. You can add or edit existing environment variables in the **User** and **System** (Machine) scopes.</span></span> <span data-ttu-id="631e4-222">Windows записывает эти значения в реестр, чтобы они сохранялись в сеансах и перезапусках системы.</span><span class="sxs-lookup"><span data-stu-id="631e4-222">Windows writes these values to the Registry so that they persist across sessions and system restarts.</span></span>

<span data-ttu-id="631e4-223">Кроме того, можно добавить или изменить переменные среды в профиле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631e4-223">Alternately, you can add or change environment variables in your PowerShell profile.</span></span> <span data-ttu-id="631e4-224">Этот метод работает для любой версии PowerShell на любой поддерживаемой платформе.</span><span class="sxs-lookup"><span data-stu-id="631e4-224">This method works for any version of PowerShell on any supported platform.</span></span>

### <a name="using-systemenvironment-methods"></a><span data-ttu-id="631e4-225">Использование методов System. Environment</span><span class="sxs-lookup"><span data-stu-id="631e4-225">Using System.Environment methods</span></span>

<span data-ttu-id="631e4-226">Класс **System. Environment** предоставляет методы **GetEnvironmentVariable** и **SetEnvironmentVariable** , позволяющие указать область действия переменной.</span><span class="sxs-lookup"><span data-stu-id="631e4-226">The **System.Environment** class provides **GetEnvironmentVariable** and **SetEnvironmentVariable** methods that allow you to specify the scope of the variable.</span></span>

<span data-ttu-id="631e4-227">В следующем примере метод **GetEnvironmentVariable** используется для получения параметра компьютера, `PSModulePath` а метод **SetEnvironmentVariable** — для добавления `C:\Program Files\Fabrikam\Modules` пути к значению.</span><span class="sxs-lookup"><span data-stu-id="631e4-227">The following example uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable("PSModulePath", $newpath, 'Machine')
```

<span data-ttu-id="631e4-228">Дополнительные сведения о методах класса **System. Environment** см. в разделе [методы среды](/dotnet/api/system.environment).</span><span class="sxs-lookup"><span data-stu-id="631e4-228">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="see-also"></a><span data-ttu-id="631e4-229">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="631e4-229">SEE ALSO</span></span>

- [<span data-ttu-id="631e4-230">Среда (поставщик)</span><span class="sxs-lookup"><span data-stu-id="631e4-230">Environment (provider)</span></span>](../About/about_Environment_Provider.md)
- [<span data-ttu-id="631e4-231">about_Modules</span><span class="sxs-lookup"><span data-stu-id="631e4-231">about_Modules</span></span>](about_Modules.md)

