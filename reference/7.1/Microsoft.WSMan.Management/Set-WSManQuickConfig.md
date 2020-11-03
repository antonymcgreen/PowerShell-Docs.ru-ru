---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: 07f984b43ee783f25e9ede4a5888cd9dbbdea417
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "93230577"
---
# <span data-ttu-id="ac57a-103">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="ac57a-103">Set-WSManQuickConfig</span></span>

## <span data-ttu-id="ac57a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ac57a-104">SYNOPSIS</span></span>
<span data-ttu-id="ac57a-105">Настраивает локальный компьютер для удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="ac57a-105">Configures the local computer for remote management.</span></span>

## <span data-ttu-id="ac57a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ac57a-106">SYNTAX</span></span>

### <span data-ttu-id="ac57a-107">Все</span><span class="sxs-lookup"><span data-stu-id="ac57a-107">All</span></span>

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## <span data-ttu-id="ac57a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ac57a-108">DESCRIPTION</span></span>

<span data-ttu-id="ac57a-109">`Set-WSManQuickConfig`Командлет настраивает компьютер для получения удаленных команд PowerShell, отправляемых с помощью технологии веб-служб для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="ac57a-109">The `Set-WSManQuickConfig` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the Web Services for Management (WS-Management) technology.</span></span>

<span data-ttu-id="ac57a-110">Подпрограмма`Set-WSManQuickConfig` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ac57a-110">`Set-WSManQuickConfig` performs the following actions:</span></span>

- <span data-ttu-id="ac57a-111">Проверяет, запущена ли служба WinRM.</span><span class="sxs-lookup"><span data-stu-id="ac57a-111">Checks whether the WinRM service is running.</span></span> <span data-ttu-id="ac57a-112">Если служба WinRM не запущена, служба запускается.</span><span class="sxs-lookup"><span data-stu-id="ac57a-112">If the WinRM service isn't running, the service is started.</span></span>
- <span data-ttu-id="ac57a-113">Задает автоматический тип запуска службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="ac57a-113">Sets the WinRM service startup type to automatic.</span></span>
- <span data-ttu-id="ac57a-114">Создает прослушиватель для приема запросов по любому IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="ac57a-114">Creates a listener to accept requests on any IP address.</span></span> <span data-ttu-id="ac57a-115">Транспортом по умолчанию является **http** .</span><span class="sxs-lookup"><span data-stu-id="ac57a-115">The default transport is **HTTP** .</span></span>
- <span data-ttu-id="ac57a-116">Включает исключение брандмауэра для трафика WinRM.</span><span class="sxs-lookup"><span data-stu-id="ac57a-116">Enables a firewall exception for WinRM traffic.</span></span>

<span data-ttu-id="ac57a-117">Для запуска запустите `Set-WSManQuickConfig` PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="ac57a-117">To run `Set-WSManQuickConfig`, start PowerShell with the **Run as Administrator** option.</span></span>

## <span data-ttu-id="ac57a-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="ac57a-118">EXAMPLES</span></span>

### <span data-ttu-id="ac57a-119">Пример 1. Включение удаленного управления локальным компьютером по протоколу HTTP</span><span class="sxs-lookup"><span data-stu-id="ac57a-119">Example 1: Enable remote management of the local computer over HTTP</span></span>

<span data-ttu-id="ac57a-120">В этом примере задается необходимая конфигурация для включения удаленного управления локальным компьютером.</span><span class="sxs-lookup"><span data-stu-id="ac57a-120">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="ac57a-121">По умолчанию эта команда создает прослушиватель WS-Management на **http** .</span><span class="sxs-lookup"><span data-stu-id="ac57a-121">By default, this command creates a WS-Management listener on **HTTP** .</span></span>

```powershell
Set-WSManQuickConfig
```

### <span data-ttu-id="ac57a-122">Пример 2. Включение удаленного управления локальным компьютером по протоколу HTTPS</span><span class="sxs-lookup"><span data-stu-id="ac57a-122">Example 2: Enable remote management of the local computer over HTTPS</span></span>

<span data-ttu-id="ac57a-123">В этом примере задается необходимая конфигурация для включения удаленного управления локальным компьютером.</span><span class="sxs-lookup"><span data-stu-id="ac57a-123">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="ac57a-124">Параметр **UseSSL** указывает, что **протокол HTTPS** используется для взаимодействия с компьютером.</span><span class="sxs-lookup"><span data-stu-id="ac57a-124">The **UseSSL** parameter specifies that **HTTPS** is used to communicate with the computer.</span></span>

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> <span data-ttu-id="ac57a-125">Для **HTTPS** требуется ручная настройка.</span><span class="sxs-lookup"><span data-stu-id="ac57a-125">**HTTPS** requires manual configuration.</span></span> <span data-ttu-id="ac57a-126">Дополнительные сведения см. в описании параметра **UseSSL** .</span><span class="sxs-lookup"><span data-stu-id="ac57a-126">For more information, see the **UseSSL** parameter's description.</span></span>

## <span data-ttu-id="ac57a-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ac57a-127">PARAMETERS</span></span>

### <span data-ttu-id="ac57a-128">-Force</span><span class="sxs-lookup"><span data-stu-id="ac57a-128">-Force</span></span>

<span data-ttu-id="ac57a-129">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="ac57a-129">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ac57a-130">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="ac57a-130">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="ac57a-131">Настраивает клиентские версии Windows для удаленного взаимодействия, когда компьютер находится в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="ac57a-131">Configures Windows client versions for remoting when the computer is on a public network.</span></span> <span data-ttu-id="ac57a-132">Этот параметр включает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров, находящихся в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="ac57a-132">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="ac57a-133">Этот параметр не влияет на серверные версии Windows, по умолчанию имеющий правило брандмауэра локальной подсети для общедоступных сетей.</span><span class="sxs-lookup"><span data-stu-id="ac57a-133">This parameter has no effect on server versions of Windows, that by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="ac57a-134">Если правило брандмауэра на локальной подсети отключено на серверной версии Windows, `Enable-PSRemoting` повторно включает его, независимо от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="ac57a-134">If the local subnet firewall rule is disabled on the server version of Windows, `Enable-PSRemoting` re-enables it, regardless of this parameter's value.</span></span>

<span data-ttu-id="ac57a-135">Чтобы удалить ограничение локальной подсети и включить удаленный доступ из всех расположений в общедоступных сетях, используйте `Set-NetFirewallRule` командлет в модуле **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="ac57a-135">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="ac57a-136">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ac57a-136">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ac57a-137">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="ac57a-137">-UseSSL</span></span>

<span data-ttu-id="ac57a-138">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="ac57a-138">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span> <span data-ttu-id="ac57a-139">По умолчанию протокол SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="ac57a-139">By default, SSL isn't used.</span></span>

<span data-ttu-id="ac57a-140">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="ac57a-140">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="ac57a-141">Параметр **UseSSL** позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="ac57a-141">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="ac57a-142">Если вы используете этот параметр и протокол SSL недоступен в порте, используемом для подключения, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ac57a-142">If you use this parameter and SSL isn't available on the port that's used for the connection, the command fails.</span></span>

<span data-ttu-id="ac57a-143">Для **HTTPS** требуется ручная настройка WinRM и правил брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="ac57a-143">**HTTPS** requires manual configuration of WinRM and firewall rules.</span></span> <span data-ttu-id="ac57a-144">Дополнительные сведения см. [в разделе инструкции. Настройка WINRM для HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span><span class="sxs-lookup"><span data-stu-id="ac57a-144">For more information, see [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span></span>

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

### <span data-ttu-id="ac57a-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ac57a-145">CommonParameters</span></span>

<span data-ttu-id="ac57a-146">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ac57a-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ac57a-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ac57a-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ac57a-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ac57a-148">INPUTS</span></span>

### <span data-ttu-id="ac57a-149">Нет</span><span class="sxs-lookup"><span data-stu-id="ac57a-149">None</span></span>

<span data-ttu-id="ac57a-150">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="ac57a-150">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="ac57a-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ac57a-151">OUTPUTS</span></span>

### <span data-ttu-id="ac57a-152">Нет</span><span class="sxs-lookup"><span data-stu-id="ac57a-152">None</span></span>

<span data-ttu-id="ac57a-153">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ac57a-153">This cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="ac57a-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ac57a-154">NOTES</span></span>

## <span data-ttu-id="ac57a-155">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ac57a-155">RELATED LINKS</span></span>

[<span data-ttu-id="ac57a-156">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="ac57a-156">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="ac57a-157">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ac57a-157">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="ac57a-158">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="ac57a-158">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="ac57a-159">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="ac57a-159">Enable-PSRemoting</span></span>](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[<span data-ttu-id="ac57a-160">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ac57a-160">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="ac57a-161">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ac57a-161">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="ac57a-162">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ac57a-162">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="ac57a-163">Как настроить WINRM для HTTPS</span><span class="sxs-lookup"><span data-stu-id="ac57a-163">How To: Configure WINRM for HTTPS</span></span>](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[<span data-ttu-id="ac57a-164">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="ac57a-164">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="ac57a-165">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="ac57a-165">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="ac57a-166">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ac57a-166">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="ac57a-167">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="ac57a-167">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="ac57a-168">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="ac57a-168">Test-WSMan</span></span>](Test-WSMan.md)

