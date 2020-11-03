---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: f98684b4d10a9755428b4798f2f03d944e4bbb84
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229170"
---
# <span data-ttu-id="d6c05-103">Save-Help</span><span class="sxs-lookup"><span data-stu-id="d6c05-103">Save-Help</span></span>

## <span data-ttu-id="d6c05-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d6c05-104">SYNOPSIS</span></span>
<span data-ttu-id="d6c05-105">Скачивает и сохраняет последние файлы справки в каталог файловой системы.</span><span class="sxs-lookup"><span data-stu-id="d6c05-105">Downloads and saves the newest help files to a file system directory.</span></span>

## <span data-ttu-id="d6c05-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6c05-106">SYNTAX</span></span>

### <span data-ttu-id="d6c05-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d6c05-107">Path (Default)</span></span>

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### <span data-ttu-id="d6c05-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d6c05-108">LiteralPath</span></span>

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## <span data-ttu-id="d6c05-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6c05-109">DESCRIPTION</span></span>

<span data-ttu-id="d6c05-110">Командлет **Save-Help** скачивает новейшие файлы справки для модулей PowerShell и сохраняет их в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="d6c05-110">The **Save-Help** cmdlet downloads the newest help files for PowerShell modules and saves them to a directory that you specify.</span></span>
<span data-ttu-id="d6c05-111">Эта функция позволяет обновлять файлы справки на компьютерах без доступа к Интернету и упрощает обновление файлов справки на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d6c05-111">This feature lets you update the help files on computers that do not have access to the Internet, and makes it easier to update the help files on multiple computers.</span></span>

<span data-ttu-id="d6c05-112">В Windows PowerShell 3,0 **Сохранение — Справка** работала только для модулей, установленных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-112">In Windows PowerShell 3.0, **Save-Help** worked only for modules that are installed on the local computer.</span></span>
<span data-ttu-id="d6c05-113">Хотя можно импортировать модуль с удаленного компьютера или получить ссылку на объект **PSModuleInfo** с удаленного компьютера с помощью удаленного взаимодействия PowerShell, свойство **HelpInfoUri** не сохранилось, а **Сохранение-Справка** не будет работать в справке по удаленному модулю.</span><span class="sxs-lookup"><span data-stu-id="d6c05-113">Although it was possible to import a module from a remote computer, or obtain a reference to a **PSModuleInfo** object from a remote computer by using PowerShell remoting, the **HelpInfoUri** property was not preserved, and **Save-Help** would not work for remote module Help.</span></span>

<span data-ttu-id="d6c05-114">В Windows PowerShell 4,0 свойство **HelpInfoUri** сохраняется через удаленное взаимодействие PowerShell, что позволяет **сохранять и помогать** работать с модулями, установленными на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d6c05-114">In Windows PowerShell 4.0, the **HelpInfoUri** property is preserved over PowerShell remoting, which enables **Save-Help** to work for modules that are installed on remote computers.</span></span>
<span data-ttu-id="d6c05-115">Можно также сохранить объект **PSModuleInfo** на диске или съемном носителе, запустив Export-Clixml на компьютере без доступа к Интернету, импортировать объект на компьютере, который имеет доступ к Интернету, а затем выполнить команду **Save-Help** для объекта **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="d6c05-115">It is also possible to save a **PSModuleInfo** object to disk or removable media by running Export-Clixml on a computer that does not have Internet access, import the object on a computer that does have Internet access, and then run **Save-Help** on the **PSModuleInfo** object.</span></span>
<span data-ttu-id="d6c05-116">Сохраненная Справка может быть перенесена на удаленный компьютер с помощью съемных носителей, таких как USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="d6c05-116">The saved help can be transported to the remote computer by using removable storage media, such as a USB drive.</span></span>
<span data-ttu-id="d6c05-117">Справку можно установить на удаленном компьютере, выполнив команду **Update-Help**.</span><span class="sxs-lookup"><span data-stu-id="d6c05-117">The help can be installed on the remote computer by running **Update-Help**.</span></span>
<span data-ttu-id="d6c05-118">Этот процесс можно использовать для установки справки на компьютерах без доступа к какой-либо сети.</span><span class="sxs-lookup"><span data-stu-id="d6c05-118">This process can be used to install help on computers that do not have any kind of network access.</span></span>

<span data-ttu-id="d6c05-119">Чтобы установить сохраненные файлы справки, выполните командлет Update-Help.</span><span class="sxs-lookup"><span data-stu-id="d6c05-119">To install saved help files, run the Update-Help cmdlet.</span></span>
<span data-ttu-id="d6c05-120">Добавьте его параметр *SourcePath* , чтобы указать папку, в которой были сохранены файлы справки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-120">Add its *SourcePath* parameter to specify the folder in which you saved the Help files.</span></span>

<span data-ttu-id="d6c05-121">Без параметров команда **Save-Help** загружает последние файлы справки для всех модулей в сеансе и модулей, установленных на компьютере в папке, заданной в переменной среды **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="d6c05-121">Without parameters, a **Save-Help** command downloads the newest help for all modules in the session and for modules that are installed on the computer in a location listed in the **PSModulePath** environment variable.</span></span>
<span data-ttu-id="d6c05-122">Это действие пропускает модули, которые не поддерживают обновляемую справку без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="d6c05-122">This action skips modules that do not support Updatable Help without warning.</span></span>

<span data-ttu-id="d6c05-123">Командлет **Save-Help** проверяет версию всех файлов справки в папке назначения.</span><span class="sxs-lookup"><span data-stu-id="d6c05-123">The **Save-Help** cmdlet checks the version of any help files in the destination folder.</span></span>
<span data-ttu-id="d6c05-124">Если доступны новые файлы справки, этот командлет скачивает новейшие файлы справки из Интернета, а затем сохраняет их в папке.</span><span class="sxs-lookup"><span data-stu-id="d6c05-124">If newer help files are available, this cmdlet downloads the newest help files from the Internet, and then saves them in the folder.</span></span>
<span data-ttu-id="d6c05-125">Командлет **Save-Help** работает так же, как командлет Update-Help, за исключением того, что он сохраняет загруженные файлы CAB (CAB), а не извлекает файлы справки из CAB-файлов и не устанавливает их на компьютер.</span><span class="sxs-lookup"><span data-stu-id="d6c05-125">The **Save-Help** cmdlet works just like the Update-Help cmdlet, except that it saves the downloaded cabinet (.cab) files, instead of extracting the help files from the cabinet files and installing them on the computer.</span></span>

<span data-ttu-id="d6c05-126">Сохраненные файлы справки для каждого модуля — это один файл сведений о справке (HelpInfo XML) и по одному CAB-файлу для каждого языка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6c05-126">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span>
<span data-ttu-id="d6c05-127">Нет необходимости извлекать файлы справки из CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="d6c05-127">You do not have to extract the help files from the cabinet file.</span></span>
<span data-ttu-id="d6c05-128">Командлет **Update-Help** извлекает файлы справки, проверяет XML для обеспечения безопасности, а затем устанавливает файлы справки и файл справки в подпапку, зависящую от языка, в папке Module.</span><span class="sxs-lookup"><span data-stu-id="d6c05-128">The **Update-Help** cmdlet extracts the help files, validates the XML for safety, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>

<span data-ttu-id="d6c05-129">Чтобы сохранить файлы справки для модулей в папке установки PowerShell ($pshome \Модулес), запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="d6c05-129">To save the help files for modules in the PowerShell installation folder ($pshome\Modules), start PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="d6c05-130">Для загрузки файлов справки для этих модулей необходимо быть членом группы администраторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-130">You must be a member of the Administrators group on the computer to download the help files for these modules.</span></span>

<span data-ttu-id="d6c05-131">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d6c05-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d6c05-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="d6c05-132">EXAMPLES</span></span>

### <span data-ttu-id="d6c05-133">Пример 1. Сохранение справки для модуля DhcpServer</span><span class="sxs-lookup"><span data-stu-id="d6c05-133">Example 1: Save the help for the DhcpServer module</span></span>

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module, save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

<span data-ttu-id="d6c05-134">В этом примере показаны три разных способа использования функции **Save-Help** для сохранения справки для модуля **DhcpServer** с клиентского компьютера, подключенного к Интернету, без установки модуля **DhcpServer** или роли DHCP-сервера на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-134">This example shows three different ways to use **Save-Help** to save the help for the **DhcpServer** module from an Internet-connected client computer, without installing the **DhcpServer** module or the DHCP Server role on the local computer.</span></span>

### <span data-ttu-id="d6c05-135">Пример 2. Установка справки для модуля DhcpServer</span><span class="sxs-lookup"><span data-stu-id="d6c05-135">Example 2: Install help for the DhcpServer module</span></span>

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

<span data-ttu-id="d6c05-136">В этом примере показано, как установить справку, сохраненную в примере 1 для модуля **DhcpServer** на компьютере без доступа к Интернету.</span><span class="sxs-lookup"><span data-stu-id="d6c05-136">This example shows how to install help that you saved in Example 1 for the **DhcpServer** module on a computer that does not have Internet access.</span></span>

### <span data-ttu-id="d6c05-137">Пример 3. Сохранение справки для всех модулей</span><span class="sxs-lookup"><span data-stu-id="d6c05-137">Example 3: Save help for all modules</span></span>

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

<span data-ttu-id="d6c05-138">Эта команда загружает последние файлы справки для всех модулей для языка Windows на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-138">This command downloads the newest help files for all modules in the UI culture set for Windows on the local computer.</span></span>
<span data-ttu-id="d6c05-139">Файлы справки сохраняются в \\ \\ папке Server01\Fileshare01</span><span class="sxs-lookup"><span data-stu-id="d6c05-139">It saves the help files in the \\\\Server01\Fileshare01 folder.</span></span>

### <span data-ttu-id="d6c05-140">Пример 4. Сохранение справки для модуля на компьютере</span><span class="sxs-lookup"><span data-stu-id="d6c05-140">Example 4: Save help for a module on the computer</span></span>

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

<span data-ttu-id="d6c05-141">Эта команда скачивает новейшие файлы справки для модуля **ServerManager** , а затем сохраняет их в \\ \\ папке Server01\Fileshare01</span><span class="sxs-lookup"><span data-stu-id="d6c05-141">This command downloads the newest help files for the **ServerManager** module, and then saves them in the \\\\Server01\Fileshare01 folder.</span></span>

<span data-ttu-id="d6c05-142">Если модуль установлен на компьютере, можно ввести имя модуля в параметре *Module* , даже если модуль не импортируется в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="d6c05-142">When a module is installed on the computer, you can type the module name as the value of the *Module* parameter, even if the module is not imported into the current session.</span></span>

<span data-ttu-id="d6c05-143">Команда использует параметр *Credential* , чтобы передать учетные данные пользователя с разрешением на запись в общую папку.</span><span class="sxs-lookup"><span data-stu-id="d6c05-143">The command uses the *Credential* parameter to supply the credentials of a user who has permission to write to the file share.</span></span>

### <span data-ttu-id="d6c05-144">Пример 5. Сохранение справки для модуля на другом компьютере</span><span class="sxs-lookup"><span data-stu-id="d6c05-144">Example 5: Save help for a module on a different computer</span></span>

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

<span data-ttu-id="d6c05-145">Эти команды загружают самые новые файлы справки для модуля **кустомскл** и сохраняют их в \\ \\ папке Server01\Fileshare01.</span><span class="sxs-lookup"><span data-stu-id="d6c05-145">These commands download the newest help files for the **CustomSQL** module and save them in the \\\\Server01\Fileshare01 folder.</span></span>

<span data-ttu-id="d6c05-146">Так как модуль **кустомскл** не установлен на компьютере, последовательность включает команду Invoke-Command, которая получает объект модуля для модуля кустомскл с компьютера Server02, а затем передает объект Module в командлет **Save-Help** .</span><span class="sxs-lookup"><span data-stu-id="d6c05-146">Because the **CustomSQL** module is not installed on the computer, the sequence includes an Invoke-Command command that gets the module object for the CustomSQL module from the Server02 computer and then pipes the module object to the **Save-Help** cmdlet.</span></span>

<span data-ttu-id="d6c05-147">Если модуль не установлен на компьютере, **Save-Help** требуется объект модуля, который содержит сведения о расположении новых файлов справки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-147">When a module is not installed on the computer, **Save-Help** needs the module object, which includes information about the location of the newest help files.</span></span>

### <span data-ttu-id="d6c05-148">Пример 6. Сохранение справки для модуля на нескольких языках</span><span class="sxs-lookup"><span data-stu-id="d6c05-148">Example 6: Save help for a module in multiple languages</span></span>

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

<span data-ttu-id="d6c05-149">Эта команда сохраняет справку для модулей PowerShell Core в четырех различных культурах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6c05-149">This command saves help for the PowerShell Core modules in four different UI cultures.</span></span>
<span data-ttu-id="d6c05-150">Языковые пакеты для этих языков не должны устанавливаться на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-150">The language packs for these locales do not have to be installed on the computer.</span></span>

<span data-ttu-id="d6c05-151">**Save — Help** позволяет скачивать файлы справки для модулей в разных культурах пользовательского интерфейса только в том случае, если владелец модуля делает переведенные файлы доступными в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d6c05-151">**Save-Help** can download help files for modules in different UI cultures only when the module owner makes the translated files available on the Internet.</span></span>

### <span data-ttu-id="d6c05-152">Пример 7. Сохранение справки более одного раза в день</span><span class="sxs-lookup"><span data-stu-id="d6c05-152">Example 7: Save help more than one time each day</span></span>

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

<span data-ttu-id="d6c05-153">Эта команда сохраняет справку для всех модулей, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-153">This command saves help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="d6c05-154">Команда задает параметр *Force* для переопределения правила, которое не позволяет командлету **Save-Help** загрузить справку более одного раза в течение каждого 24-часового периода.</span><span class="sxs-lookup"><span data-stu-id="d6c05-154">The command specifies the *Force* parameter to override the rule that prevents the **Save-Help** cmdlet from downloading help more than once in each 24-hour period.</span></span>

<span data-ttu-id="d6c05-155">Параметр *Force* также переопределяет ограничение 1 ГБ и обходит проверку версии.</span><span class="sxs-lookup"><span data-stu-id="d6c05-155">The *Force* parameter also overrides the 1 GB restriction and circumvents version checking.</span></span>
<span data-ttu-id="d6c05-156">Таким образом, можно загружать файлы, даже если версия не превышает версию в папке назначения.</span><span class="sxs-lookup"><span data-stu-id="d6c05-156">Therefore, you can download files even if the version is not later than the version in the destination folder.</span></span>

<span data-ttu-id="d6c05-157">Команда сохраняет и сохраняет файлы справки в указанной папке с помощью командлета **Save-Help** .</span><span class="sxs-lookup"><span data-stu-id="d6c05-157">The command uses the **Save-Help** cmdlet to download and save the help files to the specified folder.</span></span>
<span data-ttu-id="d6c05-158">Параметр *Force* является обязательным, если требуется однократное выполнение команды **Save-Help** в день.</span><span class="sxs-lookup"><span data-stu-id="d6c05-158">The *Force* parameter is required when you have to run a **Save-Help** command more than one time each day.</span></span>

## <span data-ttu-id="d6c05-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6c05-159">PARAMETERS</span></span>

### <span data-ttu-id="d6c05-160">-Credential</span><span class="sxs-lookup"><span data-stu-id="d6c05-160">-Credential</span></span>

<span data-ttu-id="d6c05-161">Указывает учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="d6c05-161">Specifies a user credential.</span></span> <span data-ttu-id="d6c05-162">Этот командлет выполняет команду, используя учетные данные пользователя, имеющего разрешение на доступ к расположению файловой системы, заданному параметром **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="d6c05-162">This cmdlet runs the command by using credentials of a user who has permission to access the file system location specified by the **DestinationPath** parameter.</span></span> <span data-ttu-id="d6c05-163">Этот параметр доступен, только если в команде используется параметр **DestinationPath** или **LiteralPath**.</span><span class="sxs-lookup"><span data-stu-id="d6c05-163">This parameter is valid only when the **DestinationPath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="d6c05-164">Этот параметр позволяет выполнять `Save-Help` команды, использующие параметр **DestinationPath** на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d6c05-164">This parameter enables you to run `Save-Help` commands that use the **DestinationPath** parameter on remote computers.</span></span> <span data-ttu-id="d6c05-165">Предоставляя явные учетные данные, можно выполнить команду на удаленном компьютере и получить доступ к общей папке на третьем компьютере без возникновения ошибки отказа в доступе или использования проверки подлинности CredSSP для делегирования учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d6c05-165">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="d6c05-166">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="d6c05-166">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d6c05-167">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="d6c05-167">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d6c05-168">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="d6c05-168">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d6c05-169">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="d6c05-169">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="d6c05-170">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="d6c05-170">-DestinationPath</span></span>

<span data-ttu-id="d6c05-171">Указывает путь к папке, в которой сохраняются файлы справки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-171">Specifies the path of the folder in which the help files are saved.</span></span>
<span data-ttu-id="d6c05-172">Не указывайте имя или расширение файла.</span><span class="sxs-lookup"><span data-stu-id="d6c05-172">Do not specify a file name or file name extension.</span></span>

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

### <span data-ttu-id="d6c05-173">-Force</span><span class="sxs-lookup"><span data-stu-id="d6c05-173">-Force</span></span>

<span data-ttu-id="d6c05-174">Указывает, что этот командлет не соответствует ограничению "один за день", пропускает проверку версий и скачивает файлы, превышающие ограничение в 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="d6c05-174">Indicates that this cmdlet does not follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="d6c05-175">Без этого параметра в течение 24 часов команду **Save-Help** можно выполнить только один раз для каждого модуля, размер загружаемых файлов не превышает 1 ГБ (несжатого содержимого) для каждого модуля, а файлы справки для модуля устанавливаются, только если новее, чем файлы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-175">Without this parameter, only one **Save-Help** command for each module is permitted in each 24-hour period, downloads are limited to 1 GB of uncompressed content per module, and help files for a module are installed only when they are newer than the files on the computer.</span></span>

<span data-ttu-id="d6c05-176">Ограничение "один за день" защищает серверы, на которых размещаются файлы справки, и упрощает добавление команды " **сохранить-Справка** " в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6c05-176">The once-per-day limit protects the servers that host the help files, and makes it practical for you to add a **Save-Help** command to your PowerShell profile.</span></span>

<span data-ttu-id="d6c05-177">Чтобы сохранить справку для модуля в нескольких культурах пользовательского интерфейса без параметра *Force* , включите все языки и региональные параметры пользовательского интерфейса в той же команде, например: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span><span class="sxs-lookup"><span data-stu-id="d6c05-177">To save help for a module in multiple UI cultures without the *Force* parameter, include all UI cultures in the same command, such as: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span></span>

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

### <span data-ttu-id="d6c05-178">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="d6c05-178">-FullyQualifiedModule</span></span>

<span data-ttu-id="d6c05-179">Указывает модули с именами, указанными в форме объектов ModuleSpecification.</span><span class="sxs-lookup"><span data-stu-id="d6c05-179">Specifies modules with names that are specified in the form of ModuleSpecification objects.</span></span>
<span data-ttu-id="d6c05-180">Это описано в разделе "Примечания" [конструктора ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="d6c05-180">This is described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library.</span></span>
<span data-ttu-id="d6c05-181">Например, параметр *FullyQualifiedModule* принимает имя модуля, указанное в формате @ {ModuleName = "ModuleName"; ", ИД =" version_number "} или @ {ModuleName =" ModuleName "; "ИД" = "version_number"; GUID = "GUID"}.</span><span class="sxs-lookup"><span data-stu-id="d6c05-181">For example, the *FullyQualifiedModule* parameter accepts a module name that is specified in the format @{ModuleName = "modulename"; ModuleVersion = "version_number"} or @{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.</span></span>
<span data-ttu-id="d6c05-182">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="d6c05-182">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="d6c05-183">Нельзя указать параметр *FullyQualifiedModule* в той же команде, что и параметр *module* .</span><span class="sxs-lookup"><span data-stu-id="d6c05-183">You cannot specify the *FullyQualifiedModule* parameter in the same command as a *Module* parameter.</span></span>

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

### <span data-ttu-id="d6c05-184">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d6c05-184">-LiteralPath</span></span>

<span data-ttu-id="d6c05-185">Указывает путь к папке назначения.</span><span class="sxs-lookup"><span data-stu-id="d6c05-185">Specifies a path of the destination folder.</span></span>
<span data-ttu-id="d6c05-186">В отличие от значения параметра *DestinationPath* значение параметра *LiteralPath* используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="d6c05-186">Unlike the value of the *DestinationPath* parameter, the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="d6c05-187">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-187">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="d6c05-188">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-188">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="d6c05-189">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="d6c05-189">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="d6c05-190">-Module</span><span class="sxs-lookup"><span data-stu-id="d6c05-190">-Module</span></span>

<span data-ttu-id="d6c05-191">Указывает модули, для которых этот командлет скачивает справку.</span><span class="sxs-lookup"><span data-stu-id="d6c05-191">Specifies modules for which this cmdlet downloads help.</span></span>
<span data-ttu-id="d6c05-192">Введите одно или несколько имен модулей или имя шаблонов в списке с разделителями-запятыми или в файле с одним именем модуля в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="d6c05-192">Enter one or more module names or name patters in a comma-separated list or in a file that has one module name on each line.</span></span>
<span data-ttu-id="d6c05-193">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-193">Wildcard characters are permitted.</span></span>
<span data-ttu-id="d6c05-194">Вы также можете передать объекты модуля из командлета Get-Module в службу **Save-Help**.</span><span class="sxs-lookup"><span data-stu-id="d6c05-194">You can also pipe module objects from the Get-Module cmdlet to **Save-Help**.</span></span>

<span data-ttu-id="d6c05-195">По умолчанию **Save-Help** загружает файлы справки для всех модулей, которые поддерживают обновляемую справку и установлены на локальном компьютере в расположении, заданном в переменной среды **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="d6c05-195">By default, **Save-Help** downloads help for all modules that support Updatable Help and are installed on the local computer in a location listed in the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="d6c05-196">Чтобы сохранить справку для модулей, которые не установлены на компьютере, выполните команду **Get-Module** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-196">To save help for modules that are not installed on the computer, run a **Get-Module** command on a remote computer.</span></span>
<span data-ttu-id="d6c05-197">Затем передайте полученные объекты модуля командлету **Save-Help** или отправьте их как значение параметра *Module* или *InputObject*.</span><span class="sxs-lookup"><span data-stu-id="d6c05-197">Then pipe the resulting module objects to the **Save-Help** cmdlet or submit the module objects as the value of the *Module* or *InputObject* parameters.</span></span>

<span data-ttu-id="d6c05-198">Если указанный модуль установлен на компьютере, можно ввести имя модуля или объект модуля.</span><span class="sxs-lookup"><span data-stu-id="d6c05-198">If the module that you specify is installed on the computer, you can enter the module name or a module object.</span></span>
<span data-ttu-id="d6c05-199">Если модуль не установлен на компьютере, необходимо ввести объект модуля, например тот, что возвращается командлетом **Get-Module**.</span><span class="sxs-lookup"><span data-stu-id="d6c05-199">If the module is not installed on the computer, you must enter a module object, such as one returned by the **Get-Module** cmdlet.</span></span>

<span data-ttu-id="d6c05-200">Параметр *module* командлета **Save-Help** не принимает полный путь к файлу модуля или файлу манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="d6c05-200">The *Module* parameter of the **Save-Help** cmdlet does not accept the full path of a module file or module manifest file.</span></span>
<span data-ttu-id="d6c05-201">Чтобы сохранить справку для модуля, который не находится в **PSModulePath** расположении, импортируйте модуль в текущий сеанс перед запуском команды **Save-Help** .</span><span class="sxs-lookup"><span data-stu-id="d6c05-201">To save help for a module that is not in a **PSModulePath** location, import the module into the current session before you run the **Save-Help** command.</span></span>

<span data-ttu-id="d6c05-202">Значение "\*" (все) пытается обновить справку для всех модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-202">A value of "\*" (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="d6c05-203">Сюда входят модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="d6c05-203">This includes modules that do not support Updatable Help.</span></span>
<span data-ttu-id="d6c05-204">Это значение может выдавать ошибки, если команда обнаруживает модули, которые не поддерживают обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="d6c05-204">This value might generate errors when the command encounters modules that do not support Updatable Help.</span></span>

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

### <span data-ttu-id="d6c05-205">-UICulture</span><span class="sxs-lookup"><span data-stu-id="d6c05-205">-UICulture</span></span>

<span data-ttu-id="d6c05-206">Задает значения языка и региональных параметров пользовательского интерфейса, для которых этот командлет получает обновленные файлы справки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-206">Specifies UI culture values for which this cmdlet gets updated help files.</span></span>
<span data-ttu-id="d6c05-207">Введите один или несколько кодов языка, например es-ES, переменную, содержащую объекты языка и региональных параметров, или команду, которая получает объекты языка и региональных параметров, например Get-Culture или Get-UICulture.</span><span class="sxs-lookup"><span data-stu-id="d6c05-207">Enter one or more language codes, such as es-ES, a variable that contains culture objects, or a command that gets culture objects, such as a Get-Culture or Get-UICulture command.</span></span>

<span data-ttu-id="d6c05-208">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="d6c05-208">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="d6c05-209">Не указывайте код частичного языка, например "de".</span><span class="sxs-lookup"><span data-stu-id="d6c05-209">Do not specify a partial language code, such as "de".</span></span>

<span data-ttu-id="d6c05-210">По умолчанию **Save-Help** получает файлы справки на языке Windows или резервном языке.</span><span class="sxs-lookup"><span data-stu-id="d6c05-210">By default, **Save-Help** gets help files in the UI culture set for Windows or its fallback culture.</span></span>
<span data-ttu-id="d6c05-211">Если указан параметр *UICulture* , командлет **Save-Help** ищет справку только для указанной культуры пользовательского интерфейса, а не для резервной культуры.</span><span class="sxs-lookup"><span data-stu-id="d6c05-211">If you specify the *UICulture* parameter, **Save-Help** looks for help only for the specified UI culture, not in any fallback culture.</span></span>

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

### <span data-ttu-id="d6c05-212">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="d6c05-212">-UseDefaultCredentials</span></span>

<span data-ttu-id="d6c05-213">Указывает, что этот командлет выполняет команду, включая загрузку в Интернете, с учетными данными текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d6c05-213">Indicates that this cmdlet runs the command, including the web download, with the credentials of the current user.</span></span>
<span data-ttu-id="d6c05-214">По умолчанию команда выполняется без явных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d6c05-214">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="d6c05-215">Этот параметр действует, только если веб-загрузка использует проверку подлинности NTLM, проверку подлинности с согласованием или проверку подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d6c05-215">This parameter is effective only when the web download uses NTLM, negotiate, or Kerberos-based authentication.</span></span>

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

### <span data-ttu-id="d6c05-216">-Scope</span><span class="sxs-lookup"><span data-stu-id="d6c05-216">-Scope</span></span>

<span data-ttu-id="d6c05-217">Этот не делает ничего в этом командлете.</span><span class="sxs-lookup"><span data-stu-id="d6c05-217">This paramater does nothing in this cmdlet.</span></span>

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

### <span data-ttu-id="d6c05-218">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d6c05-218">CommonParameters</span></span>

<span data-ttu-id="d6c05-219">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6c05-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6c05-220">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6c05-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6c05-221">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d6c05-221">INPUTS</span></span>

### <span data-ttu-id="d6c05-222">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="d6c05-222">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="d6c05-223">Объект модуля можно передать из командлета **Get-Module** в параметр *module* функции **Save-Help**.</span><span class="sxs-lookup"><span data-stu-id="d6c05-223">You can pipe a module object from the **Get-Module** cmdlet to the *Module* parameter of **Save-Help**.</span></span>

## <span data-ttu-id="d6c05-224">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d6c05-224">OUTPUTS</span></span>

### <span data-ttu-id="d6c05-225">Нет</span><span class="sxs-lookup"><span data-stu-id="d6c05-225">None</span></span>

<span data-ttu-id="d6c05-226">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d6c05-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d6c05-227">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d6c05-227">NOTES</span></span>

* <span data-ttu-id="d6c05-228">Чтобы сохранить справку по модулям в папке $pshome \Модулес, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="d6c05-228">To save help for modules in the $pshome\Modules folder, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="d6c05-229">Только члены группы "Администраторы" на компьютере могут загружать справку по модулям в папке $pshome \Модулес.</span><span class="sxs-lookup"><span data-stu-id="d6c05-229">Only members of the Administrators group on the computer can download help for modules in the $pshome\Modules folder.</span></span>
* <span data-ttu-id="d6c05-230">Сохраненные файлы справки для каждого модуля — это один файл сведений о справке (HelpInfo XML) и по одному CAB-файлу для каждого языка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6c05-230">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="d6c05-231">Нет необходимости извлекать файлы справки из CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="d6c05-231">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="d6c05-232">Командлет Update-Help извлекает файлы справки, проверяет XML, а затем устанавливает файлы справки и файл справки в подпапку, зависящую от языка, в папке Module.</span><span class="sxs-lookup"><span data-stu-id="d6c05-232">The Update-Help cmdlet extracts the help files, validates the XML, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>
* <span data-ttu-id="d6c05-233">Командлет **Save-Help** может сохранить справку для модулей, которые не установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-233">The **Save-Help** cmdlet can save help for modules that are not installed on the computer.</span></span> <span data-ttu-id="d6c05-234">Однако, поскольку файлы справки устанавливаются в папку Module, командлет **Update-Help** может установить обновленный файл справки только для модулей, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6c05-234">However, because help files are installed in the module folder, the **Update-Help** cmdlet can install updated help file only for modules that are installed on the computer.</span></span>
* <span data-ttu-id="d6c05-235">Если командлету **Save-Help** не удается найти файлы обновленной справки для модуля или для указанного языка, его выполнение продолжается без отображения сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d6c05-235">If **Save-Help** cannot find updated help files for a module, or cannot find updated help files in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="d6c05-236">Чтобы узнать, какие файлы были сохранены с помощью команды, укажите параметр *verbose* .</span><span class="sxs-lookup"><span data-stu-id="d6c05-236">To see which files were saved by the command, specify the *Verbose* parameter.</span></span>
* <span data-ttu-id="d6c05-237">Модули — это наименьшая единица обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-237">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="d6c05-238">Невозможно сохранить справку для конкретного командлета только для всех командлетов в модуле.</span><span class="sxs-lookup"><span data-stu-id="d6c05-238">You cannot save help for a particular cmdlet, only for all cmdlets in module.</span></span> <span data-ttu-id="d6c05-239">Чтобы найти модуль, содержащий конкретный командлет, используйте свойство **ModuleName** вместе с командлетом Get-Command, например `(Get-Command \<cmdlet-name\>).ModuleName`</span><span class="sxs-lookup"><span data-stu-id="d6c05-239">To find the module that contains a particular cmdlet, use the **ModuleName** property together with the Get-Command cmdlet, for example, `(Get-Command \<cmdlet-name\>).ModuleName`</span></span>
* <span data-ttu-id="d6c05-240">**Save — Help** поддерживает все модули и оснастки PowerShell Core. Она не поддерживает никакие другие оснастки.</span><span class="sxs-lookup"><span data-stu-id="d6c05-240">**Save-Help** supports all modules and the PowerShell Core snap-ins. It does not support any other snap-ins.</span></span>
* <span data-ttu-id="d6c05-241">Командлеты **Update-Help** и **Save-Help** используют следующие порты для скачивания файлов справки: порт 80 для HTTP и порт 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d6c05-241">The **Update-Help** and **Save-Help** cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>
* <span data-ttu-id="d6c05-242">Командлеты **Update-Help** и **Save-Help** не поддерживаются в среде предустановки Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="d6c05-242">The **Update-Help** and **Save-Help** cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="d6c05-243">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d6c05-243">RELATED LINKS</span></span>

[<span data-ttu-id="d6c05-244">Get-Help</span><span class="sxs-lookup"><span data-stu-id="d6c05-244">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="d6c05-245">Get-Module</span><span class="sxs-lookup"><span data-stu-id="d6c05-245">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="d6c05-246">Update-Help</span><span class="sxs-lookup"><span data-stu-id="d6c05-246">Update-Help</span></span>](Update-Help.md)

