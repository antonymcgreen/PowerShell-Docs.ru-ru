---
description: Описание функций совместимости Windows PowerShell для PowerShell 7.
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 3a7605765da8c17bad2d98a1d3fc3f7cc96f57b8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601500"
---
# <a name="about-windows-powershell-compatibility"></a><span data-ttu-id="6fa26-103">О совместимости с Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fa26-103">About Windows PowerShell compatibility</span></span>

## <a name="short-description"></a><span data-ttu-id="6fa26-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6fa26-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6fa26-105">Описание функций совместимости Windows PowerShell для PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="6fa26-105">Describes the Windows PowerShell Compatibility functionality for PowerShell 7.</span></span>

## <a name="long-description"></a><span data-ttu-id="6fa26-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6fa26-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="6fa26-107">Если манифест модуля не указывает на то, что модуль совместим с PowerShell Core, модули в `%windir%\system32\WindowsPowerShell\v1.0\Modules` папке загружаются в фоновом режиме Windows powershell 5,1 с помощью функции совместимости Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-107">Unless the module manifest indicates that module is compatible with PowerShell Core, modules in the `%windir%\system32\WindowsPowerShell\v1.0\Modules` folder are loaded in a background Windows PowerShell 5.1 process by Windows PowerShell Compatibility feature.</span></span>

### <a name="using-the-compatibility-feature"></a><span data-ttu-id="6fa26-108">Использование функции совместимости</span><span class="sxs-lookup"><span data-stu-id="6fa26-108">Using the Compatibility feature</span></span>

<span data-ttu-id="6fa26-109">Когда первый модуль импортируется с помощью функции совместимости Windows PowerShell, PowerShell создает удаленный сеанс с именем `WinPSCompatSession` , который выполняется в фоновом процессе Windows powershell 5,1.</span><span class="sxs-lookup"><span data-stu-id="6fa26-109">When the first module is imported using Windows PowerShell Compatibility feature, PowerShell creates a remote session named `WinPSCompatSession` that is running in a background Windows PowerShell 5.1 process.</span></span> <span data-ttu-id="6fa26-110">Этот процесс создается, когда функция совместимости импортирует первый модуль.</span><span class="sxs-lookup"><span data-stu-id="6fa26-110">This process is created when the Compatibility feature imports the first module.</span></span> <span data-ttu-id="6fa26-111">Процесс закрывается при удалении последнего такого модуля (с помощью `Remove-Module` ) или при завершении работы процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-111">The process is closed when the last such module is removed (using `Remove-Module`) or when PowerShell process exits.</span></span>

<span data-ttu-id="6fa26-112">Модули, загруженные в `WinPSCompatSession` сеансе, используются через неявное удаленное взаимодействие и отражаются в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-112">The modules loaded in the `WinPSCompatSession` session are used via implicit remoting and reflected into current PowerShell session.</span></span> <span data-ttu-id="6fa26-113">Это тот же метод транспорта, который используется для заданий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-113">This is the same transport method used for PowerShell jobs.</span></span>

<span data-ttu-id="6fa26-114">При импорте модуля в `WinPSCompatSession` сеанс Неявное удаленное взаимодействие создает модуль прокси в `$env:Temp` каталоге пользователя и импортирует этот модуль прокси в текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-114">When a module is imported into the `WinPSCompatSession` session, implicit remoting generates a proxy module in the user's `$env:Temp` directory and imports this proxy module into current PowerShell session.</span></span> <span data-ttu-id="6fa26-115">Это позволяет PowerShell обнаружить, что модуль был загружен с помощью функции совместимости Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-115">This allows PowerShell to detect that the module was loaded using Windows PowerShell Compatibility functionality.</span></span>

<span data-ttu-id="6fa26-116">После создания сеанса его можно использовать для операций, которые неправильно работают в десериализованных объектах.</span><span class="sxs-lookup"><span data-stu-id="6fa26-116">Once the session is created, it can be used for operations that don't work correctly on deserialized objects.</span></span> <span data-ttu-id="6fa26-117">Весь конвейер выполняется в Windows PowerShell, и возвращается только окончательный результат.</span><span class="sxs-lookup"><span data-stu-id="6fa26-117">The entire pipeline is executed in Windows PowerShell and only the final result is returned.</span></span> <span data-ttu-id="6fa26-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="6fa26-118">For example:</span></span>

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

<span data-ttu-id="6fa26-119">Функцию совместимости можно вызвать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="6fa26-119">The Compatibility feature can be invoked in two ways:</span></span>

- <span data-ttu-id="6fa26-120">Явным образом путем импорта модуля с помощью параметра **усевиндовсповершелл**</span><span class="sxs-lookup"><span data-stu-id="6fa26-120">Explicitly by importing a module using the **UseWindowsPowerShell** parameter</span></span>

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- <span data-ttu-id="6fa26-121">Неявным образом Импортируйте модуль Windows PowerShell по имени модуля, пути или автозагрузке с помощью обнаружения команд.</span><span class="sxs-lookup"><span data-stu-id="6fa26-121">Implicitly by importing a Windows PowerShell module by module name, path, or autoloading via command discovery.</span></span>

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   <span data-ttu-id="6fa26-122">Если он еще не загружен, модуль AppLocker будет выгружен при запуске  `Get-AppLockerPolicy` .</span><span class="sxs-lookup"><span data-stu-id="6fa26-122">If not already loaded, the AppLocker module is autoloaded when you run  `Get-AppLockerPolicy`.</span></span>

<span data-ttu-id="6fa26-123">Совместимость Windows PowerShell блокирует загрузку модулей, перечисленных в `WindowsPowerShellCompatibilityModuleDenyList` параметре в файле конфигурации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-123">Windows PowerShell Compatibility blocks loading of modules that are listed in the `WindowsPowerShellCompatibilityModuleDenyList` setting in PowerShell configuration file.</span></span>

<span data-ttu-id="6fa26-124">Значение этого параметра по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="6fa26-124">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a><span data-ttu-id="6fa26-125">Управление неявной загрузкой модуля</span><span class="sxs-lookup"><span data-stu-id="6fa26-125">Managing implicit module loading</span></span>

<span data-ttu-id="6fa26-126">Чтобы отключить неявное поведение импорта функции совместимости Windows PowerShell, используйте `DisableImplicitWinCompat` параметр в файле конфигурации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-126">To disable implicit import behavior of the Windows PowerShell Compatibility feature, use the `DisableImplicitWinCompat` setting in a PowerShell configuration file.</span></span> <span data-ttu-id="6fa26-127">Этот параметр можно добавить в `powershell.config.json` файл.</span><span class="sxs-lookup"><span data-stu-id="6fa26-127">This setting can be added to the `powershell.config.json` file.</span></span> <span data-ttu-id="6fa26-128">Дополнительные сведения см. в разделе [about_powershell_config](about_powershell_config.md).</span><span class="sxs-lookup"><span data-stu-id="6fa26-128">For more information, see [about_powershell_config](about_powershell_config.md).</span></span>

<span data-ttu-id="6fa26-129">В этом примере показано, как создать файл конфигурации, который отключает функцию неявной загрузки модуля для совместимости с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-129">This example shows how to create a configuration file that disables the implicit module-loading feature of Windows PowerShell Compatibility.</span></span>

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

<span data-ttu-id="6fa26-130">Последние сведения о совместимости модулей см. в списке [совместимости модулей PowerShell 7](https://aka.ms/PSModuleCompat) .</span><span class="sxs-lookup"><span data-stu-id="6fa26-130">For more the latest information about module compatibility, see the [PowerShell 7 module compatibility](https://aka.ms/PSModuleCompat) list.</span></span>

### <a name="managing-cmdlet-clobbering"></a><span data-ttu-id="6fa26-131">Управление командлетами клобберинг</span><span class="sxs-lookup"><span data-stu-id="6fa26-131">Managing cmdlet clobbering</span></span>

<span data-ttu-id="6fa26-132">Функция совместимости Windows PowerShell использует неявное удаленное взаимодействие для загрузки модулей в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="6fa26-132">The Windows PowerShell Compatibility feature uses implicit remoting to load modules in compatibility mode.</span></span> <span data-ttu-id="6fa26-133">В результате команды, экспортированные модулем, имеют приоритет над командами с тем же именем в текущем сеансе PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="6fa26-133">The result is that commands exported by the module take precedence over commands of the same name in the current PowerShell 7 session.</span></span> <span data-ttu-id="6fa26-134">В 7.0.0 выпуске PowerShell включены основные модули, поставляемые с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-134">In the PowerShell 7.0.0 release, this included the core modules that ship with PowerShell.</span></span>

<span data-ttu-id="6fa26-135">В PowerShell 7,1 поведение было изменено таким образом, чтобы следующие базовые модули PowerShell не затерт:</span><span class="sxs-lookup"><span data-stu-id="6fa26-135">In PowerShell 7.1, the behavior was changed so that the following core PowerShell modules are not clobbered:</span></span>

- <span data-ttu-id="6fa26-136">Microsoft. PowerShell. ConsoleHost</span><span class="sxs-lookup"><span data-stu-id="6fa26-136">Microsoft.PowerShell.ConsoleHost</span></span>
- <span data-ttu-id="6fa26-137">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="6fa26-137">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="6fa26-138">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="6fa26-138">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="6fa26-139">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="6fa26-139">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="6fa26-140">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="6fa26-140">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="6fa26-141">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="6fa26-141">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="6fa26-142">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="6fa26-142">Microsoft.WSMan.Management</span></span>

<span data-ttu-id="6fa26-143">В PowerShell 7,1 также добавлена возможность перечисления дополнительных модулей, которые не должны быть затерт в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="6fa26-143">PowerShell 7.1 also added the ability to list additional modules that should not be clobbered by compatibility mode.</span></span>

<span data-ttu-id="6fa26-144">Вы можете добавить `WindowsPowerShellCompatibilityNoClobberModuleList` параметр в файл конфигурации PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa26-144">You can add the `WindowsPowerShellCompatibilityNoClobberModuleList` setting to PowerShell configuration file.</span></span> <span data-ttu-id="6fa26-145">Значение этого параметра представляет собой разделенный запятыми список имен модулей.</span><span class="sxs-lookup"><span data-stu-id="6fa26-145">The value of this setting is a comma-separated list of module names.</span></span> <span data-ttu-id="6fa26-146">Значение этого параметра по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="6fa26-146">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a><span data-ttu-id="6fa26-147">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6fa26-147">Limitations</span></span>

<span data-ttu-id="6fa26-148">Функции совместимости Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6fa26-148">The Windows PowerShell Compatibility functionality:</span></span>

1. <span data-ttu-id="6fa26-149">Работает только локально на компьютерах Windows</span><span class="sxs-lookup"><span data-stu-id="6fa26-149">Only works locally on Windows computers</span></span>
1. <span data-ttu-id="6fa26-150">Требует, чтобы Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="6fa26-150">Requires that Windows PowerShell 5.1</span></span>
1. <span data-ttu-id="6fa26-151">Работает с сериализованными параметрами командлета и возвращаемыми значениями, а не с активными объектами.</span><span class="sxs-lookup"><span data-stu-id="6fa26-151">Operates on serialized cmdlet parameters and return values, not on live objects</span></span>
1. <span data-ttu-id="6fa26-152">Все модули, импортированные в сеанс удаленного взаимодействия Windows PowerShell, совместно используют одно и то же пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="6fa26-152">All modules imported into the Windows PowerShell remoting session share the same runspace.</span></span>

## <a name="keywords"></a><span data-ttu-id="6fa26-153">Keywords</span><span class="sxs-lookup"><span data-stu-id="6fa26-153">Keywords</span></span>

<span data-ttu-id="6fa26-154">about_Windows_PowerShell_Compatibility</span><span class="sxs-lookup"><span data-stu-id="6fa26-154">about_Windows_PowerShell_Compatibility</span></span>

## <a name="see-also"></a><span data-ttu-id="6fa26-155">См. также</span><span class="sxs-lookup"><span data-stu-id="6fa26-155">See also</span></span>

[<span data-ttu-id="6fa26-156">about_Modules</span><span class="sxs-lookup"><span data-stu-id="6fa26-156">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="6fa26-157">Import-Module</span><span class="sxs-lookup"><span data-stu-id="6fa26-157">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

