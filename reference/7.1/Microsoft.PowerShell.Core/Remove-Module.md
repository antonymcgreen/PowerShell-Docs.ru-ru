---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: f0fb0847d43a8fa8541ed194e474a1fab1f5ffa9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229174"
---
# <span data-ttu-id="4dea1-103">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="4dea1-103">Remove-Module</span></span>

## <span data-ttu-id="4dea1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4dea1-104">SYNOPSIS</span></span>
<span data-ttu-id="4dea1-105">Удаляет модули из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="4dea1-105">Removes modules from the current session.</span></span>

## <span data-ttu-id="4dea1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4dea1-106">SYNTAX</span></span>

### <span data-ttu-id="4dea1-107">name</span><span class="sxs-lookup"><span data-stu-id="4dea1-107">name</span></span>

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4dea1-108">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="4dea1-108">FullyQualifiedName</span></span>

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4dea1-109">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="4dea1-109">ModuleInfo</span></span>

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4dea1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4dea1-110">DESCRIPTION</span></span>

<span data-ttu-id="4dea1-111">Командлет **Remove-Module** удаляет члены модуля, например командлеты и функции, из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="4dea1-111">The **Remove-Module** cmdlet removes the members of a module, such as cmdlets and functions, from the current session.</span></span>

<span data-ttu-id="4dea1-112">Если модуль содержит сборку (DLL), все члены, реализованные в этой сборке, удаляются, но сборка не выгружается.</span><span class="sxs-lookup"><span data-stu-id="4dea1-112">If the module includes an assembly (.dll), all members that are implemented by the assembly are removed, but the assembly is not unloaded.</span></span>

<span data-ttu-id="4dea1-113">Командлет не деинсталлирует модуль и не удаляет его с компьютера.</span><span class="sxs-lookup"><span data-stu-id="4dea1-113">This cmdlet does not uninstall the module or delete it from the computer.</span></span>
<span data-ttu-id="4dea1-114">Он влияет только на текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dea1-114">It affects only the current PowerShell session.</span></span>

## <span data-ttu-id="4dea1-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="4dea1-115">EXAMPLES</span></span>

### <span data-ttu-id="4dea1-116">Пример 1. Удаление модуля</span><span class="sxs-lookup"><span data-stu-id="4dea1-116">Example 1: Remove a module</span></span>

```powershell
Remove-Module -Name "BitsTransfer"
```

<span data-ttu-id="4dea1-117">Эта команда удаляет модуль BitsTransfer из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="4dea1-117">This command removes the BitsTransfer module from the current session.</span></span>

### <span data-ttu-id="4dea1-118">Пример 2. Удаление всех модулей</span><span class="sxs-lookup"><span data-stu-id="4dea1-118">Example 2: Remove all modules</span></span>

```powershell
Get-Module | Remove-Module
```

<span data-ttu-id="4dea1-119">Эта команда удаляет все модули из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="4dea1-119">This command removes all modules from the current session.</span></span>

### <span data-ttu-id="4dea1-120">Пример 3. Удаление модулей с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="4dea1-120">Example 3: Remove modules by using the pipeline</span></span>

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

<span data-ttu-id="4dea1-121">Эта команда удаляет модули BitsTransfer и PSDiagnostics из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="4dea1-121">This command removes the BitsTransfer and PSDiagnostics modules from the current session.</span></span>

<span data-ttu-id="4dea1-122">Имена модулей отправляются в командлет **Remove-Module** с помощью конвейерного оператора (|).</span><span class="sxs-lookup"><span data-stu-id="4dea1-122">The command uses a pipeline operator (|) to send the module names to **Remove-Module**.</span></span>
<span data-ttu-id="4dea1-123">Для получения подробной информации об удаляемых членах модуля используется общий параметр *Verbose*.</span><span class="sxs-lookup"><span data-stu-id="4dea1-123">It uses the *Verbose* common parameter to get detailed information about the members that are removed.</span></span>

<span data-ttu-id="4dea1-124">В *подробных* сообщениях отображаются элементы, которые были удалены.</span><span class="sxs-lookup"><span data-stu-id="4dea1-124">The *Verbose* messages show the items that are removed.</span></span>
<span data-ttu-id="4dea1-125">Сообщения различаются, поскольку модуль BitsTransfer включает сборку, реализующую его командлеты, и вложенный модуль с его собственной сборкой.</span><span class="sxs-lookup"><span data-stu-id="4dea1-125">The messages differ because the BitsTransfer module includes an assembly that implements its cmdlets and a nested module with its own assembly.</span></span>
<span data-ttu-id="4dea1-126">Модуль PSDiagnostics включает файл скрипта модуля (PSM1), который экспортирует функции.</span><span class="sxs-lookup"><span data-stu-id="4dea1-126">The PSDiagnostics module includes a module script file (.psm1) that exports functions.</span></span>

### <span data-ttu-id="4dea1-127">Пример 4. Удаление модуля с помощью ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="4dea1-127">Example 4: Remove a module by using ModuleInfo</span></span>

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

<span data-ttu-id="4dea1-128">Эта команда использует параметр *ModuleInfo* для удаления модуля BitsTransfer.</span><span class="sxs-lookup"><span data-stu-id="4dea1-128">This command uses the *ModuleInfo* parameter to remove the BitsTransfer module.</span></span>

## <span data-ttu-id="4dea1-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4dea1-129">PARAMETERS</span></span>

### <span data-ttu-id="4dea1-130">-Force</span><span class="sxs-lookup"><span data-stu-id="4dea1-130">-Force</span></span>

<span data-ttu-id="4dea1-131">Указывает, что этот командлет удаляет модули, которые доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4dea1-131">Indicates that this cmdlet removes read-only modules.</span></span>
<span data-ttu-id="4dea1-132">По умолчанию командлет **Remove-Module** удаляет только модули, предназначенные и для чтения, и для записи.</span><span class="sxs-lookup"><span data-stu-id="4dea1-132">By default, **Remove-Module** removes only read-write modules.</span></span>

<span data-ttu-id="4dea1-133">Значения **ReadOnly** и **ReadWrite** хранятся в свойстве модуля **AccessMode**.</span><span class="sxs-lookup"><span data-stu-id="4dea1-133">The **ReadOnly** and **ReadWrite** values are stored in **AccessMode** property of a module.</span></span>

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

### <span data-ttu-id="4dea1-134">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="4dea1-134">-FullyQualifiedName</span></span>

<span data-ttu-id="4dea1-135">Указывает полные имена модулей для удаления.</span><span class="sxs-lookup"><span data-stu-id="4dea1-135">Specifies the fully qualified names of modules to remove.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4dea1-136">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="4dea1-136">-ModuleInfo</span></span>

<span data-ttu-id="4dea1-137">Задает объекты модулей, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="4dea1-137">Specifies the module objects to remove.</span></span>
<span data-ttu-id="4dea1-138">Введите переменную, которая содержит объект модуля ( **PSModuleInfo** ), или команду, которая получает объект модуля, например команду Get-Module.</span><span class="sxs-lookup"><span data-stu-id="4dea1-138">Enter a variable that contains a module object ( **PSModuleInfo** ) or a command that gets a module object, such as a Get-Module command.</span></span>
<span data-ttu-id="4dea1-139">Объекты модулей можно также передать в командлет **Remove-Module** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4dea1-139">You can also pipe module objects to **Remove-Module**.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4dea1-140">-Name</span><span class="sxs-lookup"><span data-stu-id="4dea1-140">-Name</span></span>

<span data-ttu-id="4dea1-141">Задает имена модулей, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="4dea1-141">Specifies the names of modules to remove.</span></span>
<span data-ttu-id="4dea1-142">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4dea1-142">Wildcard characters are permitted.</span></span>
<span data-ttu-id="4dea1-143">Строки с именами модулей можно также передать в командлет **Remove-Module** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4dea1-143">You can also pipe name strings to **Remove-Module**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="4dea1-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4dea1-144">-Confirm</span></span>

<span data-ttu-id="4dea1-145">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="4dea1-145">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4dea1-146">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4dea1-146">-WhatIf</span></span>

<span data-ttu-id="4dea1-147">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="4dea1-147">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4dea1-148">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4dea1-148">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4dea1-149">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4dea1-149">CommonParameters</span></span>

<span data-ttu-id="4dea1-150">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4dea1-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4dea1-151">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4dea1-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4dea1-152">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4dea1-152">INPUTS</span></span>

### <span data-ttu-id="4dea1-153">System. String, System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="4dea1-153">System.String, System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="4dea1-154">Имена модулей и объекты модулей можно передать в командлет **Remove-Module**.</span><span class="sxs-lookup"><span data-stu-id="4dea1-154">You can pipe module names and module objects to **Remove-Module**.</span></span>

## <span data-ttu-id="4dea1-155">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4dea1-155">OUTPUTS</span></span>

### <span data-ttu-id="4dea1-156">Нет</span><span class="sxs-lookup"><span data-stu-id="4dea1-156">None</span></span>

<span data-ttu-id="4dea1-157">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4dea1-157">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4dea1-158">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4dea1-158">NOTES</span></span>

<span data-ttu-id="4dea1-159">При удалении модуля существует событие в модуле, который будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="4dea1-159">When removing a module, there is an event on the module that will execute.</span></span>
<span data-ttu-id="4dea1-160">Это событие позволяет модулю реагировать на удаление и выполнять некоторую очистку, например освобождение ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4dea1-160">This event allows a module to react to being removed and perform some cleanup such as freeing up resources.</span></span> <span data-ttu-id="4dea1-161">Пример</span><span class="sxs-lookup"><span data-stu-id="4dea1-161">Example:</span></span>

<span data-ttu-id="4dea1-162">$OnRemoveScript = {</span><span class="sxs-lookup"><span data-stu-id="4dea1-162">$OnRemoveScript = {</span></span>

  <span data-ttu-id="4dea1-163">\# выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="4dea1-163">\# perform cleanup</span></span>

  <span data-ttu-id="4dea1-164">$cachedSessions | Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="4dea1-164">$cachedSessions | Remove-PSSession</span></span>

<span data-ttu-id="4dea1-165">}</span><span class="sxs-lookup"><span data-stu-id="4dea1-165">}</span></span>

<span data-ttu-id="4dea1-166">$ExecutionContext. sessionState. Module. Remove + = $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="4dea1-166">$ExecutionContext.SessionState.Module.OnRemove += $OnRemoveScript</span></span>

<span data-ttu-id="4dea1-167">Для полной согласованности может также быть полезно реагировать на закрытие процесса PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4dea1-167">For full consistency, it might be also useful to react to the closing of the PowerShell process:</span></span>

<span data-ttu-id="4dea1-168">Register-EngineEvent-SourceIdentifier ([System. Management. Automation. Псенгинивент]:: завершение работы) — действие $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="4dea1-168">Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Action $OnRemoveScript</span></span>

## <span data-ttu-id="4dea1-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4dea1-169">RELATED LINKS</span></span>

[<span data-ttu-id="4dea1-170">Get-Module</span><span class="sxs-lookup"><span data-stu-id="4dea1-170">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="4dea1-171">Import-Module</span><span class="sxs-lookup"><span data-stu-id="4dea1-171">Import-Module</span></span>](Import-Module.md)

