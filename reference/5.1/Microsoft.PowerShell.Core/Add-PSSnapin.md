---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: a21c2974fd66a9b02929752ae487c8995579b8a7
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388830"
---
# <span data-ttu-id="6294a-103">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="6294a-103">Add-PSSnapin</span></span>

## <span data-ttu-id="6294a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6294a-104">SYNOPSIS</span></span>
<span data-ttu-id="6294a-105">Добавляет в текущий сеанс одну или несколько оснасток Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6294a-105">Adds one or more Windows PowerShell snap-ins to the current session.</span></span>

## <span data-ttu-id="6294a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6294a-106">SYNTAX</span></span>

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="6294a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6294a-107">DESCRIPTION</span></span>

<span data-ttu-id="6294a-108">`Add-PSSnapin`Командлет добавляет зарегистрированные оснастки Windows PowerShell в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="6294a-108">The `Add-PSSnapin` cmdlet adds registered Windows PowerShell snap-ins to the current session.</span></span> <span data-ttu-id="6294a-109">После добавления оснастки можно использовать в текущем сеансе командлеты и поставщиков, поддерживающих оснастки.</span><span class="sxs-lookup"><span data-stu-id="6294a-109">After the snap-ins are added, you can use the cmdlets and providers that the snap-ins support in the current session.</span></span>

<span data-ttu-id="6294a-110">Чтобы добавить оснастку во все будущие сеансы Windows PowerShell, добавьте `Add-PSSnapin` команду в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6294a-110">To add the snap-in to all future Windows PowerShell sessions, add an `Add-PSSnapin` command to your Windows PowerShell profile.</span></span> <span data-ttu-id="6294a-111">Дополнительные сведения см. в разделе [about_Profiles](about/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6294a-111">For more information, see [about_Profiles](about/about_Profiles.md).</span></span>

<span data-ttu-id="6294a-112">Начиная с Windows PowerShell 3.0, основные команды, включенные в Windows PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="6294a-112">Beginning in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="6294a-113">Исключение составляет **Microsoft.PowerShell.Core** , который является оснасткой (PSSnapin).</span><span class="sxs-lookup"><span data-stu-id="6294a-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="6294a-114">По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core**.</span><span class="sxs-lookup"><span data-stu-id="6294a-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="6294a-115">Модули импортируются автоматически при первом использовании. для их импорта можно использовать командлет Import-Module.</span><span class="sxs-lookup"><span data-stu-id="6294a-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="6294a-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="6294a-116">EXAMPLES</span></span>

### <span data-ttu-id="6294a-117">Пример 1. Добавление оснасток</span><span class="sxs-lookup"><span data-stu-id="6294a-117">Example 1: Add snap-ins</span></span>

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

<span data-ttu-id="6294a-118">Эта команда добавляет оснастки Microsoft Exchange и Active Directory в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="6294a-118">This command adds the Microsoft Exchange and Active Directory snap-ins to the current session.</span></span>

### <span data-ttu-id="6294a-119">Пример 2. Добавление всех зарегистрированных оснасток</span><span class="sxs-lookup"><span data-stu-id="6294a-119">Example 2: Add all the registered snap-ins</span></span>

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

<span data-ttu-id="6294a-120">Эта команда добавляет в сеанс все зарегистрированные оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6294a-120">This command adds all of the registered Windows PowerShell snap-ins to the session.</span></span> <span data-ttu-id="6294a-121">Для получения объектов, представляющих все зарегистрированные оснастки, используется командлет Get-PSSnapin с **зарегистрированным** параметром. Оператор конвейера (|) передает результат в `Add-PSSnapin` , который добавляет их в сеанс.</span><span class="sxs-lookup"><span data-stu-id="6294a-121">It uses the Get-PSSnapin cmdlet with the **Registered** parameter to get objects representing each of the registered snap-ins. The pipeline operator (|) passes the result to `Add-PSSnapin`, which adds them to the session.</span></span> <span data-ttu-id="6294a-122">Параметр **PassThru** возвращает объекты, представляющие все добавленные оснастки.</span><span class="sxs-lookup"><span data-stu-id="6294a-122">The **PassThru** parameter returns objects that represent each of the added snap-ins.</span></span>

### <span data-ttu-id="6294a-123">Пример 3. Регистрация оснастки и добавление ее</span><span class="sxs-lookup"><span data-stu-id="6294a-123">Example 3: Register a snap-in and add it</span></span>

<span data-ttu-id="6294a-124">Первая команда получает оснастки, которые были добавлены в текущий сеанс, включающий оснастки, которые устанавливаются вместе с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6294a-124">The first command gets snap-ins that have been added to the current session that include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="6294a-125">В этом примере ManagementFeatures не возвращается.</span><span class="sxs-lookup"><span data-stu-id="6294a-125">In this example, ManagementFeatures is not returned.</span></span> <span data-ttu-id="6294a-126">Это означает, что данная оснастка в сеанс не добавлена.</span><span class="sxs-lookup"><span data-stu-id="6294a-126">This indicates that it has not been added to the session.</span></span>

<span data-ttu-id="6294a-127">Вторая команда получает оснастки, которые были зарегистрированы в системе, включая те, которые уже были добавлены в сеанс.</span><span class="sxs-lookup"><span data-stu-id="6294a-127">The second command gets snap-ins that have been registered on your system, which includes those that have already been added to the session.</span></span> <span data-ttu-id="6294a-128">В нее не входят оснастки, устанавливаемые вместе с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6294a-128">It does not include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="6294a-129">В этом случае команда не возвращает ни одной оснастки. Это означает, что оснастка Манажементфеатурес не зарегистрирована в системе.</span><span class="sxs-lookup"><span data-stu-id="6294a-129">In this case, the command does not return any snap-ins. This indicates that the ManagementFeatures snapin has not been registered on the system.</span></span>

<span data-ttu-id="6294a-130">Третья команда создает псевдоним, InstallUtil, для пути к средству InstallUtil в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6294a-130">The third command creates an alias, installutil, for the path of the InstallUtil tool in .NET Framework.</span></span>

<span data-ttu-id="6294a-131">Четвертая команда использует средство InstallUtil для регистрации оснастки.</span><span class="sxs-lookup"><span data-stu-id="6294a-131">The fourth command uses the InstallUtil tool to register the snap-in.</span></span> <span data-ttu-id="6294a-132">Команда задает путь к ManagementCmdlets.dll, имя файла или модуля оснастки.</span><span class="sxs-lookup"><span data-stu-id="6294a-132">The command specifies the path of ManagementCmdlets.dll, the filename or module name of the snap-in.</span></span>

<span data-ttu-id="6294a-133">Пятая команда совпадает со второй,</span><span class="sxs-lookup"><span data-stu-id="6294a-133">The fifth command is the same as the second command.</span></span> <span data-ttu-id="6294a-134">но на этот раз она используется для того, чтобы проверить регистрацию оснастки ManagementCmdlets.</span><span class="sxs-lookup"><span data-stu-id="6294a-134">This time, you use it to verify that the ManagementCmdlets snap-in is registered.</span></span>

<span data-ttu-id="6294a-135">Шестая команда использует `Add-PSSnapin` командлет для добавления к сеансу оснастки манажементфеатурес.</span><span class="sxs-lookup"><span data-stu-id="6294a-135">The sixth command uses the `Add-PSSnapin` cmdlet to add the ManagementFeatures snap-in to the session.</span></span> <span data-ttu-id="6294a-136">Она указывает имя оснастки, ManagementFeatures, а не имя файла.</span><span class="sxs-lookup"><span data-stu-id="6294a-136">It specifies the name of the snap-in, ManagementFeatures, not the file name.</span></span>

<span data-ttu-id="6294a-137">Чтобы убедиться, что оснастка добавлена в сеанс, Седьмая команда использует параметр **module** командлета Get-Command.</span><span class="sxs-lookup"><span data-stu-id="6294a-137">To verify that the snap-in is added to the session, the seventh command uses the **Module** parameter of the Get-Command cmdlet.</span></span> <span data-ttu-id="6294a-138">Она отображает элементы, добавленные в сеанс оснасткой или модулем.</span><span class="sxs-lookup"><span data-stu-id="6294a-138">It displays the items that were added to the session by a snap-in or module.</span></span>

<span data-ttu-id="6294a-139">Можно также использовать свойство **PSSnapin** объекта, `Get-Command` возвращаемого командлетом, для поиска оснастки или модуля, в котором был создан командлет.</span><span class="sxs-lookup"><span data-stu-id="6294a-139">You can also use the **PSSnapin** property of the object that the `Get-Command` cmdlet returns to find the snap-in or module in which a cmdlet originated.</span></span> <span data-ttu-id="6294a-140">Восьмая команда использует точечную нотацию для поиска значения свойства PSSnapin командлета Set-Alias.</span><span class="sxs-lookup"><span data-stu-id="6294a-140">The eighth command uses dot notation to find the value of the PSSnapin property of the Set-Alias cmdlet.</span></span>

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

<span data-ttu-id="6294a-141">В этом примере показан процесс регистрации оснастки в системе и последующее добавление этой оснастки в сеанс.</span><span class="sxs-lookup"><span data-stu-id="6294a-141">This example demonstrates the process of registering a snap-in on your system and then adding it to your session.</span></span> <span data-ttu-id="6294a-142">В нем используется Манажементфеатурес — вымышленная оснастка, реализованная в файле с именем ManagementCmdlets.dll.</span><span class="sxs-lookup"><span data-stu-id="6294a-142">It uses ManagementFeatures, a fictitious snap-in implemented in a file that is named ManagementCmdlets.dll.</span></span>

## <span data-ttu-id="6294a-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6294a-143">PARAMETERS</span></span>

### <span data-ttu-id="6294a-144">-Name</span><span class="sxs-lookup"><span data-stu-id="6294a-144">-Name</span></span>

<span data-ttu-id="6294a-145">Задает имя оснастки.</span><span class="sxs-lookup"><span data-stu-id="6294a-145">Specifies the name of the snap-in.</span></span> <span data-ttu-id="6294a-146">Это имя, а не AssemblyName или ModuleName.</span><span class="sxs-lookup"><span data-stu-id="6294a-146">This is the Name, not the AssemblyName or ModuleName.</span></span> <span data-ttu-id="6294a-147">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6294a-147">Wildcards are permitted.</span></span>

<span data-ttu-id="6294a-148">Чтобы найти имена зарегистрированных оснасток в системе, введите `Get-PSSnapin -Registered` .</span><span class="sxs-lookup"><span data-stu-id="6294a-148">To find the names of the registered snap-ins on your system, type `Get-PSSnapin -Registered`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="6294a-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6294a-149">-PassThru</span></span>

<span data-ttu-id="6294a-150">Указывает, что этот командлет возвращает объект, представляющий каждую добавленную оснастку.</span><span class="sxs-lookup"><span data-stu-id="6294a-150">Indicates that this cmdlet returns an object that represents each added snap-in.</span></span> <span data-ttu-id="6294a-151">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="6294a-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="6294a-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6294a-152">CommonParameters</span></span>

<span data-ttu-id="6294a-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6294a-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6294a-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6294a-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6294a-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6294a-155">INPUTS</span></span>

### <span data-ttu-id="6294a-156">Нет</span><span class="sxs-lookup"><span data-stu-id="6294a-156">None</span></span>
<span data-ttu-id="6294a-157">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="6294a-157">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="6294a-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6294a-158">OUTPUTS</span></span>

### <span data-ttu-id="6294a-159">None или System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="6294a-159">None or System.Management.Automation.PSSnapInInfo</span></span>

<span data-ttu-id="6294a-160">Этот командлет возвращает объект PSSnapInInfo, представляющий оснастку, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="6294a-160">This cmdlet returns a PSSnapInInfo object that represents the snap-in if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="6294a-161">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6294a-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6294a-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6294a-162">NOTES</span></span>

- <span data-ttu-id="6294a-163">Начиная с Windows PowerShell 3.0, основные команды, включенные в Windows PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="6294a-163">Beginning in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="6294a-164">В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях Windows PowerShell, основные команды упаковываются в оснастки (PSSnapin).</span><span class="sxs-lookup"><span data-stu-id="6294a-164">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins (PSSnapins).</span></span> <span data-ttu-id="6294a-165">Исключением является **Microsoft. PowerShell. Core** , который всегда является оснасткой.</span><span class="sxs-lookup"><span data-stu-id="6294a-165">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="6294a-166">Кроме того, удаленные сеансы, например, запущенные командлетом New-PSSession, являются сеансами предыдущих версий, включающими основные оснастки.</span><span class="sxs-lookup"><span data-stu-id="6294a-166">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="6294a-167">Дополнительные сведения о методе **CreateDefault2** , который создает сеансы нового стиля с основными модулями, см. в разделе [метод CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).</span><span class="sxs-lookup"><span data-stu-id="6294a-167">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).</span></span>

- <span data-ttu-id="6294a-168">Дополнительные сведения об оснастках см. в разделе [about_PSSnapins](About/about_PSSnapins.md) и [Создание оснастки Windows PowerShell](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).</span><span class="sxs-lookup"><span data-stu-id="6294a-168">For more information about snap-ins, see [about_PSSnapins](About/about_PSSnapins.md) and [How to Create a Windows PowerShell Snap-in](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).</span></span>
- <span data-ttu-id="6294a-169">`Add-PSSnapin` добавляет оснастку только в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="6294a-169">`Add-PSSnapin` adds the snap-in only to the current session.</span></span> <span data-ttu-id="6294a-170">Чтобы оснастка добавлялась во все сеансы Windows PowerShell, вставьте эту команду в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6294a-170">To add the snap-in to all Windows PowerShell sessions, add it to your Windows PowerShell profile.</span></span> <span data-ttu-id="6294a-171">Дополнительные сведения см. в разделе about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="6294a-171">For more information, see about_Profiles.</span></span>
- <span data-ttu-id="6294a-172">Можно добавить любую оснастку, зарегистрированную с помощью служебной программы установки Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6294a-172">You can add any snap-in that has been registered using the Microsoft .NET Framework install utility.</span></span> <span data-ttu-id="6294a-173">Дополнительные сведения см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="6294a-173">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>
- <span data-ttu-id="6294a-174">Чтобы получить список оснасток, зарегистрированных на компьютере, введите `Get-PSSnapin -Registered` .</span><span class="sxs-lookup"><span data-stu-id="6294a-174">To get a list of snap-ins that are registered on your computer, type `Get-PSSnapin -Registered`.</span></span>
- <span data-ttu-id="6294a-175">Перед добавлением оснастки `Add-PSSnapin` проверяет версию оснастки, чтобы убедиться, что она совместима с текущей версией Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6294a-175">Before adding a snap-in, `Add-PSSnapin` checks the version of the snap-in to verify that it is compatible with the current version of Windows PowerShell.</span></span> <span data-ttu-id="6294a-176">Если оснастка не проходит проверку версии, Windows PowerShell сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="6294a-176">If the snap-in fails the version check, Windows PowerShell reports an error.</span></span>

## <span data-ttu-id="6294a-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6294a-177">RELATED LINKS</span></span>

[<span data-ttu-id="6294a-178">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="6294a-178">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="6294a-179">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="6294a-179">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
