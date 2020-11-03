---
description: Описание обновляемой справочной системы в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_updatable_help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Updatable_Help
ms.openlocfilehash: 9f946fa1ef0f11efc3e0d964cf9ea8a55e01ff8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231205"
---
# <a name="about-updatable-help"></a><span data-ttu-id="0b484-104">Сведения об обновляемой справке</span><span class="sxs-lookup"><span data-stu-id="0b484-104">About Updatable Help</span></span>

## <a name="short-description"></a><span data-ttu-id="0b484-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="0b484-105">Short description</span></span>
<span data-ttu-id="0b484-106">Описание обновляемой справочной системы в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b484-106">Describes the updatable help system in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0b484-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="0b484-107">Long description</span></span>

<span data-ttu-id="0b484-108">PowerShell предоставляет несколько различных способов доступа к наиболее актуальным разделам справки по командлетам и концепциям PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b484-108">PowerShell provides several different ways to access the most up-to-date help topics for PowerShell cmdlets and concepts.</span></span>

<span data-ttu-id="0b484-109">Обновляемая справочная система, представленная в PowerShell 3,0, предназначена для того, чтобы всегда иметь новейшие разделы справки на локальном компьютере, чтобы вы могли прочитать их в командной строке.</span><span class="sxs-lookup"><span data-stu-id="0b484-109">The Updatable Help system, introduced in PowerShell 3.0, is designed to assure that you always have the newest help topics on your local computer so that you can read them at the command line.</span></span> <span data-ttu-id="0b484-110">Это позволяет легко загружать и устанавливать файлы справки, а также обновлять их каждый раз, когда становятся доступны новые файлы справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-110">It makes it easy to download and install help files and to update them whenever newer help files become available.</span></span>

<span data-ttu-id="0b484-111">Чтобы обеспечить обновленную справку для нескольких компьютеров предприятия и компьютеров, которые не имеют доступа к Интернету, обновляемая Справка позволяет загружать файлы справки в каталог файловой системы или общую папку, а затем устанавливать файлы справки из общей папки.</span><span class="sxs-lookup"><span data-stu-id="0b484-111">To provide updated help for multiple computers in an enterprise and for computers that do not have access to the internet, Updatable Help lets you download help files to a filesystem directory or file share, and then install the help files from the file share.</span></span>

<span data-ttu-id="0b484-112">В PowerShell 4,0 свойство **HelpInfoUri** сохраняется при удаленном взаимодействии Windows PowerShell, что позволяет `Save-Help` работать с модулями, которые установлены на удаленном компьютере, но не обязательно устанавливаются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b484-112">In PowerShell 4.0, the **HelpInfoUri** property is preserved over Windows PowerShell remoting, which allows `Save-Help` to work for modules that are installed on a remote computer, but are not necessarily installed on the local computer.</span></span> <span data-ttu-id="0b484-113">Объект **PSModuleInfo** можно сохранить на диске или съемном носителе (например, на USB-накопителе), запустив `Export-Clixml` на компьютере без доступа к Интернету, импортировав объект **PSModuleInfo** на компьютере, который имеет доступ к Интернету, а затем запуская `Save-Help` объект **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="0b484-113">You can save a **PSModuleInfo** object to disk or removable media (such as a USB drive) by running `Export-Clixml` on a computer that does not have internet access, importing the **PSModuleInfo** object on a computer that does have internet access, and then running `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="0b484-114">Сохраненную справку можно скопировать на удаленный, отключенный компьютер с помощью съемного носителя, а затем установить, запустив `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0b484-114">The saved help can be copied to the remote, disconnected computer by using removable media, and then installed by running `Update-Help`.</span></span> <span data-ttu-id="0b484-115">Эти улучшения `Save-Help` функциональности позволяют установить справку на компьютерах, которые не имеют какого либо сетевого доступа.</span><span class="sxs-lookup"><span data-stu-id="0b484-115">These improvements in `Save-Help` functionality let you install help on computers that are without any kind of network access.</span></span> <span data-ttu-id="0b484-116">Пример использования новых `Save-Help` функциональных возможностей см. в разделе [обновление справки из общей папки](#how-to-update-help-from-a-file-share) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0b484-116">For an example of how to use the new `Save-Help` functionality, see [How to update help from a file share](#how-to-update-help-from-a-file-share) in this topic.</span></span>

<span data-ttu-id="0b484-117">Обновляемая Справка также поддерживает доступ в Интернет к новым темам справки и основную справку по командлетам, даже если на компьютере нет файлов справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-117">Updatable Help also supports online access to the newest help topics and basic help for cmdlets, even when there are no help files on the computer.</span></span>

<span data-ttu-id="0b484-118">PowerShell 3,0 не поставляется с файлами справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-118">PowerShell 3.0 does not come with Help files.</span></span> <span data-ttu-id="0b484-119">Можно использовать функцию обновляемой справки для установки файлов справки для всех команд, включенных по умолчанию в PowerShell, и для всех модулей Windows.</span><span class="sxs-lookup"><span data-stu-id="0b484-119">You can use the Updatable Help feature to install the help files for all of the commands that are included by default in PowerShell and for all Windows modules.</span></span>

## <a name="updatable-help-cmdlets"></a><span data-ttu-id="0b484-120">Обновляемые командлеты справки</span><span class="sxs-lookup"><span data-stu-id="0b484-120">Updatable help cmdlets</span></span>

- <span data-ttu-id="0b484-121">`Update-Help`: Скачивает новейшие файлы справки из Интернета или общей папки и устанавливает их на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="0b484-121">`Update-Help`: Downloads the newest help files from the internet or a file share, and installs them on the local computer.</span></span>

- <span data-ttu-id="0b484-122">`Save-Help`: Скачивает новейшие файлы справки из Интернета и сохраняет их в каталоге файловой системы или в общей папке.</span><span class="sxs-lookup"><span data-stu-id="0b484-122">`Save-Help`: Downloads the newest help files from the internet and saves them in a filesystem directory or file share.</span></span> <span data-ttu-id="0b484-123">Чтобы установить файлы справки на компьютерах, используйте `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0b484-123">To install the help files on computers, use `Update-Help`.</span></span>

- <span data-ttu-id="0b484-124">`Get-Help`: Отображает разделы справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="0b484-124">`Get-Help`: Displays help topics at the command line.</span></span> <span data-ttu-id="0b484-125">Получение справки из файлов справки на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b484-125">Gets help from the help files on the computer.</span></span> <span data-ttu-id="0b484-126">Отображает автоматически созданную справку для командлетов и функций, не имеющих файлов справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-126">Displays auto-generated help for cmdlets and functions that do not have help files.</span></span> <span data-ttu-id="0b484-127">Открывает разделы справки в Интернете по командлетам, функциям, сценариям и рабочим процессам в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b484-127">Opens online help topics for cmdlets, functions, scripts, and workflows in your default internet browser.</span></span>

## <a name="auto-generated-help-help-without-help-files"></a><span data-ttu-id="0b484-128">Автоматически созданная Справка: Справка без файлов справки</span><span class="sxs-lookup"><span data-stu-id="0b484-128">Auto-generated help: help without help files</span></span>

<span data-ttu-id="0b484-129">Если у вас нет файла справки для командлета, функции или рабочего процесса на компьютере, `Get-Help` командлет отображает автоматически созданную справку и предлагает загрузить файлы справки или прочитать их в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0b484-129">If you do not have the help file for a cmdlet, function, or workflow on the computer, the `Get-Help` cmdlet displays auto-generated help and prompts you to download the help files or read them online.</span></span>

<span data-ttu-id="0b484-130">Автоматически созданная Справка содержит синтаксис и псевдонимы, а также комментарии, объясняющие, как использовать обновляемые командлеты справки и получать доступ к разделам справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0b484-130">Auto-generated help includes syntax and aliases, and remarks that explain how to use the Updatable Help cmdlets and to access the online help topics.</span></span>

<span data-ttu-id="0b484-131">Например, следующая команда возвращает основную справку для `Get-Culture` командлета.</span><span class="sxs-lookup"><span data-stu-id="0b484-131">For example, the following command gets basic help for the `Get-Culture` cmdlet.</span></span> <span data-ttu-id="0b484-132">В выходных данных отображается `Get-Help` Отображение, если на компьютере нет файлов справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-132">The output shows the `Get-Help` display when there are no help files on the computer.</span></span>

```powershell
Get-Help Get-Culture
```

```output
NAME
    Get-Culture

SYNTAX
    Get-Culture [<CommonParameters>]

ALIASES
    None

REMARKS
    To get the latest Help content including descriptions and examples
    type: Update-Help.
```

## <a name="help-files-for-modules"></a><span data-ttu-id="0b484-133">Файлы справки для модулей</span><span class="sxs-lookup"><span data-stu-id="0b484-133">Help files for modules</span></span>

<span data-ttu-id="0b484-134">Самая маленькая единица обновляемой справки — Справка по модулю.</span><span class="sxs-lookup"><span data-stu-id="0b484-134">The smallest unit of Updatable Help is help for a module.</span></span> <span data-ttu-id="0b484-135">Справка по модулям включает в себя справку по всем командлетам, функциям, рабочим процессам, поставщикам, скриптам и концепциям в модуле.</span><span class="sxs-lookup"><span data-stu-id="0b484-135">Module help includes help for all of the cmdlets, functions, workflows, providers, scripts, and concepts in a module.</span></span> <span data-ttu-id="0b484-136">Можно обновить справку для всех модулей, установленных на компьютере, даже если они не импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="0b484-136">You can update help for all modules that are installed on the computer, even if they are not imported into the current session.</span></span>

<span data-ttu-id="0b484-137">Можно обновить справку для всего модуля, но нельзя обновить справку для отдельных командлетов.</span><span class="sxs-lookup"><span data-stu-id="0b484-137">You can update help for the entire module, but you cannot update help for individual cmdlets.</span></span>

<span data-ttu-id="0b484-138">Чтобы найти модуль, содержащий конкретный командлет, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="0b484-138">To find the module that contains a particular cmdlet, use the following command format:</span></span>

```powershell
(Get-Command <cmdlet-name>).ModuleName
```

<span data-ttu-id="0b484-139">Например, чтобы найти модуль, содержащий `Set-ExecutionPolicy` командлет, введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-139">For example, to find the module that contains the `Set-ExecutionPolicy` cmdlet, type:</span></span>

```powershell
(Get-Command Set-ExecutionPolicy).ModuleName
```

<span data-ttu-id="0b484-140">Чтобы обновить справку для конкретного модуля, введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-140">To update help for a particular module, type:</span></span>

```powershell
Update-Help -Module <ModuleName>
```

<span data-ttu-id="0b484-141">Например, чтобы обновить справку для модуля, содержащего командлет Set-ExecutionPolicy, введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-141">For example, to update help for the module that contains the Set-ExecutionPolicy cmdlet, type:</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Security
```

## <a name="permissions-for-updatable-help"></a><span data-ttu-id="0b484-142">Разрешения для обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="0b484-142">Permissions for updatable help</span></span>

<span data-ttu-id="0b484-143">Для обновления справки по модулям в каталоге `$pshome/Modules` необходимо быть членом группы администраторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b484-143">To update help for the modules in the directory `$pshome/Modules`, you must be member of the Administrators group on the computer.</span></span>

<span data-ttu-id="0b484-144">Если вы не являетесь членом группы "Администраторы", обновление справки для этих модулей невозможно; но если у вас есть доступ к Интернету, можно просмотреть справку в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0b484-144">If you are not a member of the Administrators group, you cannot update help for these modules; but if you have internet access, you can view help online.</span></span>

<span data-ttu-id="0b484-145">Для обновления справки по модулям в каталоге `$home/Documents/PowerShell/Modules` или модулях в других подкаталогах `$home` каталога не требуются специальные разрешения.</span><span class="sxs-lookup"><span data-stu-id="0b484-145">Updating help for modules in the directory `$home/Documents/PowerShell/Modules` or modules in other subdirectories of the `$home` directory does not require special permissions.</span></span>

<span data-ttu-id="0b484-146">`Update-Help` `Save-Help` Командлеты и имеют параметр **уседефаулткредентиалс** , предоставляющий явные учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b484-146">The `Update-Help` and `Save-Help` cmdlets have a **UseDefaultCredentials** parameter that provides the explicit credentials of the current user.</span></span> <span data-ttu-id="0b484-147">Этот параметр предназначен для доступа к защищенным Интернет-расположениям.</span><span class="sxs-lookup"><span data-stu-id="0b484-147">This parameter is designed for accessing secure internet locations.</span></span>

<span data-ttu-id="0b484-148">`Update-Help` `Save-Help` Командлеты и также имеют параметр **Credential** , позволяющий выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b484-148">The `Update-Help` and `Save-Help` cmdlets also have a **Credential** parameter that allows you to run the command on a remote computer and access a file share on a third computer.</span></span> <span data-ttu-id="0b484-149">Параметр **Credential** допустим только при использовании параметров SourcePath или **LiteralPath** `Update-Help` и параметров **DestinationPath** или **LiteralPath** параметра `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="0b484-149">The **Credential** parameter is valid only when you use the SourcePath or **LiteralPath** parameters of `Update-Help` and the **DestinationPath** or **LiteralPath** parameters of `Save-Help`.</span></span>

## <a name="how-to-install-and-update-help-files"></a><span data-ttu-id="0b484-150">Установка и обновление файлов справки</span><span class="sxs-lookup"><span data-stu-id="0b484-150">How to install and update help files</span></span>

<span data-ttu-id="0b484-151">Чтобы загрузить и установить файлы справки в первый раз или обновить файлы справки на компьютере, используйте `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="0b484-151">To download and install help files for the first time, or to update the help files on your computer, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="0b484-152">`Update-Help`Командлет выполняет всю твердую работу, включая следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="0b484-152">The `Update-Help` cmdlet does all of the hard work for you, including the following tasks.</span></span>

- <span data-ttu-id="0b484-153">Определяет, какие модули поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="0b484-153">Determines which modules support Updatable Help.</span></span>
- <span data-ttu-id="0b484-154">Находит расположение в Интернете, в котором каждый модуль хранит свои обновляемые файлы справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-154">Finds the internet location where each module stores its Updatable Help files.</span></span>
- <span data-ttu-id="0b484-155">Сравнение файлов справки для каждого модуля на компьютере с последними файлами справки, доступными для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="0b484-155">Compares the help files for each module on your computer to the newest help files that are available for each module.</span></span>
- <span data-ttu-id="0b484-156">Скачивает новые файлы из Интернета.</span><span class="sxs-lookup"><span data-stu-id="0b484-156">Downloads the new files from the internet.</span></span>
- <span data-ttu-id="0b484-157">Распаковывает пакет файла справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-157">Unwraps the help file package.</span></span>
- <span data-ttu-id="0b484-158">Проверяет, являются ли файлы допустимыми файлами справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-158">Verifies that the files are valid help files.</span></span>
- <span data-ttu-id="0b484-159">Устанавливает файлы справки в подкаталоге, зависящем от языка, в каталоге Module.</span><span class="sxs-lookup"><span data-stu-id="0b484-159">Installs the help files in the language-specific subdirectory of the module directory.</span></span>

<span data-ttu-id="0b484-160">Для доступа к новым разделам справки используйте `Get-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="0b484-160">To access the new help topics, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="0b484-161">Перезапускать PowerShell не требуется.</span><span class="sxs-lookup"><span data-stu-id="0b484-161">You do not need to restart PowerShell.</span></span>

<span data-ttu-id="0b484-162">Чтобы установить или обновить справку для всех модулей на компьютере, поддерживающем обновляемую справку, введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-162">To install or update help for all modules on the computer that supports Updatable Help, type:</span></span>

```powershell
Update-Help
```

<span data-ttu-id="0b484-163">Чтобы обновить справку для определенных модулей, добавьте параметр **module** в `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0b484-163">To update help for particular modules, add the **Module** parameter of `Update-Help`.</span></span> <span data-ttu-id="0b484-164">В имени модуля допускаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0b484-164">Wildcard characters are permitted in the module name.</span></span>

<span data-ttu-id="0b484-165">Например, чтобы обновить справку для модуля ServerManager, введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-165">For example, to update help for the ServerManager module, type:</span></span>

```powershell
Update-Help -Module ServerManager
```

<span data-ttu-id="0b484-166">Без параметров `Update-Help` обновления помогают для всех модулей в сеансе и для всех установленных модулей, поддерживающих обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="0b484-166">Without parameters, `Update-Help` updates help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="0b484-167">Для включения необходимо установить модули в каталогах, указанных в значении переменной среды PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="0b484-167">To be included, modules must be installed in directories that are listed in the value of the PSModulePath environment variable.</span></span> <span data-ttu-id="0b484-168">Это также модули, возвращаемые командой "Get-Help-ListAvailable".</span><span class="sxs-lookup"><span data-stu-id="0b484-168">These are also modules that are returned by a "Get-Help -ListAvailable" command.</span></span>

<span data-ttu-id="0b484-169">Если параметр **module** имеет значение `*` (ALL), то `Update-Help` пытается обновить справку для всех установленных модулей, включая модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="0b484-169">If the value of the **Module** parameter is `*` (all), `Update-Help` attempts to update help for all installed modules, including modules that do not support Updatable Help.</span></span> <span data-ttu-id="0b484-170">Эта команда обычно создает много ошибок, так как командлет встречает модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="0b484-170">This command typically generates many errors as the cmdlet encounters modules that do not support Updatable Help.</span></span>

## <a name="how-to-update-help-from-a-file-share"></a><span data-ttu-id="0b484-171">Обновление справки из общей папки</span><span class="sxs-lookup"><span data-stu-id="0b484-171">How to update help from a file share</span></span>

<span data-ttu-id="0b484-172">Для поддержки компьютеров, не подключенных к Интернету, а также для управления или оптимизации обновления справки на предприятии используйте `Save-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="0b484-172">To support computers that are not connected to the internet, or to control or streamline help updating in an enterprise, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="0b484-173">`Save-Help`Командлет загружает файлы справки из Интернета и сохраняет их в указанном каталоге файловой системы.</span><span class="sxs-lookup"><span data-stu-id="0b484-173">The `Save-Help` cmdlet downloads help files from the internet and saves them in a filesystem directory that you specify.</span></span>

<span data-ttu-id="0b484-174">`Save-Help` Сравнивает файлы справки в указанном каталоге с последними файлами справки, доступными для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="0b484-174">`Save-Help` compares the help files in the specified directory to the newest help files that are available for each module.</span></span> <span data-ttu-id="0b484-175">Если в каталоге нет файлов справки или более новых файлов справки для модуля, `Save-Help` командлет загружает новые файлы из Интернета.</span><span class="sxs-lookup"><span data-stu-id="0b484-175">If the directory has no help files or newer help files are available for the module, the `Save-Help` cmdlet downloads the new files from the internet.</span></span> <span data-ttu-id="0b484-176">Однако он не распаковывает и не устанавливает файлы справки.</span><span class="sxs-lookup"><span data-stu-id="0b484-176">However, it does not unwrap or install the help files.</span></span>

<span data-ttu-id="0b484-177">Чтобы установить или обновить файлы справки на компьютере из файлов справки, сохраненных в каталоге файловой системы, используйте параметр **SourcePath** `Update-Help` командлета.</span><span class="sxs-lookup"><span data-stu-id="0b484-177">To install or update the help files on a computer from help files that were saved to a filesystem directory, use the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="0b484-178">`Update-Help`Командлет определяет самые новые файлы справки, распаковывает их и проверяет, а также устанавливает их в подкаталоги, зависящие от языка, в каталогах модулей.</span><span class="sxs-lookup"><span data-stu-id="0b484-178">The `Update-Help` cmdlet identifies the newest help files, unwraps and validates them, and installs them in the language-specific subdirectories of the module directories.</span></span>

<span data-ttu-id="0b484-179">Например, чтобы сохранить справку для всех установленных модулей в `\\Server\Share` каталоге, введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-179">For example, to save help for all installed modules to the `\\Server\Share` directory, type:</span></span>

```powershell
Save-Help -DestinationPath \\Server\Share
```

<span data-ttu-id="0b484-180">Затем, чтобы обновить справку из `\\Server\Share` каталога, введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-180">Then, to update help from the `\\Server\Share` directory, type:</span></span>

```powershell
Update-Help -SourcePath \\Server\Share
```

<span data-ttu-id="0b484-181">В следующих примерах показано использование `Save-Help` для сохранения справки по модулям, которые не установлены на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b484-181">The following examples show the use of `Save-Help` to save help for modules that are not installed on the local computer.</span></span> <span data-ttu-id="0b484-182">В этом примере администратор выполняет команду, `Save-Help` чтобы сохранить справку для модуля DhcpServer с клиентского компьютера, подключенного к Интернету, не устанавливая на локальном компьютере роль модуля DhcpServer или DHCP-сервера.</span><span class="sxs-lookup"><span data-stu-id="0b484-182">In this example, the administrator runs `Save-Help` to save the help for the DhcpServer module from an internet-connected client computer, without installing the DhcpServer module or DHCP Server role on the local computer.</span></span>

<span data-ttu-id="0b484-183">Вариант 1. выполните команду, `Invoke-Command` чтобы получить объект **PSModuleInfo** для удаленного модуля, сохраните его в переменной, `$m` а затем выполните `Save-Help` в объекте **PSModuleInfo** , указав переменную в `$m` качестве имени модуля.</span><span class="sxs-lookup"><span data-stu-id="0b484-183">Option 1: Run `Invoke-Command` to get the **PSModuleInfo** object for the remote module, save it in a variable, `$m`, and then run `Save-Help` on the **PSModuleInfo** object by specifying the variable `$m` as the module name.</span></span>

```powershell
$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock
{ Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="0b484-184">Вариант 2. Откройте сеанс PSSession, предназначенный для компьютера, на котором выполняется модуль DHCP-сервера, чтобы получить объект **PSModuleInfo** для модуля, сохраните его в переменной `$m` , а затем выполните `Save-Help` для объекта, сохраненного в `$m` переменной.</span><span class="sxs-lookup"><span data-stu-id="0b484-184">Option 2: Open a PSSession targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName RemoteServer
$m = Get-Module -PSSession $s -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="0b484-185">Вариант 3. Откройте сеанс CIM, предназначенный для компьютера, на котором работает модуль DHCP-сервера, чтобы получить объект **PSModuleInfo** для модуля, сохраните его в переменной `$m` , а затем выполните `Save-Help` для объекта, сохраненного в `$m` переменной.</span><span class="sxs-lookup"><span data-stu-id="0b484-185">Option 3: Open a CIM session, targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$c = New-CimSession -ComputerName RemoteServer
$m = Get-Module -CimSession $c -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="0b484-186">В следующем примере администратор устанавливает справку для модуля DHCP-сервера на компьютере, который не имеет доступа к сети.</span><span class="sxs-lookup"><span data-stu-id="0b484-186">In the following example, the administrator installs help for the DHCP Server module on a computer that does not have network access.</span></span>

<span data-ttu-id="0b484-187">Сначала выполните команду, `Export-Clixml` чтобы экспортировать объект **PSModuleInfo** в общую папку или на съемный носитель.</span><span class="sxs-lookup"><span data-stu-id="0b484-187">First, run `Export-Clixml` to export the **PSModuleInfo** object to a shared folder or to removable media.</span></span>

```powershell
$m = Get-Module -Name DhcpServer -ListAvailable
Export-Clixml -Path E:\UsbFlashDrive\DhcpModule.xml -InputObject $m
```

<span data-ttu-id="0b484-188">Затем необходимо передать съемный носитель на компьютер с доступом к Интернету, а затем импортировать объект **PSModuleInfo** с помощью `Import-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="0b484-188">Next, transport the removable media to a computer that has internet access, and then import the **PSModuleInfo** object with `Import-Clixml`.</span></span> <span data-ttu-id="0b484-189">Выполните команду `Save-Help` , чтобы сохранить справку для импортированного объекта **PSModuleInfo** модуля DhcpServer.</span><span class="sxs-lookup"><span data-stu-id="0b484-189">Run `Save-Help` to save the Help for the imported DhcpServer module **PSModuleInfo** object.</span></span>

```powershell
$deserialized_m = Import-Clixml E:\UsbFlashDrive\DhcpModule.xml
Save-Help -Module $deserialized_m -DestinationPath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="0b484-190">Наконец, выполните транспортный носитель обратно на компьютер без доступа к сети, а затем установите справку, выполнив команду `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0b484-190">Finally, transport the removable media back to the computer that does not have network access, and then install the help by running `Update-Help`.</span></span>

```powershell
Update-Help -Module DhcpServer -SourcePath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="0b484-191">Без параметров `Save-Help` загружает справку по всем модулям в сеансе и ко всем установленным модулям, поддерживающим обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="0b484-191">Without parameters, `Save-Help` downloads help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="0b484-192">Для включения необходимо установить модули в каталогах, указанных в значении `$env:PSModulePath` переменной среды, на локальном компьютере или на удаленном компьютере, для которого требуется сохранить справку.</span><span class="sxs-lookup"><span data-stu-id="0b484-192">To be included, modules must be installed in directories that are listed in the value of the `$env:PSModulePath` environment variable, on either the local computer or on a remote computer for which you want to save help.</span></span> <span data-ttu-id="0b484-193">Это также модули, возвращаемые при выполнении `Get-Help -ListAvailable` команды.</span><span class="sxs-lookup"><span data-stu-id="0b484-193">These are also modules that are returned by running a `Get-Help -ListAvailable` command.</span></span>

## <a name="how-to-update-help-files-in-different-languages"></a><span data-ttu-id="0b484-194">Обновление файлов справки на разных языках</span><span class="sxs-lookup"><span data-stu-id="0b484-194">How to update help files in different languages</span></span>

<span data-ttu-id="0b484-195">По умолчанию `Update-Help` `Save-Help` командлеты и загружают справку по языку и региональным параметрам пользовательского интерфейса, установленным для Windows на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b484-195">By default, the `Update-Help` and `Save-Help` cmdlets download help in the UI culture and language that is set for Windows on the local computer.</span></span> <span data-ttu-id="0b484-196">Если файлы справки для указанных модулей недоступны в локальном пользовательском интерфейсе, `Update-Help` и `Save-Help` для поиска лучшего поддерживаемого языка используются правила резервирования на языке Windows.</span><span class="sxs-lookup"><span data-stu-id="0b484-196">If help files for the specified modules are not available in the local UI culture, `Update-Help` and `Save-Help` use the Windows language fallback rules to find the best supported language.</span></span>

<span data-ttu-id="0b484-197">Однако можно использовать параметры **UICulture** `Update-Help` `Save-Help` командлетов и для загрузки и установки файлов справки в любых культурах пользовательского интерфейса, в которых они доступны.</span><span class="sxs-lookup"><span data-stu-id="0b484-197">However, you can use the **UICulture** parameters of the `Update-Help` and `Save-Help` cmdlets to download and install help files in any UI cultures in which they are available.</span></span>

<span data-ttu-id="0b484-198">Например, чтобы сохранить самые новые файлы справки для всех модулей в сеансе на японском языке (ja-JP) и французском (fr-FR), введите:</span><span class="sxs-lookup"><span data-stu-id="0b484-198">For example, to save the newest help files for all modules on the session in Japanese (Ja-jp) and French (fr-FR), type:</span></span>

```powershell
Save-Help -Path \Server\Share -UICulture ja-jp, fr-fr
```

<span data-ttu-id="0b484-199">Если файлы справки для модулей недоступны на указанных языках, `Update-Help` `Save-Help` командлеты и возвращают сообщение об ошибке, в котором перечислены языки, на которых доступна справка для каждого модуля, чтобы можно было выбрать альтернативный вариант, который наилучшим образом соответствует вашим потребностям.</span><span class="sxs-lookup"><span data-stu-id="0b484-199">If help files for the modules are not available in the languages that you specified, the `Update-Help` and `Save-Help` cmdlets return an error message that lists the languages in which help for each module is available so you can choose the alternative that best meets your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="0b484-200">В настоящее время обновляемое содержимое справки публикуется только на английском языке (EN-US).</span><span class="sxs-lookup"><span data-stu-id="0b484-200">Currently, Updateable Help content is only published in English (en-US).</span></span> <span data-ttu-id="0b484-201">В некоторых системах, отличных от Windows, для явного запроса содержимого необходимо использовать параметр **UICulture** `en-US` .</span><span class="sxs-lookup"><span data-stu-id="0b484-201">On some non-Windows systems you must use the **UICulture** parameter to explicitly request the `en-US` content.</span></span>

## <a name="how-to-use-online-help"></a><span data-ttu-id="0b484-202">Использование справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="0b484-202">How to use online help</span></span>

<span data-ttu-id="0b484-203">Если вы не можете или не хотите обновлять файлы справки на локальном компьютере, вы по-прежнему можете получать самые новые файлы справки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0b484-203">If you cannot or choose not to update the help files on your local computer, you can still get the newest help files online.</span></span>

<span data-ttu-id="0b484-204">Чтобы открыть раздел справки в Интернете для любого командлета или функции, используйте параметр **Online** `Get-Help` командлета.</span><span class="sxs-lookup"><span data-stu-id="0b484-204">To open the online help topic for any cmdlet or function, use the **Online** parameter of the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="0b484-205">Например, следующая команда открывает раздел справки в Интернете для `Get-Job` командлета в браузере по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="0b484-205">For example, the following command opens the online help topic for the `Get-Job` cmdlet in your default internet browser:</span></span>

```powershell
Get-Help Get-Job -Online
```

<span data-ttu-id="0b484-206">Чтобы получить справку в Интернете для скрипта, используйте параметр **Online** и полный путь к скрипту.</span><span class="sxs-lookup"><span data-stu-id="0b484-206">To get online help for a script, use the **Online** parameter and the full path to the script.</span></span>

<span data-ttu-id="0b484-207">Параметр **Online** не работает с разделами About.</span><span class="sxs-lookup"><span data-stu-id="0b484-207">The **Online** parameter does not work with About topics.</span></span> <span data-ttu-id="0b484-208">Разделы о PowerShell, в том числе разделы справки по языку PowerShell, см. в статье [о темах в PowerShell](about.md).</span><span class="sxs-lookup"><span data-stu-id="0b484-208">To see the about topics for PowerShell, including help topics about the PowerShell language, see [PowerShell About Topics](about.md).</span></span>

## <a name="how-to-minimize-or-prevent-internet-downloads"></a><span data-ttu-id="0b484-209">Как выполнить минимальную или невозможность загрузки из Интернета</span><span class="sxs-lookup"><span data-stu-id="0b484-209">How to minimize or prevent internet downloads</span></span>

<span data-ttu-id="0b484-210">Чтобы сократить загрузку из Интернета и предоставить обновляемую справку пользователям, которые не подключены к Интернету, используйте `Save-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="0b484-210">To minimize internet downloads and provide Updatable Help to users who are not connected to the internet, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="0b484-211">Загрузите справку из Интернета и сохраните ее в сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="0b484-211">Download help from the internet and save it to a network share.</span></span> <span data-ttu-id="0b484-212">Затем создайте параметр групповая политика или запланированное задание, которое запускает `Update-Help` команду на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0b484-212">Then, create a Group Policy setting or scheduled job that runs an `Update-Help` command on all computers.</span></span> <span data-ttu-id="0b484-213">Задайте в качестве значения параметра **SourcePath** `Update-Help` командлета сетевую папку.</span><span class="sxs-lookup"><span data-stu-id="0b484-213">Set the value of the **SourcePath** parameter of the `Update-Help` cmdlet to the network share.</span></span>

<span data-ttu-id="0b484-214">Чтобы запретить пользователям, имеющим доступ к Интернету, загрузку обновляемой справки из Интернета, используйте параметр **задать путь к источнику по умолчанию для параметра обновить-Help** групповая политика.</span><span class="sxs-lookup"><span data-stu-id="0b484-214">To prevent users who have internet access from downloading Updatable Help from the internet, use the **Set the default source path for Update-Help** Group Policy setting.</span></span>

<span data-ttu-id="0b484-215">Этот групповая политика неявно добавляет параметр **SourcePath** с указанной папкой FileSystem в каждую `Update-Help` команду на каждом затронутом компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b484-215">This Group Policy setting implicitly adds the **SourcePath** parameter, with the filesystem location that you specify, to every `Update-Help` command on every affected computer.</span></span> <span data-ttu-id="0b484-216">Пользователи могут явно использовать параметр **SourcePath** , чтобы указать другое расположение файловой системы, но не может исключить параметр **SourcePath** и загрузить справку из Интернета.</span><span class="sxs-lookup"><span data-stu-id="0b484-216">Users can use the **SourcePath** parameter explicitly to specify a different filesystem location, but they cannot exclude the **SourcePath** parameter and download help from the internet.</span></span>

> [!NOTE]
> <span data-ttu-id="0b484-217">В разделе **Конфигурация компьютера** и **Конфигурация пользователя** появится параметр **задать исходный путь по умолчанию для групповой политики обновления-справки** .</span><span class="sxs-lookup"><span data-stu-id="0b484-217">The **Set the default source path for Update-Help** group policy setting appears under **Computer Configuration** and **User Configuration** .</span></span> <span data-ttu-id="0b484-218">Однако действует только параметр политики в разделе **Конфигурация компьютера** .</span><span class="sxs-lookup"><span data-stu-id="0b484-218">However, only the policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="0b484-219">Параметр политики в разделе **Конфигурация пользователя** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="0b484-219">The policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="0b484-220">Дополнительные сведения см. в статье [О параметрах групповой политики](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="0b484-220">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="how-to-update-help-for-non-standard-modules"></a><span data-ttu-id="0b484-221">Обновление справки по нестандартным модулям</span><span class="sxs-lookup"><span data-stu-id="0b484-221">How to update help for non-standard modules</span></span>

<span data-ttu-id="0b484-222">Чтобы обновить или сохранить справку для модуля, который не возвращается параметром **ListAvailable** `Get-Module` командлета, импортируйте модуль в текущий сеанс перед выполнением `Update-Help` `Save-Help` команды или.</span><span class="sxs-lookup"><span data-stu-id="0b484-222">To update or save help for a module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, import the module into the current session before running an `Update-Help` or `Save-Help` command.</span></span> <span data-ttu-id="0b484-223">На удаленном компьютере перед выполнением `Save-Help` команды Импортируйте модуль в текущий сеанс или `Invoke-Command` блок сценария, подключенный к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0b484-223">On a remote computer, before running the `Save-Help` command, import the module into the current Session, or `Invoke-Command` script block, that is connected to the remote computer.</span></span>

<span data-ttu-id="0b484-224">Если модуль находится в текущем сеансе, выполните `Update-Help` `Save-Help` командлеты или без параметров или используйте параметр **module** , чтобы указать имя модуля.</span><span class="sxs-lookup"><span data-stu-id="0b484-224">When the module is in the current session, run the `Update-Help` or `Save-Help` cmdlets without parameters, or use the **Module** parameter to specify the module name.</span></span>

<span data-ttu-id="0b484-225">Параметры **модуля** `Update-Help` `Save-Help` командлетов и принимают только имя модуля.</span><span class="sxs-lookup"><span data-stu-id="0b484-225">The **Module** parameters of the `Update-Help` and `Save-Help` cmdlets accept only a module name.</span></span> <span data-ttu-id="0b484-226">Они не принимают путь к файлу модуля.</span><span class="sxs-lookup"><span data-stu-id="0b484-226">They do not accept the path to a module file.</span></span>

<span data-ttu-id="0b484-227">Эта методика используется для обновления или сохранения справки для любого модуля, который не возвращается параметром **ListAvailable** `Get-Module` командлета, например модуля, установленного в расположении, отсутствующем в `$env:PSModulePath` переменной среды, или неверно сформированном модуле (каталог модуля не содержит по крайней мере одного файла, базовое имя которого совпадает с именем каталога).</span><span class="sxs-lookup"><span data-stu-id="0b484-227">Use this technique to update or save help for any module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, such as a module that is installed in a location that is not listed in the `$env:PSModulePath` environment variable, or a module that is not well-formed (the module directory does not contain at least one file whose basename is the same as the directory name).</span></span>

## <a name="how-to-support-updatable-help"></a><span data-ttu-id="0b484-228">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="0b484-228">How to support updatable help</span></span>

<span data-ttu-id="0b484-229">При создании модуля можно поддерживать интерактивную справку и обновляемую справку для модулей.</span><span class="sxs-lookup"><span data-stu-id="0b484-229">If you author a module, you can support online help and Updatable Help for your modules.</span></span> <span data-ttu-id="0b484-230">Дополнительные сведения см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/help/supporting-updatable-help) и [поддержка справки в Интернете](/powershell/scripting/developer/module/supporting-online-help) в документация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0b484-230">For more information, see [Supporting Updatable Help](/powershell/scripting/developer/help/supporting-updatable-help) and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help) in the Microsoft Docs.</span></span>

<span data-ttu-id="0b484-231">Обновляемая Справка недоступна для оснасток PowerShell или справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="0b484-231">Updatable help not available for PowerShell snap-ins or comment-based help.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b484-232">Remarks</span><span class="sxs-lookup"><span data-stu-id="0b484-232">Remarks</span></span>

<span data-ttu-id="0b484-233">`Update-Help` `Save-Help` Командлеты и не поддерживаются в среда предустановки Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="0b484-233">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b484-234">См. также статью</span><span class="sxs-lookup"><span data-stu-id="0b484-234">See also</span></span>

[<span data-ttu-id="0b484-235">Get-Help</span><span class="sxs-lookup"><span data-stu-id="0b484-235">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="0b484-236">Save-Help</span><span class="sxs-lookup"><span data-stu-id="0b484-236">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

[<span data-ttu-id="0b484-237">Update-Help</span><span class="sxs-lookup"><span data-stu-id="0b484-237">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)
