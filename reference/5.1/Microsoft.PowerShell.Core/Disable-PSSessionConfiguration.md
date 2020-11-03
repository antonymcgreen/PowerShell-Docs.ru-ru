---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 978f42174d211d1ceaf7a19d4a348e1bbcaa270b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226718"
---
# <span data-ttu-id="c457e-103">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c457e-103">Disable-PSSessionConfiguration</span></span>

## <span data-ttu-id="c457e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c457e-104">SYNOPSIS</span></span>
<span data-ttu-id="c457e-105">Отключает конфигурации сеансов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c457e-105">Disables session configurations on the local computer.</span></span>

## <span data-ttu-id="c457e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c457e-106">SYNTAX</span></span>

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="c457e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c457e-107">DESCRIPTION</span></span>

<span data-ttu-id="c457e-108">`Disable-PSSessionConfiguration`Командлет отключает конфигурации сеансов на локальном компьютере, что запрещает всем пользователям использовать конфигурации сеанса для создания управляемых пользователем сеансов ( **PSSession** ) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c457e-108">The `Disable-PSSessionConfiguration` cmdlet disables session configurations on the local computer, which prevents all users from using the session configurations to create a user-managed sessions ( **PSSessions** ) on the local computer.</span></span> <span data-ttu-id="c457e-109">Этот расширенный командлет предназначен для использования системными администраторами и позволяет управлять конфигурациями сеансов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="c457e-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="c457e-110">Начиная с PowerShell 3,0, `Disable-PSSessionConfiguration` командлет устанавливает для параметра **Enabled** в конфигурации сеанса () значение `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` false.</span><span class="sxs-lookup"><span data-stu-id="c457e-110">Starting in PowerShell 3.0, the `Disable-PSSessionConfiguration` cmdlet sets the **Enabled** setting of the session configuration (`WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled`) to False.</span></span>

<span data-ttu-id="c457e-111">В PowerShell 2,0 `Disable-PSSessionConfiguration` командлет добавляет запись **Deny_All** в дескриптор безопасности одной или нескольких зарегистрированных конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="c457e-111">In PowerShell 2.0, the `Disable-PSSessionConfiguration` cmdlet adds a **Deny_All** entry to the security descriptor of one or more registered session configurations.</span></span>

<span data-ttu-id="c457e-112">Без параметров `Disable-PSSessionConfiguration` отключает конфигурацию **Microsoft. PowerShell** — конфигурацию по умолчанию, используемую для сеансов.</span><span class="sxs-lookup"><span data-stu-id="c457e-112">Without parameters, `Disable-PSSessionConfiguration` disables the **Microsoft.PowerShell** configuration, the default configuration used for sessions.</span></span> <span data-ttu-id="c457e-113">Если пользователь не указывает другую конфигурацию, командлет эффективно блокирует создание сеансов подключения к компьютеру локальными и удаленными пользователями.</span><span class="sxs-lookup"><span data-stu-id="c457e-113">Unless the user specifies a different configuration, both local and remote users are effectively prevented from creating any sessions that connect to the computer.</span></span>

<span data-ttu-id="c457e-114">Чтобы отключить все конфигурации сеансов на компьютере, используйте `Disable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="c457e-114">To disable all session configurations on the computer, use `Disable-PSRemoting`.</span></span>

## <span data-ttu-id="c457e-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="c457e-115">EXAMPLES</span></span>

### <span data-ttu-id="c457e-116">Пример 1. Отключение конфигурации по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c457e-116">Example 1: Disable the default configuration</span></span>

<span data-ttu-id="c457e-117">Этот пример отключает конфигурацию сеанса Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c457e-117">This example disables the Microsoft.PowerShell session configuration.</span></span>

```powershell
Disable-PSSessionConfiguration
```

### <span data-ttu-id="c457e-118">Пример 2. Отключение всех конфигураций зарегистрированных сеансов</span><span class="sxs-lookup"><span data-stu-id="c457e-118">Example 2: Disable all registered session configurations</span></span>

<span data-ttu-id="c457e-119">В этом примере отключаются все зарегистрированные конфигурации сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c457e-119">This example disables all registered session configurations on the computer.</span></span>

```powershell
Disable-PSSessionConfiguration -Name *
```

### <span data-ttu-id="c457e-120">Пример 3. Отключение конфигураций сеансов по имени</span><span class="sxs-lookup"><span data-stu-id="c457e-120">Example 3: Disable session configurations by name</span></span>

<span data-ttu-id="c457e-121">В этом примере отключаются все конфигурации сеансов, имена которых начинаются с Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c457e-121">This example disables all session configurations that have names that begin with Microsoft.</span></span> <span data-ttu-id="c457e-122">Параметр **Force** подавляет все запросы пользователя от командлета.</span><span class="sxs-lookup"><span data-stu-id="c457e-122">The **Force** parameter suppresses all user prompts from the cmdlet.</span></span>

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### <span data-ttu-id="c457e-123">Пример 4. Отключение конфигураций сеанса с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="c457e-123">Example 4: Disable session configurations by using the pipeline</span></span>

<span data-ttu-id="c457e-124">В этом примере отключаются конфигурации сеанса **MaintenanceShell** и **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="c457e-124">This example disables the **MaintenanceShell** and **AdminShell** session configurations.</span></span> <span data-ttu-id="c457e-125">Оператор конвейера (|) отправляет результаты в `Get-PSSessionConfiguration` `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="c457e-125">The pipeline operator (|) sends the results of a `Get-PSSessionConfiguration` to `Disable-PSSessionConfiguration`.</span></span>

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### <span data-ttu-id="c457e-126">Пример 5. последствия отключения конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="c457e-126">Example 5: Effects of disabling a session configuration</span></span>

<span data-ttu-id="c457e-127">В этом примере показаны разрешения до и после выполнения, `Disable-PSSessionConfiguration` а также действия по отключению конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c457e-127">This example shows the permissions before and after running `Disable-PSSessionConfiguration` and the effect of disabling a session configuration.</span></span>

```
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> Disable-PSSessionConfiguration -Name MaintenanceShell -Force
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       Everyone AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> New-PSSession -ComputerName localhost -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message : Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

> [!NOTE]
> <span data-ttu-id="c457e-128">Отключение конфигурации не мешает изменить конфигурацию с помощью `Set-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="c457e-128">Disabling the configuration does not prevent you from changing the configuration using the `Set-PSSessionConfiguration` cmdlet.</span></span> <span data-ttu-id="c457e-129">Он только предотвращает использование конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c457e-129">It only prevents use of the configuration.</span></span>

## <span data-ttu-id="c457e-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c457e-130">PARAMETERS</span></span>

### <span data-ttu-id="c457e-131">-Force</span><span class="sxs-lookup"><span data-stu-id="c457e-131">-Force</span></span>

<span data-ttu-id="c457e-132">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="c457e-132">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c457e-133">-Name</span><span class="sxs-lookup"><span data-stu-id="c457e-133">-Name</span></span>

<span data-ttu-id="c457e-134">Указывает массив имен конфигураций сеансов для отключения.</span><span class="sxs-lookup"><span data-stu-id="c457e-134">Specifies an array of names of session configurations to disable.</span></span> <span data-ttu-id="c457e-135">Введите одно или несколько имен конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c457e-135">Enter one or more configuration names.</span></span> <span data-ttu-id="c457e-136">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c457e-136">Wildcard characters are permitted.</span></span> <span data-ttu-id="c457e-137">Можно также передать по конвейеру строку, содержащую имя конфигурации или объект конфигурации сеанса, в `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="c457e-137">You can also pipe a string that contains a configuration name or a session configuration object to `Disable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="c457e-138">Если этот параметр не задан, `Disable-PSSessionConfiguration` отключает конфигурацию сеанса Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c457e-138">If you omit this parameter, `Disable-PSSessionConfiguration` disables the Microsoft.PowerShell session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c457e-139">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="c457e-139">-NoServiceRestart</span></span>

<span data-ttu-id="c457e-140">Используется для предотвращения перезапуска службы WSMan.</span><span class="sxs-lookup"><span data-stu-id="c457e-140">Used to prevent the restart of the WSMan service.</span></span> <span data-ttu-id="c457e-141">Перезапускать службу для отключения конфигурации не требуется.</span><span class="sxs-lookup"><span data-stu-id="c457e-141">It is not necessary to restart the service to disable the configuration.</span></span>

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

### <span data-ttu-id="c457e-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c457e-142">-Confirm</span></span>

<span data-ttu-id="c457e-143">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c457e-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c457e-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c457e-144">-WhatIf</span></span>

<span data-ttu-id="c457e-145">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c457e-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c457e-146">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c457e-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c457e-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c457e-147">CommonParameters</span></span>

<span data-ttu-id="c457e-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c457e-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c457e-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c457e-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c457e-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c457e-150">INPUTS</span></span>

### <span data-ttu-id="c457e-151">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span><span class="sxs-lookup"><span data-stu-id="c457e-151">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="c457e-152">Вы можете передать по конвейеру объект конфигурации сеанса или строку, которая содержит имя конфигурации сеанса в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="c457e-152">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="c457e-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c457e-153">OUTPUTS</span></span>

### <span data-ttu-id="c457e-154">Нет</span><span class="sxs-lookup"><span data-stu-id="c457e-154">None</span></span>

<span data-ttu-id="c457e-155">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="c457e-155">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="c457e-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c457e-156">NOTES</span></span>

<span data-ttu-id="c457e-157">Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="c457e-157">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="c457e-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c457e-158">RELATED LINKS</span></span>

[<span data-ttu-id="c457e-159">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c457e-159">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="c457e-160">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c457e-160">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="c457e-161">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="c457e-161">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="c457e-162">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c457e-162">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="c457e-163">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c457e-163">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="c457e-164">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="c457e-164">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="c457e-165">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c457e-165">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="c457e-166">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="c457e-166">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="c457e-167">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="c457e-167">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="c457e-168">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="c457e-168">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
