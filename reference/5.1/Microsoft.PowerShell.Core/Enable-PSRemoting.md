---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "93229685"
---
# <span data-ttu-id="90d59-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="90d59-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="90d59-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="90d59-104">SYNOPSIS</span></span>
<span data-ttu-id="90d59-105">Настраивает прием удаленных команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="90d59-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="90d59-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90d59-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="90d59-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="90d59-107">DESCRIPTION</span></span>

<span data-ttu-id="90d59-108">`Enable-PSRemoting`Командлет настраивает компьютер для получения удаленных команд PowerShell, отправляемых с помощью технологии WS-Management.</span><span class="sxs-lookup"><span data-stu-id="90d59-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span>

<span data-ttu-id="90d59-109">Удаленное взаимодействие PowerShell включено по умолчанию в Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="90d59-109">PowerShell remoting is enabled by default on Windows Server 2012.</span></span> <span data-ttu-id="90d59-110">С помощью можно `Enable-PSRemoting` включить удаленное взаимодействие PowerShell в других поддерживаемых версиях Windows и повторно включить удаленное взаимодействие на Windows Server 2012, если оно будет отключено.</span><span class="sxs-lookup"><span data-stu-id="90d59-110">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting on Windows Server 2012 if it becomes disabled.</span></span>

<span data-ttu-id="90d59-111">Эту команду необходимо выполнить только один раз на каждом компьютере, который будет принимать команды.</span><span class="sxs-lookup"><span data-stu-id="90d59-111">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="90d59-112">Ее не нужно выполнять на компьютерах, которые только отправляют команды.</span><span class="sxs-lookup"><span data-stu-id="90d59-112">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="90d59-113">Так как в такой конфигурации запускаются прослушиватели, мы рекомендуем использовать ее только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="90d59-113">Because the configuration starts listeners, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="90d59-114">Начиная с PowerShell 3,0, `Enable-PSRemoting` командлет может включить удаленное взаимодействие PowerShell для клиентских версий Windows, когда компьютер находится в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="90d59-114">Beginning in PowerShell 3.0, the `Enable-PSRemoting` cmdlet can enable PowerShell remoting on client versions of Windows when the computer is on a public network.</span></span> <span data-ttu-id="90d59-115">Подробнее см. в описании параметра **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="90d59-115">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="90d59-116">`Enable-PSRemoting`Командлет выполняет следующие операции:</span><span class="sxs-lookup"><span data-stu-id="90d59-116">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="90d59-117">Выполняет командлет [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , который выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="90d59-117">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="90d59-118">Запускает службу WinRM.</span><span class="sxs-lookup"><span data-stu-id="90d59-118">Starts the WinRM service.</span></span>
  - <span data-ttu-id="90d59-119">Задает автоматический тип запуска службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="90d59-119">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="90d59-120">Создает прослушиватель для приема запросов по любому IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="90d59-120">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="90d59-121">Включает исключение брандмауэра для WS-Management связи.</span><span class="sxs-lookup"><span data-stu-id="90d59-121">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="90d59-122">Регистрирует конфигурации сеанса **Microsoft. PowerShell** и **Microsoft. PowerShell. Workflow** , если они еще не зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="90d59-122">Registers the **Microsoft.PowerShell** and **Microsoft.PowerShell.Workflow** session configurations, if it they are not already registered.</span></span>
  - <span data-ttu-id="90d59-123">Регистрирует конфигурацию сеанса **Microsoft. PowerShell32** на 64-разрядных компьютерах, если она еще не зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="90d59-123">Registers the **Microsoft.PowerShell32** session configuration on 64-bit computers, if it is not already registered.</span></span>
  - <span data-ttu-id="90d59-124">Включает все конфигурации сеансов.</span><span class="sxs-lookup"><span data-stu-id="90d59-124">Enables all session configurations.</span></span>
  - <span data-ttu-id="90d59-125">Изменяет дескриптор безопасности всех конфигураций сеансов, чтобы разрешить удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="90d59-125">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="90d59-126">Перезапускает службу WinRM, чтобы внести предыдущие изменения в силу.</span><span class="sxs-lookup"><span data-stu-id="90d59-126">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="90d59-127">Чтобы запустить этот командлет на платформе Windows, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="90d59-127">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="90d59-128">Это не относится к версиям PowerShell для Linux и MacOS.</span><span class="sxs-lookup"><span data-stu-id="90d59-128">This does not apply to Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="90d59-129">В системах, где есть PowerShell 3,0 и PowerShell 2,0, не используйте PowerShell 2,0 для запуска `Enable-PSRemoting` `Disable-PSRemoting` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="90d59-129">On systems that have both PowerShell 3.0 and PowerShell 2.0, do not use PowerShell 2.0 to run the `Enable-PSRemoting` and `Disable-PSRemoting` cmdlets.</span></span> <span data-ttu-id="90d59-130">Команды могут казаться выполненными успешно, но удаленный доступ будет настроен неправильно.</span><span class="sxs-lookup"><span data-stu-id="90d59-130">The commands might appear to succeed, but the remoting is not configured correctly.</span></span> <span data-ttu-id="90d59-131">Удаленные команды и последующие попытки включить или отключить удаленный доступ, скорее всего, будут завершаться сбоем.</span><span class="sxs-lookup"><span data-stu-id="90d59-131">Remote commands and later attempts to enable and disable remoting, are likely to fail.</span></span>

## <span data-ttu-id="90d59-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="90d59-132">EXAMPLES</span></span>

### <span data-ttu-id="90d59-133">Пример 1. Настройка приема удаленных команд на компьютере</span><span class="sxs-lookup"><span data-stu-id="90d59-133">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="90d59-134">Эта команда настраивает прием удаленных команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="90d59-134">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

### <span data-ttu-id="90d59-135">Пример 2. Настройка приема удаленных команд без запроса подтверждения на компьютере</span><span class="sxs-lookup"><span data-stu-id="90d59-135">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="90d59-136">Эта команда настраивает прием удаленных команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="90d59-136">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="90d59-137">Параметр **Force** подавляет запросы пользователя.</span><span class="sxs-lookup"><span data-stu-id="90d59-137">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

### <span data-ttu-id="90d59-138">Пример 3. Разрешение удаленного доступа для клиентов</span><span class="sxs-lookup"><span data-stu-id="90d59-138">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="90d59-139">В этом примере показано, как разрешить удаленный доступ из общедоступных сетей в клиентских версиях ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="90d59-139">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="90d59-140">Имя правила брандмауэра может отличаться для разных версий Windows.</span><span class="sxs-lookup"><span data-stu-id="90d59-140">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="90d59-141">Используйте `Get-NetFirewallRule` для просмотра списка правил.</span><span class="sxs-lookup"><span data-stu-id="90d59-141">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="90d59-142">Перед включением правила брандмауэра просмотрите параметры безопасности в правиле, чтобы убедиться, что конфигурация подходит для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="90d59-142">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

<span data-ttu-id="90d59-143">По умолчанию `Enable-PSRemoting` создает правила сети, разрешающие удаленный доступ из частных и доменных сетей.</span><span class="sxs-lookup"><span data-stu-id="90d59-143">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="90d59-144">В команде используется параметр **SkipNetworkProfileCheck** для разрешения удаленного доступа из общедоступных сетей в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="90d59-144">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="90d59-145">В команде указывается параметр **Force** , блокирующий вывод запросов подтверждения.</span><span class="sxs-lookup"><span data-stu-id="90d59-145">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="90d59-146">Параметр **SkipNetworkProfileCheck** не влияет на серверные версии операционной системы Windows, которые по умолчанию разрешают удаленный доступ из общедоступных сетей в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="90d59-146">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="90d59-147">`Set-NetFirewallRule`Командлет в модуле **NetSecurity** добавляет правило брандмауэра, которое разрешает удаленный доступ из общедоступных сетей из любого удаленного расположения.</span><span class="sxs-lookup"><span data-stu-id="90d59-147">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="90d59-148">включая расположения в других подсетях.</span><span class="sxs-lookup"><span data-stu-id="90d59-148">This includes locations in different subnets.</span></span>

> [!NOTE]
> <span data-ttu-id="90d59-149">Имя правила брандмауэра может отличаться в зависимости от версии Windows.</span><span class="sxs-lookup"><span data-stu-id="90d59-149">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="90d59-150">Используйте `Get-NetFirewallRule` командлет, чтобы вывести список имен правил в системе.</span><span class="sxs-lookup"><span data-stu-id="90d59-150">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="90d59-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90d59-151">PARAMETERS</span></span>

### <span data-ttu-id="90d59-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="90d59-152">-Confirm</span></span>

<span data-ttu-id="90d59-153">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="90d59-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="90d59-154">-Force</span><span class="sxs-lookup"><span data-stu-id="90d59-154">-Force</span></span>

<span data-ttu-id="90d59-155">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="90d59-155">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="90d59-156">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="90d59-156">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="90d59-157">Указывает, что этот командлет включает удаленное взаимодействие в клиентских версиях ОС Windows, если компьютер находится в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="90d59-157">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="90d59-158">Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="90d59-158">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="90d59-159">Этот параметр не оказывает влияния на серверные версии ОС Windows, в которых для общедоступных сетей по умолчанию задано правило брандмауэра локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="90d59-159">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="90d59-160">Если правило брандмауэра локальной подсети отключено на версии сервера, `Enable-PSRemoting` повторно включает его, независимо от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="90d59-160">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="90d59-161">Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="90d59-161">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="90d59-162">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="90d59-162">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="90d59-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="90d59-163">-WhatIf</span></span>

<span data-ttu-id="90d59-164">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="90d59-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="90d59-165">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="90d59-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="90d59-166">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="90d59-166">CommonParameters</span></span>

<span data-ttu-id="90d59-167">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="90d59-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="90d59-168">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="90d59-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="90d59-169">Входные данные</span><span class="sxs-lookup"><span data-stu-id="90d59-169">INPUTS</span></span>

### <span data-ttu-id="90d59-170">Нет</span><span class="sxs-lookup"><span data-stu-id="90d59-170">None</span></span>

<span data-ttu-id="90d59-171">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="90d59-171">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="90d59-172">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="90d59-172">OUTPUTS</span></span>

### <span data-ttu-id="90d59-173">System.String</span><span class="sxs-lookup"><span data-stu-id="90d59-173">System.String</span></span>

<span data-ttu-id="90d59-174">Этот командлет возвращает строки, которые описывают результаты его выполнения.</span><span class="sxs-lookup"><span data-stu-id="90d59-174">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="90d59-175">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="90d59-175">NOTES</span></span>

<span data-ttu-id="90d59-176">В PowerShell 3,0 `Enable-PSRemoting` создает следующие исключения брандмауэра для WS-Management связи.</span><span class="sxs-lookup"><span data-stu-id="90d59-176">In PowerShell 3.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="90d59-177">В серверных версиях операционной системы Windows `Enable-PSRemoting` создает правила брандмауэра для частных и доменных сетей, разрешающих удаленный доступ, и создает правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ только с компьютеров в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="90d59-177">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="90d59-178">В клиентских версиях операционной системы Windows `Enable-PSRemoting` в PowerShell 3,0 создаются правила брандмауэра для частных и доменных сетей, которые обеспечивают неограниченный удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="90d59-178">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 3.0 creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="90d59-179">Чтобы создать правило брандмауэра для общедоступных сетей, разрешающее удаленный доступ из той же локальной подсети, используйте параметр **SkipNetworkProfileCheck** .</span><span class="sxs-lookup"><span data-stu-id="90d59-179">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="90d59-180">В клиентской или серверной версиях операционной системы Windows для создания правила брандмауэра для общедоступных сетей, которое удаляет ограничение локальной подсети и разрешает удаленный доступ, используйте `Set-NetFirewallRule` командлет в модуле NetSecurity для выполнения следующей команды: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="90d59-180">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="90d59-181">В PowerShell 2,0 `Enable-PSRemoting` создает следующие исключения брандмауэра для WS-Management связи.</span><span class="sxs-lookup"><span data-stu-id="90d59-181">In PowerShell 2.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="90d59-182">В серверных версиях ОС Windows он создает правила брандмауэра, разрешающие удаленный доступ, для всех сетей.</span><span class="sxs-lookup"><span data-stu-id="90d59-182">On server versions of the Windows operating system, it creates firewall rules for all networks that allow remote access.</span></span>

<span data-ttu-id="90d59-183">В клиентских версиях операционной системы Windows `Enable-PSRemoting` в PowerShell 2,0 создается исключение брандмауэра только для расположений домена и частных сетей.</span><span class="sxs-lookup"><span data-stu-id="90d59-183">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 2.0 creates a firewall exception only for domain and private network locations.</span></span> <span data-ttu-id="90d59-184">Чтобы снизить риски безопасности, не `Enable-PSRemoting` создает правило брандмауэра для общедоступных сетей в клиентских версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="90d59-184">To minimize security risks, `Enable-PSRemoting` does not create a firewall rule for public networks on client versions of Windows.</span></span> <span data-ttu-id="90d59-185">Если текущее сетевое расположение является общедоступным, `Enable-PSRemoting` возвращает следующее сообщение: не удалось проверить состояние брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="90d59-185">When the current network location is public, `Enable-PSRemoting` returns the following message: Unable to check the status of the firewall.</span></span>

<span data-ttu-id="90d59-186">Начиная с версии PowerShell 3,0, `Enable-PSRemoting` включает все конфигурации сеанса, устанавливая для свойства **Enabled** всех конфигураций сеансов значение `$True` .</span><span class="sxs-lookup"><span data-stu-id="90d59-186">Starting in PowerShell 3.0, `Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="90d59-187">В PowerShell 2,0 `Enable-PSRemoting` удаляет параметр **Deny_All** из дескриптора безопасности конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="90d59-187">In PowerShell 2.0, `Enable-PSRemoting` removes the **Deny_All** setting from the security descriptor of session configurations.</span></span> <span data-ttu-id="90d59-188">В PowerShell 3,0 `Enable-PSRemoting` удаляет параметры **Deny_All** и **Network_Deny_All** .</span><span class="sxs-lookup"><span data-stu-id="90d59-188">In PowerShell 3.0, `Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="90d59-189">Это обеспечивает удаленный доступ к конфигурациям сеансов, зарезервированным для локального использования.</span><span class="sxs-lookup"><span data-stu-id="90d59-189">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="90d59-190">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="90d59-190">RELATED LINKS</span></span>

[<span data-ttu-id="90d59-191">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="90d59-191">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="90d59-192">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="90d59-192">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="90d59-193">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="90d59-193">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="90d59-194">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="90d59-194">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="90d59-195">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="90d59-195">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="90d59-196">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="90d59-196">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="90d59-197">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="90d59-197">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="90d59-198">about_Remote</span><span class="sxs-lookup"><span data-stu-id="90d59-198">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="90d59-199">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="90d59-199">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
