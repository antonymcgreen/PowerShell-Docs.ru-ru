---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: c622642a572509e9069fceff2492baf0cc8ea911
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229985"
---
# <span data-ttu-id="4b40c-103">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-103">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="4b40c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b40c-104">SYNOPSIS</span></span>
<span data-ttu-id="4b40c-105">Удаляет зарегистрированные конфигурации сеанса с компьютера.</span><span class="sxs-lookup"><span data-stu-id="4b40c-105">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="4b40c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b40c-106">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="4b40c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b40c-107">DESCRIPTION</span></span>

<span data-ttu-id="4b40c-108">`Unregister-PSSessionConfiguration`Командлет удаляет зарегистрированные конфигурации сеанса с компьютера.</span><span class="sxs-lookup"><span data-stu-id="4b40c-108">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="4b40c-109">Этот командлет предназначен для системных администраторов, позволяющих управлять настроенными конфигурациями сеансов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b40c-109">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="4b40c-110">Чтобы внести изменение в силу, `Unregister-PSSessionConfiguration` перезапустите службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-110">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="4b40c-111">Чтобы предотвратить перезагрузку, укажите параметр **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-111">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="4b40c-112">Если вы случайно удалили конфигурации сеанса **Microsoft. PowerShell** или **Microsoft. PowerShell32** по умолчанию, используйте `Enable-PSRemoting` командлет для их восстановления.</span><span class="sxs-lookup"><span data-stu-id="4b40c-112">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="4b40c-113">Дополнительные сведения см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4b40c-113">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="4b40c-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b40c-114">EXAMPLES</span></span>

### <span data-ttu-id="4b40c-115">Пример 1. Удаление конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="4b40c-115">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="4b40c-116">В этом примере удаляется конфигурация сеанса **MaintenanceShell** с компьютера.</span><span class="sxs-lookup"><span data-stu-id="4b40c-116">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="4b40c-117">Пример 2. Удаление конфигурации сеанса и перезапуск службы WinRM</span><span class="sxs-lookup"><span data-stu-id="4b40c-117">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="4b40c-118">В этом примере мы удалим конфигурацию **MaintenanceShell** и перезапустите службу WinRM.</span><span class="sxs-lookup"><span data-stu-id="4b40c-118">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="4b40c-119">Параметр **Force** подавляет все пользовательские сообщения для перезапуска службы **WinRM** без запроса.</span><span class="sxs-lookup"><span data-stu-id="4b40c-119">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="4b40c-120">Пример 3. Удаление всех конфигураций сеансов</span><span class="sxs-lookup"><span data-stu-id="4b40c-120">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="4b40c-121">В этом примере показаны два способа удаления всех конфигураций сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4b40c-121">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="4b40c-122">Обе команды имеют одинаковый результат и могут использоваться взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="4b40c-122">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="4b40c-123">Пример 4. Отмена регистрации без перезагрузки</span><span class="sxs-lookup"><span data-stu-id="4b40c-123">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="4b40c-124">В этом примере показан результат использования параметра **NoServiceRestart** для предотвращения перезапуска службы, которая приведет к нарушению сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4b40c-124">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="4b40c-125">`Unregister-PSSessionConfiguration`Удаляет конфигурацию сеанса **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-125">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="4b40c-126">Однако, поскольку команда использует параметр **NoServiceRestart** , служба **WinRM** не перезапускается и изменение еще не полностью эффективно.</span><span class="sxs-lookup"><span data-stu-id="4b40c-126">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="4b40c-127">Затем `Get-PSSessionConfiguration` попытается получить сеанс **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-127">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="4b40c-128">Поскольку сеанс был удален из таблицы ресурсов WS-Management, `Get-PSSessionConfiguration` он не может вернуть его.</span><span class="sxs-lookup"><span data-stu-id="4b40c-128">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="4b40c-129">`New-PSSession`Командлет создает сеанс, используя конфигурацию **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-129">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="4b40c-130">Команда выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="4b40c-130">The command succeeds.</span></span> <span data-ttu-id="4b40c-131">Затем перезапустите службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-131">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="4b40c-132">Наконец, `New-PSSession` командлет пытается создать сеанс, использующий конфигурацию **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-132">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="4b40c-133">На этот раз сеанс завершается сбоем, так как конфигурация **MaintenanceShell** была удалена при перезапуске службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="4b40c-133">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="4b40c-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b40c-134">PARAMETERS</span></span>

### <span data-ttu-id="4b40c-135">-Force</span><span class="sxs-lookup"><span data-stu-id="4b40c-135">-Force</span></span>

<span data-ttu-id="4b40c-136">Указывает, что командлет не запрашивает подтверждение и перезапускает службу **WinRM** без запроса.</span><span class="sxs-lookup"><span data-stu-id="4b40c-136">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="4b40c-137">Перезапуск службы обеспечивает вступление изменений конфигурации в силу.</span><span class="sxs-lookup"><span data-stu-id="4b40c-137">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="4b40c-138">Чтобы предотвратить перезапуск и подавить запрос на перезапуск, используйте параметр **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-138">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="4b40c-139">-Name</span><span class="sxs-lookup"><span data-stu-id="4b40c-139">-Name</span></span>

<span data-ttu-id="4b40c-140">Указывает имена конфигураций сеансов, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="4b40c-140">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="4b40c-141">Введите имя одной конфигурации сеанса или шаблон для отбора имен конфигураций.</span><span class="sxs-lookup"><span data-stu-id="4b40c-141">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="4b40c-142">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4b40c-142">Wildcard characters are permitted.</span></span> <span data-ttu-id="4b40c-143">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="4b40c-143">This parameter is required.</span></span>

<span data-ttu-id="4b40c-144">Можно также передать конфигурации сеанса в `Unregister-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="4b40c-144">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="4b40c-145">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="4b40c-145">-NoServiceRestart</span></span>

<span data-ttu-id="4b40c-146">Указывает, что этот командлет не перезапускает службу **WinRM** и подавляет запрос на перезапуск службы.</span><span class="sxs-lookup"><span data-stu-id="4b40c-146">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="4b40c-147">По умолчанию при выполнении `Unregister-PSSessionConfiguration` команды вам будет предложено перезапустить службу **WinRM** , чтобы изменения были эффективны.</span><span class="sxs-lookup"><span data-stu-id="4b40c-147">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="4b40c-148">Пока служба **WinRM** не будет перезапущена, пользователи по-прежнему смогут использовать конфигурацию незарегистрированного сеанса, даже если `Get-PSSessionConfiguration` она не найдена.</span><span class="sxs-lookup"><span data-stu-id="4b40c-148">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="4b40c-149">Чтобы перезапустить службу **WinRM** без запроса, укажите параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-149">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="4b40c-150">Чтобы перезапустить службу **WinRM** вручную, используйте `Restart-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="4b40c-150">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="4b40c-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4b40c-151">-Confirm</span></span>

<span data-ttu-id="4b40c-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="4b40c-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4b40c-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4b40c-153">-WhatIf</span></span>

<span data-ttu-id="4b40c-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="4b40c-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4b40c-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4b40c-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4b40c-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4b40c-156">CommonParameters</span></span>

<span data-ttu-id="4b40c-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b40c-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b40c-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b40c-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b40c-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4b40c-159">INPUTS</span></span>

### <span data-ttu-id="4b40c-160">Microsoft. PowerShell. Commands. Пссессионконфигуратионкоммандс # PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="4b40c-161">Объект конфигурации сеанса можно передать `Get-PSSessionConfiguration` в командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4b40c-161">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="4b40c-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4b40c-162">OUTPUTS</span></span>

### <span data-ttu-id="4b40c-163">Нет</span><span class="sxs-lookup"><span data-stu-id="4b40c-163">None</span></span>

<span data-ttu-id="4b40c-164">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="4b40c-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="4b40c-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4b40c-165">NOTES</span></span>

<span data-ttu-id="4b40c-166">Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="4b40c-166">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="4b40c-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4b40c-167">RELATED LINKS</span></span>

[<span data-ttu-id="4b40c-168">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-168">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="4b40c-169">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-169">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="4b40c-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="4b40c-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="4b40c-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="4b40c-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="4b40c-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="4b40c-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="4b40c-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="4b40c-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="4b40c-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="4b40c-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b40c-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="4b40c-177">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="4b40c-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="4b40c-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="4b40c-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="4b40c-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="4b40c-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
