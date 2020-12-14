---
description: Объясняет, как устанавливать, импортировать и использовать модули PowerShell.
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: 30af4ed84e2332aecd60838f3bcd7741965c2ba1
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564345"
---
# <a name="about-modules"></a><span data-ttu-id="567d1-103">О модулях</span><span class="sxs-lookup"><span data-stu-id="567d1-103">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="567d1-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="567d1-104">Short Description</span></span>
<span data-ttu-id="567d1-105">Объясняет, как устанавливать, импортировать и использовать модули PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-105">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="567d1-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="567d1-106">Long Description</span></span>

<span data-ttu-id="567d1-107">Модуль — это пакет, содержащий члены PowerShell, такие как командлеты, поставщики, функции, рабочие процессы, переменные и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="567d1-107">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="567d1-108">Составляя команды, пользователи могут организовывать их с помощью модулей и передавать их другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="567d1-108">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="567d1-109">Пользователи, получающие модули, могут добавлять команды в модули в свои сеансы PowerShell и использовать их так же, как и встроенные команды.</span><span class="sxs-lookup"><span data-stu-id="567d1-109">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="567d1-110">В этом разделе объясняется, как использовать модули PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-110">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="567d1-111">Сведения о том, как создавать модули PowerShell, см. в разделе [написание модуля PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="567d1-111">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="567d1-112">Что такое модуль?</span><span class="sxs-lookup"><span data-stu-id="567d1-112">What Is a Module?</span></span>

<span data-ttu-id="567d1-113">Модуль — это пакет, содержащий члены PowerShell, такие как командлеты, поставщики, функции, рабочие процессы, переменные и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="567d1-113">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span> <span data-ttu-id="567d1-114">Члены этого пакета могут быть реализованы в сценарии PowerShell, скомпилированной библиотеке DLL или в сочетании обоих типов.</span><span class="sxs-lookup"><span data-stu-id="567d1-114">The members of this package can be implemented in a PowerShell script, a compiled DLL, or a combination of both.</span></span> <span data-ttu-id="567d1-115">Эти файлы обычно группируются в один каталог.</span><span class="sxs-lookup"><span data-stu-id="567d1-115">These files are usually grouped together in a single directory.</span></span> <span data-ttu-id="567d1-116">Дополнительные сведения см. в разделе [понятие о модуле Windows PowerShell](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) в документации по пакету SDK.</span><span class="sxs-lookup"><span data-stu-id="567d1-116">For more information, see [Understanding a Windows PowerShell Module](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) in the SDK documentation.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="567d1-117">Автоматическая загрузка модуля</span><span class="sxs-lookup"><span data-stu-id="567d1-117">Module Auto-Loading</span></span>

<span data-ttu-id="567d1-118">Начиная с PowerShell 3,0, PowerShell автоматически импортирует модули при первом выполнении любой команды в установленном модуле.</span><span class="sxs-lookup"><span data-stu-id="567d1-118">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="567d1-119">Теперь для использования команд в модуле не требуется выполнять установку или настройку профиля, поэтому необходимость управления модулями после их установки на компьютере отпадает.</span><span class="sxs-lookup"><span data-stu-id="567d1-119">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="567d1-120">Также упрощен поиск команд в модуле.</span><span class="sxs-lookup"><span data-stu-id="567d1-120">The commands in a module are also easier to find.</span></span> <span data-ttu-id="567d1-121">`Get-Command`Теперь командлет получает все команды во всех установленных модулях, даже если они еще не находятся в сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-121">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session.</span></span> <span data-ttu-id="567d1-122">Вы можете найти команду и использовать ее без импорта, чтобы сначала импортировать модуль.</span><span class="sxs-lookup"><span data-stu-id="567d1-122">You can find a command and use it without importing needing to import the module first.</span></span>

<span data-ttu-id="567d1-123">В каждом из приведенных ниже примеров модуль Цимкмдлетс, который содержит `Get-CimInstance` , будет импортирован в сеанс.</span><span class="sxs-lookup"><span data-stu-id="567d1-123">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="567d1-124">Выполните команду</span><span class="sxs-lookup"><span data-stu-id="567d1-124">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="567d1-125">Получение команды</span><span class="sxs-lookup"><span data-stu-id="567d1-125">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="567d1-126">Получение справки по команде</span><span class="sxs-lookup"><span data-stu-id="567d1-126">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="567d1-127">`Get-Command` команды, содержащие подстановочный знак ( `*` ), считаются для обнаружения, не используют и не импортируют модули.</span><span class="sxs-lookup"><span data-stu-id="567d1-127">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="567d1-128">Автоматически импортируются только те модули, которые хранятся в расположении, указанном в переменной среды PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="567d1-128">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="567d1-129">Модули в других расположениях необходимо импортировать, выполнив `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="567d1-129">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="567d1-130">Кроме того, команды, использующие поставщики PowerShell, не импортируют модуль автоматически.</span><span class="sxs-lookup"><span data-stu-id="567d1-130">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="567d1-131">Например, если вы используете команду, для которой требуется диск WSMan:, например `Get-PSSessionConfiguration` командлет, может потребоваться выполнить `Import-Module` командлет, чтобы импортировать модуль **Microsoft. WSMan. Management** , включающий `WSMan:` диск.</span><span class="sxs-lookup"><span data-stu-id="567d1-131">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="567d1-132">Вы по-прежнему можете выполнить `Import-Module` команду, чтобы импортировать модуль и использовать `$PSModuleAutoloadingPreference` переменную для включения, отключения и настройки автоматического импорта модулей.</span><span class="sxs-lookup"><span data-stu-id="567d1-132">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="567d1-133">Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="567d1-133">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="567d1-134">Как использовать модуль</span><span class="sxs-lookup"><span data-stu-id="567d1-134">How to Use a Module</span></span>

<span data-ttu-id="567d1-135">Чтобы воспользоваться модулем, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="567d1-135">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="567d1-136">Установите модуль.</span><span class="sxs-lookup"><span data-stu-id="567d1-136">Install the module.</span></span> <span data-ttu-id="567d1-137">(Обычно это выполняется автоматически.)</span><span class="sxs-lookup"><span data-stu-id="567d1-137">(This is often done for you.)</span></span>
1. <span data-ttu-id="567d1-138">Найдите команды, которые добавил модуль.</span><span class="sxs-lookup"><span data-stu-id="567d1-138">Find the commands that the module added.</span></span>
1. <span data-ttu-id="567d1-139">Теперь вы можете использовать эти команды.</span><span class="sxs-lookup"><span data-stu-id="567d1-139">Use the commands that the module added.</span></span>

<span data-ttu-id="567d1-140">В данном разделе описано, как выполнить эти задачи.</span><span class="sxs-lookup"><span data-stu-id="567d1-140">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="567d1-141">В нем также содержатся другие полезные сведения об управлении модулями.</span><span class="sxs-lookup"><span data-stu-id="567d1-141">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="567d1-142">Установка модуля</span><span class="sxs-lookup"><span data-stu-id="567d1-142">How to Install a Module</span></span>

<span data-ttu-id="567d1-143">Если вы получаете модуль в качестве папки с файлами в нем, его необходимо установить на компьютере, прежде чем его можно будет использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-143">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="567d1-144">Обычно модули устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="567d1-144">Most modules are installed for you.</span></span> <span data-ttu-id="567d1-145">PowerShell поставляется с несколькими предварительно установленными модулями, которые иногда называют _основными_ модулями.</span><span class="sxs-lookup"><span data-stu-id="567d1-145">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="567d1-146">На компьютерах под управлением Windows, если компоненты, включенные в операционную систему, имеют командлеты для управления ими, эти модули предварительно устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="567d1-146">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="567d1-147">При установке компонента Windows с помощью, например, мастера добавления ролей и компонентов в диспетчер сервера или в диалоговом окне Включение или отключение компонентов Windows на панели управления, устанавливаются все модули PowerShell, которые являются частью компонента.</span><span class="sxs-lookup"><span data-stu-id="567d1-147">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="567d1-148">Многие модули поставляются с программой установки, выполняющей установку модуля.</span><span class="sxs-lookup"><span data-stu-id="567d1-148">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="567d1-149">Чтобы создать каталог **modules** для текущего пользователя, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="567d1-149">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\WindowsPowerShell\Modules
```

<span data-ttu-id="567d1-150">Полностью скопируйте папку модуля в каталог Modules.</span><span class="sxs-lookup"><span data-stu-id="567d1-150">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="567d1-151">Для копирования папки можно использовать любой метод, в том числе проводник Windows и Cmd.exe, а также PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-151">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="567d1-152">В PowerShell используйте `Copy-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="567d1-152">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="567d1-153">Например, чтобы скопировать папку MyModule из `C:\ps-test\MyModule` в каталог modules, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-153">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\WindowsPowerShell\Modules
```

<span data-ttu-id="567d1-154">Установить модуль можно в любое местоположение, однако если всегда устанавливать их в местоположение модулей по умолчанию, ими проще управлять.</span><span class="sxs-lookup"><span data-stu-id="567d1-154">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="567d1-155">Дополнительные сведения о расположениях модулей по умолчанию см. в разделе [модули и расположения ресурсов DSC и PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) .</span><span class="sxs-lookup"><span data-stu-id="567d1-155">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="567d1-156">Поиск установленных модулей</span><span class="sxs-lookup"><span data-stu-id="567d1-156">How to Find Installed Modules</span></span>

<span data-ttu-id="567d1-157">Чтобы найти модули, установленные в местоположении модулей по умолчанию, но еще не импортированные в сеанс, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="567d1-157">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="567d1-158">Чтобы найти модули, которые уже были импортированы в сеанс, в командной строке PowerShell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="567d1-158">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="567d1-159">Дополнительные сведения о `Get-Module` командлете см. в разделе [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="567d1-159">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="567d1-160">Как найти команды в модуле</span><span class="sxs-lookup"><span data-stu-id="567d1-160">How to Find the Commands in a Module</span></span>

<span data-ttu-id="567d1-161">Используйте `Get-Command` командлет, чтобы найти все доступные команды.</span><span class="sxs-lookup"><span data-stu-id="567d1-161">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="567d1-162">Параметры `Get-Command` командлета можно использовать для фильтрации команд, таких как Module, Name и существительное.</span><span class="sxs-lookup"><span data-stu-id="567d1-162">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="567d1-163">Чтобы найти все команды в модуле, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-163">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="567d1-164">Например, чтобы найти команды в модуле BitsTransfer, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-164">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="567d1-165">Дополнительные сведения о `Get-Command` командлете см. в разделе [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span><span class="sxs-lookup"><span data-stu-id="567d1-165">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="567d1-166">Получение справки по командам в модуле</span><span class="sxs-lookup"><span data-stu-id="567d1-166">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="567d1-167">Если модуль содержит файлы справки для экспортируемых команд, то в `Get-Help` командлете будут отображаться разделы справки.</span><span class="sxs-lookup"><span data-stu-id="567d1-167">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="567d1-168">Используйте тот же `Get-Help` Формат команды, который используется для получения справки по любой команде в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-168">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="567d1-169">Начиная с PowerShell 3,0 можно скачать файлы справки для модуля и загрузить обновления в файлы справки, чтобы они никогда не были устаревшими.</span><span class="sxs-lookup"><span data-stu-id="567d1-169">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="567d1-170">Чтобы найти раздел справки по содержащимся в модуле командам, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="567d1-170">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="567d1-171">Чтобы получить справку в Интернете для команды в модуле, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-171">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="567d1-172">Чтобы скачать и установить файлы справки для команд в модуле, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-172">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="567d1-173">Дополнительные сведения см. в разделе [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) и [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span><span class="sxs-lookup"><span data-stu-id="567d1-173">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="567d1-174">Импорт модуля</span><span class="sxs-lookup"><span data-stu-id="567d1-174">How to Import a Module</span></span>

<span data-ttu-id="567d1-175">Может потребоваться выполнить импорт модуля или файла модуля.</span><span class="sxs-lookup"><span data-stu-id="567d1-175">You might have to import a module or import a module file.</span></span> <span data-ttu-id="567d1-176">Импорт требуется, если модуль не установлен в расположениях, указанных в переменной среды **PSModulePath** , `$env:PSModulePath` или модуль состоит из файла, такого как DLL или PSM1, вместо обычного модуля, который доставляется в виде папки.</span><span class="sxs-lookup"><span data-stu-id="567d1-176">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="567d1-177">Можно также импортировать модуль, чтобы можно было использовать параметры `Import-Module` команды, такие как параметр prefix, который добавляет отличительный префикс к именам существительных всех импортированных команд или параметр **NoClobber** , который предотвращает добавление в модуль команд, которые скрывают или заменяют существующие команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-177">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="567d1-178">Чтобы импортировать модули, используйте `Import-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="567d1-178">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="567d1-179">Чтобы импортировать модули в расположении PSModulePath в текущий сеанс, используйте следующий формат команды.</span><span class="sxs-lookup"><span data-stu-id="567d1-179">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="567d1-180">Например, следующая команда импортирует модуль BitsTransfer в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="567d1-180">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="567d1-181">Чтобы импортировать модуль, не находящийся в местоположении по умолчанию, укажите в команде полный путь к папке этого модуля.</span><span class="sxs-lookup"><span data-stu-id="567d1-181">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="567d1-182">Например, чтобы добавить модуль TestCmdlets в `C:\ps-test` Каталог сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-182">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="567d1-183">Чтобы импортировать файл модуля, который не расположен в папке модуля, укажите в команде полный путь к файлу модуля.</span><span class="sxs-lookup"><span data-stu-id="567d1-183">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="567d1-184">Например, чтобы добавить модуль TestCmdlets.dll в `C:\ps-test` Каталог сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-184">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="567d1-185">Дополнительные сведения о добавлении модулей в сеанс см. в разделе [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="567d1-185">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="567d1-186">Импорт модуля в каждый сеанс</span><span class="sxs-lookup"><span data-stu-id="567d1-186">How to Import a Module into Every Session</span></span>

<span data-ttu-id="567d1-187">`Import-Module`Команда импортирует модули в текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-187">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="567d1-188">Чтобы импортировать модуль в каждый запущенный сеанс PowerShell, добавьте `Import-Module` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-188">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="567d1-189">Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="567d1-189">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="567d1-190">Удаление модуля</span><span class="sxs-lookup"><span data-stu-id="567d1-190">How to Remove a Module</span></span>

<span data-ttu-id="567d1-191">Если удалить модуль, добавленные им команды удаляются из сеанса.</span><span class="sxs-lookup"><span data-stu-id="567d1-191">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="567d1-192">Чтобы удалить модуль из сеанса, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="567d1-192">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="567d1-193">Например, следующая команда удаляет модуль BitsTransfer из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="567d1-193">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="567d1-194">Удаление модуля отменяет операцию импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="567d1-194">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="567d1-195">При этом установка модуля не отменяется.</span><span class="sxs-lookup"><span data-stu-id="567d1-195">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="567d1-196">Дополнительные сведения см. в разделе [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="567d1-196">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="567d1-197">Расположение модулей и ресурсов DSC, а PSModulePath</span><span class="sxs-lookup"><span data-stu-id="567d1-197">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="567d1-198">`$env:PSModulePath`Переменная среды содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="567d1-198">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="567d1-199">По умолчанию действующие расположения, назначенные, `$env:PSModulePath` являются:</span><span class="sxs-lookup"><span data-stu-id="567d1-199">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="567d1-200">Расположение на уровне системы: `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="567d1-200">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="567d1-201">Эти папки содержат модули, поставляемые с Windows и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-201">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="567d1-202">Ресурсы DSC, входящие в состав PowerShell, хранятся в `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` папке.</span><span class="sxs-lookup"><span data-stu-id="567d1-202">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="567d1-203">Пользовательские модули: это модули, устанавливаемые пользователем в области пользователя.</span><span class="sxs-lookup"><span data-stu-id="567d1-203">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="567d1-204">`Install-Module` имеет параметр **области** , который позволяет указать, установлен ли модуль для текущего пользователя или для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="567d1-204">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="567d1-205">Дополнительные сведения см. в разделе [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="567d1-205">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="567d1-206">Расположение **CurrentUser** для конкретного пользователя в Windows — это `PowerShell\Modules` Папка, расположенная в папке **Documents** в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="567d1-206">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="567d1-207">Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок.</span><span class="sxs-lookup"><span data-stu-id="567d1-207">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="567d1-208">Microsoft OneDrive также может изменить расположение папки **документов** .</span><span class="sxs-lookup"><span data-stu-id="567d1-208">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="567d1-209">По умолчанию в Windows 10 это расположение имеет значение `$HOME\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="567d1-209">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="567d1-210">В Linux или Mac расположение **CurrentUser** — `$HOME/.local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="567d1-210">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="567d1-211">Расположение папки **документов** можно проверить с помощью следующей команды: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="567d1-211">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="567d1-212">Расположение **ALLUSERS** находится `$env:PROGRAMFILES\PowerShell\Modules` в Windows.</span><span class="sxs-lookup"><span data-stu-id="567d1-212">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="567d1-213">В Linux или Mac модули хранятся в `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="567d1-213">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="567d1-214">Чтобы добавить или изменить файлы в `$env:Windir\System32` каталоге, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="567d1-214">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="567d1-215">Вы можете изменить расположение модулей по умолчанию в системе, изменив значение переменной среды **PSModulePath** , `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="567d1-215">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="567d1-216">Переменная среды **PSModulePath** моделируется в переменной среды PATH и имеет тот же формат.</span><span class="sxs-lookup"><span data-stu-id="567d1-216">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="567d1-217">Чтобы отобразить местоположения модулей по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="567d1-217">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="567d1-218">Чтобы добавить местоположение модулей по умолчанию, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="567d1-218">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="567d1-219">Точка с запятой ( `;` ) в команде отделяет новый путь от пути, расположенного перед ним в списке.</span><span class="sxs-lookup"><span data-stu-id="567d1-219">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="567d1-220">Например, чтобы добавить `C:\ps-test\Modules` каталог, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-220">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="567d1-221">При добавлении пути к **PSModulePath** `Get-Module` `Import-Module` команды также включают модули в этом пути.</span><span class="sxs-lookup"><span data-stu-id="567d1-221">When you add a path to **PSModulePath**, `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="567d1-222">Задаваемое значение влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="567d1-222">The value that you set affects only the current session.</span></span> <span data-ttu-id="567d1-223">Чтобы сделать это изменение постоянным, добавьте команду в профиль PowerShell или используйте элемент система на панели управления, чтобы изменить значение переменной среды **PSModulePath** в реестре.</span><span class="sxs-lookup"><span data-stu-id="567d1-223">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="567d1-224">Кроме того, чтобы сделать это изменение постоянным, можно также использовать метод **SetEnvironmentVariable** класса **System. Environment** , чтобы добавить путь к переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="567d1-224">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="567d1-225">Дополнительные сведения о переменной **PSModulePath** см. в разделе [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="567d1-225">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="567d1-226">Конфликты модулей и имен</span><span class="sxs-lookup"><span data-stu-id="567d1-226">Modules and Name Conflicts</span></span>

<span data-ttu-id="567d1-227">Конфликт имен происходит, когда в сеансе имеется несколько команд с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="567d1-227">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="567d1-228">При импорте модуля возникает конфликт имен, если содержащиеся в нем команды имеют такие же имена, как команды или элементы, уже имеющиеся в сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-228">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="567d1-229">Конфликты имен могут возникать в результате скрытия или замены команд.</span><span class="sxs-lookup"><span data-stu-id="567d1-229">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="567d1-230">Скрытый</span><span class="sxs-lookup"><span data-stu-id="567d1-230">Hidden</span></span>

<span data-ttu-id="567d1-231">Скрытой называется команда, не выполняемая при вводе ее имени, но выполняемая другими способами (например, с указанием имени модуля или оснастки, из которой добавлена команда).</span><span class="sxs-lookup"><span data-stu-id="567d1-231">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="567d1-232">Замененный текст</span><span class="sxs-lookup"><span data-stu-id="567d1-232">Replaced</span></span>

<span data-ttu-id="567d1-233">Замененной называется команда, которую невозможно выполнить, поскольку поверх нее записана команда с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="567d1-233">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="567d1-234">Даже если удалить модуль, являющийся причиной конфликта, выполнить замененную команду можно только после перезапуска сеанса.</span><span class="sxs-lookup"><span data-stu-id="567d1-234">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="567d1-235">`Import-Module` может добавлять команды, которые скрывают и заменяют команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-235">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="567d1-236">Кроме того, команды в текущем сеансе могут скрыть команды, добавленные модулем.</span><span class="sxs-lookup"><span data-stu-id="567d1-236">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="567d1-237">Чтобы обнаружить конфликты имен, используйте параметр **ALL** `Get-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="567d1-237">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="567d1-238">Начиная с PowerShell 3,0, `Get-Command` получает только те команды, которые выполняются при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="567d1-238">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="567d1-239">Параметр **ALL** получает все команды с указанным именем в сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-239">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="567d1-240">Чтобы предотвратить конфликты имен, используйте параметры **NoClobber** или **prefix** `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="567d1-240">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="567d1-241">Параметр **prefix** добавляет префикс к именам импортированных команд, чтобы они были уникальными в сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-241">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="567d1-242">Параметр **NoClobber** не импортирует команды, которые скрывают или заменяют существующие команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-242">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="567d1-243">Можно также использовать параметры **псевдонима**, **командлета**, **функции** и **переменной** , `Import-Module` чтобы выбрать только те команды, которые необходимо импортировать, а также исключить команды, вызывающие конфликты имен в сеансе.</span><span class="sxs-lookup"><span data-stu-id="567d1-243">You can also use the **Alias**, **Cmdlet**, **Function**, and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="567d1-244">Авторы модулей могут предотвратить конфликты имен, используя свойство **DefaultCommandPrefix** манифеста модуля для добавления префикса по умолчанию ко всем именам команд.</span><span class="sxs-lookup"><span data-stu-id="567d1-244">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="567d1-245">Значение параметра **prefix** имеет приоритет над значением **DefaultCommandPrefix**.</span><span class="sxs-lookup"><span data-stu-id="567d1-245">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix**.</span></span>

<span data-ttu-id="567d1-246">Даже если команда скрыта, можно выполнить ее, указав (помимо ее имени) имя модуля или оснастки, из которой она добавлена.</span><span class="sxs-lookup"><span data-stu-id="567d1-246">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="567d1-247">Правила очередности команд PowerShell определяют, какие команды выполняются, когда сеанс включает команды с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="567d1-247">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="567d1-248">Например, если сеанс включает функцию и командлет с тем же именем, по умолчанию PowerShell выполняет эту функцию.</span><span class="sxs-lookup"><span data-stu-id="567d1-248">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="567d1-249">Если сеанс содержит команды одинакового типа (например, два командлета) с одинаковым именем, по умолчанию выполняется команда, добавленная последней.</span><span class="sxs-lookup"><span data-stu-id="567d1-249">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="567d1-250">Дополнительные сведения, включая описание правил приоритета и инструкции по выполнению скрытых команд, см. в разделе [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="567d1-250">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="567d1-251">Модули и оснастки</span><span class="sxs-lookup"><span data-stu-id="567d1-251">Modules and Snap-ins</span></span>

<span data-ttu-id="567d1-252">В сеанс можно добавлять команды из модулей и оснасток. Модули могут добавлять все типы команд, в том числе командлеты, поставщики и функции, а также элементы, такие как переменные, псевдонимы и диски PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-252">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="567d1-253">Из оснасток можно добавлять только командлеты и поставщики.</span><span class="sxs-lookup"><span data-stu-id="567d1-253">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="567d1-254">Прежде чем удалить модуль или оснастку из сеанса, с помощью следующих команд определите, какие команды будут при этом удалены</span><span class="sxs-lookup"><span data-stu-id="567d1-254">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="567d1-255">Чтобы найти источник командлета в сеансе, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="567d1-255">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="567d1-256">Например, чтобы найти источник `Get-Date` командлета, введите:</span><span class="sxs-lookup"><span data-stu-id="567d1-256">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

<span data-ttu-id="567d1-257">Дополнительные сведения об оснастках PowerShell см. в разделе [about_PSSnapins](about_PSSnapins.md).</span><span class="sxs-lookup"><span data-stu-id="567d1-257">For more information about PowerShell snap-ins, see [about_PSSnapins](about_PSSnapins.md).</span></span>

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="567d1-258">Предупреждения и ошибки, связанные с модулем</span><span class="sxs-lookup"><span data-stu-id="567d1-258">Module-related Warnings and Errors</span></span>

<span data-ttu-id="567d1-259">Команды, экспортируемые модулем, должны следовать правилам именования команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-259">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="567d1-260">Если импортируемый модуль экспортирует командлеты или функции с неодобренными командами в именах, `Import-Module` командлет выводит следующее предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="567d1-260">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="567d1-261">ПРЕДУПРЕЖДЕНИЕ. Некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="567d1-261">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="567d1-262">Чтобы получить подробные сведения, используйте параметр Verbose, или введите Get-Verb, чтобы просмотреть список утвержденных команд.</span><span class="sxs-lookup"><span data-stu-id="567d1-262">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="567d1-263">Это сообщение является всего лишь предупреждением.</span><span class="sxs-lookup"><span data-stu-id="567d1-263">This message is only a warning.</span></span> <span data-ttu-id="567d1-264">Импорт осуществляется для всего модуля, включая недопустимые команды.</span><span class="sxs-lookup"><span data-stu-id="567d1-264">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="567d1-265">Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.</span><span class="sxs-lookup"><span data-stu-id="567d1-265">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="567d1-266">Чтобы отключить предупреждающее сообщение, используйте параметр **DisableNameChecking** `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="567d1-266">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="567d1-267">Встроенные модули и оснастки</span><span class="sxs-lookup"><span data-stu-id="567d1-267">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="567d1-268">В PowerShell 2,0 и в более старых основных программах в PowerShell 3,0 и более поздних версиях основные команды, устанавливаемые с помощью PowerShell, упаковываются в оснастки, которые автоматически добавляются во все сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-268">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="567d1-269">Начиная с PowerShell 3,0, для ведущих программ, которые реализуют `InitialSessionState.CreateDefault2` начальный API состояния сеанса, оснастка Microsoft. PowerShell. Core добавляется в каждый сеанс по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="567d1-269">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="567d1-270">Модули загружаются автоматически при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="567d1-270">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="567d1-271">Удаленные сеансы, включая сеансы, запущенные с помощью `New-PSSession` командлета, — это сеансы предыдущих версий, в которых встроенные команды упаковываются в оснастки.</span><span class="sxs-lookup"><span data-stu-id="567d1-271">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="567d1-272">Следующие модули (или оснастки) устанавливаются с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-272">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="567d1-273">CimCmdlets</span><span class="sxs-lookup"><span data-stu-id="567d1-273">CimCmdlets</span></span>
- <span data-ttu-id="567d1-274">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="567d1-274">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="567d1-275">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="567d1-275">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="567d1-276">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="567d1-276">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="567d1-277">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="567d1-277">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="567d1-278">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="567d1-278">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="567d1-279">Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="567d1-279">Microsoft.PowerShell.ODataUtils</span></span>
- <span data-ttu-id="567d1-280">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="567d1-280">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="567d1-281">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="567d1-281">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="567d1-282">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="567d1-282">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="567d1-283">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="567d1-283">PackageManagement</span></span>
- <span data-ttu-id="567d1-284">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="567d1-284">PowerShellGet</span></span>
- <span data-ttu-id="567d1-285">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="567d1-285">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="567d1-286">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="567d1-286">PSDiagnostics</span></span>
- <span data-ttu-id="567d1-287">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="567d1-287">PSScheduledJob</span></span>
- <span data-ttu-id="567d1-288">PSWorkflow</span><span class="sxs-lookup"><span data-stu-id="567d1-288">PSWorkflow</span></span>
- <span data-ttu-id="567d1-289">PSWorkflowUtility</span><span class="sxs-lookup"><span data-stu-id="567d1-289">PSWorkflowUtility</span></span>
- <span data-ttu-id="567d1-290">ISE</span><span class="sxs-lookup"><span data-stu-id="567d1-290">ISE</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="567d1-291">События модуля ведения журнала</span><span class="sxs-lookup"><span data-stu-id="567d1-291">Logging Module Events</span></span>

<span data-ttu-id="567d1-292">Начиная с версии PowerShell 3,0 можно записывать события выполнения для командлетов и функций в модулях PowerShell и оснастках, установив свойство **LogPipelineExecutionDetails** модулей и оснасток в значение `$True` .</span><span class="sxs-lookup"><span data-stu-id="567d1-292">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="567d1-293">Можно также использовать параметр групповая политика, включить ведение журнала модуля, чтобы включить ведение журнала модуля во всех сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="567d1-293">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="567d1-294">Дополнительные сведения см. в разделе [about_EventLogs](about_EventLogs.md) и [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="567d1-294">For more information, see [about_EventLogs](about_EventLogs.md) and [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="567d1-295">См. также:</span><span class="sxs-lookup"><span data-stu-id="567d1-295">See Also</span></span>

[<span data-ttu-id="567d1-296">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="567d1-296">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="567d1-297">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="567d1-297">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="567d1-298">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="567d1-298">about_PSSnapins</span></span>](about_PSSnapins.md)

[<span data-ttu-id="567d1-299">Get-Command</span><span class="sxs-lookup"><span data-stu-id="567d1-299">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="567d1-300">Get-Help</span><span class="sxs-lookup"><span data-stu-id="567d1-300">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="567d1-301">Get-Module</span><span class="sxs-lookup"><span data-stu-id="567d1-301">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="567d1-302">Import-Module</span><span class="sxs-lookup"><span data-stu-id="567d1-302">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="567d1-303">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="567d1-303">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
