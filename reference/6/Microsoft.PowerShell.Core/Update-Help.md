---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 2851305f40c9805ae3f0fcc2a25a82a57a78cd23
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "93230230"
---
# <span data-ttu-id="4cf40-103">Update-Help</span><span class="sxs-lookup"><span data-stu-id="4cf40-103">Update-Help</span></span>

## <span data-ttu-id="4cf40-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4cf40-104">SYNOPSIS</span></span>
<span data-ttu-id="4cf40-105">Скачивает и устанавливает новейшие файлы справки на компьютер.</span><span class="sxs-lookup"><span data-stu-id="4cf40-105">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="4cf40-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4cf40-106">SYNTAX</span></span>

### <span data-ttu-id="4cf40-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4cf40-107">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="4cf40-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4cf40-108">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="4cf40-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4cf40-109">DESCRIPTION</span></span>

<span data-ttu-id="4cf40-110">`Update-Help`Командлет загружает новейшие файлы справки для модулей PowerShell и устанавливает их на компьютер.</span><span class="sxs-lookup"><span data-stu-id="4cf40-110">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="4cf40-111">Не нужно перезапускать PowerShell, чтобы изменения были эффективны.</span><span class="sxs-lookup"><span data-stu-id="4cf40-111">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="4cf40-112">`Get-Help`Для немедленного просмотра новых файлов справки можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="4cf40-112">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="4cf40-113">`Update-Help` проверяет версию файлов справки на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-113">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="4cf40-114">Если у вас нет файлов справки для модуля или файлы справки устарели, `Update-Help` загружает новейшие файлы справки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-114">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="4cf40-115">Файлы справки можно скачать и установить из Интернета или общей папки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-115">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="4cf40-116">Без параметров `Update-Help` обновляет файлы справки для модулей в сеансе и для всех установленных модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-116">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="4cf40-117">Включены модули, которые установлены, но не загружены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="4cf40-117">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="4cf40-118">Модули PowerShell хранятся в расположении, указанном в `$env:PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="4cf40-118">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="4cf40-119">Дополнительные сведения см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="4cf40-119">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="4cf40-120">Параметр **module** можно использовать для обновления файлов справки для определенного модуля.</span><span class="sxs-lookup"><span data-stu-id="4cf40-120">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="4cf40-121">Используйте параметр **UICulture** для скачивания файлов справки на нескольких языках и языковых стандартах.</span><span class="sxs-lookup"><span data-stu-id="4cf40-121">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="4cf40-122">Также можно использовать `Update-Help` на компьютерах, которые не подключены к Интернету.</span><span class="sxs-lookup"><span data-stu-id="4cf40-122">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="4cf40-123">Сначала используйте `Save-Help` командлет для загрузки файлов справки из Интернета и сохраните их в общей папке, доступной системе, не подключенной к Интернету.</span><span class="sxs-lookup"><span data-stu-id="4cf40-123">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="4cf40-124">Затем используйте параметр **SourcePath** функции, `Update-Help` чтобы скачать обновленные файлы справки из общего доступа и установить их на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-124">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="4cf40-125">Вы можете автоматизировать обновление справки, добавив `Update-Help` командлет в свой профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cf40-125">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="4cf40-126">По умолчанию `Update-Help` выполняется только один раз в день на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-126">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="4cf40-127">Чтобы переопределить ограничение одного раза в день, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-127">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="4cf40-128">`Update-Help`Командлет появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4cf40-128">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cf40-129">`Update-Help` требуются права администратора в PowerShell 6,0 и ниже.</span><span class="sxs-lookup"><span data-stu-id="4cf40-129">`Update-Help` requires administrative privileges in PowerShell 6.0 and below.</span></span>
> <span data-ttu-id="4cf40-130">В PowerShell 6,1 и выше для **области** по умолчанию задано значение `CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="4cf40-130">PowerShell 6.1 and above set the default **Scope** to `CurrentUser`.</span></span>
> <span data-ttu-id="4cf40-131">До выхода версии PowerShell 6,1 параметр **Scope** был недоступен.</span><span class="sxs-lookup"><span data-stu-id="4cf40-131">Prior to PowerShell 6.1, the **Scope** parameter was not available.</span></span>
>
> <span data-ttu-id="4cf40-132">Для обновления файлов справки для модулей PowerShell Core необходимо быть членом группы администраторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-132">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="4cf40-133">Чтобы скачать или обновить файлы справки для модулей в каталоге установки PowerShell ( `$PSHOME\Modules` ), включая модули PowerShell Core, запустите PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-133">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the **Run as administrator** option.</span></span>
> <span data-ttu-id="4cf40-134">Например: `Start-Process pwsh.exe -Verb RunAs`.</span><span class="sxs-lookup"><span data-stu-id="4cf40-134">For example: `Start-Process pwsh.exe -Verb RunAs`.</span></span>

## <span data-ttu-id="4cf40-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="4cf40-135">EXAMPLES</span></span>

### <span data-ttu-id="4cf40-136">Пример 1. обновление файлов справки для всех модулей</span><span class="sxs-lookup"><span data-stu-id="4cf40-136">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="4cf40-137">`Update-Help`Командлет обновляет файлы справки для установленных модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-137">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="4cf40-138">Язык и региональные параметры пользовательского интерфейса задаются в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="4cf40-138">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="4cf40-139">Пример 2. обновление файлов справки для указанных модулей</span><span class="sxs-lookup"><span data-stu-id="4cf40-139">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="4cf40-140">`Update-Help`Командлет обновляет файлы справки только для имен модулей, начинающихся с **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-140">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell** .</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="4cf40-141">Пример 3. обновление файлов справки для разных языков</span><span class="sxs-lookup"><span data-stu-id="4cf40-141">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="4cf40-142">`Update-Help`Командлет обновляет файлы справки на японском языке (ja-JP) и английском (EN-US) для всех модулей.</span><span class="sxs-lookup"><span data-stu-id="4cf40-142">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="4cf40-143">Если модуль не предоставляет файлы справки для указанного языка и региональных параметров пользовательского интерфейса, выводится сообщение об ошибке для модуля и языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4cf40-143">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="4cf40-144">В этом примере сообщение об ошибке указывает на то, что файлы справки **ja-JP** не найдены для модуля **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-144">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility** .</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="4cf40-145">Пример 4. обновление файлов справки на нескольких компьютерах из общей папки</span><span class="sxs-lookup"><span data-stu-id="4cf40-145">Example 4: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="4cf40-146">В этом примере обновленные файлы справки загружаются из Интернета и сохраняются в общей папке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-146">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="4cf40-147">Требуются учетные данные пользователя, имеющие разрешения на доступ к общей папке и установку обновлений.</span><span class="sxs-lookup"><span data-stu-id="4cf40-147">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="4cf40-148">При использовании общей папки можно обновить компьютеры, находящиеся за брандмауэрами или не подключенные к Интернету.</span><span class="sxs-lookup"><span data-stu-id="4cf40-148">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="4cf40-149">`Save-Help`Команда скачивает самые новые файлы справки для всех модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-149">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="4cf40-150">Параметр **DestinationPath** сохраняет файлы в `\\Server01\Share\PSHelp` общей папке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-150">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="4cf40-151">Параметр **Credential** указывает пользователя, имеющего разрешение на доступ к общей папке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-151">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="4cf40-152">`Invoke-Command`Командлет запускает удаленные `Update-Help` команды на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4cf40-152">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="4cf40-153">Параметр **ComputerName** возвращает список удаленных компьютеров из файла **Servers.txt** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-153">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="4cf40-154">Параметр **ScriptBlock** выполняет `Update-Help` команду и использует параметр **SourcePath** для указания общего файлового ресурса, содержащего обновленные файлы справки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-154">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="4cf40-155">Параметр **Credential** указывает пользователя, который имеет доступ к общей папке и выполняет удаленную `Update-Help` команду.</span><span class="sxs-lookup"><span data-stu-id="4cf40-155">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="4cf40-156">Пример 5. Получение списка обновленных файлов справки</span><span class="sxs-lookup"><span data-stu-id="4cf40-156">Example 5: Get a list of updated help files</span></span>

<span data-ttu-id="4cf40-157">`Update-Help`Командлет обновляет справку для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="4cf40-157">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="4cf40-158">Командлет использует параметр **verbose** Common для вывода списка обновленных файлов справки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-158">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="4cf40-159">Для просмотра выходных данных для всех файлов справки и файлов справки для конкретного модуля можно использовать параметр **verbose** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-159">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="4cf40-160">Без параметра **verbose** `Update-Help` не отображает результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="4cf40-160">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="4cf40-161">Вывод **подробных** параметров полезен для проверки обновления файлов справки или установки последней версии.</span><span class="sxs-lookup"><span data-stu-id="4cf40-161">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="4cf40-162">Пример 6. Поиск модулей, поддерживающих обновляемую справку</span><span class="sxs-lookup"><span data-stu-id="4cf40-162">Example 6: Find modules that support Updatable Help</span></span>

<span data-ttu-id="4cf40-163">В этом примере перечислены модули, поддерживающие обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-163">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="4cf40-164">Команда использует свойство **HelpInfoUri** модуля для выявления модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-164">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="4cf40-165">Свойство **HelpInfoUri** содержит адрес, который перенаправляется при `Update-Help` выполнении командлета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-165">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### <span data-ttu-id="4cf40-166">Пример 7. обновление файлов справки инвентаризации</span><span class="sxs-lookup"><span data-stu-id="4cf40-166">Example 7: Inventory updated help files</span></span>

<span data-ttu-id="4cf40-167">В этом примере сценарий `Get-UpdateHelpVersion.ps1` создает инвентаризацию обновляемых файлов справки для каждого модуля и их номеров версий.</span><span class="sxs-lookup"><span data-stu-id="4cf40-167">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="4cf40-168">Скрипт определяет модули, поддерживающие обновляемую справку, с помощью свойства **HelpInfoUri** модулей.</span><span class="sxs-lookup"><span data-stu-id="4cf40-168">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="4cf40-169">Для модулей, поддерживающих обновляемую справку, сценарий ищет и анализирует файл справочной информации (\* helpinfo.xml), чтобы найти номер последней версии.</span><span class="sxs-lookup"><span data-stu-id="4cf40-169">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="4cf40-170">Для создания пользовательского выходного объекта скрипт использует класс **PSCustomObject** и хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="4cf40-170">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## <span data-ttu-id="4cf40-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4cf40-171">PARAMETERS</span></span>

### <span data-ttu-id="4cf40-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="4cf40-172">-Credential</span></span>

<span data-ttu-id="4cf40-173">Указывает учетные данные пользователя, имеющего разрешение на доступ к расположению файловой системы, заданному параметром **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-173">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath** .</span></span> <span data-ttu-id="4cf40-174">Этот параметр допустим, только если в команде используется параметр **SourcePath** или **LiteralPath** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-174">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="4cf40-175">Параметр **Credential** позволяет выполнять `Update-Help` команды с параметром **SourcePath** на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4cf40-175">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="4cf40-176">Предоставляя явные учетные данные, можно выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере без возникновения ошибки отказа в доступе или использования проверки подлинности CredSSP для делегирования учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4cf40-176">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="4cf40-177">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="4cf40-177">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="4cf40-178">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="4cf40-178">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="4cf40-179">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="4cf40-179">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="4cf40-180">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="4cf40-180">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-181">-Force</span><span class="sxs-lookup"><span data-stu-id="4cf40-181">-Force</span></span>

<span data-ttu-id="4cf40-182">Указывает, что этот командлет не соответствует ограничению "один за день", пропускает проверку версий и скачивает файлы, размер которых превышает ограничение в 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="4cf40-182">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="4cf40-183">Без этого параметра `Update-Help` выполняется только один раз в 24-часовом периоде.</span><span class="sxs-lookup"><span data-stu-id="4cf40-183">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="4cf40-184">Размер загружаемых файлов ограничен 1 ГБ несжатого содержимого на модуль, а файлы справки устанавливаются только в том случае, если они новее, чем существующие файлы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-184">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="4cf40-185">Ограничение "один за день" защищает серверы, на которых размещаются файлы справки, и упрощает добавление `Update-Help` команды в профиль PowerShell без затрат на ресурсы при повторяющихся подключениях или загрузках.</span><span class="sxs-lookup"><span data-stu-id="4cf40-185">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="4cf40-186">Чтобы обновить справку для модуля на нескольких языках и в региональных параметрах пользовательского интерфейса без параметра **Force** , включите все языки и региональные параметры пользовательского интерфейса в одну команду, например:</span><span class="sxs-lookup"><span data-stu-id="4cf40-186">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-187">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="4cf40-187">-FullyQualifiedModule</span></span>

<span data-ttu-id="4cf40-188">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-188">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="4cf40-189">Эти модули описаны в разделе "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="4cf40-189">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="4cf40-190">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в формате:</span><span class="sxs-lookup"><span data-stu-id="4cf40-190">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="4cf40-191">or</span><span class="sxs-lookup"><span data-stu-id="4cf40-191">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="4cf40-192">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="4cf40-192">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="4cf40-193">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-193">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-194">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4cf40-194">-LiteralPath</span></span>

<span data-ttu-id="4cf40-195">Указывает папку для обновленных файлов справки, а не скачивает их из Интернета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-195">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="4cf40-196">Используйте этот параметр или **SourcePath** , если вы использовали `Save-Help` командлет для загрузки файлов справки в каталог.</span><span class="sxs-lookup"><span data-stu-id="4cf40-196">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="4cf40-197">Вы можете выполнить конвейер объекта каталога, например из `Get-Item` `Get-ChildItem` командлетов или, в `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="4cf40-197">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="4cf40-198">В отличие от значения **SourcePath** , значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="4cf40-198">Unlike the value of **SourcePath** , the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="4cf40-199">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-199">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="4cf40-200">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-200">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4cf40-201">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="4cf40-201">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-202">-Module</span><span class="sxs-lookup"><span data-stu-id="4cf40-202">-Module</span></span>

<span data-ttu-id="4cf40-203">Обновляет справку для указанных модулей.</span><span class="sxs-lookup"><span data-stu-id="4cf40-203">Updates help for the specified modules.</span></span> <span data-ttu-id="4cf40-204">Введите одно или несколько имен модулей или шаблонов имен в списке с разделителями-запятыми или укажите файл, в котором перечислены имена отдельных модулей в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-204">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="4cf40-205">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-205">Wildcard characters are permitted.</span></span> <span data-ttu-id="4cf40-206">Вы можете конвейерировать модули из `Get-Module` командлета в `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="4cf40-206">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="4cf40-207">Указанные модули должны быть установлены на компьютере, но их не нужно импортировать в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="4cf40-207">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="4cf40-208">Можно указать любой модуль в сеансе или любой модуль, установленный в расположении, указанном в `$env:PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="4cf40-208">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="4cf40-209">Значение `*` (все) пытается обновить справку для всех модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-209">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="4cf40-210">Включены модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-210">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="4cf40-211">Это значение может выдавать ошибки, если команда обнаруживает модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-211">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="4cf40-212">Вместо этого запустите `Update-Help` без параметров.</span><span class="sxs-lookup"><span data-stu-id="4cf40-212">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="4cf40-213">Параметр **module** `Update-Help` командлета не принимает полный путь к файлу модуля или файлу манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="4cf40-213">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="4cf40-214">Чтобы обновить справку для модуля, который не находится в `$env:PSModulePath` расположении, импортируйте модуль в текущий сеанс перед выполнением `Update-Help` команды.</span><span class="sxs-lookup"><span data-stu-id="4cf40-214">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="4cf40-215">-Recurse</span><span class="sxs-lookup"><span data-stu-id="4cf40-215">-Recurse</span></span>

<span data-ttu-id="4cf40-216">Выполняет рекурсивный поиск файлов справки в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="4cf40-216">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="4cf40-217">Этот параметр допустим только в том случае, если в команде используется параметр **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-217">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-218">-Scope</span><span class="sxs-lookup"><span data-stu-id="4cf40-218">-Scope</span></span>

<span data-ttu-id="4cf40-219">Указывает область системы, в которой обновляется Справка.</span><span class="sxs-lookup"><span data-stu-id="4cf40-219">Specifies the system scope where help is updated.</span></span> <span data-ttu-id="4cf40-220">Для обновлений в области **ALLUSERS** требуются права администратора в системах Windows.</span><span class="sxs-lookup"><span data-stu-id="4cf40-220">Updates at the **AllUsers** scope require administrative privileges on Windows systems.</span></span> <span data-ttu-id="4cf40-221">`-Scope`Параметр был представлен в PowerShell Core версии 6,1.</span><span class="sxs-lookup"><span data-stu-id="4cf40-221">The `-Scope` parameter was introduced in PowerShell Core version 6.1.</span></span>

<span data-ttu-id="4cf40-222">**CurrentUser** — это область по умолчанию для файлов справки в PowerShell 6,1 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="4cf40-222">**CurrentUser** is the default scope for help files in PowerShell 6.1 and above.</span></span> <span data-ttu-id="4cf40-223">Можно указать **ALLUSERS** для установки или обновления справки для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="4cf40-223">**AllUsers** can be specified to install or update help for all users.</span></span> <span data-ttu-id="4cf40-224">В системах UNIX `sudo` требуются права на обновление справки для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="4cf40-224">On Unix systems `sudo` privileges are required to update help for all users.</span></span> <span data-ttu-id="4cf40-225">Пример: `sudo pwsh -c Update-Help`</span><span class="sxs-lookup"><span data-stu-id="4cf40-225">For example: `sudo pwsh -c Update-Help`</span></span>

<span data-ttu-id="4cf40-226">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="4cf40-226">The acceptable values are:</span></span>

- <span data-ttu-id="4cf40-227">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="4cf40-227">CurrentUser</span></span>
- <span data-ttu-id="4cf40-228">AllUsers</span><span class="sxs-lookup"><span data-stu-id="4cf40-228">AllUsers</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-229">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="4cf40-229">-SourcePath</span></span>

<span data-ttu-id="4cf40-230">Указывает папку файловой системы `Update-Help` , в которой будут обновляться файлы справки, а не загружать их из Интернета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-230">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="4cf40-231">Введите путь к папке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-231">Enter the path of a folder.</span></span> <span data-ttu-id="4cf40-232">Не указывайте имя файла или расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="4cf40-232">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="4cf40-233">Вы можете конвейерировать папку, такую как, из `Get-Item` `Get-ChildItem` командлетов или, в `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="4cf40-233">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="4cf40-234">По умолчанию `Update-Help` скачивает обновленные файлы справки из Интернета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-234">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="4cf40-235">Используйте параметр **SourcePath** , если вы использовали `Save-Help` командлет для загрузки обновленных файлов справки в каталог.</span><span class="sxs-lookup"><span data-stu-id="4cf40-235">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="4cf40-236">Чтобы указать значение **SourcePath** по умолчанию, перейдите в раздел **Групповая политика** , **Конфигурация компьютера** и **Задайте путь к источнику по умолчанию для Update-Help** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-236">To specify a default value for **SourcePath** , go to **Group Policy** , **Computer Configuration** , and **Set the default source path for Update-Help** .</span></span> <span data-ttu-id="4cf40-237">Этот параметр групповая политика запрещает пользователям использовать `Update-Help` для загрузки файлов справки из Интернета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-237">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="4cf40-238">Дополнительные сведения см. в статье [О параметрах групповой политики](./About/about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="4cf40-238">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-239">-UICulture</span><span class="sxs-lookup"><span data-stu-id="4cf40-239">-UICulture</span></span>

<span data-ttu-id="4cf40-240">Задает значения языка и региональных параметров пользовательского интерфейса, которые `Update-Help` используются для получения обновленных файлов справки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-240">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="4cf40-241">Введите один или несколько кодов языка, например **es-ES** , переменную, содержащую объекты языка и региональных параметров, или команду, которая получает объекты языка и региональных параметров, такие как `Get-Culture` `Get-UICulture` команда или.</span><span class="sxs-lookup"><span data-stu-id="4cf40-241">Enter one or more language codes, such as **es-ES** , a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="4cf40-242">Подстановочные знаки не допускаются, и нельзя отправлять код частичного языка, например **de** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-242">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de** .</span></span>

<span data-ttu-id="4cf40-243">По умолчанию `Update-Help` получает файлы справки в языке и региональных параметрах пользовательского интерфейса, заданных для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4cf40-243">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="4cf40-244">Если указан параметр **UICulture** , `Update-Help` ищет справку только для указанного языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4cf40-244">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

> [!NOTE]
> <span data-ttu-id="4cf40-245">Ubuntu 18,04 изменила параметр языкового стандарта по умолчанию на `C.UTF.8` , который не является распознаваемым языком пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4cf40-245">Ubuntu 18.04 changed the default locale setting to `C.UTF.8`, which is not a recognized UI culture.</span></span> <span data-ttu-id="4cf40-246">`Update-Help` автоматически не удается загрузить справку, если вы не используете этот параметр с поддерживаемым языковым стандартом, например `en-US` .</span><span class="sxs-lookup"><span data-stu-id="4cf40-246">`Update-Help` silently fails to download help unless you use this parameter with a supported locale like `en-US`.</span></span> <span data-ttu-id="4cf40-247">Это может произойти на любой платформе, которая использует неподдерживаемое значение.</span><span class="sxs-lookup"><span data-stu-id="4cf40-247">This could occur on any platform that uses an unsupported value.</span></span>

<span data-ttu-id="4cf40-248">Команды, которые используют параметр **UICulture** , выполняются, только если модуль предоставляет файлы справки для указанного языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4cf40-248">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="4cf40-249">Если команда завершается ошибкой из-за того, что указанная культура пользовательского интерфейса не поддерживается, выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-249">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-250">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="4cf40-250">-UseDefaultCredentials</span></span>

<span data-ttu-id="4cf40-251">Указывает, что `Update-Help` выполняет команду, включая загрузку из Интернета, используя учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="4cf40-251">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="4cf40-252">По умолчанию команда выполняется без явных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="4cf40-252">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="4cf40-253">Этот параметр эффективен, только если веб-скачивание использует проверку подлинности NT LAN Manager (NTLM), согласование или аутентификацию на основе Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4cf40-253">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-254">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4cf40-254">-Confirm</span></span>

<span data-ttu-id="4cf40-255">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-255">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-256">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4cf40-256">-WhatIf</span></span>

<span data-ttu-id="4cf40-257">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-257">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4cf40-258">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4cf40-258">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cf40-259">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4cf40-259">CommonParameters</span></span>

<span data-ttu-id="4cf40-260">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4cf40-260">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4cf40-261">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4cf40-261">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4cf40-262">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4cf40-262">INPUTS</span></span>

### <span data-ttu-id="4cf40-263">System.IO.DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="4cf40-263">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="4cf40-264">Путь к каталогу можно передать по конвейеру `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="4cf40-264">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="4cf40-265">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="4cf40-265">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="4cf40-266">Объект модуля можно передать из `Get-Module` командлета в `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="4cf40-266">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="4cf40-267">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4cf40-267">OUTPUTS</span></span>

### <span data-ttu-id="4cf40-268">Нет</span><span class="sxs-lookup"><span data-stu-id="4cf40-268">None</span></span>

<span data-ttu-id="4cf40-269">`Update-Help` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4cf40-269">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="4cf40-270">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4cf40-270">NOTES</span></span>

<span data-ttu-id="4cf40-271">Чтобы обновить справку для модулей PowerShell Core, содержащих команды, установленные с помощью PowerShell, или любой модуль в `$PSHOME\Modules` каталоге, запустите PowerShell с параметром для **запуска от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-271">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator** .</span></span>

<span data-ttu-id="4cf40-272">Только члены группы администраторов на компьютере могут обновлять справку по модулям PowerShell Core, командам, которые устанавливаются вместе с PowerShell и для модулей в `$PSHOME\Modules` папке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-272">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="4cf40-273">Если у вас нет разрешения на обновление файлов справки, можно прочитать файлы справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4cf40-273">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="4cf40-274">Например, `Get-Help Update-Help -Online`.</span><span class="sxs-lookup"><span data-stu-id="4cf40-274">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="4cf40-275">Модули — это наименьшая единица обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-275">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="4cf40-276">Невозможно обновить справку для конкретного командлета.</span><span class="sxs-lookup"><span data-stu-id="4cf40-276">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="4cf40-277">Чтобы найти модуль, содержащий конкретный командлет, используйте свойство **ModuleName** `Get-Command` командлета, например `(Get-Command Update-Help).ModuleName` .</span><span class="sxs-lookup"><span data-stu-id="4cf40-277">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="4cf40-278">Поскольку файлы справки устанавливаются в каталог Module, `Update-Help` командлет может установить обновленный файл справки только для модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-278">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="4cf40-279">Однако `Save-Help` командлет может сохранить справку для модулей, которые не установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cf40-279">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="4cf40-280">Если `Update-Help` не удается найти обновленные файлы справки для модуля или не удается найти обновленную справку на указанном языке, она продолжится без вывода сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4cf40-280">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="4cf40-281">Чтобы увидеть состояние и сведения о ходе выполнения, используйте параметр **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-281">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="4cf40-282">`Update-Help`Командлет появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4cf40-282">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="4cf40-283">Он не работает в более ранних версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cf40-283">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="4cf40-284">На компьютерах, где установлены Windows PowerShell 2,0 и Windows PowerShell 3,0, используйте `Update-Help` командлет в сеансе Windows powershell 3,0 для скачивания и обновления файлов справки.</span><span class="sxs-lookup"><span data-stu-id="4cf40-284">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="4cf40-285">Файлы справки доступны как для Windows PowerShell 2,0, так и для Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4cf40-285">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="4cf40-286">`Update-Help` `Save-Help` Командлеты и используют следующие порты для скачивания файлов справки: порт 80 для HTTP и порт 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4cf40-286">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="4cf40-287">`Update-Help` поддерживает все модули и оснастки PowerShell Core. Другие оснастки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4cf40-287">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="4cf40-288">Чтобы обновить справку для модуля в расположении, не указанном в `$env:PSModulePath` переменной среды, импортируйте модуль в текущий сеанс, а затем выполните `Update-Help` команду.</span><span class="sxs-lookup"><span data-stu-id="4cf40-288">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="4cf40-289">Выполните команду `Update-Help` без параметров или укажите имя модуля с помощью параметра **module** .</span><span class="sxs-lookup"><span data-stu-id="4cf40-289">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="4cf40-290">Параметр **module** `Update-Help` `Save-Help` командлетов и не принимает полный путь к файлу модуля или файлу манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="4cf40-290">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="4cf40-291">Любой модуль может поддерживать обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="4cf40-291">Any module can support Updatable Help.</span></span> <span data-ttu-id="4cf40-292">Инструкции по поддержке обновляемой справки в созданных вами модулях см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="4cf40-292">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="4cf40-293">`Update-Help` `Save-Help` Командлеты и не поддерживаются в среда предустановки Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="4cf40-293">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="4cf40-294">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4cf40-294">RELATED LINKS</span></span>

[<span data-ttu-id="4cf40-295">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="4cf40-295">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="4cf40-296">Get-Help</span><span class="sxs-lookup"><span data-stu-id="4cf40-296">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="4cf40-297">Get-Module</span><span class="sxs-lookup"><span data-stu-id="4cf40-297">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="4cf40-298">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="4cf40-298">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="4cf40-299">Start-Job</span><span class="sxs-lookup"><span data-stu-id="4cf40-299">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="4cf40-300">Save-Help</span><span class="sxs-lookup"><span data-stu-id="4cf40-300">Save-Help</span></span>](Save-Help.md)
