---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSSessionConfiguration
ms.openlocfilehash: 86650f33f376ccb7d1428836c9d0070e749cf0ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604647"
---
# <span data-ttu-id="9f66f-102">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f66f-102">Enable-PSSessionConfiguration</span></span>

## <span data-ttu-id="9f66f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9f66f-103">SYNOPSIS</span></span>
<span data-ttu-id="9f66f-104">Включает конфигурации сеанса на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f66f-104">Enables the session configurations on the local computer.</span></span>

## <span data-ttu-id="9f66f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f66f-105">SYNTAX</span></span>

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9f66f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f66f-106">DESCRIPTION</span></span>

<span data-ttu-id="9f66f-107">`Enable-PSSessionConfiguration`Командлет активирует зарегистрированные конфигурации сеансов, которые были отключены, например с помощью `Disable-PSSessionConfiguration` `Disable-PSRemoting` командлетов или или параметра **AccessMode** `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="9f66f-107">The `Enable-PSSessionConfiguration` cmdlet enables registered session configurations that have been disabled, such as by using the `Disable-PSSessionConfiguration` or `Disable-PSRemoting` cmdlets, or the **AccessMode** parameter of `Register-PSSessionConfiguration`.</span></span> <span data-ttu-id="9f66f-108">Этот расширенный командлет предназначен для использования системными администраторами и позволяет управлять конфигурациями сеансов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9f66f-108">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="9f66f-109">Без параметров `Enable-PSSessionConfiguration` включает конфигурацию **Microsoft. PowerShell** , которая является конфигурацией по умолчанию, используемой для сеансов.</span><span class="sxs-lookup"><span data-stu-id="9f66f-109">Without parameters, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** configuration, which is the default configuration that is used for sessions.</span></span>

<span data-ttu-id="9f66f-110">`Enable-PSSessionConfiguration` Удаляет параметр **Deny_All** из дескриптора безопасности затронутых конфигураций сеанса, включает прослушиватель, который принимает запросы по любому IP-адресу, и перезапускает службу WinRM.</span><span class="sxs-lookup"><span data-stu-id="9f66f-110">`Enable-PSSessionConfiguration` removes the **Deny_All** setting from the security descriptor of the affected session configurations, turns on the listener that accepts requests on any IP address, and restarts the WinRM service.</span></span> <span data-ttu-id="9f66f-111">Начиная с PowerShell 3,0, `Enable-PSSessionConfiguration` также устанавливает значение true для свойства **Enabled** конфигурации сеанса ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ).</span><span class="sxs-lookup"><span data-stu-id="9f66f-111">Beginning in PowerShell 3.0, `Enable-PSSessionConfiguration` also sets the value of the **Enabled** property of the session configuration (`WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled`) to True.</span></span> <span data-ttu-id="9f66f-112">Однако не `Enable-PSSessionConfiguration` удаляет или не изменяет  `AccessMode=Local` параметр дескриптора безопасности Network_Deny_All (), который позволяет использовать в конфигурации сеанса только пользователи локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="9f66f-112">However, `Enable-PSSessionConfiguration` does not remove or change the **Network_Deny_All** (`AccessMode=Local`) security descriptor setting that allows only users of the local computer to use to the session configuration.</span></span>

## <span data-ttu-id="9f66f-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="9f66f-113">EXAMPLES</span></span>

### <span data-ttu-id="9f66f-114">Пример 1. Повторное включение сеанса по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9f66f-114">Example 1: Re-enable the default session</span></span>

<span data-ttu-id="9f66f-115">В этом примере повторно включается конфигурация сеанса **Microsoft. PowerShell** по умолчанию на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f66f-115">This example re-enables the **Microsoft.PowerShell** default session configuration on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration
```

### <span data-ttu-id="9f66f-116">Пример 2. Повторное включение указанных сеансов</span><span class="sxs-lookup"><span data-stu-id="9f66f-116">Example 2: Re-enable specified sessions</span></span>

<span data-ttu-id="9f66f-117">В этом примере повторно включаются конфигурации сеанса **MaintenanceShell** и **AdminShell** на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f66f-117">This example re-enables the **MaintenanceShell** and **AdminShell** session configurations on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### <span data-ttu-id="9f66f-118">Пример 3. Повторное включение всех сеансов</span><span class="sxs-lookup"><span data-stu-id="9f66f-118">Example 3: Re-enable the all sessions</span></span>

<span data-ttu-id="9f66f-119">В этом примере повторно включаются все конфигурации сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f66f-119">This example re-enables all session configurations on the computer.</span></span> <span data-ttu-id="9f66f-120">Эти команды эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="9f66f-120">These commands are equivalent.</span></span>
<span data-ttu-id="9f66f-121">Таким образом, можно использовать любую из них.</span><span class="sxs-lookup"><span data-stu-id="9f66f-121">Therefore, you can use either.</span></span>

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

<span data-ttu-id="9f66f-122">`Enable-PSSessionConfiguration` не создает ошибку, если включена конфигурация сеанса, которая уже включена.</span><span class="sxs-lookup"><span data-stu-id="9f66f-122">`Enable-PSSessionConfiguration` does not generate an error if you enable a session configuration that is already enabled.</span></span>

### <span data-ttu-id="9f66f-123">Пример 4. Повторное включение сеанса и указание нового дескриптора безопасности</span><span class="sxs-lookup"><span data-stu-id="9f66f-123">Example 4: Re-enable a session and specify a new security descriptor</span></span>

<span data-ttu-id="9f66f-124">В этом примере повторно включается конфигурация сеанса **MaintenanceShell** и указывается новый дескриптор безопасности для конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9f66f-124">This example re-enables the **MaintenanceShell** session configuration and specifies a new security descriptor for the configuration.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## <span data-ttu-id="9f66f-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f66f-125">PARAMETERS</span></span>

### <span data-ttu-id="9f66f-126">-Force</span><span class="sxs-lookup"><span data-stu-id="9f66f-126">-Force</span></span>

<span data-ttu-id="9f66f-127">Указывает, что командлет не запрашивает подтверждение и перезапускает службу WinRM без запроса.</span><span class="sxs-lookup"><span data-stu-id="9f66f-127">Indicates that the cmdlet does not prompt you for confirmation, and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="9f66f-128">Перезапуск службы обеспечивает вступление изменений конфигурации в силу.</span><span class="sxs-lookup"><span data-stu-id="9f66f-128">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="9f66f-129">Чтобы предотвратить перезапуск и подавить запрос на перезапуск, используйте параметр **NoServiceRestart**.</span><span class="sxs-lookup"><span data-stu-id="9f66f-129">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="9f66f-130">-Name</span><span class="sxs-lookup"><span data-stu-id="9f66f-130">-Name</span></span>

<span data-ttu-id="9f66f-131">Указывает включаемые имена конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="9f66f-131">Specifies the names of session configurations to enable.</span></span> <span data-ttu-id="9f66f-132">Введите одно или несколько имен конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9f66f-132">Enter one or more configuration names.</span></span>
<span data-ttu-id="9f66f-133">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9f66f-133">Wildcard characters are permitted.</span></span>

<span data-ttu-id="9f66f-134">Можно также передать по конвейеру строку, содержащую имя конфигурации или объект конфигурации сеанса, в `Enable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="9f66f-134">You can also pipe a string that contains a configuration name or a session configuration object to `Enable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="9f66f-135">Если этот параметр не задан, `Enable-PSSessionConfiguration` включается Настройка сеанса **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="9f66f-135">If you omit this parameter, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** session configuration.</span></span>

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

### <span data-ttu-id="9f66f-136">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="9f66f-136">-NoServiceRestart</span></span>

<span data-ttu-id="9f66f-137">Указывает, что командлет не перезапускает службу.</span><span class="sxs-lookup"><span data-stu-id="9f66f-137">Indicates that the cmdlet does not restart the service.</span></span>

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

### <span data-ttu-id="9f66f-138">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="9f66f-138">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="9f66f-139">Указывает дескриптор безопасности, на который этот командлет заменяет дескриптор безопасности в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="9f66f-139">Specifies a security descriptor with which this cmdlet replaces the security descriptor on the session configuration.</span></span>

<span data-ttu-id="9f66f-140">Если опустить этот параметр, `Enable-PSSessionConfiguration` удаляется только элемент Deny All из дескриптора безопасности.</span><span class="sxs-lookup"><span data-stu-id="9f66f-140">If you omit this parameter, `Enable-PSSessionConfiguration` only deletes the deny all item from the security descriptor.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9f66f-141">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="9f66f-141">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="9f66f-142">Указывает, что этот командлет включает конфигурацию сеанса, если компьютер находится в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="9f66f-142">Indicates that this cmdlet enables the session configuration when the computer is on a public network.</span></span> <span data-ttu-id="9f66f-143">Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="9f66f-143">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="9f66f-144">По умолчанию `Enable-PSSessionConfiguration` не работает в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="9f66f-144">By default, `Enable-PSSessionConfiguration` fails on a public network.</span></span>

<span data-ttu-id="9f66f-145">Этот параметр предназначен для клиентских версий операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="9f66f-145">This parameter is designed for client versions of the Windows operating system.</span></span> <span data-ttu-id="9f66f-146">Серверные версии операционной системы Windows имеют правило брандмауэра локальной подсети для общедоступных сетей.</span><span class="sxs-lookup"><span data-stu-id="9f66f-146">Server versions of the Windows operating system have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="9f66f-147">Но если правило брандмауэра локальной подсети отключено в серверной версии операционной системы Windows, этот параметр повторно включает его.</span><span class="sxs-lookup"><span data-stu-id="9f66f-147">However, if the local subnet firewall rule is disabled on a server version of the Windows operating system, this parameter re-enables it.</span></span>

<span data-ttu-id="9f66f-148">Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="9f66f-148">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="9f66f-149">Для получения дополнительной информации см. `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="9f66f-149">For more information, see `Enable-PSRemoting`.</span></span>

<span data-ttu-id="9f66f-150">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9f66f-150">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9f66f-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f66f-151">-Confirm</span></span>

<span data-ttu-id="9f66f-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9f66f-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9f66f-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f66f-153">-WhatIf</span></span>

<span data-ttu-id="9f66f-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9f66f-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9f66f-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9f66f-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9f66f-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9f66f-156">CommonParameters</span></span>

<span data-ttu-id="9f66f-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f66f-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f66f-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f66f-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f66f-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9f66f-159">INPUTS</span></span>

### <span data-ttu-id="9f66f-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span><span class="sxs-lookup"><span data-stu-id="9f66f-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="9f66f-161">Вы можете передать по конвейеру объект конфигурации сеанса или строку, которая содержит имя конфигурации сеанса в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="9f66f-161">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="9f66f-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9f66f-162">OUTPUTS</span></span>

### <span data-ttu-id="9f66f-163">None</span><span class="sxs-lookup"><span data-stu-id="9f66f-163">None</span></span>

<span data-ttu-id="9f66f-164">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="9f66f-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="9f66f-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9f66f-165">NOTES</span></span>

<span data-ttu-id="9f66f-166">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="9f66f-166">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="9f66f-167">Чтобы использовать этот командлет, необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="9f66f-167">To use this cmdlet, you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="9f66f-168">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9f66f-168">RELATED LINKS</span></span>

[<span data-ttu-id="9f66f-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f66f-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="9f66f-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f66f-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="9f66f-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="9f66f-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="9f66f-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="9f66f-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="9f66f-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f66f-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="9f66f-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f66f-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="9f66f-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="9f66f-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="9f66f-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f66f-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="9f66f-177">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="9f66f-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="9f66f-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="9f66f-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="9f66f-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="9f66f-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
