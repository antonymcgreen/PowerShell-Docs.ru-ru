---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: c2f88431c0a09a2d4093c6523467a812812c10bc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600690"
---
# <span data-ttu-id="17d08-102">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="17d08-102">Disable-PSSessionConfiguration</span></span>

## <span data-ttu-id="17d08-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="17d08-103">SYNOPSIS</span></span>
<span data-ttu-id="17d08-104">Отключает конфигурации сеансов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="17d08-104">Disables session configurations on the local computer.</span></span>

## <span data-ttu-id="17d08-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="17d08-105">SYNTAX</span></span>

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="17d08-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="17d08-106">DESCRIPTION</span></span>

<span data-ttu-id="17d08-107">`Disable-PSSessionConfiguration`Командлет отключает конфигурации сеансов на локальном компьютере, что запрещает всем пользователям использовать конфигурации сеанса для создания управляемых пользователем сеансов (**PSSession**) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="17d08-107">The `Disable-PSSessionConfiguration` cmdlet disables session configurations on the local computer, which prevents all users from using the session configurations to create a user-managed sessions (**PSSessions**) on the local computer.</span></span> <span data-ttu-id="17d08-108">Этот расширенный командлет предназначен для использования системными администраторами и позволяет управлять конфигурациями сеансов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="17d08-108">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="17d08-109">Начиная с PowerShell 3,0, `Disable-PSSessionConfiguration` командлет устанавливает для параметра **Enabled** в конфигурации сеанса () значение `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` false.</span><span class="sxs-lookup"><span data-stu-id="17d08-109">Starting in PowerShell 3.0, the `Disable-PSSessionConfiguration` cmdlet sets the **Enabled** setting of the session configuration (`WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled`) to False.</span></span>

<span data-ttu-id="17d08-110">В PowerShell 2,0 `Disable-PSSessionConfiguration` командлет добавляет запись **Deny_All** в дескриптор безопасности одной или нескольких зарегистрированных конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="17d08-110">In PowerShell 2.0, the `Disable-PSSessionConfiguration` cmdlet adds a **Deny_All** entry to the security descriptor of one or more registered session configurations.</span></span>

<span data-ttu-id="17d08-111">Без параметров `Disable-PSSessionConfiguration` отключает конфигурацию **Microsoft. PowerShell** — конфигурацию по умолчанию, используемую для сеансов.</span><span class="sxs-lookup"><span data-stu-id="17d08-111">Without parameters, `Disable-PSSessionConfiguration` disables the **Microsoft.PowerShell** configuration, the default configuration used for sessions.</span></span> <span data-ttu-id="17d08-112">Если пользователь не указывает другую конфигурацию, командлет эффективно блокирует создание сеансов подключения к компьютеру локальными и удаленными пользователями.</span><span class="sxs-lookup"><span data-stu-id="17d08-112">Unless the user specifies a different configuration, both local and remote users are effectively prevented from creating any sessions that connect to the computer.</span></span>

<span data-ttu-id="17d08-113">Чтобы отключить все конфигурации сеансов на компьютере, используйте `Disable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="17d08-113">To disable all session configurations on the computer, use `Disable-PSRemoting`.</span></span>

## <span data-ttu-id="17d08-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="17d08-114">EXAMPLES</span></span>

### <span data-ttu-id="17d08-115">Пример 1. Отключение конфигурации по умолчанию</span><span class="sxs-lookup"><span data-stu-id="17d08-115">Example 1: Disable the default configuration</span></span>

<span data-ttu-id="17d08-116">Этот пример отключает конфигурацию сеанса Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17d08-116">This example disables the Microsoft.PowerShell session configuration.</span></span>

```powershell
Disable-PSSessionConfiguration
```

### <span data-ttu-id="17d08-117">Пример 2. Отключение всех конфигураций зарегистрированных сеансов</span><span class="sxs-lookup"><span data-stu-id="17d08-117">Example 2: Disable all registered session configurations</span></span>

<span data-ttu-id="17d08-118">В этом примере отключаются все зарегистрированные конфигурации сеансов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17d08-118">This example disables all registered session configurations on the computer.</span></span>

```powershell
Disable-PSSessionConfiguration -Name *
```

### <span data-ttu-id="17d08-119">Пример 3. Отключение конфигураций сеансов по имени</span><span class="sxs-lookup"><span data-stu-id="17d08-119">Example 3: Disable session configurations by name</span></span>

<span data-ttu-id="17d08-120">В этом примере отключаются все конфигурации сеансов, имена которых начинаются с Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17d08-120">This example disables all session configurations that have names that begin with Microsoft.</span></span> <span data-ttu-id="17d08-121">Параметр **Force** подавляет все запросы пользователя от командлета.</span><span class="sxs-lookup"><span data-stu-id="17d08-121">The **Force** parameter suppresses all user prompts from the cmdlet.</span></span>

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### <span data-ttu-id="17d08-122">Пример 4. Отключение конфигураций сеанса с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="17d08-122">Example 4: Disable session configurations by using the pipeline</span></span>

<span data-ttu-id="17d08-123">В этом примере отключаются конфигурации сеанса **MaintenanceShell** и **AdminShell** .</span><span class="sxs-lookup"><span data-stu-id="17d08-123">This example disables the **MaintenanceShell** and **AdminShell** session configurations.</span></span> <span data-ttu-id="17d08-124">Оператор конвейера (|) отправляет результаты в `Get-PSSessionConfiguration` `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="17d08-124">The pipeline operator (|) sends the results of a `Get-PSSessionConfiguration` to `Disable-PSSessionConfiguration`.</span></span>

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### <span data-ttu-id="17d08-125">Пример 5. последствия отключения конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="17d08-125">Example 5: Effects of disabling a session configuration</span></span>

<span data-ttu-id="17d08-126">В этом примере показаны разрешения до и после выполнения, `Disable-PSSessionConfiguration` а также действия по отключению конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="17d08-126">This example shows the permissions before and after running `Disable-PSSessionConfiguration` and the effect of disabling a session configuration.</span></span>

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
> <span data-ttu-id="17d08-127">Отключение конфигурации не мешает изменить конфигурацию с помощью `Set-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="17d08-127">Disabling the configuration does not prevent you from changing the configuration using the `Set-PSSessionConfiguration` cmdlet.</span></span> <span data-ttu-id="17d08-128">Он только предотвращает использование конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17d08-128">It only prevents use of the configuration.</span></span>

## <span data-ttu-id="17d08-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="17d08-129">PARAMETERS</span></span>

### <span data-ttu-id="17d08-130">-Force</span><span class="sxs-lookup"><span data-stu-id="17d08-130">-Force</span></span>

<span data-ttu-id="17d08-131">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="17d08-131">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="17d08-132">-Name</span><span class="sxs-lookup"><span data-stu-id="17d08-132">-Name</span></span>

<span data-ttu-id="17d08-133">Указывает массив имен конфигураций сеансов для отключения.</span><span class="sxs-lookup"><span data-stu-id="17d08-133">Specifies an array of names of session configurations to disable.</span></span> <span data-ttu-id="17d08-134">Введите одно или несколько имен конфигурации.</span><span class="sxs-lookup"><span data-stu-id="17d08-134">Enter one or more configuration names.</span></span> <span data-ttu-id="17d08-135">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="17d08-135">Wildcard characters are permitted.</span></span> <span data-ttu-id="17d08-136">Можно также передать по конвейеру строку, содержащую имя конфигурации или объект конфигурации сеанса, в `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="17d08-136">You can also pipe a string that contains a configuration name or a session configuration object to `Disable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="17d08-137">Если этот параметр не задан, `Disable-PSSessionConfiguration` отключает конфигурацию сеанса Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17d08-137">If you omit this parameter, `Disable-PSSessionConfiguration` disables the Microsoft.PowerShell session configuration.</span></span>

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

### <span data-ttu-id="17d08-138">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="17d08-138">-NoServiceRestart</span></span>

<span data-ttu-id="17d08-139">Используется для предотвращения перезапуска службы WSMan.</span><span class="sxs-lookup"><span data-stu-id="17d08-139">Used to prevent the restart of the WSMan service.</span></span> <span data-ttu-id="17d08-140">Перезапускать службу для отключения конфигурации не требуется.</span><span class="sxs-lookup"><span data-stu-id="17d08-140">It is not necessary to restart the service to disable the configuration.</span></span>

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

### <span data-ttu-id="17d08-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="17d08-141">-Confirm</span></span>

<span data-ttu-id="17d08-142">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="17d08-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="17d08-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="17d08-143">-WhatIf</span></span>

<span data-ttu-id="17d08-144">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="17d08-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="17d08-145">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="17d08-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="17d08-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="17d08-146">CommonParameters</span></span>

<span data-ttu-id="17d08-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="17d08-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="17d08-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="17d08-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="17d08-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="17d08-149">INPUTS</span></span>

### <span data-ttu-id="17d08-150">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span><span class="sxs-lookup"><span data-stu-id="17d08-150">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="17d08-151">Вы можете передать по конвейеру объект конфигурации сеанса или строку, которая содержит имя конфигурации сеанса в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="17d08-151">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="17d08-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="17d08-152">OUTPUTS</span></span>

### <span data-ttu-id="17d08-153">None</span><span class="sxs-lookup"><span data-stu-id="17d08-153">None</span></span>

<span data-ttu-id="17d08-154">Этот командлет не создает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="17d08-154">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="17d08-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="17d08-155">NOTES</span></span>

<span data-ttu-id="17d08-156">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="17d08-156">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="17d08-157">Для запуска этого командлета необходимо запустить PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="17d08-157">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="17d08-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="17d08-158">RELATED LINKS</span></span>

[<span data-ttu-id="17d08-159">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="17d08-159">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="17d08-160">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="17d08-160">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="17d08-161">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="17d08-161">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="17d08-162">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="17d08-162">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="17d08-163">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="17d08-163">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="17d08-164">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="17d08-164">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="17d08-165">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="17d08-165">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="17d08-166">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="17d08-166">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="17d08-167">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="17d08-167">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="17d08-168">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="17d08-168">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
