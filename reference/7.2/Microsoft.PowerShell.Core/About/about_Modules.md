---
description: Объясняет, как устанавливать, импортировать и использовать модули PowerShell.
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: b98c8b27b68c213ac43fbd350ecd920f813dec6b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "99605292"
---
# <a name="about-modules"></a><span data-ttu-id="56db3-103">О модулях</span><span class="sxs-lookup"><span data-stu-id="56db3-103">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="56db3-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="56db3-104">Short Description</span></span>
<span data-ttu-id="56db3-105">Объясняет, как устанавливать, импортировать и использовать модули PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-105">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="56db3-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="56db3-106">Long Description</span></span>

<span data-ttu-id="56db3-107">Модуль — это пакет, содержащий члены PowerShell, такие как командлеты, поставщики, функции, рабочие процессы, переменные и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="56db3-107">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="56db3-108">Составляя команды, пользователи могут организовывать их с помощью модулей и передавать их другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="56db3-108">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="56db3-109">Пользователи, получающие модули, могут добавлять команды в модули в свои сеансы PowerShell и использовать их так же, как и встроенные команды.</span><span class="sxs-lookup"><span data-stu-id="56db3-109">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="56db3-110">В этом разделе объясняется, как использовать модули PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-110">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="56db3-111">Сведения о том, как создавать модули PowerShell, см. в разделе [написание модуля PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="56db3-111">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="56db3-112">Что такое модуль?</span><span class="sxs-lookup"><span data-stu-id="56db3-112">What Is a Module?</span></span>

<span data-ttu-id="56db3-113">Модуль — это пакет, содержащий члены PowerShell, такие как командлеты, поставщики, функции, рабочие процессы, переменные и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="56db3-113">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span> <span data-ttu-id="56db3-114">Члены этого пакета могут быть реализованы в сценарии PowerShell, скомпилированной библиотеке DLL или в сочетании обоих типов.</span><span class="sxs-lookup"><span data-stu-id="56db3-114">The members of this package can be implemented in a PowerShell script, a compiled DLL, or a combination of both.</span></span> <span data-ttu-id="56db3-115">Эти файлы обычно группируются в один каталог.</span><span class="sxs-lookup"><span data-stu-id="56db3-115">These files are usually grouped together in a single directory.</span></span> <span data-ttu-id="56db3-116">Дополнительные сведения см. в разделе [понятие о модуле Windows PowerShell](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) в документации по пакету SDK.</span><span class="sxs-lookup"><span data-stu-id="56db3-116">For more information, see [Understanding a Windows PowerShell Module](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) in the SDK documentation.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="56db3-117">Автоматическая загрузка модуля</span><span class="sxs-lookup"><span data-stu-id="56db3-117">Module Auto-Loading</span></span>

<span data-ttu-id="56db3-118">Начиная с PowerShell 3,0, PowerShell автоматически импортирует модули при первом выполнении любой команды в установленном модуле.</span><span class="sxs-lookup"><span data-stu-id="56db3-118">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="56db3-119">Теперь для использования команд в модуле не требуется выполнять установку или настройку профиля, поэтому необходимость управления модулями после их установки на компьютере отпадает.</span><span class="sxs-lookup"><span data-stu-id="56db3-119">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="56db3-120">Также упрощен поиск команд в модуле.</span><span class="sxs-lookup"><span data-stu-id="56db3-120">The commands in a module are also easier to find.</span></span> <span data-ttu-id="56db3-121">`Get-Command`Теперь командлет получает все команды во всех установленных модулях, даже если они еще не находятся в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-121">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session.</span></span> <span data-ttu-id="56db3-122">Вы можете найти команду и использовать ее без импорта, чтобы сначала импортировать модуль.</span><span class="sxs-lookup"><span data-stu-id="56db3-122">You can find a command and use it without importing needing to import the module first.</span></span>

<span data-ttu-id="56db3-123">В каждом из приведенных ниже примеров модуль Цимкмдлетс, который содержит `Get-CimInstance` , будет импортирован в сеанс.</span><span class="sxs-lookup"><span data-stu-id="56db3-123">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="56db3-124">Выполните команду</span><span class="sxs-lookup"><span data-stu-id="56db3-124">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="56db3-125">Получение команды</span><span class="sxs-lookup"><span data-stu-id="56db3-125">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="56db3-126">Получение справки по команде</span><span class="sxs-lookup"><span data-stu-id="56db3-126">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="56db3-127">`Get-Command` команды, содержащие подстановочный знак ( `*` ), считаются для обнаружения, не используют и не импортируют модули.</span><span class="sxs-lookup"><span data-stu-id="56db3-127">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="56db3-128">Автоматически импортируются только те модули, которые хранятся в расположении, указанном в переменной среды PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="56db3-128">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="56db3-129">Модули в других расположениях необходимо импортировать, выполнив `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="56db3-129">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="56db3-130">Кроме того, команды, использующие поставщики PowerShell, не импортируют модуль автоматически.</span><span class="sxs-lookup"><span data-stu-id="56db3-130">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="56db3-131">Например, если вы используете команду, для которой требуется диск WSMan:, например `Get-PSSessionConfiguration` командлет, может потребоваться выполнить `Import-Module` командлет, чтобы импортировать модуль **Microsoft. WSMan. Management** , включающий `WSMan:` диск.</span><span class="sxs-lookup"><span data-stu-id="56db3-131">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="56db3-132">Вы по-прежнему можете выполнить `Import-Module` команду, чтобы импортировать модуль и использовать `$PSModuleAutoloadingPreference` переменную для включения, отключения и настройки автоматического импорта модулей.</span><span class="sxs-lookup"><span data-stu-id="56db3-132">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="56db3-133">Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="56db3-133">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="56db3-134">Как использовать модуль</span><span class="sxs-lookup"><span data-stu-id="56db3-134">How to Use a Module</span></span>

<span data-ttu-id="56db3-135">Чтобы воспользоваться модулем, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="56db3-135">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="56db3-136">Установите модуль.</span><span class="sxs-lookup"><span data-stu-id="56db3-136">Install the module.</span></span> <span data-ttu-id="56db3-137">(Обычно это выполняется автоматически.)</span><span class="sxs-lookup"><span data-stu-id="56db3-137">(This is often done for you.)</span></span>
1. <span data-ttu-id="56db3-138">Найдите команды, которые добавил модуль.</span><span class="sxs-lookup"><span data-stu-id="56db3-138">Find the commands that the module added.</span></span>
1. <span data-ttu-id="56db3-139">Теперь вы можете использовать эти команды.</span><span class="sxs-lookup"><span data-stu-id="56db3-139">Use the commands that the module added.</span></span>

<span data-ttu-id="56db3-140">В данном разделе описано, как выполнить эти задачи.</span><span class="sxs-lookup"><span data-stu-id="56db3-140">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="56db3-141">В нем также содержатся другие полезные сведения об управлении модулями.</span><span class="sxs-lookup"><span data-stu-id="56db3-141">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="56db3-142">Установка модуля</span><span class="sxs-lookup"><span data-stu-id="56db3-142">How to Install a Module</span></span>

<span data-ttu-id="56db3-143">Если вы получаете модуль в качестве папки с файлами в нем, его необходимо установить на компьютере, прежде чем его можно будет использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-143">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="56db3-144">Обычно модули устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="56db3-144">Most modules are installed for you.</span></span> <span data-ttu-id="56db3-145">PowerShell поставляется с несколькими предварительно установленными модулями, которые иногда называют _основными_ модулями.</span><span class="sxs-lookup"><span data-stu-id="56db3-145">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="56db3-146">На компьютерах под управлением Windows, если компоненты, включенные в операционную систему, имеют командлеты для управления ими, эти модули предварительно устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="56db3-146">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="56db3-147">При установке компонента Windows с помощью, например, мастера добавления ролей и компонентов в диспетчер сервера или в диалоговом окне Включение или отключение компонентов Windows на панели управления, устанавливаются все модули PowerShell, которые являются частью компонента.</span><span class="sxs-lookup"><span data-stu-id="56db3-147">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="56db3-148">Многие модули поставляются с программой установки, выполняющей установку модуля.</span><span class="sxs-lookup"><span data-stu-id="56db3-148">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="56db3-149">Чтобы создать каталог **modules** для текущего пользователя, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56db3-149">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="56db3-150">Полностью скопируйте папку модуля в каталог Modules.</span><span class="sxs-lookup"><span data-stu-id="56db3-150">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="56db3-151">Для копирования папки можно использовать любой метод, в том числе проводник Windows и Cmd.exe, а также PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-151">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="56db3-152">В PowerShell используйте `Copy-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="56db3-152">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="56db3-153">Например, чтобы скопировать папку MyModule из `C:\ps-test\MyModule` в каталог modules, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-153">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="56db3-154">Установить модуль можно в любое местоположение, однако если всегда устанавливать их в местоположение модулей по умолчанию, ими проще управлять.</span><span class="sxs-lookup"><span data-stu-id="56db3-154">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="56db3-155">Дополнительные сведения о расположениях модулей по умолчанию см. в разделе [модули и расположения ресурсов DSC и PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) .</span><span class="sxs-lookup"><span data-stu-id="56db3-155">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="56db3-156">Поиск установленных модулей</span><span class="sxs-lookup"><span data-stu-id="56db3-156">How to Find Installed Modules</span></span>

<span data-ttu-id="56db3-157">Чтобы найти модули, установленные в местоположении модулей по умолчанию, но еще не импортированные в сеанс, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="56db3-157">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="56db3-158">Чтобы найти модули, которые уже были импортированы в сеанс, в командной строке PowerShell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56db3-158">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="56db3-159">Дополнительные сведения о `Get-Module` командлете см. в разделе [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="56db3-159">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="56db3-160">Как найти команды в модуле</span><span class="sxs-lookup"><span data-stu-id="56db3-160">How to Find the Commands in a Module</span></span>

<span data-ttu-id="56db3-161">Используйте `Get-Command` командлет, чтобы найти все доступные команды.</span><span class="sxs-lookup"><span data-stu-id="56db3-161">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="56db3-162">Параметры `Get-Command` командлета можно использовать для фильтрации команд, таких как Module, Name и существительное.</span><span class="sxs-lookup"><span data-stu-id="56db3-162">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="56db3-163">Чтобы найти все команды в модуле, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-163">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="56db3-164">Например, чтобы найти команды в модуле BitsTransfer, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-164">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="56db3-165">Дополнительные сведения о `Get-Command` командлете см. в разделе [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span><span class="sxs-lookup"><span data-stu-id="56db3-165">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="56db3-166">Получение справки по командам в модуле</span><span class="sxs-lookup"><span data-stu-id="56db3-166">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="56db3-167">Если модуль содержит файлы справки для экспортируемых команд, то в `Get-Help` командлете будут отображаться разделы справки.</span><span class="sxs-lookup"><span data-stu-id="56db3-167">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="56db3-168">Используйте тот же `Get-Help` Формат команды, который используется для получения справки по любой команде в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-168">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="56db3-169">Начиная с PowerShell 3,0 можно скачать файлы справки для модуля и загрузить обновления в файлы справки, чтобы они никогда не были устаревшими.</span><span class="sxs-lookup"><span data-stu-id="56db3-169">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="56db3-170">Чтобы найти раздел справки по содержащимся в модуле командам, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="56db3-170">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="56db3-171">Чтобы получить справку в Интернете для команды в модуле, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-171">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="56db3-172">Чтобы скачать и установить файлы справки для команд в модуле, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-172">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="56db3-173">Дополнительные сведения см. в разделе [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) и [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span><span class="sxs-lookup"><span data-stu-id="56db3-173">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="56db3-174">Импорт модуля</span><span class="sxs-lookup"><span data-stu-id="56db3-174">How to Import a Module</span></span>

<span data-ttu-id="56db3-175">Может потребоваться выполнить импорт модуля или файла модуля.</span><span class="sxs-lookup"><span data-stu-id="56db3-175">You might have to import a module or import a module file.</span></span> <span data-ttu-id="56db3-176">Импорт требуется, если модуль не установлен в расположениях, указанных в переменной среды **PSModulePath** , `$env:PSModulePath` или модуль состоит из файла, такого как DLL или PSM1, вместо обычного модуля, который доставляется в виде папки.</span><span class="sxs-lookup"><span data-stu-id="56db3-176">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="56db3-177">Можно также импортировать модуль, чтобы можно было использовать параметры `Import-Module` команды, такие как параметр prefix, который добавляет отличительный префикс к именам существительных всех импортированных команд или параметр **NoClobber** , который предотвращает добавление в модуль команд, которые скрывают или заменяют существующие команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-177">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="56db3-178">Чтобы импортировать модули, используйте `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="56db3-178">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="56db3-179">Чтобы импортировать модули в расположении PSModulePath в текущий сеанс, используйте следующий формат команды.</span><span class="sxs-lookup"><span data-stu-id="56db3-179">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="56db3-180">Например, следующая команда импортирует модуль BitsTransfer в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="56db3-180">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="56db3-181">Чтобы импортировать модуль, не находящийся в местоположении по умолчанию, укажите в команде полный путь к папке этого модуля.</span><span class="sxs-lookup"><span data-stu-id="56db3-181">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="56db3-182">Например, чтобы добавить модуль TestCmdlets в `C:\ps-test` Каталог сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-182">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="56db3-183">Чтобы импортировать файл модуля, который не расположен в папке модуля, укажите в команде полный путь к файлу модуля.</span><span class="sxs-lookup"><span data-stu-id="56db3-183">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="56db3-184">Например, чтобы добавить модуль TestCmdlets.dll в `C:\ps-test` Каталог сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-184">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="56db3-185">Дополнительные сведения о добавлении модулей в сеанс см. в разделе [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="56db3-185">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="56db3-186">Импорт модуля в каждый сеанс</span><span class="sxs-lookup"><span data-stu-id="56db3-186">How to Import a Module into Every Session</span></span>

<span data-ttu-id="56db3-187">`Import-Module`Команда импортирует модули в текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-187">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="56db3-188">Чтобы импортировать модуль в каждый запущенный сеанс PowerShell, добавьте `Import-Module` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-188">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="56db3-189">Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="56db3-189">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="56db3-190">Удаление модуля</span><span class="sxs-lookup"><span data-stu-id="56db3-190">How to Remove a Module</span></span>

<span data-ttu-id="56db3-191">Если удалить модуль, добавленные им команды удаляются из сеанса.</span><span class="sxs-lookup"><span data-stu-id="56db3-191">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="56db3-192">Чтобы удалить модуль из сеанса, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="56db3-192">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="56db3-193">Например, следующая команда удаляет модуль BitsTransfer из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="56db3-193">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="56db3-194">Удаление модуля отменяет операцию импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="56db3-194">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="56db3-195">При этом установка модуля не отменяется.</span><span class="sxs-lookup"><span data-stu-id="56db3-195">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="56db3-196">Дополнительные сведения см. в разделе [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="56db3-196">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="56db3-197">Расположение модулей и ресурсов DSC, а PSModulePath</span><span class="sxs-lookup"><span data-stu-id="56db3-197">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="56db3-198">`$env:PSModulePath`Переменная среды содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="56db3-198">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="56db3-199">По умолчанию действующие расположения, назначенные, `$env:PSModulePath` являются:</span><span class="sxs-lookup"><span data-stu-id="56db3-199">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="56db3-200">Расположение на уровне системы: `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="56db3-200">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="56db3-201">Эти папки содержат модули, поставляемые с Windows и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-201">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="56db3-202">Ресурсы DSC, входящие в состав PowerShell, хранятся в `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` папке.</span><span class="sxs-lookup"><span data-stu-id="56db3-202">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="56db3-203">Пользовательские модули: это модули, устанавливаемые пользователем в области пользователя.</span><span class="sxs-lookup"><span data-stu-id="56db3-203">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="56db3-204">`Install-Module` имеет параметр **области** , который позволяет указать, установлен ли модуль для текущего пользователя или для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="56db3-204">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="56db3-205">Дополнительные сведения см. в разделе [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="56db3-205">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="56db3-206">Расположение **CurrentUser** для конкретного пользователя в Windows — это `PowerShell\Modules` Папка, расположенная в папке **Documents** в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="56db3-206">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="56db3-207">Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок.</span><span class="sxs-lookup"><span data-stu-id="56db3-207">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="56db3-208">Microsoft OneDrive также может изменить расположение папки **документов** .</span><span class="sxs-lookup"><span data-stu-id="56db3-208">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="56db3-209">По умолчанию в Windows 10 это расположение имеет значение `$HOME\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="56db3-209">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="56db3-210">В Linux или Mac расположение **CurrentUser** — `$HOME/.local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="56db3-210">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="56db3-211">Расположение папки **документов** можно проверить с помощью следующей команды: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="56db3-211">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="56db3-212">Расположение **ALLUSERS** находится `$env:PROGRAMFILES\PowerShell\Modules` в Windows.</span><span class="sxs-lookup"><span data-stu-id="56db3-212">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="56db3-213">В Linux или Mac модули хранятся в `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="56db3-213">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="56db3-214">Чтобы добавить или изменить файлы в `$env:Windir\System32` каталоге, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="56db3-214">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="56db3-215">Вы можете изменить расположение модулей по умолчанию в системе, изменив значение переменной среды **PSModulePath** , `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="56db3-215">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="56db3-216">Переменная среды **PSModulePath** моделируется в переменной среды PATH и имеет тот же формат.</span><span class="sxs-lookup"><span data-stu-id="56db3-216">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="56db3-217">Чтобы отобразить местоположения модулей по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56db3-217">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="56db3-218">Чтобы добавить местоположение модулей по умолчанию, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="56db3-218">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="56db3-219">Точка с запятой ( `;` ) в команде отделяет новый путь от пути, расположенного перед ним в списке.</span><span class="sxs-lookup"><span data-stu-id="56db3-219">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="56db3-220">Например, чтобы добавить `C:\ps-test\Modules` каталог, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-220">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="56db3-221">Чтобы добавить расположение модуля по умолчанию в Linux или MacOS, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="56db3-221">To add a default module location on Linux or MacOS, use the following command format:</span></span>

```powershell
$Env:PSModulePath += ":<path>"
```

<span data-ttu-id="56db3-222">Например, чтобы добавить `/usr/local/Fabrikam/Modules` Каталог к значению переменной среды **PSModulePath** , введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-222">For example, to add the `/usr/local/Fabrikam/Modules` directory to the value of the **PSModulePath** environment variable, type:</span></span>

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

<span data-ttu-id="56db3-223">В Linux или MacOS двоеточие ( `:` ) в команде отделяет новый путь от пути, расположенного перед ним в списке.</span><span class="sxs-lookup"><span data-stu-id="56db3-223">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="56db3-224">При добавлении пути к **PSModulePath** `Get-Module` `Import-Module` команды также включают модули в этом пути.</span><span class="sxs-lookup"><span data-stu-id="56db3-224">When you add a path to **PSModulePath**, `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="56db3-225">Задаваемое значение влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="56db3-225">The value that you set affects only the current session.</span></span> <span data-ttu-id="56db3-226">Чтобы сделать это изменение постоянным, добавьте команду в профиль PowerShell или используйте элемент система на панели управления, чтобы изменить значение переменной среды **PSModulePath** в реестре.</span><span class="sxs-lookup"><span data-stu-id="56db3-226">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="56db3-227">Кроме того, чтобы сделать это изменение постоянным, можно также использовать метод **SetEnvironmentVariable** класса **System. Environment** , чтобы добавить путь к переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="56db3-227">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="56db3-228">Дополнительные сведения о переменной **PSModulePath** см. в разделе [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="56db3-228">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="56db3-229">Конфликты модулей и имен</span><span class="sxs-lookup"><span data-stu-id="56db3-229">Modules and Name Conflicts</span></span>

<span data-ttu-id="56db3-230">Конфликт имен происходит, когда в сеансе имеется несколько команд с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="56db3-230">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="56db3-231">При импорте модуля возникает конфликт имен, если содержащиеся в нем команды имеют такие же имена, как команды или элементы, уже имеющиеся в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-231">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="56db3-232">Конфликты имен могут возникать в результате скрытия или замены команд.</span><span class="sxs-lookup"><span data-stu-id="56db3-232">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="56db3-233">Скрытый</span><span class="sxs-lookup"><span data-stu-id="56db3-233">Hidden</span></span>

<span data-ttu-id="56db3-234">Скрытой называется команда, не выполняемая при вводе ее имени, но выполняемая другими способами (например, с указанием имени модуля или оснастки, из которой добавлена команда).</span><span class="sxs-lookup"><span data-stu-id="56db3-234">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="56db3-235">Замененный текст</span><span class="sxs-lookup"><span data-stu-id="56db3-235">Replaced</span></span>

<span data-ttu-id="56db3-236">Замененной называется команда, которую невозможно выполнить, поскольку поверх нее записана команда с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="56db3-236">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="56db3-237">Даже если удалить модуль, являющийся причиной конфликта, выполнить замененную команду можно только после перезапуска сеанса.</span><span class="sxs-lookup"><span data-stu-id="56db3-237">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="56db3-238">`Import-Module` может добавлять команды, которые скрывают и заменяют команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-238">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="56db3-239">Кроме того, команды в текущем сеансе могут скрыть команды, добавленные модулем.</span><span class="sxs-lookup"><span data-stu-id="56db3-239">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="56db3-240">Чтобы обнаружить конфликты имен, используйте параметр **ALL** `Get-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="56db3-240">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="56db3-241">Начиная с PowerShell 3,0, `Get-Command` получает только те команды, которые выполняются при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="56db3-241">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="56db3-242">Параметр **ALL** получает все команды с указанным именем в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-242">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="56db3-243">Чтобы предотвратить конфликты имен, используйте параметры **NoClobber** или **prefix** `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="56db3-243">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="56db3-244">Параметр **prefix** добавляет префикс к именам импортированных команд, чтобы они были уникальными в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-244">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="56db3-245">Параметр **NoClobber** не импортирует команды, которые скрывают или заменяют существующие команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-245">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="56db3-246">Можно также использовать параметры **псевдонима**, **командлета**, **функции** и **переменной** , `Import-Module` чтобы выбрать только те команды, которые необходимо импортировать, а также исключить команды, вызывающие конфликты имен в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56db3-246">You can also use the **Alias**, **Cmdlet**, **Function**, and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="56db3-247">Авторы модулей могут предотвратить конфликты имен, используя свойство **DefaultCommandPrefix** манифеста модуля для добавления префикса по умолчанию ко всем именам команд.</span><span class="sxs-lookup"><span data-stu-id="56db3-247">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="56db3-248">Значение параметра **prefix** имеет приоритет над значением **DefaultCommandPrefix**.</span><span class="sxs-lookup"><span data-stu-id="56db3-248">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix**.</span></span>

<span data-ttu-id="56db3-249">Даже если команда скрыта, можно выполнить ее, указав (помимо ее имени) имя модуля или оснастки, из которой она добавлена.</span><span class="sxs-lookup"><span data-stu-id="56db3-249">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="56db3-250">Правила очередности команд PowerShell определяют, какие команды выполняются, когда сеанс включает команды с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="56db3-250">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="56db3-251">Например, если сеанс включает функцию и командлет с тем же именем, по умолчанию PowerShell выполняет эту функцию.</span><span class="sxs-lookup"><span data-stu-id="56db3-251">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="56db3-252">Если сеанс содержит команды одинакового типа (например, два командлета) с одинаковым именем, по умолчанию выполняется команда, добавленная последней.</span><span class="sxs-lookup"><span data-stu-id="56db3-252">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="56db3-253">Дополнительные сведения, включая описание правил приоритета и инструкции по выполнению скрытых команд, см. в разделе [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="56db3-253">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="56db3-254">Модули и оснастки</span><span class="sxs-lookup"><span data-stu-id="56db3-254">Modules and Snap-ins</span></span>

<span data-ttu-id="56db3-255">В сеанс можно добавлять команды из модулей и оснасток. Модули могут добавлять все типы команд, в том числе командлеты, поставщики и функции, а также элементы, такие как переменные, псевдонимы и диски PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-255">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="56db3-256">Из оснасток можно добавлять только командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="56db3-256">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="56db3-257">Прежде чем удалить модуль или оснастку из сеанса, с помощью следующих команд определите, какие команды будут при этом удалены</span><span class="sxs-lookup"><span data-stu-id="56db3-257">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="56db3-258">Чтобы найти источник командлета в сеансе, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="56db3-258">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="56db3-259">Например, чтобы найти источник `Get-Date` командлета, введите:</span><span class="sxs-lookup"><span data-stu-id="56db3-259">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="56db3-260">Предупреждения и ошибки, связанные с модулем</span><span class="sxs-lookup"><span data-stu-id="56db3-260">Module-related Warnings and Errors</span></span>

<span data-ttu-id="56db3-261">Команды, экспортируемые модулем, должны следовать правилам именования команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-261">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="56db3-262">Если импортируемый модуль экспортирует командлеты или функции с неодобренными командами в именах, `Import-Module` командлет выводит следующее предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="56db3-262">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="56db3-263">ПРЕДУПРЕЖДЕНИЕ. Некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="56db3-263">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="56db3-264">Чтобы получить подробные сведения, используйте параметр Verbose, или введите Get-Verb, чтобы просмотреть список утвержденных команд.</span><span class="sxs-lookup"><span data-stu-id="56db3-264">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="56db3-265">Это сообщение является всего лишь предупреждением.</span><span class="sxs-lookup"><span data-stu-id="56db3-265">This message is only a warning.</span></span> <span data-ttu-id="56db3-266">Импорт осуществляется для всего модуля, включая недопустимые команды.</span><span class="sxs-lookup"><span data-stu-id="56db3-266">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="56db3-267">Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.</span><span class="sxs-lookup"><span data-stu-id="56db3-267">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="56db3-268">Чтобы отключить предупреждающее сообщение, используйте параметр **DisableNameChecking** `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="56db3-268">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="56db3-269">Встроенные модули и оснастки</span><span class="sxs-lookup"><span data-stu-id="56db3-269">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="56db3-270">В PowerShell 2,0 и в более старых основных программах в PowerShell 3,0 и более поздних версиях основные команды, устанавливаемые с помощью PowerShell, упаковываются в оснастки, которые автоматически добавляются во все сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-270">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="56db3-271">Начиная с PowerShell 3,0, для ведущих программ, которые реализуют `InitialSessionState.CreateDefault2` начальный API состояния сеанса, оснастка Microsoft. PowerShell. Core добавляется в каждый сеанс по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="56db3-271">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="56db3-272">Модули загружаются автоматически при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="56db3-272">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="56db3-273">Удаленные сеансы, включая сеансы, запущенные с помощью `New-PSSession` командлета, — это сеансы предыдущих версий, в которых встроенные команды упаковываются в оснастки.</span><span class="sxs-lookup"><span data-stu-id="56db3-273">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="56db3-274">Следующие модули (или оснастки) устанавливаются с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-274">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="56db3-275">CimCmdlets</span><span class="sxs-lookup"><span data-stu-id="56db3-275">CimCmdlets</span></span>
- <span data-ttu-id="56db3-276">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="56db3-276">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="56db3-277">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="56db3-277">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="56db3-278">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="56db3-278">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="56db3-279">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="56db3-279">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="56db3-280">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="56db3-280">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="56db3-281">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="56db3-281">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="56db3-282">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="56db3-282">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="56db3-283">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="56db3-283">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="56db3-284">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="56db3-284">PackageManagement</span></span>
- <span data-ttu-id="56db3-285">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="56db3-285">PowerShellGet</span></span>
- <span data-ttu-id="56db3-286">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="56db3-286">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="56db3-287">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="56db3-287">PSDiagnostics</span></span>
- <span data-ttu-id="56db3-288">PSReadline</span><span class="sxs-lookup"><span data-stu-id="56db3-288">PSReadline</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="56db3-289">События модуля ведения журнала</span><span class="sxs-lookup"><span data-stu-id="56db3-289">Logging Module Events</span></span>

<span data-ttu-id="56db3-290">Начиная с версии PowerShell 3,0 можно записывать события выполнения для командлетов и функций в модулях PowerShell и оснастках, установив свойство **LogPipelineExecutionDetails** модулей и оснасток в значение `$True` .</span><span class="sxs-lookup"><span data-stu-id="56db3-290">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="56db3-291">Можно также использовать параметр групповая политика, включить ведение журнала модуля, чтобы включить ведение журнала модуля во всех сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56db3-291">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="56db3-292">Дополнительные сведения см. в статьях ведение журналов и групповая политика.</span><span class="sxs-lookup"><span data-stu-id="56db3-292">For more information, see the logging and group policy articles.</span></span>

## <a name="see-also"></a><span data-ttu-id="56db3-293">См. также:</span><span class="sxs-lookup"><span data-stu-id="56db3-293">See Also</span></span>

[<span data-ttu-id="56db3-294">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="56db3-294">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="56db3-295">about_Logging_Non — Windows</span><span class="sxs-lookup"><span data-stu-id="56db3-295">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="56db3-296">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="56db3-296">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="56db3-297">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="56db3-297">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="56db3-298">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="56db3-298">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="56db3-299">Get-Command</span><span class="sxs-lookup"><span data-stu-id="56db3-299">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="56db3-300">Get-Help</span><span class="sxs-lookup"><span data-stu-id="56db3-300">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="56db3-301">Get-Module</span><span class="sxs-lookup"><span data-stu-id="56db3-301">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="56db3-302">Import-Module</span><span class="sxs-lookup"><span data-stu-id="56db3-302">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="56db3-303">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="56db3-303">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
