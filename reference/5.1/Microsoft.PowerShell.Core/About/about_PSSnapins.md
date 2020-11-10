---
description: Описывает оснастки Windows PowerShell и показывает, как использовать их и управлять ими.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: 494b3275e4fe8a3aacdc358317950542962957cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388898"
---
# <a name="about-pssnapins"></a><span data-ttu-id="b1824-104">О PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b1824-104">About PSSnapins</span></span>

## <a name="short-description"></a><span data-ttu-id="b1824-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b1824-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b1824-106">Описывает оснастки Windows PowerShell и показывает, как использовать их и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="b1824-106">Describes  Windows PowerShell snap-ins and shows how to use and manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="b1824-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b1824-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b1824-108">Оснастка Windows PowerShell — это сборка Microsoft .NET Framework, которая содержит поставщики и \/ командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-108">A Windows PowerShell snap-in is a Microsoft .NET Framework assembly that contains Windows PowerShell providers and\/or cmdlets.</span></span> <span data-ttu-id="b1824-109">Windows PowerShell включает набор основных оснасток, но вы можете расширить возможности и преимущества Windows PowerShell, добавив оснастки, которые содержат поставщики и командлеты, созданные или получаемые из других.</span><span class="sxs-lookup"><span data-stu-id="b1824-109">Windows PowerShell includes a set of basic snap-ins, but you can extend the power and value of Windows PowerShell by adding snap-ins that contain providers and cmdlets that you create or get from others.</span></span>

<span data-ttu-id="b1824-110">При добавлении оснастки командлеты и поставщики, которые она содержит, немедленно становятся доступными для использования в текущем сеансе, но это изменение затрагивает только текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b1824-110">When you add a snap-in, the cmdlets and providers that it contains are immediately available for use in the current session, but the change affects only the current session.</span></span>

<span data-ttu-id="b1824-111">Чтобы добавить оснастку во все будущие сеансы, сохраните ее в профиле Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-111">To add the snap-in to all future sessions, save it in your Windows PowerShell profile.</span></span> <span data-ttu-id="b1824-112">Можно также использовать командлет Export-Console, чтобы сохранить имена оснасток в файле консоли, а затем использовать их в будущих сеансах.</span><span class="sxs-lookup"><span data-stu-id="b1824-112">You can also use the Export-Console cmdlet to save the snap-in names to a console file and then use it in future sessions.</span></span> <span data-ttu-id="b1824-113">Можно даже сохранить несколько консольных файлов, каждый из которых имеет другой набор оснасток.</span><span class="sxs-lookup"><span data-stu-id="b1824-113">You can even save multiple console files, each with a different set of snap-ins.</span></span>

<span data-ttu-id="b1824-114">Примечание. оснастки Windows PowerShell (PSSnapin) доступны для использования в Windows PowerShell 3,0 и Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="b1824-114">NOTE: Windows PowerShell snap-ins (PSSnapins) are available for use in Windows PowerShell 3.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="b1824-115">Они могут быть изменены или недоступны в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="b1824-115">They might be altered or unavailable in subsequent versions.</span></span> <span data-ttu-id="b1824-116">Для упаковки командлетов и поставщиков Windows PowerShell используйте модули.</span><span class="sxs-lookup"><span data-stu-id="b1824-116">To package Windows PowerShell cmdlets and providers, use modules.</span></span> <span data-ttu-id="b1824-117">Сведения о создании модулей и преобразовании оснасток в модули см. в разделе [написание модуля Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="b1824-117">For information about creating modules and converting snap-ins to modules, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

### <a name="finding-snap-ins"></a><span data-ttu-id="b1824-118">ПОИСК ОСНАСТОК</span><span class="sxs-lookup"><span data-stu-id="b1824-118">FINDING SNAP-INS</span></span>

<span data-ttu-id="b1824-119">Чтобы получить список оснасток Windows PowerShell на компьютере, введите:</span><span class="sxs-lookup"><span data-stu-id="b1824-119">To get a list of the  Windows PowerShell snap-ins on your computer, type:</span></span>

```powershell
Get-PSSnapin
```

<span data-ttu-id="b1824-120">Чтобы получить оснастку для каждого поставщика Windows PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="b1824-120">To get the snap-in for each  Windows PowerShell provider, type:</span></span>

```powershell
Get-PSProvider | Format-List name, pssnapin
```

<span data-ttu-id="b1824-121">Чтобы получить список командлетов в оснастке Windows PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="b1824-121">To get a list of the cmdlets in a  Windows PowerShell snap-in, type:</span></span>

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a><span data-ttu-id="b1824-122">УСТАНОВКА ОСНАСТКИ</span><span class="sxs-lookup"><span data-stu-id="b1824-122">INSTALLING A SNAP-IN</span></span>

<span data-ttu-id="b1824-123">Встроенные оснастки регистрируются в системе и добавляются в сеанс по умолчанию при запуске Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-123">The built-in snap-ins are registered in the system and added to the default session when you start Windows PowerShell.</span></span> <span data-ttu-id="b1824-124">Однако необходимо зарегистрировать оснастки, созданные или получаемые от других, а затем добавить оснастки в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b1824-124">However, you have to register snap-ins that you create or obtain from others and then add the snap-ins to your session.</span></span>

### <a name="registering-a-snap-in"></a><span data-ttu-id="b1824-125">РЕГИСТРАЦИЯ ОСНАСТКИ</span><span class="sxs-lookup"><span data-stu-id="b1824-125">REGISTERING A SNAP-IN</span></span>

<span data-ttu-id="b1824-126">Оснастка Windows PowerShell — это программа, написанная на языке .NET Framework, который компилируется в DLL-файл.</span><span class="sxs-lookup"><span data-stu-id="b1824-126">A Windows PowerShell snap-in is a program written in a .NET Framework language that is compiled into a .dll file.</span></span> <span data-ttu-id="b1824-127">Чтобы использовать поставщики и командлеты в оснастке, необходимо сначала зарегистрировать оснастку (добавить ее в реестр).</span><span class="sxs-lookup"><span data-stu-id="b1824-127">To use the providers and cmdlets in a snap-in, you must first register the snap-in (add it to the registry).</span></span>

<span data-ttu-id="b1824-128">В большинство оснасток входит программа установки (exe-или MSI-файл), которая регистрирует файл. dll.</span><span class="sxs-lookup"><span data-stu-id="b1824-128">Most snap-ins include an installation program (an .exe or .msi file) that registers the .dll file for you.</span></span> <span data-ttu-id="b1824-129">Однако если вы получаете оснастку в виде DLL-файла, вы можете зарегистрировать ее в системе.</span><span class="sxs-lookup"><span data-stu-id="b1824-129">However, if you receive a snap-in as a .dll file, you can register it on your system.</span></span> <span data-ttu-id="b1824-130">Дополнительные сведения см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="b1824-130">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

<span data-ttu-id="b1824-131">Чтобы получить все зарегистрированные оснастки в системе или убедиться, что оснастка зарегистрирована, введите:</span><span class="sxs-lookup"><span data-stu-id="b1824-131">To get all the registered snap-ins on your system or to verify that a snap-in is registered, type:</span></span>

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a><span data-ttu-id="b1824-132">ДОБАВЛЕНИЕ ОСНАСТКИ В ТЕКУЩИЙ СЕАНС</span><span class="sxs-lookup"><span data-stu-id="b1824-132">ADDING THE SNAP-IN TO THE CURRENT SESSION</span></span>

<span data-ttu-id="b1824-133">Чтобы добавить зарегистрированную оснастку в текущий сеанс, используйте командлет Add-PsSnapin.</span><span class="sxs-lookup"><span data-stu-id="b1824-133">To add a registered snap-in to the current session, use the Add-PsSnapin cmdlet.</span></span> <span data-ttu-id="b1824-134">Например, чтобы добавить в сеанс оснастку Microsoft SQL Server, введите:</span><span class="sxs-lookup"><span data-stu-id="b1824-134">For example, to add the Microsoft SQL Server snap-in to the session, type:</span></span>

```powershell
Add-PSSnapin sql
```

<span data-ttu-id="b1824-135">После завершения команды поставщики и командлеты в оснастке будут доступны в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b1824-135">After the command is completed, the providers and cmdlets in the snap-in are available in the session.</span></span> <span data-ttu-id="b1824-136">Однако они доступны только в текущем сеансе, если они не сохранены.</span><span class="sxs-lookup"><span data-stu-id="b1824-136">However, they are available only in the current session unless you save them.</span></span>

### <a name="saving-the-snap-ins"></a><span data-ttu-id="b1824-137">СОХРАНЕНИЕ ОСНАСТОК</span><span class="sxs-lookup"><span data-stu-id="b1824-137">SAVING THE SNAP-INS</span></span>

<span data-ttu-id="b1824-138">Чтобы использовать оснастку в будущих сеансах Windows PowerShell, добавьте команду Add-PsSnapin в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-138">To use a snap-in in future Windows PowerShell sessions, add the Add-PsSnapin command to your Windows PowerShell profile.</span></span> <span data-ttu-id="b1824-139">Также можно экспортировать имена оснасток в файл консоли.</span><span class="sxs-lookup"><span data-stu-id="b1824-139">Or, export the snap-in names to a console file.</span></span>

<span data-ttu-id="b1824-140">Если добавить в профиль команду Add-PSSnapin, она будет доступна во всех будущих сеансах Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-140">If you add the Add-PSSnapin command to your profile, it is available in all future Windows PowerShell sessions.</span></span> <span data-ttu-id="b1824-141">Если вы экспортируете имена оснасток в сеансе, файл экспорта можно использовать только тогда, когда требуются оснастки.</span><span class="sxs-lookup"><span data-stu-id="b1824-141">If you export the names of the snap-ins in your session, you can use the export file only when you need the snap-ins.</span></span>

<span data-ttu-id="b1824-142">Чтобы добавить команду Add-PsSnapin в профиль Windows PowerShell, откройте профиль, вставьте или введите команду, а затем сохраните профиль.</span><span class="sxs-lookup"><span data-stu-id="b1824-142">To add the Add-PsSnapin command to your Windows PowerShell profile, open your profile, paste or type the command, and then save the profile.</span></span> <span data-ttu-id="b1824-143">Дополнительные сведения см. в разделе about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="b1824-143">For more information, see about_Profiles.</span></span>

<span data-ttu-id="b1824-144">Чтобы сохранить оснастки из сеанса в файле консоли (. psc1), используйте командлет Export-Console.</span><span class="sxs-lookup"><span data-stu-id="b1824-144">To save the snap-ins from a session in console file (.psc1), use the Export-Console cmdlet.</span></span> <span data-ttu-id="b1824-145">Например, чтобы сохранить оснастки в текущей конфигурации сеанса в файле Невконсоле. psc1 в текущем каталоге, введите:</span><span class="sxs-lookup"><span data-stu-id="b1824-145">For example, to save the snap-ins in the current session configuration to the NewConsole.psc1 file in the current directory, type:</span></span>

```powershell
Export-Console NewConsole
```

<span data-ttu-id="b1824-146">Дополнительные сведения см. в разделе Export-Console.</span><span class="sxs-lookup"><span data-stu-id="b1824-146">For more information, see Export-Console.</span></span>

### <a name="opening-windows-powershell-with-a-console-file"></a><span data-ttu-id="b1824-147">ОТКРЫТИЕ WINDOWS POWERSHELL С ПОМОЩЬЮ ФАЙЛА КОНСОЛИ</span><span class="sxs-lookup"><span data-stu-id="b1824-147">OPENING WINDOWS POWERSHELL WITH A CONSOLE FILE</span></span>

<span data-ttu-id="b1824-148">Чтобы использовать файл консоли, включающий оснастку, запустите Windows PowerShell (PowerShell.exe) из командной строки в Cmd.exe или в другом сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-148">To use a console file that includes the snap-in, start Windows PowerShell (PowerShell.exe) from the command prompt in Cmd.exe or in another Windows PowerShell session.</span></span> <span data-ttu-id="b1824-149">Используйте параметр PsConsoleFile, чтобы указать файл консоли, включающий оснастку.</span><span class="sxs-lookup"><span data-stu-id="b1824-149">Use the PsConsoleFile parameter to specify the console file that includes the snap-in.</span></span> <span data-ttu-id="b1824-150">Например, следующая команда запускает Windows PowerShell с файлом консоли Невконсоле. psc1:</span><span class="sxs-lookup"><span data-stu-id="b1824-150">For example, the following command starts Windows PowerShell with the NewConsole.psc1 console file:</span></span>

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

<span data-ttu-id="b1824-151">Поставщики и командлеты в оснастке теперь доступны для использования в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b1824-151">The providers and cmdlets in the snapin are now available for use in the session.</span></span>

### <a name="removing-a-snap-in"></a><span data-ttu-id="b1824-152">УДАЛЕНИЕ ОСНАСТКИ</span><span class="sxs-lookup"><span data-stu-id="b1824-152">REMOVING A SNAP-IN</span></span>

<span data-ttu-id="b1824-153">Чтобы удалить оснастку Windows PowerShell из текущего сеанса, используйте командлет Remove-PsSnapin.</span><span class="sxs-lookup"><span data-stu-id="b1824-153">To remove a Windows PowerShell snap-in from the current session, use the Remove-PsSnapin cmdlet.</span></span> <span data-ttu-id="b1824-154">Например, чтобы удалить оснастку SQL Server из текущего сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="b1824-154">For example, to remove the SQL Server snap-in from the current session, type:</span></span>

```powershell
Remove-PSSnapin sql
```

<span data-ttu-id="b1824-155">Этот командлет удаляет оснастку из сеанса.</span><span class="sxs-lookup"><span data-stu-id="b1824-155">This cmdlet removes the snap-in from the session.</span></span> <span data-ttu-id="b1824-156">Оснастка все еще загружена, но поставщики и командлеты, которые она поддерживает, больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="b1824-156">The snap-in is still loaded, but the providers and cmdlets that it supports are no longer available.</span></span>

### <a name="built-in-commands"></a><span data-ttu-id="b1824-157">ВСТРОЕННЫЕ КОМАНДЫ</span><span class="sxs-lookup"><span data-stu-id="b1824-157">BUILT-IN COMMANDS</span></span>

<span data-ttu-id="b1824-158">В Windows PowerShell 2,0 и в старых программах Windows PowerShell 3,0 и более поздних версиях встроенные команды, устанавливаемые вместе с Windows PowerShell, упаковываются в оснастки, которые автоматически добавляются в каждый сеанс Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-158">In Windows PowerShell 2.0 and in older-style host programs in Windows PowerShell 3.0 and later, the built-in commands that are installed with Windows PowerShell are packaged in snap-ins that are added automatically to every Windows PowerShell session.</span></span>

<span data-ttu-id="b1824-159">Начиная с Windows PowerShell 3,0, в более новых приложениях-компонентах, запускающих сеансы с помощью метода InitialSessionState. CreateDefault2 — встроенные команды упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="b1824-159">Beginning in Windows PowerShell 3.0, in newer-style host programs -- those that start sessions by using the InitialSessionState.CreateDefault2 method -- the built-in commands are packaged in modules.</span></span> <span data-ttu-id="b1824-160">Исключением является Microsoft. PowerShell. Core, которое всегда отображается как оснастка.</span><span class="sxs-lookup"><span data-stu-id="b1824-160">The exception is Microsoft.PowerShell.Core, which always appears as a snap-in.</span></span> <span data-ttu-id="b1824-161">Основная оснастка по умолчанию включена в каждый сеанс.</span><span class="sxs-lookup"><span data-stu-id="b1824-161">The Core snap-in is included in every session by default.</span></span> <span data-ttu-id="b1824-162">Встроенные модули загружаются автоматически при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="b1824-162">The built-in modules are loaded automatically on first-use.</span></span>

<span data-ttu-id="b1824-163">Примечание. удаленные сеансы, включая сеансы, запущенные с помощью командлета New-PSSession, — это сеансы предыдущих версий, в которых встроенные команды упаковываются в оснастки.</span><span class="sxs-lookup"><span data-stu-id="b1824-163">NOTE: Remote sessions, including sessions that are started by using the New-PSSession cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="b1824-164">Следующие оснастки (или модули) устанавливаются вместе с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-164">The following snap-ins (or modules) are installed with Windows PowerShell.</span></span>

- <span data-ttu-id="b1824-165">Microsoft. PowerShell. Core — содержит поставщики и командлеты, используемые для управления основными функциями Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1824-165">Microsoft.PowerShell.Core - Contains providers and cmdlets used to manage the basic features of Windows PowerShell.</span></span> <span data-ttu-id="b1824-166">Он включает в себя файл FileSystem, реестр, псевдоним, среду, функцию и поставщики переменных, а также базовые командлеты, такие как Get-Help, Get-Command и Get-History.</span><span class="sxs-lookup"><span data-stu-id="b1824-166">It includes the FileSystem, Registry, Alias, Environment, Function, and Variable providers and basic cmdlets like Get-Help, Get-Command, and Get-History.</span></span>

- <span data-ttu-id="b1824-167">Microsoft. PowerShell. host — содержит командлеты, используемые узлом Windows PowerShell, такие как Start-Transcript и командлеты типа "точка-расшифровка".</span><span class="sxs-lookup"><span data-stu-id="b1824-167">Microsoft.PowerShell.Host - Contains cmdlets used by the Windows PowerShell host, such as Start-Transcript and Stop-Transcript.</span></span>

- <span data-ttu-id="b1824-168">Microsoft. PowerShell. Management — содержит командлеты, такие как Get-Service и Get-ChildItem, которые используются для управления компонентами Windows.</span><span class="sxs-lookup"><span data-stu-id="b1824-168">Microsoft.PowerShell.Management - Contains cmdlets such as Get-Service and Get-ChildItem that are used to manage Windows-based features.</span></span>

- <span data-ttu-id="b1824-169">Microsoft. PowerShell. Security — содержит поставщик сертификатов и командлеты, используемые для управления безопасностью Windows PowerShell, такие как Get-ACL, Get-AuthenticodeSignature и ConvertTo-SecureString.</span><span class="sxs-lookup"><span data-stu-id="b1824-169">Microsoft.PowerShell.Security - Contains the Certificate provider and cmdlets used to manage Windows PowerShell security, such as Get-Acl, Get-AuthenticodeSignature, and ConvertTo-SecureString.</span></span>

- <span data-ttu-id="b1824-170">Microsoft. PowerShell. Utility — содержит командлеты, используемые для работы с объектами и данными, например Get-Member, Write-Host и Format-List.</span><span class="sxs-lookup"><span data-stu-id="b1824-170">Microsoft.PowerShell.Utility - Contains cmdlets used to manipulate objects and data, such as Get-Member, Write-Host, and Format-List.</span></span>

- <span data-ttu-id="b1824-171">Microsoft. WSMan. Management — содержит поставщик WSMan и командлеты, управляющие службой служба удаленного управления Windows, такие как Connect-WSMan и Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="b1824-171">Microsoft.WSMan.Management - Contains the WSMan provider and cmdlets that manage the Windows Remote Management service, such as Connect-WSMan and Enable-WSManCredSSP.</span></span>

## <a name="logging-snap-in-events"></a><span data-ttu-id="b1824-172">РЕГИСТРАЦИЯ СОБЫТИЙ ОСНАСТКИ</span><span class="sxs-lookup"><span data-stu-id="b1824-172">LOGGING SNAP-IN EVENTS</span></span>

<span data-ttu-id="b1824-173">Начиная с Windows PowerShell 3,0, вы можете записывать события выполнения для командлетов в модулях и оснастках Windows PowerShell, установив для свойства LogPipelineExecutionDetails модулей и оснасток значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="b1824-173">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="b1824-174">Дополнительные сведения см. в разделе [about_EventLogs](about_EventLogs.md).</span><span class="sxs-lookup"><span data-stu-id="b1824-174">For more information, see [about_EventLogs](about_EventLogs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1824-175">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="b1824-175">SEE ALSO</span></span>

[<span data-ttu-id="b1824-176">Add-PsSnapin</span><span class="sxs-lookup"><span data-stu-id="b1824-176">Add-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[<span data-ttu-id="b1824-177">Get-PsSnapin</span><span class="sxs-lookup"><span data-stu-id="b1824-177">Get-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[<span data-ttu-id="b1824-178">Remove-PsSnapin</span><span class="sxs-lookup"><span data-stu-id="b1824-178">Remove-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[<span data-ttu-id="b1824-179">Export-Console</span><span class="sxs-lookup"><span data-stu-id="b1824-179">Export-Console</span></span>](xref:Microsoft.PowerShell.Core.Export-Console)

[<span data-ttu-id="b1824-180">Get-Command</span><span class="sxs-lookup"><span data-stu-id="b1824-180">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="b1824-181">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="b1824-181">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="b1824-182">about_Modules</span><span class="sxs-lookup"><span data-stu-id="b1824-182">about_Modules</span></span>](about_Modules.md)

## <a name="keywords"></a><span data-ttu-id="b1824-183">СЛОВАМИ</span><span class="sxs-lookup"><span data-stu-id="b1824-183">KEYWORDS</span></span>

<span data-ttu-id="b1824-184">about_Snapins, about_Snap_ins, about_Snap</span><span class="sxs-lookup"><span data-stu-id="b1824-184">about_Snapins, about_Snap_ins, about_Snap-ins</span></span>
