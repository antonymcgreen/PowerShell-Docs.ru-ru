---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 472a4c8fbb9eb0d37827aff4fcfd6bb9a67f4743
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226665"
---
# <span data-ttu-id="7f32c-103">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="7f32c-103">Get-PSSnapin</span></span>

## <span data-ttu-id="7f32c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7f32c-104">SYNOPSIS</span></span>
<span data-ttu-id="7f32c-105">Получает оснастки Windows PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7f32c-105">Gets the Windows PowerShell snap-ins on the computer.</span></span>

## <span data-ttu-id="7f32c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7f32c-106">SYNTAX</span></span>

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## <span data-ttu-id="7f32c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7f32c-107">DESCRIPTION</span></span>
<span data-ttu-id="7f32c-108">Командлет **Get-PSSnapin** получает оснастки Windows PowerShell, которые были добавлены в текущий сеанс или которые были зарегистрированы в системе.</span><span class="sxs-lookup"><span data-stu-id="7f32c-108">The **Get-PSSnapin** cmdlet gets the Windows PowerShell snap-ins that have been added to the current session or that have been registered on the system.</span></span>
<span data-ttu-id="7f32c-109">Этот командлет перечисляет оснастки в том порядке, в котором они обнаружены.</span><span class="sxs-lookup"><span data-stu-id="7f32c-109">This cmdlet lists the snap-ins in the order in which they are detected.</span></span>

<span data-ttu-id="7f32c-110">**Get-PSSnapin** получает только зарегистрированные оснастки. Чтобы зарегистрировать оснастку Windows PowerShell, используйте средство InstallUtil, входящее в состав Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="7f32c-110">**Get-PSSnapin** gets only registered snap-ins. To register a Windows PowerShell snap-in, use the InstallUtil tool included with the Microsoft .NET Framework 2.0.</span></span>
<span data-ttu-id="7f32c-111">Дополнительные сведения см. в разделе [Регистрация командлетов, поставщиков и ведущих приложений](https://go.microsoft.com/fwlink/?LinkID=143619) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="7f32c-111">For more information, see [How to Register Cmdlets, Providers, and Host Applications](https://go.microsoft.com/fwlink/?LinkID=143619) in the MSDN library.</span></span>

<span data-ttu-id="7f32c-112">Начиная с Windows PowerShell 3,0, основные команды, входящие в Windows PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="7f32c-112">Starting in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span>
<span data-ttu-id="7f32c-113">Исключение составляет **Microsoft.PowerShell.Core** , который является оснасткой (PSSnapin).</span><span class="sxs-lookup"><span data-stu-id="7f32c-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="7f32c-114">По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core**.</span><span class="sxs-lookup"><span data-stu-id="7f32c-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="7f32c-115">Модули импортируются автоматически при первом использовании. для их импорта можно использовать командлет Import-Module.</span><span class="sxs-lookup"><span data-stu-id="7f32c-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="7f32c-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="7f32c-116">EXAMPLES</span></span>

### <span data-ttu-id="7f32c-117">Пример 1. получение оснасток, загруженных в данный момент</span><span class="sxs-lookup"><span data-stu-id="7f32c-117">Example 1: Get snap-ins that are currently loaded</span></span>

```
PS C:\> Get-PSSnapIn
```

<span data-ttu-id="7f32c-118">Эта команда возвращает оснастки Windows PowerShell, загруженные в сеанс на текущий момент.</span><span class="sxs-lookup"><span data-stu-id="7f32c-118">This command gets the Windows PowerShell snap-ins that are currently loaded in the session.</span></span>
<span data-ttu-id="7f32c-119">Сюда входят как оснастки, установленные вместе с Windows PowerShell, так и оснастки, добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="7f32c-119">This includes the snap-ins that are installed with Windows PowerShell and those that have been added to the session.</span></span>

### <span data-ttu-id="7f32c-120">Пример 2. получение зарегистрированных оснасток</span><span class="sxs-lookup"><span data-stu-id="7f32c-120">Example 2: Get snap-ins that have been registered</span></span>

```
PS C:\> get-PSSnapIn -Registered
```

<span data-ttu-id="7f32c-121">Эта команда получает оснастки Windows PowerShell, зарегистрированные на компьютере, включая оснастки, уже добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="7f32c-121">This command gets the Windows PowerShell snap-ins that have been registered on the computer, including those that have already been added to the session.</span></span>
<span data-ttu-id="7f32c-122">В выходные данные не включаются оснастки, установленные вместе с Windows PowerShell или библиотеками динамической компоновки (библиотеками DLL) оснасток Windows PowerShell, которые еще не зарегистрированы в системе.</span><span class="sxs-lookup"><span data-stu-id="7f32c-122">The output does not include snap-ins that are installed with Windows PowerShell or Windows PowerShell snap-in dynamic-link libraries (DLLs) that have not yet been registered on the system.</span></span>

### <span data-ttu-id="7f32c-123">Пример 3. Получение текущих оснасток, соответствующих строке</span><span class="sxs-lookup"><span data-stu-id="7f32c-123">Example 3: Get current snap-ins that match a string</span></span>

```
PS C:\> Get-PSSnapIn -Name smp*
```

<span data-ttu-id="7f32c-124">Эта команда получает оснастки Windows PowerShell в текущем сеансе, имена которых начинаются с SMP.</span><span class="sxs-lookup"><span data-stu-id="7f32c-124">This command gets the Windows PowerShell snap-ins in the current session that have names that begin with smp.</span></span>

## <span data-ttu-id="7f32c-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7f32c-125">PARAMETERS</span></span>

### <span data-ttu-id="7f32c-126">-Name</span><span class="sxs-lookup"><span data-stu-id="7f32c-126">-Name</span></span>
<span data-ttu-id="7f32c-127">Указывает массив имен оснасток.</span><span class="sxs-lookup"><span data-stu-id="7f32c-127">Specifies an array of snap-in names.</span></span>
<span data-ttu-id="7f32c-128">Этот командлет возвращает только указанные оснастки Windows PowerShell. Допускаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="7f32c-128">This cmdlet gets only the specified Windows PowerShell snap-ins. Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f32c-129">— Зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="7f32c-129">-Registered</span></span>
<span data-ttu-id="7f32c-130">Указывает, что этот командлет получает оснастки Windows PowerShell, которые были зарегистрированы в системе, даже если они еще не были добавлены в сеанс.</span><span class="sxs-lookup"><span data-stu-id="7f32c-130">Indicates that this cmdlet gets the Windows PowerShell snap-ins that have been registered on the system even if they have not yet been added to the session.</span></span>

<span data-ttu-id="7f32c-131">Оснастки, устанавливаемые с Windows PowerShell, не включаются в этот список.</span><span class="sxs-lookup"><span data-stu-id="7f32c-131">The snap-ins that are installed with Windows PowerShell do not appear in this list.</span></span>

<span data-ttu-id="7f32c-132">Без этого параметра командлет **Get-PSSnapin** получает оснастки Windows PowerShell, которые были добавлены в сеанс.</span><span class="sxs-lookup"><span data-stu-id="7f32c-132">Without this parameter, **Get-PSSnapin** gets the Windows PowerShell snap-ins that have been added to the session.</span></span>

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

### <span data-ttu-id="7f32c-133">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7f32c-133">CommonParameters</span></span>
<span data-ttu-id="7f32c-134">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7f32c-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7f32c-135">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7f32c-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7f32c-136">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7f32c-136">INPUTS</span></span>

### <span data-ttu-id="7f32c-137">Нет</span><span class="sxs-lookup"><span data-stu-id="7f32c-137">None</span></span>
<span data-ttu-id="7f32c-138">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="7f32c-138">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7f32c-139">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7f32c-139">OUTPUTS</span></span>

### <span data-ttu-id="7f32c-140">System. Management. Automation. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="7f32c-140">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="7f32c-141">Командлет Get-PSSnapin возвращает объект для каждой получаемой оснастки.</span><span class="sxs-lookup"><span data-stu-id="7f32c-141">Get-PSSnapin returns an object for each snap-in that it gets.</span></span>

## <span data-ttu-id="7f32c-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7f32c-142">NOTES</span></span>

* <span data-ttu-id="7f32c-143">Начиная с Windows PowerShell 3,0, основные команды, устанавливаемые вместе с Windows PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="7f32c-143">Starting in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="7f32c-144">В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях Windows PowerShell, основные команды упаковываются в оснастки ( **PSSnapin** ).</span><span class="sxs-lookup"><span data-stu-id="7f32c-144">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins ( **PSSnapin** ).</span></span> <span data-ttu-id="7f32c-145">Исключением является **Microsoft. PowerShell. Core** , который всегда является оснасткой.</span><span class="sxs-lookup"><span data-stu-id="7f32c-145">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="7f32c-146">Кроме того, удаленные сеансы, например, запущенные командлетом New-PSSession, являются сеансами предыдущих версий, включающими основные оснастки.</span><span class="sxs-lookup"><span data-stu-id="7f32c-146">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="7f32c-147">Дополнительные сведения о методе **CreateDefault2** , который создает сеансы более новых версий с основными модулями, см. в разделе [метод CREATEDEFAULT2](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="7f32c-147">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

## <span data-ttu-id="7f32c-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7f32c-148">RELATED LINKS</span></span>

[<span data-ttu-id="7f32c-149">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="7f32c-149">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="7f32c-150">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="7f32c-150">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
