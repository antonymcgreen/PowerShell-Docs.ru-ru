---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: 0d0e9701bdc67b2a48fb0f8f25e0ac9269cb74d8
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229994"
---
# <span data-ttu-id="83d1f-103">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-103">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="83d1f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="83d1f-104">SYNOPSIS</span></span>
<span data-ttu-id="83d1f-105">Удаляет зарегистрированные конфигурации сеанса с компьютера.</span><span class="sxs-lookup"><span data-stu-id="83d1f-105">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="83d1f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="83d1f-106">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="83d1f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="83d1f-107">DESCRIPTION</span></span>

<span data-ttu-id="83d1f-108">`Unregister-PSSessionConfiguration`Командлет удаляет зарегистрированные конфигурации сеанса с компьютера.</span><span class="sxs-lookup"><span data-stu-id="83d1f-108">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="83d1f-109">Этот командлет предназначен для системных администраторов, позволяющих управлять настроенными конфигурациями сеансов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="83d1f-109">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="83d1f-110">Чтобы внести изменение в силу, `Unregister-PSSessionConfiguration` перезапустите службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-110">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="83d1f-111">Чтобы предотвратить перезагрузку, укажите параметр **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-111">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="83d1f-112">Если вы случайно удалили конфигурации сеанса **Microsoft. PowerShell** или **Microsoft. PowerShell32** по умолчанию, используйте `Enable-PSRemoting` командлет для их восстановления.</span><span class="sxs-lookup"><span data-stu-id="83d1f-112">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="83d1f-113">Дополнительные сведения см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="83d1f-113">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="83d1f-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="83d1f-114">EXAMPLES</span></span>

### <span data-ttu-id="83d1f-115">Пример 1. Удаление конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="83d1f-115">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="83d1f-116">В этом примере удаляется конфигурация сеанса **MaintenanceShell** с компьютера.</span><span class="sxs-lookup"><span data-stu-id="83d1f-116">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="83d1f-117">Пример 2. Удаление конфигурации сеанса и перезапуск службы WinRM</span><span class="sxs-lookup"><span data-stu-id="83d1f-117">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="83d1f-118">В этом примере мы удалим конфигурацию **MaintenanceShell** и перезапустите службу WinRM.</span><span class="sxs-lookup"><span data-stu-id="83d1f-118">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="83d1f-119">Параметр **Force** подавляет все пользовательские сообщения для перезапуска службы **WinRM** без запроса.</span><span class="sxs-lookup"><span data-stu-id="83d1f-119">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="83d1f-120">Пример 3. Удаление всех конфигураций сеансов</span><span class="sxs-lookup"><span data-stu-id="83d1f-120">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="83d1f-121">В этом примере показаны два способа удаления всех конфигураций сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="83d1f-121">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="83d1f-122">Обе команды имеют одинаковый результат и могут использоваться взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="83d1f-122">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="83d1f-123">Пример 4. Отмена регистрации без перезагрузки</span><span class="sxs-lookup"><span data-stu-id="83d1f-123">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="83d1f-124">В этом примере показан результат использования параметра **NoServiceRestart** для предотвращения перезапуска службы, которая приведет к нарушению сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="83d1f-124">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

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

<span data-ttu-id="83d1f-125">`Unregister-PSSessionConfiguration`Удаляет конфигурацию сеанса **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-125">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="83d1f-126">Однако, поскольку команда использует параметр **NoServiceRestart** , служба **WinRM** не перезапускается и изменение еще не полностью эффективно.</span><span class="sxs-lookup"><span data-stu-id="83d1f-126">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="83d1f-127">Затем `Get-PSSessionConfiguration` попытается получить сеанс **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-127">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="83d1f-128">Поскольку сеанс был удален из таблицы ресурсов WS-Management, `Get-PSSessionConfiguration` он не может вернуть его.</span><span class="sxs-lookup"><span data-stu-id="83d1f-128">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="83d1f-129">`New-PSSession`Командлет создает сеанс, используя конфигурацию **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-129">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="83d1f-130">Команда выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="83d1f-130">The command succeeds.</span></span> <span data-ttu-id="83d1f-131">Затем перезапустите службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-131">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="83d1f-132">Наконец, `New-PSSession` командлет пытается создать сеанс, использующий конфигурацию **MaintenanceShell** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-132">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="83d1f-133">На этот раз сеанс завершается сбоем, так как конфигурация **MaintenanceShell** была удалена при перезапуске службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="83d1f-133">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="83d1f-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="83d1f-134">PARAMETERS</span></span>

### <span data-ttu-id="83d1f-135">-Force</span><span class="sxs-lookup"><span data-stu-id="83d1f-135">-Force</span></span>

<span data-ttu-id="83d1f-136">Указывает, что командлет не запрашивает подтверждение и перезапускает службу **WinRM** без запроса.</span><span class="sxs-lookup"><span data-stu-id="83d1f-136">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="83d1f-137">Перезапуск службы обеспечивает вступление изменений конфигурации в силу.</span><span class="sxs-lookup"><span data-stu-id="83d1f-137">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="83d1f-138">Чтобы предотвратить перезапуск и подавить запрос на перезапуск, используйте параметр **NoServiceRestart** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-138">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="83d1f-139">-Name</span><span class="sxs-lookup"><span data-stu-id="83d1f-139">-Name</span></span>

<span data-ttu-id="83d1f-140">Указывает имена конфигураций сеансов, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="83d1f-140">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="83d1f-141">Введите имя одной конфигурации сеанса или шаблон для отбора имен конфигураций.</span><span class="sxs-lookup"><span data-stu-id="83d1f-141">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="83d1f-142">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="83d1f-142">Wildcard characters are permitted.</span></span> <span data-ttu-id="83d1f-143">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="83d1f-143">This parameter is required.</span></span>

<span data-ttu-id="83d1f-144">Можно также передать конфигурации сеанса в `Unregister-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="83d1f-144">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

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

### <span data-ttu-id="83d1f-145">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="83d1f-145">-NoServiceRestart</span></span>

<span data-ttu-id="83d1f-146">Указывает, что этот командлет не перезапускает службу **WinRM** и подавляет запрос на перезапуск службы.</span><span class="sxs-lookup"><span data-stu-id="83d1f-146">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="83d1f-147">По умолчанию при выполнении `Unregister-PSSessionConfiguration` команды вам будет предложено перезапустить службу **WinRM** , чтобы изменения были эффективны.</span><span class="sxs-lookup"><span data-stu-id="83d1f-147">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="83d1f-148">Пока служба **WinRM** не будет перезапущена, пользователи по-прежнему смогут использовать конфигурацию незарегистрированного сеанса, даже если `Get-PSSessionConfiguration` она не найдена.</span><span class="sxs-lookup"><span data-stu-id="83d1f-148">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="83d1f-149">Чтобы перезапустить службу **WinRM** без запроса, укажите параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-149">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="83d1f-150">Чтобы перезапустить службу **WinRM** вручную, используйте `Restart-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="83d1f-150">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="83d1f-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="83d1f-151">-Confirm</span></span>

<span data-ttu-id="83d1f-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="83d1f-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="83d1f-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="83d1f-153">-WhatIf</span></span>

<span data-ttu-id="83d1f-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="83d1f-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="83d1f-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="83d1f-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="83d1f-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="83d1f-156">CommonParameters</span></span>

<span data-ttu-id="83d1f-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="83d1f-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="83d1f-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="83d1f-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="83d1f-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="83d1f-159">INPUTS</span></span>

### <span data-ttu-id="83d1f-160">Microsoft. PowerShell. Commands. Пссессионконфигуратионкоммандс # PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="83d1f-161">Объект конфигурации сеанса можно передать `Get-PSSessionConfiguration` в командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="83d1f-161">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="83d1f-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="83d1f-162">OUTPUTS</span></span>

### <span data-ttu-id="83d1f-163">Нет</span><span class="sxs-lookup"><span data-stu-id="83d1f-163">None</span></span>

<span data-ttu-id="83d1f-164">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="83d1f-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="83d1f-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="83d1f-165">NOTES</span></span>

<span data-ttu-id="83d1f-166">Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="83d1f-166">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="83d1f-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="83d1f-167">RELATED LINKS</span></span>

[<span data-ttu-id="83d1f-168">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-168">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="83d1f-169">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-169">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="83d1f-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="83d1f-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="83d1f-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="83d1f-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="83d1f-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="83d1f-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="83d1f-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="83d1f-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="83d1f-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="83d1f-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="83d1f-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="83d1f-177">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="83d1f-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="83d1f-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="83d1f-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="83d1f-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="83d1f-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
