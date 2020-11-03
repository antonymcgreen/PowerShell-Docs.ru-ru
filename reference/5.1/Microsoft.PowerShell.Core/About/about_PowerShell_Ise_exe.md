---
description: Объясняется, как использовать средство командной строки PowerShell_Ise.exe.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232334"
---
# <a name="about-powershell-iseexe"></a><span data-ttu-id="3cab4-104">О Ise.exe PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cab4-104">About PowerShell Ise.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="3cab4-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3cab4-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="3cab4-106">Объясняется, как использовать средство командной строки PowerShell_Ise.exe.</span><span class="sxs-lookup"><span data-stu-id="3cab4-106">Explains how to use the PowerShell_Ise.exe command-line tool.</span></span>

## <a name="long-description"></a><span data-ttu-id="3cab4-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3cab4-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3cab4-108">PowerShell_Ise.exe запускает сеанс интегрированной среды сценариев (ISE) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cab4-108">PowerShell_Ise.exe starts a Windows PowerShell Integrated Scripting Environment (ISE) session.</span></span> <span data-ttu-id="3cab4-109">Его можно запустить в Cmd.exe и в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cab4-109">You can run it in Cmd.exe and in Windows PowerShell.</span></span>

<span data-ttu-id="3cab4-110">Чтобы запустить PowerShell_ISE.exe, введите PowerShell_ISE.exe, PowerShell_ISE или ISE.</span><span class="sxs-lookup"><span data-stu-id="3cab4-110">To run PowerShell_ISE.exe, type PowerShell_ISE.exe, PowerShell_ISE, or ISE.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cab4-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3cab4-111">SYNTAX</span></span>

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a><span data-ttu-id="3cab4-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3cab4-112">PARAMETERS</span></span>

### <a name="-file"></a><span data-ttu-id="3cab4-113">-File</span><span class="sxs-lookup"><span data-stu-id="3cab4-113">-File</span></span>

<span data-ttu-id="3cab4-114">Открывает указанные файлы в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cab4-114">Opens the specified files in Windows PowerShell ISE.</span></span> <span data-ttu-id="3cab4-115">Имя параметра ("-File") является необязательным.</span><span class="sxs-lookup"><span data-stu-id="3cab4-115">The parameter name ("-File") is optional.</span></span> <span data-ttu-id="3cab4-116">Чтобы получить список из нескольких файлов, введите одну текстовую строку, заключенную в кавычки.</span><span class="sxs-lookup"><span data-stu-id="3cab4-116">To list more than one file, enter one text string enclosed in quotation marks.</span></span> <span data-ttu-id="3cab4-117">Используйте запятые для разделения имен файлов в строке.</span><span class="sxs-lookup"><span data-stu-id="3cab4-117">Use commas to separate the file names within the string.</span></span>

<span data-ttu-id="3cab4-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="3cab4-118">For example:</span></span>

<span data-ttu-id="3cab4-119">PowerShell_ISE-файл "File1.ps1, File2.ps1, File3.xml".</span><span class="sxs-lookup"><span data-stu-id="3cab4-119">PowerShell_ISE -File "File1.ps1,File2.ps1,File3.xml".</span></span>

<span data-ttu-id="3cab4-120">В Windows PowerShell разрешены пробелы между именами файлов, но они могут неправильно интерпретироваться другими программами, например Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="3cab4-120">Spaces between the file names are permitted in Windows PowerShell, but might not be interpreted correctly by other programs, such as Cmd.exe.</span></span>

<span data-ttu-id="3cab4-121">Этот параметр можно использовать для открытия любого текстового файла, включая файлы сценариев Windows PowerShell и XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="3cab4-121">You can use this parameter to open any text file, including Windows PowerShell script files and XML files.</span></span>

### <a name="-mta"></a><span data-ttu-id="3cab4-122">-Mta</span><span class="sxs-lookup"><span data-stu-id="3cab4-122">-Mta</span></span>

<span data-ttu-id="3cab4-123">Запускает интегрированную среду сценариев Windows PowerShell с использованием многопоточного подразделения.</span><span class="sxs-lookup"><span data-stu-id="3cab4-123">Starts Windows PowerShell ISE using a multi-threaded apartment.</span></span> <span data-ttu-id="3cab4-124">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="3cab4-124">This parameter is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="3cab4-125">Однопотоковое подразделение (STA) является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cab4-125">Single-threaded apartment (STA) is the default.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="3cab4-126">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="3cab4-126">-NoProfile</span></span>

<span data-ttu-id="3cab4-127">Не запускает профили Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cab4-127">Does not run Windows PowerShell profiles.</span></span> <span data-ttu-id="3cab4-128">По умолчанию профили Windows PowerShell выполняются в каждом сеансе.</span><span class="sxs-lookup"><span data-stu-id="3cab4-128">By default, Windows PowerShell profiles are run in every session.</span></span>

<span data-ttu-id="3cab4-129">Этот параметр рекомендуется использовать при написании общего содержимого, например функций и скриптов, которые будут выполняться в системах с разными профилями.</span><span class="sxs-lookup"><span data-stu-id="3cab4-129">This parameter is recommended when you are writing shared content, such as functions and scripts that will be run on systems with different profiles.</span></span>
<span data-ttu-id="3cab4-130">Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3cab4-130">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="-help---"></a><span data-ttu-id="3cab4-131">-Help-?,/?</span><span class="sxs-lookup"><span data-stu-id="3cab4-131">-Help -?, /?</span></span>

<span data-ttu-id="3cab4-132">Отображает справку для PowerShell_ISE.exe.</span><span class="sxs-lookup"><span data-stu-id="3cab4-132">Displays help for PowerShell_ISE.exe.</span></span>

## <a name="examples"></a><span data-ttu-id="3cab4-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="3cab4-133">EXAMPLES</span></span>

<span data-ttu-id="3cab4-134">Эти команды запускают интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cab4-134">These commands start Windows PowerShell ISE.</span></span> <span data-ttu-id="3cab4-135">Команды эквивалентны и взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="3cab4-135">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

<span data-ttu-id="3cab4-136">Эти команды открывают скрипт Get-Profile.ps1 в ИНТЕГРИРОВАНной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cab4-136">These commands open the Get-Profile.ps1 script in Windows PowerShell ISE.</span></span>
<span data-ttu-id="3cab4-137">Команды эквивалентны и взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="3cab4-137">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

<span data-ttu-id="3cab4-138">Эта команда открывает скрипты Get-Backups.ps1 и Get-BackupInstance.ps1 в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cab4-138">This command opens the Get-Backups.ps1 and Get-BackupInstance.ps1 scripts in Windows PowerShell ISE.</span></span> <span data-ttu-id="3cab4-139">Чтобы открыть более одного файла, используйте запятую для разделения имен файлов и заключите все значение имени файла в кавычки.</span><span class="sxs-lookup"><span data-stu-id="3cab4-139">To open more than one file, use a comma to separate the file names and enclose the entire file name value in quotation marks.</span></span>

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

<span data-ttu-id="3cab4-140">Эта команда запускает интегрированную среду сценариев Windows PowerShell без профилей.</span><span class="sxs-lookup"><span data-stu-id="3cab4-140">This command starts Windows PowerShell ISE with no profiles.</span></span>

```
PS C:> ISE -NoProfile
```

<span data-ttu-id="3cab4-141">Эта команда возвращает справку для PowerShell_ISE.exe.</span><span class="sxs-lookup"><span data-stu-id="3cab4-141">This command gets help for PowerShell_ISE.exe.</span></span>

```
PS C:> ISE -help
```

## <a name="see-also"></a><span data-ttu-id="3cab4-142">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="3cab4-142">SEE ALSO</span></span>

[<span data-ttu-id="3cab4-143">about_PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="3cab4-143">about_PowerShell.exe</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="3cab4-144">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="3cab4-144">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)

[<span data-ttu-id="3cab4-145">Интегрированная среда сценариев (ISE) Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cab4-145">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
