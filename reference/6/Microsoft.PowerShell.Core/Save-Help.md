---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: b4306807735d4ffd64850149f5558390f613976b
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387300"
---
# <span data-ttu-id="bd3a0-103">Save-Help</span><span class="sxs-lookup"><span data-stu-id="bd3a0-103">Save-Help</span></span>

## <span data-ttu-id="bd3a0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bd3a0-104">SYNOPSIS</span></span>
<span data-ttu-id="bd3a0-105">Скачивает и сохраняет последние файлы справки в каталог файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-105">Downloads and saves the newest help files to a file system directory.</span></span>

## <span data-ttu-id="bd3a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd3a0-106">SYNTAX</span></span>

### <span data-ttu-id="bd3a0-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bd3a0-107">Path (Default)</span></span>

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### <span data-ttu-id="bd3a0-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bd3a0-108">LiteralPath</span></span>

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## <span data-ttu-id="bd3a0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd3a0-109">DESCRIPTION</span></span>

<span data-ttu-id="bd3a0-110">`Save-Help`Командлет загружает новейшие файлы справки для модулей PowerShell и сохраняет их в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-110">The `Save-Help` cmdlet downloads the newest help files for PowerShell modules and saves them to a directory that you specify.</span></span> <span data-ttu-id="bd3a0-111">Эта функция позволяет обновлять файлы справки на компьютерах без доступа к Интернету и упрощает обновление файлов справки на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-111">This feature lets you update the help files on computers that do not have access to the Internet, and makes it easier to update the help files on multiple computers.</span></span>

<span data-ttu-id="bd3a0-112">В Windows PowerShell 3,0 `Save-Help` работает только для модулей, установленных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-112">In Windows PowerShell 3.0, `Save-Help` worked only for modules that are installed on the local computer.</span></span> <span data-ttu-id="bd3a0-113">Хотя можно импортировать модуль с удаленного компьютера или получить ссылку на объект **PSModuleInfo** с удаленного компьютера с помощью удаленного взаимодействия PowerShell, свойство **HelpInfoUri** не было сохранено и `Save-Help` не будет работать в справке по удаленному модулю.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-113">Although it was possible to import a module from a remote computer, or obtain a reference to a **PSModuleInfo** object from a remote computer by using PowerShell remoting, the **HelpInfoUri** property was not preserved, and `Save-Help` would not work for remote module Help.</span></span>

<span data-ttu-id="bd3a0-114">В Windows PowerShell 4,0 свойство **HelpInfoUri** сохраняется через удаленное взаимодействие PowerShell, что позволяет `Save-Help` работать с модулями, установленными на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-114">In Windows PowerShell 4.0, the **HelpInfoUri** property is preserved over PowerShell remoting, which enables `Save-Help` to work for modules that are installed on remote computers.</span></span> <span data-ttu-id="bd3a0-115">Можно также сохранить объект **PSModuleInfo** на диске или съемном носителе, запустив `Export-Clixml` на компьютере, который не подключен к Интернету, импортировать объект на компьютере, который имеет доступ к Интернету, а затем запустить `Save-Help` на объекте **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-115">It is also possible to save a **PSModuleInfo** object to disk or removable media by running `Export-Clixml` on a computer that does not have Internet access, import the object on a computer that does have Internet access, and then run `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="bd3a0-116">Сохраненная Справка может быть перенесена на удаленный компьютер с помощью съемных носителей, таких как USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-116">The saved help can be transported to the remote computer by using removable storage media, such as a USB drive.</span></span> <span data-ttu-id="bd3a0-117">Справку можно установить на удаленном компьютере, выполнив команду `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-117">The help can be installed on the remote computer by running `Update-Help`.</span></span> <span data-ttu-id="bd3a0-118">Этот процесс можно использовать для установки справки на компьютерах без доступа к какой-либо сети.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-118">This process can be used to install help on computers that do not have any kind of network access.</span></span>

<span data-ttu-id="bd3a0-119">Чтобы установить сохраненные файлы справки, выполните `Update-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-119">To install saved help files, run the `Update-Help` cmdlet.</span></span> <span data-ttu-id="bd3a0-120">Добавьте его параметр **SourcePath** , чтобы указать папку, в которой были сохранены файлы справки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-120">Add its **SourcePath** parameter to specify the folder in which you saved the Help files.</span></span>

<span data-ttu-id="bd3a0-121">Без параметров `Save-Help` команда загружает новейшую справку для всех модулей в сеансе и для модулей, установленных на компьютере, в расположении, указанном в переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-121">Without parameters, a `Save-Help` command downloads the newest help for all modules in the session and for modules that are installed on the computer in a location listed in the **PSModulePath** environment variable.</span></span> <span data-ttu-id="bd3a0-122">Это действие пропускает модули, которые не поддерживают обновляемую справку без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-122">This action skips modules that do not support Updatable Help without warning.</span></span>

<span data-ttu-id="bd3a0-123">`Save-Help`Командлет проверяет версию всех файлов справки в папке назначения.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-123">The `Save-Help` cmdlet checks the version of any help files in the destination folder.</span></span> <span data-ttu-id="bd3a0-124">Если доступны новые файлы справки, этот командлет скачивает новейшие файлы справки из Интернета, а затем сохраняет их в папке.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-124">If newer help files are available, this cmdlet downloads the newest help files from the Internet, and then saves them in the folder.</span></span> <span data-ttu-id="bd3a0-125">`Save-Help`Командлет работает так же, как и `Update-Help` командлет, за исключением того, что он сохраняет загруженные CAB-файлы, а не извлекает файлы справки из этих CAB-файлов и не устанавливает их на компьютер.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-125">The `Save-Help` cmdlet works just like the `Update-Help` cmdlet, except that it saves the downloaded cabinet (.cab) files, instead of extracting the help files from the cabinet files and installing them on the computer.</span></span>

<span data-ttu-id="bd3a0-126">Сохраненные файлы справки для каждого модуля — это один файл сведений о справке (HelpInfo XML) и по одному CAB-файлу для каждого языка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-126">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="bd3a0-127">Нет необходимости извлекать файлы справки из CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-127">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="bd3a0-128">`Update-Help`Командлет извлекает файлы справки, проверяет XML для обеспечения безопасности, а затем устанавливает файлы справки и файл справки в подпапку, зависящую от языка, в папке Module.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-128">The `Update-Help` cmdlet extracts the help files, validates the XML for safety, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>

<span data-ttu-id="bd3a0-129">Чтобы сохранить файлы справки для модулей в папке установки PowerShell ( `$pshome\Modules` ), запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-129">To save the help files for modules in the PowerShell installation folder (`$pshome\Modules`), start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="bd3a0-130">Для загрузки файлов справки для этих модулей необходимо быть членом группы администраторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-130">You must be a member of the Administrators group on the computer to download the help files for these modules.</span></span>

<span data-ttu-id="bd3a0-131">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="bd3a0-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="bd3a0-132">EXAMPLES</span></span>

### <span data-ttu-id="bd3a0-133">Пример 1. Сохранение справки для модуля DhcpServer</span><span class="sxs-lookup"><span data-stu-id="bd3a0-133">Example 1: Save the help for the DhcpServer module</span></span>

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module,
# save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

<span data-ttu-id="bd3a0-134">В этом примере показаны три разных способа `Save-Help` сохранения справки для модуля **DhcpServer** с клиентского компьютера, подключенного к Интернету, без установки модуля **DhcpServer** или роли DHCP-сервера на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-134">This example shows three different ways to use `Save-Help` to save the help for the **DhcpServer** module from an Internet-connected client computer, without installing the **DhcpServer** module or the DHCP Server role on the local computer.</span></span>

### <span data-ttu-id="bd3a0-135">Пример 2. Установка справки для модуля DhcpServer</span><span class="sxs-lookup"><span data-stu-id="bd3a0-135">Example 2: Install help for the DhcpServer module</span></span>

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the
# PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer
# module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and
# then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

<span data-ttu-id="bd3a0-136">В этом примере показано, как установить справку, сохраненную в примере 1 для модуля **DhcpServer** на компьютере без доступа к Интернету.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-136">This example shows how to install help that you saved in Example 1 for the **DhcpServer** module on a computer that does not have Internet access.</span></span>

### <span data-ttu-id="bd3a0-137">Пример 3. Сохранение справки для всех модулей</span><span class="sxs-lookup"><span data-stu-id="bd3a0-137">Example 3: Save help for all modules</span></span>

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

<span data-ttu-id="bd3a0-138">Эта команда загружает последние файлы справки для всех модулей для языка Windows на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-138">This command downloads the newest help files for all modules in the UI culture set for Windows on the local computer.</span></span> <span data-ttu-id="bd3a0-139">Файлы справки сохраняются в `\\Server01\Fileshare01` папке.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-139">It saves the help files in the `\\Server01\Fileshare01` folder.</span></span>

### <span data-ttu-id="bd3a0-140">Пример 4. Сохранение справки для модуля на компьютере</span><span class="sxs-lookup"><span data-stu-id="bd3a0-140">Example 4: Save help for a module on the computer</span></span>

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

<span data-ttu-id="bd3a0-141">Эта команда скачивает новейшие файлы справки для модуля **ServerManager** , а затем сохраняет их в `\\Server01\Fileshare01` папке.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-141">This command downloads the newest help files for the **ServerManager** module, and then saves them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="bd3a0-142">Если модуль установлен на компьютере, можно ввести имя модуля в параметре **Module** , даже если модуль не импортируется в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-142">When a module is installed on the computer, you can type the module name as the value of the **Module** parameter, even if the module is not imported into the current session.</span></span>

<span data-ttu-id="bd3a0-143">Команда использует параметр **Credential** , чтобы передать учетные данные пользователя с разрешением на запись в общую папку.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-143">The command uses the **Credential** parameter to supply the credentials of a user who has permission to write to the file share.</span></span>

### <span data-ttu-id="bd3a0-144">Пример 5. Сохранение справки для модуля на другом компьютере</span><span class="sxs-lookup"><span data-stu-id="bd3a0-144">Example 5: Save help for a module on a different computer</span></span>

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

<span data-ttu-id="bd3a0-145">Эти команды загружают самые новые файлы справки для модуля **кустомскл** и сохраняют их в `\\Server01\Fileshare01` папке.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-145">These commands download the newest help files for the **CustomSQL** module and save them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="bd3a0-146">Так как модуль **кустомскл** не установлен на компьютере, последовательность включает `Invoke-Command` команду, которая получает объект модуля для модуля Кустомскл с компьютера Server02, а затем передает объект модуля в `Save-Help` командлет.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-146">Because the **CustomSQL** module is not installed on the computer, the sequence includes an `Invoke-Command` command that gets the module object for the CustomSQL module from the Server02 computer and then pipes the module object to the `Save-Help` cmdlet.</span></span>

<span data-ttu-id="bd3a0-147">Если модуль не установлен на компьютере, `Save-Help` требуется объект модуля, который содержит сведения о расположении самых новых файлов справки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-147">When a module is not installed on the computer, `Save-Help` needs the module object, which includes information about the location of the newest help files.</span></span>

### <span data-ttu-id="bd3a0-148">Пример 6. Сохранение справки для модуля на нескольких языках</span><span class="sxs-lookup"><span data-stu-id="bd3a0-148">Example 6: Save help for a module in multiple languages</span></span>

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

<span data-ttu-id="bd3a0-149">Эта команда сохраняет справку для модулей PowerShell Core в четырех различных культурах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-149">This command saves help for the PowerShell Core modules in four different UI cultures.</span></span> <span data-ttu-id="bd3a0-150">Языковые пакеты для этих языков не должны устанавливаться на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-150">The language packs for these locales do not have to be installed on the computer.</span></span>

<span data-ttu-id="bd3a0-151">`Save-Help` может скачивать файлы справки для модулей в различных культурах пользовательского интерфейса только в том случае, если владелец модуля делает переведенные файлы доступными в Интернете.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-151">`Save-Help` can download help files for modules in different UI cultures only when the module owner makes the translated files available on the Internet.</span></span>

### <span data-ttu-id="bd3a0-152">Пример 7. Сохранение справки более одного раза в день</span><span class="sxs-lookup"><span data-stu-id="bd3a0-152">Example 7: Save help more than one time each day</span></span>

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

<span data-ttu-id="bd3a0-153">Эта команда сохраняет справку для всех модулей, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-153">This command saves help for all modules that are installed on the computer.</span></span> <span data-ttu-id="bd3a0-154">Команда задает параметр **Force** для переопределения правила, которое не позволяет `Save-Help` командлету загружать справку более одного раза в течение каждого 24-часового периода.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-154">The command specifies the **Force** parameter to override the rule that prevents the `Save-Help` cmdlet from downloading help more than once in each 24-hour period.</span></span>

<span data-ttu-id="bd3a0-155">Параметр **Force** также переопределяет ограничение 1 ГБ и обходит проверку версии.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-155">The **Force** parameter also overrides the 1 GB restriction and circumvents version checking.</span></span>
<span data-ttu-id="bd3a0-156">Таким образом, можно загружать файлы, даже если версия не превышает версию в папке назначения.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-156">Therefore, you can download files even if the version is not later than the version in the destination folder.</span></span>

<span data-ttu-id="bd3a0-157">Команда использует `Save-Help` командлет для загрузки и сохранения файлов справки в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-157">The command uses the `Save-Help` cmdlet to download and save the help files to the specified folder.</span></span>
<span data-ttu-id="bd3a0-158">Параметр **Force** необходим, если необходимо выполнять `Save-Help` команду более одного раза каждый день.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-158">The **Force** parameter is required when you have to run a `Save-Help` command more than one time each day.</span></span>

## <span data-ttu-id="bd3a0-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd3a0-159">PARAMETERS</span></span>

### <span data-ttu-id="bd3a0-160">-Credential</span><span class="sxs-lookup"><span data-stu-id="bd3a0-160">-Credential</span></span>

<span data-ttu-id="bd3a0-161">Указывает учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-161">Specifies a user credential.</span></span> <span data-ttu-id="bd3a0-162">Этот командлет выполняет команду, используя учетные данные пользователя, имеющего разрешение на доступ к расположению файловой системы, заданному параметром **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-162">This cmdlet runs the command by using credentials of a user who has permission to access the file system location specified by the **DestinationPath** parameter.</span></span> <span data-ttu-id="bd3a0-163">Этот параметр доступен, только если в команде используется параметр **DestinationPath** или **LiteralPath**.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-163">This parameter is valid only when the **DestinationPath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="bd3a0-164">Этот параметр позволяет выполнять `Save-Help` команды, использующие параметр **DestinationPath** на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-164">This parameter enables you to run `Save-Help` commands that use the **DestinationPath** parameter on remote computers.</span></span> <span data-ttu-id="bd3a0-165">Предоставляя явные учетные данные, можно выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере без возникновения ошибки отказа в доступе или использования проверки подлинности CredSSP для делегирования учетных данных.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-165">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="bd3a0-166">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-166">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="bd3a0-167">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-167">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="bd3a0-168">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="bd3a0-168">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="bd3a0-169">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="bd3a0-169">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3a0-170">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="bd3a0-170">-DestinationPath</span></span>

<span data-ttu-id="bd3a0-171">Указывает путь к папке, в которой сохраняются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-171">Specifies the path of the folder in which the help files are saved.</span></span> <span data-ttu-id="bd3a0-172">Не указывайте имя или расширение файла.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-172">Do not specify a file name or file name extension.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3a0-173">-Force</span><span class="sxs-lookup"><span data-stu-id="bd3a0-173">-Force</span></span>

<span data-ttu-id="bd3a0-174">Указывает, что этот командлет не соответствует ограничению "один за день", пропускает проверку версий и скачивает файлы, превышающие ограничение в 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-174">Indicates that this cmdlet does not follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="bd3a0-175">Без этого параметра `Save-Help` для каждого модуля допускается только одна команда в течение 24 часов, Загрузка ограничена 1 ГБ несжатого содержимого на модуль, а файлы справки для модуля устанавливаются только в том случае, если они новее, чем файлы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-175">Without this parameter, only one `Save-Help` command for each module is permitted in each 24-hour period, downloads are limited to 1 GB of uncompressed content per module, and help files for a module are installed only when they are newer than the files on the computer.</span></span>

<span data-ttu-id="bd3a0-176">Ограничение "один за день" защищает серверы, на которых размещаются файлы справки, и упрощает добавление `Save-Help` команды в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-176">The once-per-day limit protects the servers that host the help files, and makes it practical for you to add a `Save-Help` command to your PowerShell profile.</span></span>

<span data-ttu-id="bd3a0-177">Чтобы сохранить справку для модуля в нескольких культурах пользовательского интерфейса без параметра **Force** , включите все языки и региональные параметры пользовательского интерфейса в той же команде, например: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span><span class="sxs-lookup"><span data-stu-id="bd3a0-177">To save help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3a0-178">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="bd3a0-178">-FullyQualifiedModule</span></span>

<span data-ttu-id="bd3a0-179">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-179">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="bd3a0-180">См. раздел "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="bd3a0-180">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="bd3a0-181">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="bd3a0-181">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="bd3a0-182">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-182">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="bd3a0-183">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-183">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="bd3a0-184">два параметра являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-184">the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="bd3a0-185">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bd3a0-185">-LiteralPath</span></span>

<span data-ttu-id="bd3a0-186">Указывает путь к папке назначения.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-186">Specifies a path of the destination folder.</span></span> <span data-ttu-id="bd3a0-187">В отличие от значения параметра **DestinationPath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-187">Unlike the value of the **DestinationPath** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="bd3a0-188">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-188">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="bd3a0-189">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-189">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="bd3a0-190">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-190">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3a0-191">-Module</span><span class="sxs-lookup"><span data-stu-id="bd3a0-191">-Module</span></span>

<span data-ttu-id="bd3a0-192">Указывает модули, для которых этот командлет скачивает справку.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-192">Specifies modules for which this cmdlet downloads help.</span></span> <span data-ttu-id="bd3a0-193">Введите одно или несколько имен модулей или имя шаблонов в списке с разделителями-запятыми или в файле с одним именем модуля в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-193">Enter one or more module names or name patters in a comma-separated list or in a file that has one module name on each line.</span></span> <span data-ttu-id="bd3a0-194">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="bd3a0-195">Также можно передать объекты модуля из `Get-Module` командлета в `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-195">You can also pipe module objects from the `Get-Module` cmdlet to `Save-Help`.</span></span>

<span data-ttu-id="bd3a0-196">По умолчанию `Save-Help` загружает справку для всех модулей, поддерживающих обновляемую справку и установленных на локальном компьютере в расположении, указанном в переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-196">By default, `Save-Help` downloads help for all modules that support Updatable Help and are installed on the local computer in a location listed in the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="bd3a0-197">Чтобы сохранить справку для модулей, которые не установлены на компьютере, выполните `Get-Module` команду на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-197">To save help for modules that are not installed on the computer, run a `Get-Module` command on a remote computer.</span></span> <span data-ttu-id="bd3a0-198">Затем передавайте полученные объекты модуля в `Save-Help` командлет или отправьте объекты модуля в качестве значения параметров **модуля** или **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-198">Then pipe the resulting module objects to the `Save-Help` cmdlet or submit the module objects as the value of the **Module** or **InputObject** parameters.</span></span>

<span data-ttu-id="bd3a0-199">Если указанный модуль установлен на компьютере, можно ввести имя модуля или объект модуля.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-199">If the module that you specify is installed on the computer, you can enter the module name or a module object.</span></span> <span data-ttu-id="bd3a0-200">Если модуль не установлен на компьютере, необходимо ввести объект модуля, например один из них, возвращаемый `Get-Module` командлетом.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-200">If the module is not installed on the computer, you must enter a module object, such as one returned by the `Get-Module` cmdlet.</span></span>

<span data-ttu-id="bd3a0-201">Параметр **module** `Save-Help` командлета не принимает полный путь к файлу модуля или файлу манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-201">The **Module** parameter of the `Save-Help` cmdlet does not accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="bd3a0-202">Чтобы сохранить справку для модуля, который не находится в **PSModulePath** расположении, импортируйте модуль в текущий сеанс перед выполнением `Save-Help` команды.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-202">To save help for a module that is not in a **PSModulePath** location, import the module into the current session before you run the `Save-Help` command.</span></span>

<span data-ttu-id="bd3a0-203">Значение "\*" (все) пытается обновить справку для всех модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-203">A value of "\*" (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="bd3a0-204">Сюда входят модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-204">This includes modules that do not support Updatable Help.</span></span> <span data-ttu-id="bd3a0-205">Это значение может выдавать ошибки, если команда обнаруживает модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-205">This value might generate errors when the command encounters modules that do not support Updatable Help.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="bd3a0-206">-UICulture</span><span class="sxs-lookup"><span data-stu-id="bd3a0-206">-UICulture</span></span>

<span data-ttu-id="bd3a0-207">Задает значения языка и региональных параметров пользовательского интерфейса, для которых этот командлет получает обновленные файлы справки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-207">Specifies UI culture values for which this cmdlet gets updated help files.</span></span> <span data-ttu-id="bd3a0-208">Введите один или несколько кодов языка, например `es-ES` , переменную, содержащую объекты языка и региональных параметров, или команду, которая получает объекты языка и региональных параметров, такие как `Get-Culture` `Get-UICulture` команда или.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-208">Enter one or more language codes, such as `es-ES`, a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span>

<span data-ttu-id="bd3a0-209">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-209">Wildcard characters are not permitted.</span></span> <span data-ttu-id="bd3a0-210">Не указывайте код частичного языка, например "de".</span><span class="sxs-lookup"><span data-stu-id="bd3a0-210">Do not specify a partial language code, such as "de".</span></span>

<span data-ttu-id="bd3a0-211">По умолчанию `Save-Help` получает файлы справки в языке и региональных параметрах пользовательского интерфейса для Windows или его резервного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-211">By default, `Save-Help` gets help files in the UI culture set for Windows or its fallback culture.</span></span>
<span data-ttu-id="bd3a0-212">Если указан параметр **UICulture** , `Save-Help` ищет справку только для указанной культуры пользовательского интерфейса, а не для резервной культуры.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-212">If you specify the **UICulture** parameter, `Save-Help` looks for help only for the specified UI culture, not in any fallback culture.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3a0-213">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="bd3a0-213">-UseDefaultCredentials</span></span>

<span data-ttu-id="bd3a0-214">Указывает, что этот командлет выполняет команду, включая загрузку в Интернете, с учетными данными текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-214">Indicates that this cmdlet runs the command, including the web download, with the credentials of the current user.</span></span> <span data-ttu-id="bd3a0-215">По умолчанию команда выполняется без явных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-215">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="bd3a0-216">Этот параметр действует, только если веб-загрузка использует проверку подлинности NTLM, проверку подлинности с согласованием или проверку подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-216">This parameter is effective only when the web download uses NTLM, negotiate, or Kerberos-based authentication.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd3a0-217">-Scope</span><span class="sxs-lookup"><span data-stu-id="bd3a0-217">-Scope</span></span>

<span data-ttu-id="bd3a0-218">Этот не делает ничего в этом командлете.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-218">This paramater does nothing in this cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bd3a0-219">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bd3a0-219">CommonParameters</span></span>

<span data-ttu-id="bd3a0-220">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd3a0-221">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd3a0-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd3a0-222">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bd3a0-222">INPUTS</span></span>

### <span data-ttu-id="bd3a0-223">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="bd3a0-223">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="bd3a0-224">Объект модуля можно передать из `Get-Module` командлета в параметр **модуля** `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-224">You can pipe a module object from the `Get-Module` cmdlet to the **Module** parameter of `Save-Help`.</span></span>

## <span data-ttu-id="bd3a0-225">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bd3a0-225">OUTPUTS</span></span>

### <span data-ttu-id="bd3a0-226">Нет</span><span class="sxs-lookup"><span data-stu-id="bd3a0-226">None</span></span>

<span data-ttu-id="bd3a0-227">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-227">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bd3a0-228">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bd3a0-228">NOTES</span></span>

- <span data-ttu-id="bd3a0-229">Чтобы сохранить справку по модулям в папке $pshome \Модулес, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-229">To save help for modules in the $pshome\Modules folder, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="bd3a0-230">Только члены группы "Администраторы" на компьютере могут загружать справку по модулям в папке $pshome \Модулес.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-230">Only members of the Administrators group on the computer can download help for modules in the $pshome\Modules folder.</span></span>
- <span data-ttu-id="bd3a0-231">Сохраненные файлы справки для каждого модуля — это один файл сведений о справке (HelpInfo XML) и по одному CAB-файлу для каждого языка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-231">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="bd3a0-232">Нет необходимости извлекать файлы справки из CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-232">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="bd3a0-233">`Update-Help`Командлет извлекает файлы справки, проверяет XML, а затем устанавливает файлы справки и файл справки в подпапку, зависящую от языка, в папке Module.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-233">The `Update-Help` cmdlet extracts the help files, validates the XML, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>
- <span data-ttu-id="bd3a0-234">`Save-Help`Командлет может сохранить справку для модулей, которые не установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-234">The `Save-Help` cmdlet can save help for modules that are not installed on the computer.</span></span> <span data-ttu-id="bd3a0-235">Однако, поскольку файлы справки устанавливаются в папку Module, `Update-Help` командлет может установить обновленный файл справки только для модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-235">However, because help files are installed in the module folder, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span>
- <span data-ttu-id="bd3a0-236">Если `Save-Help` не удается найти обновленные файлы справки для модуля или не удается найти обновленные файлы справки на указанном языке, он продолжится без вывода сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-236">If `Save-Help` cannot find updated help files for a module, or cannot find updated help files in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="bd3a0-237">Чтобы узнать, какие файлы были сохранены с помощью команды, укажите параметр **verbose** .</span><span class="sxs-lookup"><span data-stu-id="bd3a0-237">To see which files were saved by the command, specify the **Verbose** parameter.</span></span>
- <span data-ttu-id="bd3a0-238">Модули — это наименьшая единица обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-238">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="bd3a0-239">Невозможно сохранить справку для конкретного командлета только для всех командлетов в модуле.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-239">You cannot save help for a particular cmdlet, only for all cmdlets in module.</span></span> <span data-ttu-id="bd3a0-240">Чтобы найти модуль, содержащий конкретный командлет, используйте свойство **ModuleName** вместе с `Get-Command` командлетом, например `(Get-Command \<cmdlet-name\>).ModuleName`</span><span class="sxs-lookup"><span data-stu-id="bd3a0-240">To find the module that contains a particular cmdlet, use the **ModuleName** property together with the `Get-Command` cmdlet, for example, `(Get-Command \<cmdlet-name\>).ModuleName`</span></span>
- <span data-ttu-id="bd3a0-241">`Save-Help` поддерживает все модули и оснастки PowerShell Core. Она не поддерживает никакие другие оснастки.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-241">`Save-Help` supports all modules and the PowerShell Core snap-ins. It does not support any other snap-ins.</span></span>
- <span data-ttu-id="bd3a0-242">`Update-Help` `Save-Help` Командлеты и используют следующие порты для скачивания файлов справки: порт 80 для HTTP и порт 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bd3a0-242">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>
- <span data-ttu-id="bd3a0-243">`Update-Help` `Save-Help` Командлеты и не поддерживаются в среда предустановки Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="bd3a0-243">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="bd3a0-244">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bd3a0-244">RELATED LINKS</span></span>

[<span data-ttu-id="bd3a0-245">Get-Help</span><span class="sxs-lookup"><span data-stu-id="bd3a0-245">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="bd3a0-246">Get-Module</span><span class="sxs-lookup"><span data-stu-id="bd3a0-246">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="bd3a0-247">Update-Help</span><span class="sxs-lookup"><span data-stu-id="bd3a0-247">Update-Help</span></span>](Update-Help.md)
