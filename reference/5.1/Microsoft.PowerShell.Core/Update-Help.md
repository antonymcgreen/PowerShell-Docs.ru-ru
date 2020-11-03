---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 4ef0865e81e01746fed77b73e265e68086a7a9e1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "93230225"
---
# <span data-ttu-id="cf365-103">Update-Help</span><span class="sxs-lookup"><span data-stu-id="cf365-103">Update-Help</span></span>

## <span data-ttu-id="cf365-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cf365-104">SYNOPSIS</span></span>
<span data-ttu-id="cf365-105">Скачивает и устанавливает новейшие файлы справки на компьютер.</span><span class="sxs-lookup"><span data-stu-id="cf365-105">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="cf365-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cf365-106">SYNTAX</span></span>

### <span data-ttu-id="cf365-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cf365-107">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cf365-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cf365-108">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cf365-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cf365-109">DESCRIPTION</span></span>

<span data-ttu-id="cf365-110">`Update-Help`Командлет загружает новейшие файлы справки для модулей PowerShell и устанавливает их на компьютер.</span><span class="sxs-lookup"><span data-stu-id="cf365-110">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="cf365-111">Не нужно перезапускать PowerShell, чтобы изменения были эффективны.</span><span class="sxs-lookup"><span data-stu-id="cf365-111">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="cf365-112">`Get-Help`Для немедленного просмотра новых файлов справки можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="cf365-112">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="cf365-113">`Update-Help` проверяет версию файлов справки на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-113">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="cf365-114">Если у вас нет файлов справки для модуля или файлы справки устарели, `Update-Help` загружает новейшие файлы справки.</span><span class="sxs-lookup"><span data-stu-id="cf365-114">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="cf365-115">Файлы справки можно скачать и установить из Интернета или общей папки.</span><span class="sxs-lookup"><span data-stu-id="cf365-115">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="cf365-116">Без параметров `Update-Help` обновляет файлы справки для модулей в сеансе и для всех установленных модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-116">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="cf365-117">Включены модули, которые установлены, но не загружены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cf365-117">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="cf365-118">Модули PowerShell хранятся в расположении, указанном в `$env:PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="cf365-118">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="cf365-119">Дополнительные сведения см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="cf365-119">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="cf365-120">Параметр **module** можно использовать для обновления файлов справки для определенного модуля.</span><span class="sxs-lookup"><span data-stu-id="cf365-120">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="cf365-121">Используйте параметр **UICulture** для скачивания файлов справки на нескольких языках и языковых стандартах.</span><span class="sxs-lookup"><span data-stu-id="cf365-121">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="cf365-122">Также можно использовать `Update-Help` на компьютерах, которые не подключены к Интернету.</span><span class="sxs-lookup"><span data-stu-id="cf365-122">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="cf365-123">Сначала используйте `Save-Help` командлет для загрузки файлов справки из Интернета и сохраните их в общей папке, доступной системе, не подключенной к Интернету.</span><span class="sxs-lookup"><span data-stu-id="cf365-123">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="cf365-124">Затем используйте параметр **SourcePath** функции, `Update-Help` чтобы скачать обновленные файлы справки из общего доступа и установить их на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-124">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="cf365-125">Вы можете автоматизировать обновление справки, добавив `Update-Help` командлет в свой профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf365-125">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="cf365-126">По умолчанию `Update-Help` выполняется только один раз в день на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-126">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="cf365-127">Чтобы переопределить ограничение одного раза в день, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="cf365-127">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="cf365-128">`Update-Help`Командлет появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="cf365-128">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf365-129">`Update-Help` требуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="cf365-129">`Update-Help` requires administrative privileges.</span></span>
>
> <span data-ttu-id="cf365-130">Для обновления файлов справки для модулей PowerShell Core необходимо быть членом группы администраторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-130">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="cf365-131">Чтобы скачать или обновить файлы справки для модулей в каталоге установки PowerShell ( `$PSHOME\Modules` ), включая модули PowerShell Core, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="cf365-131">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the Run as administrator option.</span></span>
> <span data-ttu-id="cf365-132">Например: `Start-Process powershell.exe -Verb RunAs`.</span><span class="sxs-lookup"><span data-stu-id="cf365-132">For example: `Start-Process powershell.exe -Verb RunAs`.</span></span>
>
> <span data-ttu-id="cf365-133">Файлы справки также можно обновлять с помощью пункта меню Справка обновление Windows PowerShell в меню Справка в интегрированной среде сценариев Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="cf365-133">You can also update help files by using the Update Windows PowerShell Help menu item in the Help menu in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>
>
> <span data-ttu-id="cf365-134">Элемент справки по обновлению Windows PowerShell запускает `Update-Help` командлет без параметров.</span><span class="sxs-lookup"><span data-stu-id="cf365-134">The Update Windows PowerShell Help item runs an `Update-Help` cmdlet without parameters.</span></span>
> <span data-ttu-id="cf365-135">Чтобы обновить справку по модулям в `$PSHOME` каталоге, запустите интегрированную среду сценариев Windows PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="cf365-135">To update help for modules in the `$PSHOME` directory, start Windows PowerShell ISE by using the Run as administrator option.</span></span>

## <span data-ttu-id="cf365-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="cf365-136">EXAMPLES</span></span>

### <span data-ttu-id="cf365-137">Пример 1. обновление файлов справки для всех модулей</span><span class="sxs-lookup"><span data-stu-id="cf365-137">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="cf365-138">`Update-Help`Командлет обновляет файлы справки для установленных модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-138">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="cf365-139">Язык и региональные параметры пользовательского интерфейса задаются в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="cf365-139">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="cf365-140">Пример 2. обновление файлов справки для указанных модулей</span><span class="sxs-lookup"><span data-stu-id="cf365-140">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="cf365-141">`Update-Help`Командлет обновляет файлы справки только для имен модулей, начинающихся с **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="cf365-141">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell** .</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="cf365-142">Пример 3. обновление файлов справки для разных языков</span><span class="sxs-lookup"><span data-stu-id="cf365-142">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="cf365-143">`Update-Help`Командлет обновляет файлы справки на японском языке (ja-JP) и английском (EN-US) для всех модулей.</span><span class="sxs-lookup"><span data-stu-id="cf365-143">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="cf365-144">Если модуль не предоставляет файлы справки для указанного языка и региональных параметров пользовательского интерфейса, выводится сообщение об ошибке для модуля и языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cf365-144">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="cf365-145">В этом примере сообщение об ошибке указывает на то, что файлы справки **ja-JP** не найдены для модуля **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="cf365-145">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility** .</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="cf365-146">Пример 4. Автоматическое обновление файлов справки</span><span class="sxs-lookup"><span data-stu-id="cf365-146">Example 4: Update help files automatically</span></span>

<span data-ttu-id="cf365-147">В этом примере создается запланированное задание, которое обновляет справку для всех модулей каждый день в 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="cf365-147">This example creates a scheduled job that updates help for all modules every day at 3:00 AM.</span></span>

```powershell
$jobParams = @{
  Name = 'UpdateHelpJob'
  Credential = 'Domain01\User01'
  ScriptBlock = '{Update-Help}'
  Trigger = (New-JobTrigger -Daily -At "3 AM")
}
Register-ScheduledJob @jobParams
```

```Output
Id         Name            JobTriggers     Command                                  Enabled
--         ----            -----------     -------                                  -------
1          UpdateHelpJob   1               Update-Help                              True
```

<span data-ttu-id="cf365-148">`Register-ScheduledJob`Командлет создает запланированное задание, которое выполняет `Update-Help` команду.</span><span class="sxs-lookup"><span data-stu-id="cf365-148">The `Register-ScheduledJob` cmdlet creates a scheduled job that runs an `Update-Help` command.</span></span> <span data-ttu-id="cf365-149">Команда использует параметр **Credential** для запуска с `Update-Help` использованием учетных данных члена группы «Администраторы» на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-149">The command uses the **Credential** parameter to run `Update-Help` by using the credentials of a member of the Administrators group on the computer.</span></span> <span data-ttu-id="cf365-150">Значение параметра **триггера** — это `New-JobTrigger` команда, создающая триггер задания, который запускает задание каждый день в 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="cf365-150">The value of the **Trigger** parameter is a `New-JobTrigger` command that creates a job trigger that starts the job every day at 3:00 AM.</span></span>

<span data-ttu-id="cf365-151">Чтобы выполнить `Register-ScheduledJob` команду, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="cf365-151">To run the `Register-ScheduledJob` command, start PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="cf365-152">PowerShell запрашивает пароль пользователя, указанного в параметре **Credential** .</span><span class="sxs-lookup"><span data-stu-id="cf365-152">PowerShell prompts you for the password of the user specified in the **Credential** parameter.</span></span> <span data-ttu-id="cf365-153">Учетные данные хранятся в запланированном задании.</span><span class="sxs-lookup"><span data-stu-id="cf365-153">The credentials are stored with the scheduled job.</span></span> <span data-ttu-id="cf365-154">При запуске задания не выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="cf365-154">You aren't prompted when the job runs.</span></span>

<span data-ttu-id="cf365-155">С помощью `Get-ScheduledJob` командлета можно просмотреть запланированное задание, воспользоваться `Set-ScheduledJob` командлетом для его изменения и `Unregister-ScheduledJob` удалить его с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="cf365-155">You can use the `Get-ScheduledJob` cmdlet to view the scheduled job, use the `Set-ScheduledJob` cmdlet to change it, and use the `Unregister-ScheduledJob` cmdlet to delete it.</span></span> <span data-ttu-id="cf365-156">Можно также просматривать запланированное задание и управлять им в планировщике заданий в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="cf365-156">You can also view and manage the scheduled job in Task Scheduler in the following path:</span></span>

<span data-ttu-id="cf365-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span><span class="sxs-lookup"><span data-stu-id="cf365-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

### <span data-ttu-id="cf365-158">Пример 5. обновление файлов справки на нескольких компьютерах из общей папки</span><span class="sxs-lookup"><span data-stu-id="cf365-158">Example 5: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="cf365-159">В этом примере обновленные файлы справки загружаются из Интернета и сохраняются в общей папке.</span><span class="sxs-lookup"><span data-stu-id="cf365-159">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="cf365-160">Требуются учетные данные пользователя, имеющие разрешения на доступ к общей папке и установку обновлений.</span><span class="sxs-lookup"><span data-stu-id="cf365-160">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="cf365-161">При использовании общей папки можно обновить компьютеры, находящиеся за брандмауэрами или не подключенные к Интернету.</span><span class="sxs-lookup"><span data-stu-id="cf365-161">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="cf365-162">`Save-Help`Команда скачивает самые новые файлы справки для всех модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-162">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="cf365-163">Параметр **DestinationPath** сохраняет файлы в `\\Server01\Share\PSHelp` общей папке.</span><span class="sxs-lookup"><span data-stu-id="cf365-163">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="cf365-164">Параметр **Credential** указывает пользователя, имеющего разрешение на доступ к общей папке.</span><span class="sxs-lookup"><span data-stu-id="cf365-164">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="cf365-165">`Invoke-Command`Командлет запускает удаленные `Update-Help` команды на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cf365-165">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="cf365-166">Параметр **ComputerName** возвращает список удаленных компьютеров из файла **Servers.txt** .</span><span class="sxs-lookup"><span data-stu-id="cf365-166">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="cf365-167">Параметр **ScriptBlock** выполняет `Update-Help` команду и использует параметр **SourcePath** для указания общего файлового ресурса, содержащего обновленные файлы справки.</span><span class="sxs-lookup"><span data-stu-id="cf365-167">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="cf365-168">Параметр **Credential** указывает пользователя, который имеет доступ к общей папке и выполняет удаленную `Update-Help` команду.</span><span class="sxs-lookup"><span data-stu-id="cf365-168">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="cf365-169">Пример 6. Получение списка обновленных файлов справки</span><span class="sxs-lookup"><span data-stu-id="cf365-169">Example 6: Get a list of updated help files</span></span>

<span data-ttu-id="cf365-170">`Update-Help`Командлет обновляет справку для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="cf365-170">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="cf365-171">Командлет использует параметр **verbose** Common для вывода списка обновленных файлов справки.</span><span class="sxs-lookup"><span data-stu-id="cf365-171">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="cf365-172">Для просмотра выходных данных для всех файлов справки и файлов справки для конкретного модуля можно использовать параметр **verbose** .</span><span class="sxs-lookup"><span data-stu-id="cf365-172">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="cf365-173">Без параметра **verbose** `Update-Help` не отображает результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="cf365-173">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="cf365-174">Вывод **подробных** параметров полезен для проверки обновления файлов справки или установки последней версии.</span><span class="sxs-lookup"><span data-stu-id="cf365-174">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="cf365-175">Пример 7. Поиск модулей, поддерживающих обновляемую справку</span><span class="sxs-lookup"><span data-stu-id="cf365-175">Example 7: Find modules that support Updatable Help</span></span>

<span data-ttu-id="cf365-176">В этом примере перечислены модули, поддерживающие обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-176">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="cf365-177">Команда использует свойство **HelpInfoUri** модуля для выявления модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-177">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="cf365-178">Свойство **HelpInfoUri** содержит адрес, который перенаправляется при `Update-Help` выполнении командлета.</span><span class="sxs-lookup"><span data-stu-id="cf365-178">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

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

### <span data-ttu-id="cf365-179">Пример 8. Обновленные файлы справки хранилища</span><span class="sxs-lookup"><span data-stu-id="cf365-179">Example 8: Inventory updated help files</span></span>

<span data-ttu-id="cf365-180">В этом примере сценарий `Get-UpdateHelpVersion.ps1` создает инвентаризацию обновляемых файлов справки для каждого модуля и их номеров версий.</span><span class="sxs-lookup"><span data-stu-id="cf365-180">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="cf365-181">Скрипт определяет модули, поддерживающие обновляемую справку, с помощью свойства **HelpInfoUri** модулей.</span><span class="sxs-lookup"><span data-stu-id="cf365-181">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="cf365-182">Для модулей, поддерживающих обновляемую справку, сценарий ищет и анализирует файл справочной информации (\* helpinfo.xml), чтобы найти номер последней версии.</span><span class="sxs-lookup"><span data-stu-id="cf365-182">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="cf365-183">Для создания пользовательского выходного объекта скрипт использует класс **PSCustomObject** и хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="cf365-183">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

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

## <span data-ttu-id="cf365-184">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cf365-184">PARAMETERS</span></span>

### <span data-ttu-id="cf365-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="cf365-185">-Credential</span></span>

<span data-ttu-id="cf365-186">Указывает учетные данные пользователя, имеющего разрешение на доступ к расположению файловой системы, заданному параметром **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="cf365-186">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath** .</span></span> <span data-ttu-id="cf365-187">Этот параметр допустим, только если в команде используется параметр **SourcePath** или **LiteralPath** .</span><span class="sxs-lookup"><span data-stu-id="cf365-187">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="cf365-188">Параметр **Credential** позволяет выполнять `Update-Help` команды с параметром **SourcePath** на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cf365-188">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="cf365-189">Предоставляя явные учетные данные, можно выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере без возникновения ошибки отказа в доступе или использования проверки подлинности CredSSP для делегирования учетных данных.</span><span class="sxs-lookup"><span data-stu-id="cf365-189">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="cf365-190">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="cf365-190">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="cf365-191">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="cf365-191">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="cf365-192">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="cf365-192">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="cf365-193">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="cf365-193">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="cf365-194">-Force</span><span class="sxs-lookup"><span data-stu-id="cf365-194">-Force</span></span>

<span data-ttu-id="cf365-195">Указывает, что этот командлет не соответствует ограничению "один за день", пропускает проверку версий и скачивает файлы, размер которых превышает ограничение в 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="cf365-195">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="cf365-196">Без этого параметра `Update-Help` выполняется только один раз в 24-часовом периоде.</span><span class="sxs-lookup"><span data-stu-id="cf365-196">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="cf365-197">Размер загружаемых файлов ограничен 1 ГБ несжатого содержимого на модуль, а файлы справки устанавливаются только в том случае, если они новее, чем существующие файлы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-197">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="cf365-198">Ограничение "один за день" защищает серверы, на которых размещаются файлы справки, и упрощает добавление `Update-Help` команды в профиль PowerShell без затрат на ресурсы при повторяющихся подключениях или загрузках.</span><span class="sxs-lookup"><span data-stu-id="cf365-198">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="cf365-199">Чтобы обновить справку для модуля на нескольких языках и в региональных параметрах пользовательского интерфейса без параметра **Force** , включите все языки и региональные параметры пользовательского интерфейса в одну команду, например:</span><span class="sxs-lookup"><span data-stu-id="cf365-199">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

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

### <span data-ttu-id="cf365-200">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="cf365-200">-FullyQualifiedModule</span></span>

<span data-ttu-id="cf365-201">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="cf365-201">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="cf365-202">Эти модули описаны в разделе "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="cf365-202">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="cf365-203">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в формате:</span><span class="sxs-lookup"><span data-stu-id="cf365-203">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="cf365-204">or</span><span class="sxs-lookup"><span data-stu-id="cf365-204">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="cf365-205">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="cf365-205">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="cf365-206">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="cf365-206">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

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

### <span data-ttu-id="cf365-207">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cf365-207">-LiteralPath</span></span>

<span data-ttu-id="cf365-208">Указывает папку для обновленных файлов справки, а не скачивает их из Интернета.</span><span class="sxs-lookup"><span data-stu-id="cf365-208">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="cf365-209">Используйте этот параметр или **SourcePath** , если вы использовали `Save-Help` командлет для загрузки файлов справки в каталог.</span><span class="sxs-lookup"><span data-stu-id="cf365-209">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="cf365-210">Вы можете выполнить конвейер объекта каталога, например из `Get-Item` `Get-ChildItem` командлетов или, в `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="cf365-210">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="cf365-211">В отличие от значения **SourcePath** , значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="cf365-211">Unlike the value of **SourcePath** , the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="cf365-212">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cf365-212">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="cf365-213">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="cf365-213">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="cf365-214">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="cf365-214">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cf365-215">-Module</span><span class="sxs-lookup"><span data-stu-id="cf365-215">-Module</span></span>

<span data-ttu-id="cf365-216">Обновляет справку для указанных модулей.</span><span class="sxs-lookup"><span data-stu-id="cf365-216">Updates help for the specified modules.</span></span> <span data-ttu-id="cf365-217">Введите одно или несколько имен модулей или шаблонов имен в списке с разделителями-запятыми или укажите файл, в котором перечислены имена отдельных модулей в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="cf365-217">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="cf365-218">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cf365-218">Wildcard characters are permitted.</span></span> <span data-ttu-id="cf365-219">Вы можете конвейерировать модули из `Get-Module` командлета в `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="cf365-219">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="cf365-220">Указанные модули должны быть установлены на компьютере, но их не нужно импортировать в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="cf365-220">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="cf365-221">Можно указать любой модуль в сеансе или любой модуль, установленный в расположении, указанном в `$env:PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="cf365-221">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="cf365-222">Значение `*` (все) пытается обновить справку для всех модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-222">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="cf365-223">Включены модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-223">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="cf365-224">Это значение может выдавать ошибки, если команда обнаруживает модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-224">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="cf365-225">Вместо этого запустите `Update-Help` без параметров.</span><span class="sxs-lookup"><span data-stu-id="cf365-225">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="cf365-226">Параметр **module** `Update-Help` командлета не принимает полный путь к файлу модуля или файлу манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="cf365-226">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="cf365-227">Чтобы обновить справку для модуля, который не находится в `$env:PSModulePath` расположении, импортируйте модуль в текущий сеанс перед выполнением `Update-Help` команды.</span><span class="sxs-lookup"><span data-stu-id="cf365-227">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

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

### <span data-ttu-id="cf365-228">-Recurse</span><span class="sxs-lookup"><span data-stu-id="cf365-228">-Recurse</span></span>

<span data-ttu-id="cf365-229">Выполняет рекурсивный поиск файлов справки в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="cf365-229">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="cf365-230">Этот параметр допустим только в том случае, если в команде используется параметр **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="cf365-230">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

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

### <span data-ttu-id="cf365-231">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="cf365-231">-SourcePath</span></span>

<span data-ttu-id="cf365-232">Указывает папку файловой системы `Update-Help` , в которой будут обновляться файлы справки, а не загружать их из Интернета.</span><span class="sxs-lookup"><span data-stu-id="cf365-232">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="cf365-233">Введите путь к папке.</span><span class="sxs-lookup"><span data-stu-id="cf365-233">Enter the path of a folder.</span></span> <span data-ttu-id="cf365-234">Не указывайте имя файла или расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="cf365-234">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="cf365-235">Вы можете конвейерировать папку, такую как, из `Get-Item` `Get-ChildItem` командлетов или, в `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="cf365-235">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="cf365-236">По умолчанию `Update-Help` скачивает обновленные файлы справки из Интернета.</span><span class="sxs-lookup"><span data-stu-id="cf365-236">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="cf365-237">Используйте параметр **SourcePath** , если вы использовали `Save-Help` командлет для загрузки обновленных файлов справки в каталог.</span><span class="sxs-lookup"><span data-stu-id="cf365-237">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="cf365-238">Чтобы указать значение **SourcePath** по умолчанию, перейдите в раздел **Групповая политика** , **Конфигурация компьютера** и **Задайте путь к источнику по умолчанию для Update-Help** .</span><span class="sxs-lookup"><span data-stu-id="cf365-238">To specify a default value for **SourcePath** , go to **Group Policy** , **Computer Configuration** , and **Set the default source path for Update-Help** .</span></span> <span data-ttu-id="cf365-239">Этот параметр групповая политика запрещает пользователям использовать `Update-Help` для загрузки файлов справки из Интернета.</span><span class="sxs-lookup"><span data-stu-id="cf365-239">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="cf365-240">Дополнительные сведения см. в статье [О параметрах групповой политики](./About/about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="cf365-240">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf365-241">-UICulture</span><span class="sxs-lookup"><span data-stu-id="cf365-241">-UICulture</span></span>

<span data-ttu-id="cf365-242">Задает значения языка и региональных параметров пользовательского интерфейса, которые `Update-Help` используются для получения обновленных файлов справки.</span><span class="sxs-lookup"><span data-stu-id="cf365-242">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="cf365-243">Введите один или несколько кодов языка, например **es-ES** , переменную, содержащую объекты языка и региональных параметров, или команду, которая получает объекты языка и региональных параметров, такие как `Get-Culture` `Get-UICulture` команда или.</span><span class="sxs-lookup"><span data-stu-id="cf365-243">Enter one or more language codes, such as **es-ES** , a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="cf365-244">Подстановочные знаки не допускаются, и нельзя отправлять код частичного языка, например **de** .</span><span class="sxs-lookup"><span data-stu-id="cf365-244">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de** .</span></span>

<span data-ttu-id="cf365-245">По умолчанию `Update-Help` получает файлы справки в языке и региональных параметрах пользовательского интерфейса, заданных для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="cf365-245">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="cf365-246">Если указан параметр **UICulture** , `Update-Help` ищет справку только для указанного языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cf365-246">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

<span data-ttu-id="cf365-247">Команды, которые используют параметр **UICulture** , выполняются, только если модуль предоставляет файлы справки для указанного языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cf365-247">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="cf365-248">Если команда завершается ошибкой из-за того, что указанная культура пользовательского интерфейса не поддерживается, выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cf365-248">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

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

### <span data-ttu-id="cf365-249">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="cf365-249">-UseDefaultCredentials</span></span>

<span data-ttu-id="cf365-250">Указывает, что `Update-Help` выполняет команду, включая загрузку из Интернета, используя учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="cf365-250">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="cf365-251">По умолчанию команда выполняется без явных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="cf365-251">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="cf365-252">Этот параметр эффективен, только если веб-скачивание использует проверку подлинности NT LAN Manager (NTLM), согласование или аутентификацию на основе Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cf365-252">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

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

### <span data-ttu-id="cf365-253">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cf365-253">-Confirm</span></span>

<span data-ttu-id="cf365-254">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="cf365-254">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cf365-255">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cf365-255">-WhatIf</span></span>

<span data-ttu-id="cf365-256">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="cf365-256">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cf365-257">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cf365-257">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cf365-258">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cf365-258">CommonParameters</span></span>

<span data-ttu-id="cf365-259">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cf365-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cf365-260">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cf365-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cf365-261">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cf365-261">INPUTS</span></span>

### <span data-ttu-id="cf365-262">System.IO.DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="cf365-262">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="cf365-263">Путь к каталогу можно передать по конвейеру `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="cf365-263">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="cf365-264">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="cf365-264">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="cf365-265">Объект модуля можно передать из `Get-Module` командлета в `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="cf365-265">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="cf365-266">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cf365-266">OUTPUTS</span></span>

### <span data-ttu-id="cf365-267">Нет</span><span class="sxs-lookup"><span data-stu-id="cf365-267">None</span></span>

<span data-ttu-id="cf365-268">`Update-Help` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cf365-268">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="cf365-269">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cf365-269">NOTES</span></span>

<span data-ttu-id="cf365-270">Чтобы обновить справку для модулей PowerShell Core, содержащих команды, установленные с помощью PowerShell, или любой модуль в `$PSHOME\Modules` каталоге, запустите PowerShell с параметром для **запуска от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="cf365-270">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator** .</span></span>

<span data-ttu-id="cf365-271">Только члены группы администраторов на компьютере могут обновлять справку по модулям PowerShell Core, командам, которые устанавливаются вместе с PowerShell и для модулей в `$PSHOME\Modules` папке.</span><span class="sxs-lookup"><span data-stu-id="cf365-271">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="cf365-272">Если у вас нет разрешения на обновление файлов справки, можно прочитать файлы справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cf365-272">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="cf365-273">Например, `Get-Help Update-Help -Online`.</span><span class="sxs-lookup"><span data-stu-id="cf365-273">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="cf365-274">Модули — это наименьшая единица обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="cf365-274">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="cf365-275">Невозможно обновить справку для конкретного командлета.</span><span class="sxs-lookup"><span data-stu-id="cf365-275">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="cf365-276">Чтобы найти модуль, содержащий конкретный командлет, используйте свойство **ModuleName** `Get-Command` командлета, например `(Get-Command Update-Help).ModuleName` .</span><span class="sxs-lookup"><span data-stu-id="cf365-276">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="cf365-277">Поскольку файлы справки устанавливаются в каталог Module, `Update-Help` командлет может установить обновленный файл справки только для модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-277">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="cf365-278">Однако `Save-Help` командлет может сохранить справку для модулей, которые не установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf365-278">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="cf365-279">Если `Update-Help` не удается найти обновленные файлы справки для модуля или не удается найти обновленную справку на указанном языке, она продолжится без вывода сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cf365-279">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="cf365-280">Чтобы увидеть состояние и сведения о ходе выполнения, используйте параметр **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="cf365-280">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="cf365-281">`Update-Help`Командлет появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="cf365-281">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="cf365-282">Он не работает в более ранних версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf365-282">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="cf365-283">На компьютерах, где установлены Windows PowerShell 2,0 и Windows PowerShell 3,0, используйте `Update-Help` командлет в сеансе Windows powershell 3,0 для скачивания и обновления файлов справки.</span><span class="sxs-lookup"><span data-stu-id="cf365-283">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="cf365-284">Файлы справки доступны как для Windows PowerShell 2,0, так и для Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="cf365-284">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="cf365-285">`Update-Help` `Save-Help` Командлеты и используют следующие порты для скачивания файлов справки: порт 80 для HTTP и порт 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf365-285">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="cf365-286">`Update-Help` поддерживает все модули и оснастки PowerShell Core. Другие оснастки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="cf365-286">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="cf365-287">Чтобы обновить справку для модуля в расположении, не указанном в `$env:PSModulePath` переменной среды, импортируйте модуль в текущий сеанс, а затем выполните `Update-Help` команду.</span><span class="sxs-lookup"><span data-stu-id="cf365-287">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="cf365-288">Выполните команду `Update-Help` без параметров или укажите имя модуля с помощью параметра **module** .</span><span class="sxs-lookup"><span data-stu-id="cf365-288">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="cf365-289">Параметр **module** `Update-Help` `Save-Help` командлетов и не принимает полный путь к файлу модуля или файлу манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="cf365-289">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="cf365-290">Любой модуль может поддерживать обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="cf365-290">Any module can support Updatable Help.</span></span> <span data-ttu-id="cf365-291">Инструкции по поддержке обновляемой справки в созданных вами модулях см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="cf365-291">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="cf365-292">`Update-Help` `Save-Help` Командлеты и не поддерживаются в среда предустановки Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="cf365-292">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="cf365-293">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cf365-293">RELATED LINKS</span></span>

[<span data-ttu-id="cf365-294">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="cf365-294">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="cf365-295">Get-Help</span><span class="sxs-lookup"><span data-stu-id="cf365-295">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="cf365-296">Get-Module</span><span class="sxs-lookup"><span data-stu-id="cf365-296">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="cf365-297">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="cf365-297">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="cf365-298">Start-Job</span><span class="sxs-lookup"><span data-stu-id="cf365-298">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="cf365-299">Save-Help</span><span class="sxs-lookup"><span data-stu-id="cf365-299">Save-Help</span></span>](Save-Help.md)
