---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: e5d50af0551a183b8e9e1995fbd722c331a48486
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602695"
---
# <span data-ttu-id="e6f76-102">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="e6f76-102">Set-WSManQuickConfig</span></span>

## <span data-ttu-id="e6f76-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e6f76-103">SYNOPSIS</span></span>
<span data-ttu-id="e6f76-104">Настраивает локальный компьютер для удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="e6f76-104">Configures the local computer for remote management.</span></span>

## <span data-ttu-id="e6f76-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6f76-105">SYNTAX</span></span>

### <span data-ttu-id="e6f76-106">Все</span><span class="sxs-lookup"><span data-stu-id="e6f76-106">All</span></span>

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## <span data-ttu-id="e6f76-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6f76-107">DESCRIPTION</span></span>

<span data-ttu-id="e6f76-108">`Set-WSManQuickConfig`Командлет настраивает компьютер для получения удаленных команд PowerShell, отправляемых с помощью технологии веб-служб для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="e6f76-108">The `Set-WSManQuickConfig` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the Web Services for Management (WS-Management) technology.</span></span>

<span data-ttu-id="e6f76-109">Подпрограмма`Set-WSManQuickConfig` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e6f76-109">`Set-WSManQuickConfig` performs the following actions:</span></span>

- <span data-ttu-id="e6f76-110">Проверяет, запущена ли служба WinRM.</span><span class="sxs-lookup"><span data-stu-id="e6f76-110">Checks whether the WinRM service is running.</span></span> <span data-ttu-id="e6f76-111">Если служба WinRM не запущена, служба запускается.</span><span class="sxs-lookup"><span data-stu-id="e6f76-111">If the WinRM service isn't running, the service is started.</span></span>
- <span data-ttu-id="e6f76-112">Задает автоматический тип запуска службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="e6f76-112">Sets the WinRM service startup type to automatic.</span></span>
- <span data-ttu-id="e6f76-113">Создает прослушиватель для приема запросов по любому IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="e6f76-113">Creates a listener to accept requests on any IP address.</span></span> <span data-ttu-id="e6f76-114">Транспортом по умолчанию является **http**.</span><span class="sxs-lookup"><span data-stu-id="e6f76-114">The default transport is **HTTP**.</span></span>
- <span data-ttu-id="e6f76-115">Включает исключение брандмауэра для трафика WinRM.</span><span class="sxs-lookup"><span data-stu-id="e6f76-115">Enables a firewall exception for WinRM traffic.</span></span>

<span data-ttu-id="e6f76-116">Для запуска запустите `Set-WSManQuickConfig` PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="e6f76-116">To run `Set-WSManQuickConfig`, start PowerShell with the **Run as Administrator** option.</span></span>

## <span data-ttu-id="e6f76-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="e6f76-117">EXAMPLES</span></span>

### <span data-ttu-id="e6f76-118">Пример 1. Включение удаленного управления локальным компьютером по протоколу HTTP</span><span class="sxs-lookup"><span data-stu-id="e6f76-118">Example 1: Enable remote management of the local computer over HTTP</span></span>

<span data-ttu-id="e6f76-119">В этом примере задается необходимая конфигурация для включения удаленного управления локальным компьютером.</span><span class="sxs-lookup"><span data-stu-id="e6f76-119">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="e6f76-120">По умолчанию эта команда создает прослушиватель WS-Management на **http**.</span><span class="sxs-lookup"><span data-stu-id="e6f76-120">By default, this command creates a WS-Management listener on **HTTP**.</span></span>

```powershell
Set-WSManQuickConfig
```

### <span data-ttu-id="e6f76-121">Пример 2. Включение удаленного управления локальным компьютером по протоколу HTTPS</span><span class="sxs-lookup"><span data-stu-id="e6f76-121">Example 2: Enable remote management of the local computer over HTTPS</span></span>

<span data-ttu-id="e6f76-122">В этом примере задается необходимая конфигурация для включения удаленного управления локальным компьютером.</span><span class="sxs-lookup"><span data-stu-id="e6f76-122">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="e6f76-123">Параметр **UseSSL** указывает, что **протокол HTTPS** используется для взаимодействия с компьютером.</span><span class="sxs-lookup"><span data-stu-id="e6f76-123">The **UseSSL** parameter specifies that **HTTPS** is used to communicate with the computer.</span></span>

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> <span data-ttu-id="e6f76-124">Для **HTTPS** требуется ручная настройка.</span><span class="sxs-lookup"><span data-stu-id="e6f76-124">**HTTPS** requires manual configuration.</span></span> <span data-ttu-id="e6f76-125">Дополнительные сведения см. в описании параметра **UseSSL** .</span><span class="sxs-lookup"><span data-stu-id="e6f76-125">For more information, see the **UseSSL** parameter's description.</span></span>

## <span data-ttu-id="e6f76-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6f76-126">PARAMETERS</span></span>

### <span data-ttu-id="e6f76-127">-Force</span><span class="sxs-lookup"><span data-stu-id="e6f76-127">-Force</span></span>

<span data-ttu-id="e6f76-128">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="e6f76-128">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6f76-129">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="e6f76-129">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="e6f76-130">Настраивает клиентские версии Windows для удаленного взаимодействия, когда компьютер находится в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="e6f76-130">Configures Windows client versions for remoting when the computer is on a public network.</span></span> <span data-ttu-id="e6f76-131">Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="e6f76-131">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="e6f76-132">Этот параметр не влияет на серверные версии Windows, по умолчанию имеющий правило брандмауэра локальной подсети для общедоступных сетей.</span><span class="sxs-lookup"><span data-stu-id="e6f76-132">This parameter has no effect on server versions of Windows, that by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="e6f76-133">Если правило брандмауэра на локальной подсети отключено на серверной версии Windows, `Enable-PSRemoting` повторно включает его, независимо от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="e6f76-133">If the local subnet firewall rule is disabled on the server version of Windows, `Enable-PSRemoting` re-enables it, regardless of this parameter's value.</span></span>

<span data-ttu-id="e6f76-134">Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="e6f76-134">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="e6f76-135">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e6f76-135">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6f76-136">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="e6f76-136">-UseSSL</span></span>

<span data-ttu-id="e6f76-137">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="e6f76-137">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span> <span data-ttu-id="e6f76-138">По умолчанию протокол SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="e6f76-138">By default, SSL isn't used.</span></span>

<span data-ttu-id="e6f76-139">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="e6f76-139">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="e6f76-140">Параметр **UseSSL** позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6f76-140">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="e6f76-141">Если вы используете этот параметр и протокол SSL недоступен в порте, используемом для подключения, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e6f76-141">If you use this parameter and SSL isn't available on the port that's used for the connection, the command fails.</span></span>

<span data-ttu-id="e6f76-142">Для **HTTPS** требуется ручная настройка WinRM и правил брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="e6f76-142">**HTTPS** requires manual configuration of WinRM and firewall rules.</span></span> <span data-ttu-id="e6f76-143">Дополнительные сведения см. [в разделе инструкции. Настройка WINRM для HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span><span class="sxs-lookup"><span data-stu-id="e6f76-143">For more information, see [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6f76-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e6f76-144">CommonParameters</span></span>

<span data-ttu-id="e6f76-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6f76-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6f76-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6f76-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6f76-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e6f76-147">INPUTS</span></span>

### <span data-ttu-id="e6f76-148">None</span><span class="sxs-lookup"><span data-stu-id="e6f76-148">None</span></span>

<span data-ttu-id="e6f76-149">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="e6f76-149">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="e6f76-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e6f76-150">OUTPUTS</span></span>

### <span data-ttu-id="e6f76-151">None</span><span class="sxs-lookup"><span data-stu-id="e6f76-151">None</span></span>

<span data-ttu-id="e6f76-152">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e6f76-152">This cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="e6f76-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e6f76-153">NOTES</span></span>

## <span data-ttu-id="e6f76-154">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e6f76-154">RELATED LINKS</span></span>

[<span data-ttu-id="e6f76-155">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e6f76-155">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="e6f76-156">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e6f76-156">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="e6f76-157">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e6f76-157">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="e6f76-158">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="e6f76-158">Enable-PSRemoting</span></span>](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[<span data-ttu-id="e6f76-159">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e6f76-159">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="e6f76-160">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e6f76-160">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="e6f76-161">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e6f76-161">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="e6f76-162">Как настроить WINRM для HTTPS</span><span class="sxs-lookup"><span data-stu-id="e6f76-162">How To: Configure WINRM for HTTPS</span></span>](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[<span data-ttu-id="e6f76-163">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="e6f76-163">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="e6f76-164">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="e6f76-164">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="e6f76-165">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e6f76-165">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="e6f76-166">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="e6f76-166">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="e6f76-167">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="e6f76-167">Test-WSMan</span></span>](Test-WSMan.md)

