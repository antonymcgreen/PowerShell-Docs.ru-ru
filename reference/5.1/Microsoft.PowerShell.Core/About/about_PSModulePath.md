---
description: Переменная среды PSModulePath содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSModulePath
ms.openlocfilehash: 60373e534fb319195c187b8cb26c6aabc0f3b8b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231998"
---
# <a name="about-psmodulepath"></a><span data-ttu-id="bfd2d-104">О PSModulePath</span><span class="sxs-lookup"><span data-stu-id="bfd2d-104">About PSModulePath</span></span>

<span data-ttu-id="bfd2d-105">`$env:PSModulePath`Переменная среды содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-105">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="bfd2d-106">По умолчанию действующие расположения, назначенные, `$env:PSModulePath` являются:</span><span class="sxs-lookup"><span data-stu-id="bfd2d-106">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="bfd2d-107">Расположения на уровне системы. Эти папки содержат модули, поставляемые с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-107">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="bfd2d-108">Эти модули хранятся в `$PSHOME\Modules` папке.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-108">These modules are store in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="bfd2d-109">Это также расположение, в котором установлены модули управления Windows.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-109">This is also the location where the Windows management modules are installed.</span></span>

- <span data-ttu-id="bfd2d-110">Модули, установленные пользователем: это модули, установленные пользователем.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-110">User-installed modules: These are modules installed by the user.</span></span>
  <span data-ttu-id="bfd2d-111">`Install-Module` имеет параметр **области** , который позволяет указать, установлен ли модуль для текущего пользователя или для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-111">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="bfd2d-112">Дополнительные сведения см. в разделе [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="bfd2d-112">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  - <span data-ttu-id="bfd2d-113">В Windows расположением определяемой пользователем области **CurrentUser** является `$HOME\Documents\PowerShell\Modules` Папка.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-113">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="bfd2d-114">Областью **ALLUSERS** является расположение `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-114">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
  - <span data-ttu-id="bfd2d-115">В системах, отличных от Windows, расположением определяемой пользователем области **CurrentUser** является `$HOME/.local/share/powershell/Modules` Папка.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-115">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="bfd2d-116">Областью **ALLUSERS** является расположение `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-116">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

<span data-ttu-id="bfd2d-117">Кроме того, программы установки, устанавливающие модули в других каталогах, например каталог Program Files, могут добавлять свои расположения к значению `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-117">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

> [!NOTE]
> <span data-ttu-id="bfd2d-118">В Windows пользовательское расположение — это `PowerShell\Modules` Папка, расположенная в папке **документы** в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-118">On Windows, the user-specific location is the `PowerShell\Modules` folder located in the **Documents** folder in your user profile.</span></span> <span data-ttu-id="bfd2d-119">Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-119">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="bfd2d-120">Microsoft OneDrive также может изменить расположение папки **документов** .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-120">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span> <span data-ttu-id="bfd2d-121">Расположение папки **документов** можно проверить с помощью следующей команды: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-121">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

## <a name="modifying-psmodulepath"></a><span data-ttu-id="bfd2d-122">Изменение PSModulePath</span><span class="sxs-lookup"><span data-stu-id="bfd2d-122">Modifying PSModulePath</span></span>

<span data-ttu-id="bfd2d-123">Чтобы изменить каталоги модулей по умолчанию для текущего сеанса, используйте следующий формат команды, чтобы изменить значение `PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-123">To change the default module directories for the current session, use the following command format to change the value of the `PSModulePath` environment variable.</span></span>

<span data-ttu-id="bfd2d-124">Например, чтобы добавить `C:\Program Files\Fabrikam\Modules` Каталог к значению переменной среды PSModulePath, введите:</span><span class="sxs-lookup"><span data-stu-id="bfd2d-124">For example, to add the `C:\Program Files\Fabrikam\Modules` directory to the value of the PSModulePath environment variable, type:</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

<span data-ttu-id="bfd2d-125">Точка с запятой ( `;` ) в команде отделяет новый путь от пути, расположенного перед ним в списке.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-125">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span> <span data-ttu-id="bfd2d-126">На платформах, отличных от Windows, двоеточие ( `:` ) разделяет расположения путей в переменной среды.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-126">On non-Windows platforms, the colon (`:`) separates the path locations in the environment variable.</span></span>

<span data-ttu-id="bfd2d-127">Чтобы изменить значение `PSModulePath` в каждом сеансе, добавьте предыдущую команду в профиль PowerShell или используйте метод **SetEnvironmentVariable** класса **Environment** .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-127">To change the value of `PSModulePath` in every session, add the previous command to your PowerShell profile or use the **SetEnvironmentVariable** method of the **Environment** class.</span></span>

<span data-ttu-id="bfd2d-128">Следующая команда использует метод **GetEnvironmentVariable** для получения параметра компьютера, `PSModulePath` а метод **SetEnvironmentVariable** — для добавления `C:\Program Files\Fabrikam\Modules` пути к значению.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-128">The following command uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

<span data-ttu-id="bfd2d-129">Чтобы добавить путь к пользовательскому параметру, измените целевое значение на " **пользователь** ".</span><span class="sxs-lookup"><span data-stu-id="bfd2d-129">To add a path to the user setting, change the target value to **User**.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

<span data-ttu-id="bfd2d-130">Дополнительные сведения о методах класса **System. Environment** см. в разделе [методы среды](/dotnet/api/system.environment).</span><span class="sxs-lookup"><span data-stu-id="bfd2d-130">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="powershell-psmodulepath-construction"></a><span data-ttu-id="bfd2d-131">Создание PSModulePath PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfd2d-131">PowerShell PSModulePath construction</span></span>

<span data-ttu-id="bfd2d-132">Значение формируется `$env:PSModulePath` каждый раз при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-132">The value of `$env:PSModulePath` is constructed each time PowerShell starts.</span></span>
<span data-ttu-id="bfd2d-133">Значение зависит от версии PowerShell и способа ее запуска.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-133">The value varies by version of PowerShell and how it is launched.</span></span>

### <a name="windows-powershell-startup"></a><span data-ttu-id="bfd2d-134">Запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfd2d-134">Windows PowerShell startup</span></span>

<span data-ttu-id="bfd2d-135">Windows PowerShell использует следующую логику для создания `PSModulePath` при запуске.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-135">Windows PowerShell uses the following logic to construct the `PSModulePath` at startup:</span></span>

- <span data-ttu-id="bfd2d-136">Если `PSModulePath` не существует, объедините пути **CurrentUser** , **ALLUSERS** и `$PSHOME` modules.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-136">If `PSModulePath` doesn't exist, combine **CurrentUser** , **AllUsers** , and the `$PSHOME` modules paths</span></span>
- <span data-ttu-id="bfd2d-137">Если `PSModulePath` существует:</span><span class="sxs-lookup"><span data-stu-id="bfd2d-137">If `PSModulePath` does exist:</span></span>
  - <span data-ttu-id="bfd2d-138">Если `PSModulePath` содержит `$PSHOME` путь к модулям:</span><span class="sxs-lookup"><span data-stu-id="bfd2d-138">If `PSModulePath` contains `$PSHOME` modules path:</span></span>
    - <span data-ttu-id="bfd2d-139">Путь к модулям **ALLUSERS** вставляется перед `$PSHOME` путем к модулям</span><span class="sxs-lookup"><span data-stu-id="bfd2d-139">**AllUsers** modules path is inserted before `$PSHOME` modules path</span></span>
  - <span data-ttu-id="bfd2d-140">Кроме</span><span class="sxs-lookup"><span data-stu-id="bfd2d-140">else:</span></span>
    - <span data-ttu-id="bfd2d-141">Просто используйте `PSModulePath` , как определено, так как пользователь намеренно удалил `$PSHOME` расположение.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-141">Just use `PSModulePath` as defined since the user deliberately removed the `$PSHOME` location</span></span>

<span data-ttu-id="bfd2d-142">Путь к модулю **CurrentUser** имеет префикс, только если область пользователя `$env:PSModulePath` не существует.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-142">The **CurrentUser** module path is prefixed only if User scope `$env:PSModulePath` doesn't exist.</span></span> <span data-ttu-id="bfd2d-143">В противном случае область пользователя `$env:PSModulePath` будет использоваться как определенная.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-143">Otherwise, the User scope `$env:PSModulePath` is used as defined.</span></span>

### <a name="powershell-core-6-startup"></a><span data-ttu-id="bfd2d-144">Запуск PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="bfd2d-144">PowerShell Core 6 startup</span></span>

<span data-ttu-id="bfd2d-145">PowerShell Core 6 не использует содержимое, `$env:PSModulePath` если обнаруживает, что оно было запущено из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-145">PowerShell Core 6 doesn't use contents of `$env:PSModulePath` if it detects it was started from PowerShell.</span></span> <span data-ttu-id="bfd2d-146">Он перезаписывает его следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bfd2d-146">It overwrites it with:</span></span>

- <span data-ttu-id="bfd2d-147">Модули **CurrentUser** путь + **ALLUSERS** модули путь + `$PSHOME` модули путь + `$PSHOME` путь к модулям Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-147">**CurrentUser** modules path + **AllUsers** modules path + `$PSHOME` modules path + Windows PowerShell `$PSHOME` modules path.</span></span>

### <a name="powershell-7-startup"></a><span data-ttu-id="bfd2d-148">Запуск PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="bfd2d-148">PowerShell 7 startup</span></span>

<span data-ttu-id="bfd2d-149">В Windows для большинства переменных среды, если переменная уровня пользователя существует, новый процесс использует это значение только в том случае, если переменная уровня компьютера с таким же именем существует.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-149">In Windows, for most environment variables, if the User-scoped variable exists, a new process uses that value only even if a Machine-scoped variable of the same name exists.</span></span>

<span data-ttu-id="bfd2d-150">В PowerShell 7 `PSModulePath` обрабатывается аналогично тому, как `Path` переменная среды обрабатывается в Windows.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-150">In PowerShell 7, `PSModulePath` is treated similar to how the `Path` environment variable is treated on Windows.</span></span> <span data-ttu-id="bfd2d-151">В Windows обрабатывается иначе, чем `Path` в других переменных среды.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-151">On Windows, `Path` is treated differently from other environment variables.</span></span> <span data-ttu-id="bfd2d-152">При запуске процесса Windows объединяет область пользователя `Path` с областью действия компьютера `Path` .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-152">When a process is started, Windows combines the User-scoped `Path` with the Machine-scoped `Path`.</span></span>

- <span data-ttu-id="bfd2d-153">Получение области пользователя `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="bfd2d-153">Retrieve the User-scoped `PSModulePath`</span></span>
- <span data-ttu-id="bfd2d-154">Сравнить с наследуемой `PSModulePath` переменной среды</span><span class="sxs-lookup"><span data-stu-id="bfd2d-154">Compare to process inherited `PSModulePath` environment variable</span></span>
  - <span data-ttu-id="bfd2d-155">Если это так:</span><span class="sxs-lookup"><span data-stu-id="bfd2d-155">If the same:</span></span>
    - <span data-ttu-id="bfd2d-156">Добавьте **ALLUSERS** `PSModulePath` в конец, следующий за семантикой `Path` переменной среды</span><span class="sxs-lookup"><span data-stu-id="bfd2d-156">Append the **AllUsers** `PSModulePath` to the end following the semantics of the `Path` environment variable</span></span>
    - <span data-ttu-id="bfd2d-157">Путь Windows `System32` берется из определенного компьютера, `PSModulePath` поэтому его не нужно добавлять явно.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-157">The Windows `System32` path comes from the machine defined `PSModulePath` so does not need to be added explicitly</span></span>
  - <span data-ttu-id="bfd2d-158">Если они отличаются, то следует рассматривать, как будто пользователь явно изменил его и не добавил **ALLUSERS**`PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="bfd2d-158">If different, treat as though user explicitly modified it and don't append **AllUsers** `PSModulePath`</span></span>
- <span data-ttu-id="bfd2d-159">Префикс с PS7 пользователя, системой и `$PSHOME` путями в этом порядке</span><span class="sxs-lookup"><span data-stu-id="bfd2d-159">Prefix with PS7 User, System, and `$PSHOME` paths in that order</span></span>
  - <span data-ttu-id="bfd2d-160">Если параметр `powershell.config.json` содержит пользовательскую область `PSModulePath` , используйте его вместо значения по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-160">If `powershell.config.json` contains a user scoped `PSModulePath`, use that instead of the default for the user</span></span>
  - <span data-ttu-id="bfd2d-161">Если `powershell.config.json` содержит область системы `PSModulePath` , используйте ее вместо значения по умолчанию для системы</span><span class="sxs-lookup"><span data-stu-id="bfd2d-161">If `powershell.config.json` contains a system scoped `PSModulePath`, use that instead of the default for the system</span></span>

<span data-ttu-id="bfd2d-162">В системах UNIX не существует разделения переменных среды пользователя и системы.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-162">Unix systems don't have a separation of User and System environment variables.</span></span>
<span data-ttu-id="bfd2d-163">`PSModulePath` является унаследованным, а пути, зависящие от PS7, являются префиксами, если они еще не определены.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-163">`PSModulePath` is inherited and the PS7-specific paths are prefixed if not already defined.</span></span>

### <a name="starting-windows-powershell-from-powershell-7"></a><span data-ttu-id="bfd2d-164">Запуск Windows PowerShell из PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="bfd2d-164">Starting Windows PowerShell from PowerShell 7</span></span>

<span data-ttu-id="bfd2d-165">В этом обсуждении _Windows PowerShell_ означает `powershell.exe` и, и `powershell_ise.exe` .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-165">For this discussion, _Windows PowerShell_ means both `powershell.exe` and `powershell_ise.exe`.</span></span>

<span data-ttu-id="bfd2d-166">Значение `$env:PSModulePath` копируется в `WinPSModulePath` со следующими изменениями:</span><span class="sxs-lookup"><span data-stu-id="bfd2d-166">The value of `$env:PSModulePath` is copied to `WinPSModulePath` with the following modifications:</span></span>

- <span data-ttu-id="bfd2d-167">Удалить PS7 путь к пользовательскому модулю</span><span class="sxs-lookup"><span data-stu-id="bfd2d-167">Remove PS7 the User module path</span></span>
- <span data-ttu-id="bfd2d-168">Удалить PS7 путь к системному модулю</span><span class="sxs-lookup"><span data-stu-id="bfd2d-168">Remove PS7 the System module path</span></span>
- <span data-ttu-id="bfd2d-169">Удалить PS7 в `$PSHOME` пути к модулю</span><span class="sxs-lookup"><span data-stu-id="bfd2d-169">Remove PS7 the `$PSHOME` module path</span></span>

<span data-ttu-id="bfd2d-170">Пути PS7 удаляются, чтобы модули PS7 не загружались в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-170">The PS7 paths are removed so that PS7 modules don't get loaded in Windows PowerShell.</span></span> <span data-ttu-id="bfd2d-171">`WinPSModulePath`Значение используется при запуске Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-171">The `WinPSModulePath` value is used when starting Windows PowerShell.</span></span>

### <a name="starting-powershell-7-from-windows-powershell"></a><span data-ttu-id="bfd2d-172">Запуск PowerShell 7 из Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfd2d-172">Starting PowerShell 7 from Windows PowerShell</span></span>

<span data-ttu-id="bfd2d-173">Запуск PowerShell 7 продолжится "как есть" с добавлением путей наследования, добавленных Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-173">The PowerShell 7 startup continues as-is with the addition of inheriting paths that Windows PowerShell added.</span></span> <span data-ttu-id="bfd2d-174">Так как пути, относящиеся к PS7, являются префиксами, функциональные проблемы отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-174">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

### <a name="starting-powershell-6-from-powershell-7"></a><span data-ttu-id="bfd2d-175">Запуск PowerShell 6 из PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="bfd2d-175">Starting PowerShell 6 from PowerShell 7</span></span>

<span data-ttu-id="bfd2d-176">PowerShell Core 6 перезаписывает `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="bfd2d-176">PowerShell Core 6 overwrites `$env:PSModulePath`.</span></span> <span data-ttu-id="bfd2d-177">Изменения не вносятся.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-177">No changes are made.</span></span>

### <a name="starting-powershell-7-from-powershell-6"></a><span data-ttu-id="bfd2d-178">Запуск PowerShell 7 из PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="bfd2d-178">Starting PowerShell 7 from PowerShell 6</span></span>

<span data-ttu-id="bfd2d-179">Запуск PowerShell 7 продолжится как есть с добавлением путей, добавленных PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-179">The PowerShell 7 startup continues as-is with the addition of inheriting paths that PowerShell Core 6 added.</span></span> <span data-ttu-id="bfd2d-180">Так как пути, относящиеся к PS7, являются префиксами, функциональные проблемы отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="bfd2d-180">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfd2d-181">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bfd2d-181">See also</span></span>

- [<span data-ttu-id="bfd2d-182">about_Modules</span><span class="sxs-lookup"><span data-stu-id="bfd2d-182">about_Modules</span></span>](about_Modules.md)
- [<span data-ttu-id="bfd2d-183">Методы среды</span><span class="sxs-lookup"><span data-stu-id="bfd2d-183">Environment Methods</span></span>](/dotnet/api/system.environment)
