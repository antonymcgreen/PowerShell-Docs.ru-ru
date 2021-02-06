---
description: Описывает устранение неполадок удаленных операций в PowerShell.
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Сведения об удаленной диагностике
ms.openlocfilehash: cedf38f3982f4036aae59a2019ab72b556e50cfd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600874"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="ab22d-103">Об устранении неполадок удаленного поиска</span><span class="sxs-lookup"><span data-stu-id="ab22d-103">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="ab22d-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="ab22d-104">Short description</span></span>
<span data-ttu-id="ab22d-105">Описывает устранение неполадок удаленных операций в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab22d-105">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ab22d-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ab22d-106">Long description</span></span>

<span data-ttu-id="ab22d-107">В этом разделе описываются некоторые проблемы, которые могут возникнуть при использовании функций удаленного взаимодействия PowerShell, основанных на технологии WS-Management и предлагающих решения этих проблем.</span><span class="sxs-lookup"><span data-stu-id="ab22d-107">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="ab22d-108">Прежде чем использовать удаленное взаимодействие PowerShell, ознакомьтесь со статьей [about_Remote](about_remote.md) и [about_Remote_Requirements](about_Remote_Requirements.md) , где приведены рекомендации по настройке и базовому использованию.</span><span class="sxs-lookup"><span data-stu-id="ab22d-108">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="ab22d-109">Кроме того, разделы справки по каждому из командлетов удаленного взаимодействия, в особенности описания параметров, содержат полезную информацию, которая поможет избежать проблем.</span><span class="sxs-lookup"><span data-stu-id="ab22d-109">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="ab22d-110">Чтобы просмотреть или изменить параметры локального компьютера на диске WSMan:, включая изменения в конфигурациях сеансов, доверенных узлах, портах или прослушивателях, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-110">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="ab22d-111">Устранение неполадок разрешений и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="ab22d-111">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="ab22d-112">В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с разрешениями пользователя и компьютера и требованиями удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ab22d-112">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="ab22d-113">Запуск от имени администратора</span><span class="sxs-lookup"><span data-stu-id="ab22d-113">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="ab22d-114">Чтобы запустить удаленный сеанс на локальном компьютере или просмотреть или изменить параметры для локального компьютера на диске WSMan:, включая изменения в конфигурациях сеансов, доверенных узлах, портах или прослушивателях, запустите Windows PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-114">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="ab22d-115">Чтобы запустить Windows PowerShell с параметром **Запуск от имени администратора** , выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ab22d-115">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="ab22d-116">Щелкните правой кнопкой мыши значок Windows PowerShell (интегрированная среда сценариев Windows PowerShell) и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="ab22d-116">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator**.</span></span>

  <span data-ttu-id="ab22d-117">Для запуска Windows PowerShell с параметром **Запуск от имени администратора** в Windows 7 и windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="ab22d-117">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="ab22d-118">На панели задач Windows щелкните правой кнопкой мыши значок Windows PowerShell и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="ab22d-118">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator**.</span></span>

  <span data-ttu-id="ab22d-119">В Windows Server 2008 R2 значок Windows PowerShell закреплен на панели задач по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab22d-119">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="ab22d-120">Как включить удаленное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="ab22d-120">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="ab22d-121">Для включения отправки удаленных команд на компьютере не требуется настраивать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ab22d-121">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="ab22d-122">Однако для получения удаленных команд на компьютере должна быть включена служба удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab22d-122">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="ab22d-123">Включение включает запуск службы WinRM, задание для типа запуска службы WinRM значения автоматически, создание прослушивателей для соединений HTTP и HTTPS и создание конфигураций сеансов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab22d-123">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="ab22d-124">Удаленное взаимодействие Windows PowerShell включено в Windows Server 2012 и более новых выпусках Windows Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab22d-124">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="ab22d-125">Во всех остальных системах выполните командлет, `Enable-PSRemoting` чтобы включить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="ab22d-125">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="ab22d-126">Можно также выполнить командлет, `Enable-PSRemoting` чтобы повторно включить удаленное взаимодействие на Windows server 2012 и более поздних выпусках Windows Server, если удаленное взаимодействие отключено.</span><span class="sxs-lookup"><span data-stu-id="ab22d-126">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="ab22d-127">Чтобы настроить компьютер для получения удаленных команд, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="ab22d-127">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="ab22d-128">Следующая команда включает все необходимые удаленные параметры, включает конфигурации сеанса и перезапускает службу WinRM, чтобы изменения были эффективными.</span><span class="sxs-lookup"><span data-stu-id="ab22d-128">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="ab22d-129">Чтобы отключить все запросы пользователя, введите:</span><span class="sxs-lookup"><span data-stu-id="ab22d-129">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="ab22d-130">Дополнительные сведения см. в разделе [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span><span class="sxs-lookup"><span data-stu-id="ab22d-130">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="ab22d-131">Как включить удаленное взаимодействие на предприятии</span><span class="sxs-lookup"><span data-stu-id="ab22d-131">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="ab22d-132">Чтобы разрешить одному компьютеру получать удаленные команды PowerShell и принимать подключения, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="ab22d-132">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="ab22d-133">Чтобы включить удаленное взаимодействие для нескольких компьютеров в Организации, можно использовать следующие масштабируемые параметры.</span><span class="sxs-lookup"><span data-stu-id="ab22d-133">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="ab22d-134">Чтобы настроить прослушиватели для удаленного взаимодействия, включите групповую политику **Разрешить автоматическую настройку прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-134">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="ab22d-135">Чтобы задать автоматический тип запуска служба удаленного управления Windows (WinRM) на нескольких компьютерах, используйте `Set-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="ab22d-135">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="ab22d-136">Чтобы включить исключение брандмауэра, воспользуйтесь групповой политикой **Брандмауэр Windows: разрешить исключения локальных портов** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-136">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="ab22d-137">Включение прослушивателей с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="ab22d-137">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="ab22d-138">Чтобы настроить прослушиватели для всех компьютеров в домене, включите политику **Разрешить автоматическую настройку прослушивателей** в следующем групповая политика пути:</span><span class="sxs-lookup"><span data-stu-id="ab22d-138">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="ab22d-139">Включите политику и укажите фильтры IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="ab22d-139">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="ab22d-140">Допускаются подстановочные знаки ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="ab22d-140">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="ab22d-141">Включение удаленного взаимодействия в общедоступных сетях</span><span class="sxs-lookup"><span data-stu-id="ab22d-141">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="ab22d-142">`Enable-PSRemoting`Командлет возвращает эту ошибку, если локальная сеть является общедоступной, а параметр **SkipNetworkProfileCheck** не используется в команде.</span><span class="sxs-lookup"><span data-stu-id="ab22d-142">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="ab22d-143">В серверных версиях Windows работает `Enable-PSRemoting` на всех типах сетевых расположений.</span><span class="sxs-lookup"><span data-stu-id="ab22d-143">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="ab22d-144">Он создает правила брандмауэра, разрешающие удаленный доступ к частным и доменным (домашним и рабочим) сетям.</span><span class="sxs-lookup"><span data-stu-id="ab22d-144">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="ab22d-145">Для общедоступных сетей он создает правила брандмауэра, разрешающие удаленный доступ из той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="ab22d-145">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="ab22d-146">В клиентских версиях Windows работает `Enable-PSRemoting` в частных и доменных сетях.</span><span class="sxs-lookup"><span data-stu-id="ab22d-146">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="ab22d-147">По умолчанию он завершается сбоем в общедоступных сетях, но если вы используете параметр **SkipNetworkProfileCheck** , то `Enable-PSRemoting` завершается и создается правило брандмауэра, разрешающее трафик из той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="ab22d-147">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="ab22d-148">Чтобы удалить ограничение локальной подсети в общедоступных сетях и разрешить удаленный доступ из любого расположения, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab22d-148">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="ab22d-149">`Set-NetFirewallRule`Командлет экспортируется модулем NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="ab22d-149">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="ab22d-150">В Windows PowerShell 2,0 на компьютерах под управлением серверных версий Windows `Enable-PSRemoting` создаются правила брандмауэра, обеспечивающие удаленный доступ к частным, доменным и общедоступным сетям.</span><span class="sxs-lookup"><span data-stu-id="ab22d-150">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="ab22d-151">На компьютерах с клиентскими версиями Windows `Enable-PSRemoting` создает правила брандмауэра, разрешающие удаленный доступ только в частных и доменных сетях.</span><span class="sxs-lookup"><span data-stu-id="ab22d-151">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="ab22d-152">Как включить исключение брандмауэра с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="ab22d-152">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="ab22d-153">Чтобы включить исключение брандмауэра на всех компьютерах в домене, включите политику **брандмауэра Windows: разрешить исключения локальных портов** в следующем групповая политика пути:</span><span class="sxs-lookup"><span data-stu-id="ab22d-153">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="ab22d-154">Эта политика позволяет членам группы администраторов на компьютере использовать **Брандмауэр Windows** на **панели управления** для создания исключения брандмауэра для службы Служба удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="ab22d-154">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="ab22d-155">Если конфигурация политики неверна, может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="ab22d-155">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="ab22d-156">Ошибка конфигурации в политике приводит к пустому значению свойства **листенингон** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-156">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="ab22d-157">Для проверки значения используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ab22d-157">Use the following command to check the value.</span></span>

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="ab22d-158">Как задать тип запуска службы WinRM</span><span class="sxs-lookup"><span data-stu-id="ab22d-158">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="ab22d-159">Удаленное взаимодействие PowerShell зависит от службы служба удаленного управления Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="ab22d-159">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="ab22d-160">Служба должна быть запущена для поддержки удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="ab22d-160">The service must be running to support remote commands.</span></span>

<span data-ttu-id="ab22d-161">В серверных версиях Windows тип запуска службы служба удаленного управления Windows (WinRM) — автоматически.</span><span class="sxs-lookup"><span data-stu-id="ab22d-161">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="ab22d-162">Однако в клиентских версиях Windows служба WinRM по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="ab22d-162">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="ab22d-163">Чтобы задать тип запуска службы на удаленном компьютере, используйте `Set-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="ab22d-163">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="ab22d-164">Чтобы выполнить команду на нескольких компьютерах, можно создать текстовый файл или CSV-файл с именами компьютеров.</span><span class="sxs-lookup"><span data-stu-id="ab22d-164">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="ab22d-165">Например, следующие команды получают список имен компьютеров из `Servers.txt` файла, а затем задает для всех компьютеров **Автоматический** тип запуска службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="ab22d-165">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic**.</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="ab22d-166">Чтобы просмотреть результаты, используйте `Get-WMIObject` командлет с объектом **Win32_Service** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-166">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="ab22d-167">Дополнительные сведения см. в разделе [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span><span class="sxs-lookup"><span data-stu-id="ab22d-167">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="ab22d-168">Повторное создание конфигураций сеансов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ab22d-168">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="ab22d-169">Чтобы подключиться к локальному компьютеру и выполнить команды удаленно, локальный компьютер должен включать конфигурации сеанса для удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="ab22d-169">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="ab22d-170">При использовании `Enable-PSRemoting` он создает конфигурации сеансов по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-170">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="ab22d-171">Удаленные пользователи используют эти конфигурации сеанса каждый раз, когда удаленная команда не включает параметр **configurationName** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-171">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="ab22d-172">Если конфигурации по умолчанию на компьютере не зарегистрированы или удалены, используйте `Enable-PSRemoting` командлет для их повторного создания.</span><span class="sxs-lookup"><span data-stu-id="ab22d-172">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="ab22d-173">Этот командлет можно использовать многократно.</span><span class="sxs-lookup"><span data-stu-id="ab22d-173">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="ab22d-174">Если функция уже настроена, она не создает ошибок.</span><span class="sxs-lookup"><span data-stu-id="ab22d-174">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="ab22d-175">При изменении конфигураций сеансов по умолчанию и необходимости восстановления исходных конфигураций сеансов по умолчанию используйте `Unregister-PSSessionConfiguration` командлет для удаления измененных конфигураций сеанса, а затем используйте `Enable-PSRemoting` командлет для их восстановления.</span><span class="sxs-lookup"><span data-stu-id="ab22d-175">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="ab22d-176">`Enable-PSRemoting` не изменяет существующие конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab22d-176">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="ab22d-177">При `Enable-PSRemoting` восстановлении конфигурации сеанса по умолчанию не создаются явные дескрипторы безопасности для конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ab22d-177">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="ab22d-178">Вместо этого конфигурации наследуют дескриптор безопасности Рутсддл, который является безопасным по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab22d-178">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="ab22d-179">Чтобы просмотреть дескриптор безопасности Рутсддл, введите:</span><span class="sxs-lookup"><span data-stu-id="ab22d-179">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="ab22d-180">Чтобы изменить Рутсддл, используйте `Set-Item` командлет на диске WSMan:.</span><span class="sxs-lookup"><span data-stu-id="ab22d-180">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="ab22d-181">Чтобы изменить дескриптор безопасности конфигурации сеанса, используйте `Set-PSSessionConfiguration` командлет с параметрами **SecurityDescriptorSDDL** или **ShowSecurityDescriptorUI** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-181">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="ab22d-182">Дополнительные сведения о диске WSMan: см. в разделе справки по поставщику WSMan ("Get-Help WSMAN").</span><span class="sxs-lookup"><span data-stu-id="ab22d-182">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="ab22d-183">Как указать учетные данные администратора</span><span class="sxs-lookup"><span data-stu-id="ab22d-183">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="ab22d-184">Чтобы создать сеанс PSSession или выполнить команды на удаленном компьютере, по умолчанию текущий пользователь должен быть членом группы администраторов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-184">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="ab22d-185">Учетные данные иногда требуются даже при входе текущего пользователя в учетную запись, которая является членом группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="ab22d-185">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="ab22d-186">Если текущий пользователь является членом группы "Администраторы" на удаленном компьютере или может предоставить учетные данные члена группы "Администраторы", используйте параметр **Credential** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлета или, чтобы подключиться удаленно.</span><span class="sxs-lookup"><span data-stu-id="ab22d-186">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="ab22d-187">Например, следующая команда предоставляет учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="ab22d-187">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="ab22d-188">Дополнительные сведения о параметре **Credential** см. в разделе [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) или [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span><span class="sxs-lookup"><span data-stu-id="ab22d-188">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="ab22d-189">Включение удаленного взаимодействия для пользователей, не являющихся администраторами</span><span class="sxs-lookup"><span data-stu-id="ab22d-189">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="ab22d-190">Чтобы установить PSSession или выполнить команду на удаленном компьютере, пользователь должен иметь разрешение на использование конфигураций сеансов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-190">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="ab22d-191">По умолчанию разрешения на использование конфигураций сеансов по умолчанию имеют только члены группы «Администраторы» на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-191">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="ab22d-192">Таким образом, только члены группы «Администраторы» могут подключаться к компьютеру удаленно.</span><span class="sxs-lookup"><span data-stu-id="ab22d-192">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="ab22d-193">Чтобы разрешить другим пользователям подключаться к локальному компьютеру, предоставьте пользователю разрешения на выполнение конфигураций сеансов по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-193">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="ab22d-194">Следующая команда открывает страницу свойств, которая позволяет изменить дескриптор безопасности конфигурации сеанса Microsoft. PowerShell по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-194">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="ab22d-195">Дополнительные сведения см. в разделе [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ab22d-195">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="ab22d-196">Включение удаленного взаимодействия для администраторов в других доменах</span><span class="sxs-lookup"><span data-stu-id="ab22d-196">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="ab22d-197">Если пользователь в другом домене входит в группу администраторов на локальном компьютере, он не может удаленно подключиться к локальному компьютеру с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="ab22d-197">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="ab22d-198">По умолчанию удаленные подключения из других доменов выполняются только с маркерами прав обычного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab22d-198">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="ab22d-199">Однако можно использовать запись реестра **LocalAccountTokenFilterPolicy** , чтобы изменить поведение по умолчанию и разрешить удаленным пользователям, которые являются членами группы "Администраторы", работать с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="ab22d-199">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="ab22d-200">Запись **LocalAccountTokenFilterPolicy** отключает удаленные ограничения контроля учетных записей (UAC) для всех пользователей всех затронутых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="ab22d-200">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="ab22d-201">Прежде чем изменять политику, внимательно изучите последствия этого параметра.</span><span class="sxs-lookup"><span data-stu-id="ab22d-201">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="ab22d-202">Чтобы изменить политику, используйте следующую команду, чтобы присвоить параметру реестра **LocalAccountTokenFilterPolicy** значение 1.</span><span class="sxs-lookup"><span data-stu-id="ab22d-202">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="ab22d-203">Использование IP-адреса в удаленной команде</span><span class="sxs-lookup"><span data-stu-id="ab22d-203">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="ab22d-204">Параметр **ComputerName** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, и принимает IP-адрес как допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="ab22d-204">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="ab22d-205">Однако так как проверка подлинности Kerberos не поддерживает IP-адреса, проверка подлинности NTLM используется по умолчанию при указании IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="ab22d-205">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="ab22d-206">При использовании проверки подлинности NTLM для удаленного взаимодействия требуется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="ab22d-206">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="ab22d-207">Настройте компьютер для транспорта HTTPS или добавьте IP-адреса удаленных компьютеров в список TrustedHosts на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-207">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="ab22d-208">Используйте параметр **Credential** во всех удаленных командах.</span><span class="sxs-lookup"><span data-stu-id="ab22d-208">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="ab22d-209">Это необходимо даже при отправке учетных данных текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab22d-209">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="ab22d-210">Удаленное подключение с компьютера, созданного в Рабочей группе</span><span class="sxs-lookup"><span data-stu-id="ab22d-210">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="ab22d-211">Если локальный компьютер не входит в домен, для удаленного взаимодействия требуется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="ab22d-211">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="ab22d-212">Настройте компьютер для транспорта HTTPS или добавьте имена удаленных компьютеров в список TrustedHosts на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-212">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="ab22d-213">Убедитесь, что пароль установлен на компьютере рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="ab22d-213">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="ab22d-214">Если пароль не задан или значение пароля пусто, то нельзя выполнять удаленные команды.</span><span class="sxs-lookup"><span data-stu-id="ab22d-214">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="ab22d-215">Чтобы задать пароль для учетной записи пользователя, используйте учетные записи пользователей в панели управления.</span><span class="sxs-lookup"><span data-stu-id="ab22d-215">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="ab22d-216">Используйте параметр **Credential** во всех удаленных командах.</span><span class="sxs-lookup"><span data-stu-id="ab22d-216">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="ab22d-217">Это необходимо даже при отправке учетных данных текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab22d-217">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="ab22d-218">Добавление компьютера в список надежных узлов</span><span class="sxs-lookup"><span data-stu-id="ab22d-218">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="ab22d-219">Элемент TrustedHosts может содержать разделенный запятыми список имен компьютеров, IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="ab22d-219">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="ab22d-220">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ab22d-220">Wildcards are permitted.</span></span>

<span data-ttu-id="ab22d-221">Чтобы просмотреть или изменить список надежных узлов, используйте диск WSMan:.</span><span class="sxs-lookup"><span data-stu-id="ab22d-221">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="ab22d-222">Элемент Трустедхост находится в `WSMan:\localhost\Client` узле.</span><span class="sxs-lookup"><span data-stu-id="ab22d-222">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="ab22d-223">Только члены группы "Администраторы" на компьютере имеют разрешение на изменение списка доверенных узлов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-223">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="ab22d-224">Внимание! значение, заданное для элемента TrustedHosts, влияет на всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="ab22d-224">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="ab22d-225">Чтобы просмотреть список доверенных узлов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab22d-225">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="ab22d-226">Можно также использовать `Set-Location` командлет (Alias = CD) для перемещения по адресу WSMan: Drive в расположение.</span><span class="sxs-lookup"><span data-stu-id="ab22d-226">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="ab22d-227">Пример:</span><span class="sxs-lookup"><span data-stu-id="ab22d-227">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="ab22d-228">Чтобы добавить все компьютеры в список доверенных узлов, используйте следующую команду, которая помещает в ComputerName значение \* (ALL).</span><span class="sxs-lookup"><span data-stu-id="ab22d-228">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="ab22d-229">Можно также использовать подстановочный знак ( `*` ) для добавления всех компьютеров в определенном домене в список доверенных узлов.</span><span class="sxs-lookup"><span data-stu-id="ab22d-229">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="ab22d-230">Например, следующая команда добавляет все компьютеры из домена Fabrikam в список доверенных узлов.</span><span class="sxs-lookup"><span data-stu-id="ab22d-230">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="ab22d-231">Чтобы добавить имена определенных компьютеров в список доверенных узлов, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="ab22d-231">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="ab22d-232">где каждое значение `<ComputerName>` должно иметь следующий формат:</span><span class="sxs-lookup"><span data-stu-id="ab22d-232">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="ab22d-233">Пример:</span><span class="sxs-lookup"><span data-stu-id="ab22d-233">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="ab22d-234">Чтобы добавить имя компьютера в существующий список доверенных узлов, сначала сохраните текущее значение в переменной, а затем задайте в качестве значения список с разделителями-запятыми, включающий текущие и новые значения.</span><span class="sxs-lookup"><span data-stu-id="ab22d-234">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="ab22d-235">Например, чтобы добавить компьютер Server01 в существующий список доверенных узлов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab22d-235">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="ab22d-236">Чтобы добавить IP-адреса определенных компьютеров в список доверенных узлов, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="ab22d-236">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="ab22d-237">Пример:</span><span class="sxs-lookup"><span data-stu-id="ab22d-237">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="ab22d-238">Чтобы добавить компьютер в список TrustedHosts на удаленном компьютере, используйте `Connect-WSMan` командлет, чтобы добавить узел для удаленного компьютера на диск WSMan: на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab22d-238">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="ab22d-239">Затем используйте `Set-Item` команду, чтобы добавить компьютер.</span><span class="sxs-lookup"><span data-stu-id="ab22d-239">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="ab22d-240">Дополнительные сведения о `Connect-WSMan` командлете см. в разделе [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="ab22d-240">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="ab22d-241">Устранение проблем с конфигурацией компьютера</span><span class="sxs-lookup"><span data-stu-id="ab22d-241">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="ab22d-242">В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с определенными конфигурациями компьютера, домена или предприятия.</span><span class="sxs-lookup"><span data-stu-id="ab22d-242">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="ab22d-243">Настройка удаленного взаимодействия на альтернативных портах</span><span class="sxs-lookup"><span data-stu-id="ab22d-243">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="ab22d-244">Удаленное взаимодействие PowerShell по умолчанию использует порт 80 для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="ab22d-244">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="ab22d-245">Порт по умолчанию используется каждый раз, когда пользователь не задает параметры **ConnectionURI** или **Port** в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="ab22d-245">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="ab22d-246">Чтобы изменить порт по умолчанию, используемый PowerShell, используйте `Set-Item` командлет на диске WSMan:, чтобы изменить значение порта на конечном узле прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="ab22d-246">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="ab22d-247">Например, следующая команда изменяет порт по умолчанию на 8080.</span><span class="sxs-lookup"><span data-stu-id="ab22d-247">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="ab22d-248">Настройка удаленного взаимодействия с помощью прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="ab22d-248">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="ab22d-249">Поскольку удаленное взаимодействие PowerShell использует протокол HTTP, на него влияют параметры HTTP-прокси.</span><span class="sxs-lookup"><span data-stu-id="ab22d-249">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="ab22d-250">В организациях, имеющих прокси-серверы, пользователи не могут напрямую получить доступ к удаленному компьютеру PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab22d-250">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="ab22d-251">Чтобы устранить эту проблему, используйте параметры настройки прокси-сервера в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="ab22d-251">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="ab22d-252">Доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ab22d-252">The following settings are available:</span></span>

- <span data-ttu-id="ab22d-253">проксякцесстипе</span><span class="sxs-lookup"><span data-stu-id="ab22d-253">ProxyAccessType</span></span>
- <span data-ttu-id="ab22d-254">проксяусентикатион</span><span class="sxs-lookup"><span data-stu-id="ab22d-254">ProxyAuthentication</span></span>
- <span data-ttu-id="ab22d-255">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="ab22d-255">ProxyCredential</span></span>

<span data-ttu-id="ab22d-256">Чтобы задать эти параметры для определенной команды, выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="ab22d-256">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="ab22d-257">Используйте параметры **проксякцесстипе**, **проксяусентикатион** и **ProxyCredential** `New-PSSessionOption` командлета, чтобы создать объект параметров сеанса с параметрами прокси-сервера для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ab22d-257">Use the **ProxyAccessType**, **ProxyAuthentication**, and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="ab22d-258">Сохраните объект параметра — это переменная.</span><span class="sxs-lookup"><span data-stu-id="ab22d-258">Save the option object is a variable.</span></span>

1. <span data-ttu-id="ab22d-259">Используйте переменную, содержащую объект Option, в качестве значения параметра **SessionOption** `New-PSSession` `Enter-PSSession` команды, или `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="ab22d-259">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="ab22d-260">Например, следующая команда создает объект параметра сеанса с параметрами сеанса прокси-сервера, а затем использует объект для создания удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab22d-260">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="ab22d-261">Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="ab22d-261">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="ab22d-262">Чтобы задать эти параметры для всех удаленных команд в текущем сеансе, используйте объект параметра, который `New-PSSessionOption` создает в значении `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="ab22d-262">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="ab22d-263">Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ab22d-263">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="ab22d-264">Чтобы задать эти параметры для всех удаленных команд, всех сеансов PowerShell на локальном компьютере, добавьте `$PSSessionOption` переменную предпочтений в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab22d-264">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="ab22d-265">Дополнительные сведения о профилях PowerShell см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ab22d-265">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="ab22d-266">Обнаружение 32-разрядного сеанса на 64-разрядном компьютере</span><span class="sxs-lookup"><span data-stu-id="ab22d-266">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="ab22d-267">Если удаленный компьютер работает под управлением 64-разрядной версии Windows, а удаленная команда использует конфигурацию с 32-битным сеансом, например Microsoft. PowerShell32, служба удаленного управления Windows (WinRM) загружает процесс WOW64 и Windows автоматически перенаправляет все ссылки на `$env:Windir\System32` каталог в `$env:Windir\SysWOW64` каталог.</span><span class="sxs-lookup"><span data-stu-id="ab22d-267">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="ab22d-268">В результате, если вы попытаетесь использовать в каталоге System32 средства, не имеющие аналога в каталоге SysWow64, например `Defrag.exe` , эти средства не найдены в каталоге.</span><span class="sxs-lookup"><span data-stu-id="ab22d-268">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="ab22d-269">Чтобы найти архитектуру процессора, используемую в сеансе, используйте значение переменной среды **PROCESSOR_ARCHITECTURE** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-269">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="ab22d-270">Следующая команда находит архитектуру процессора для сеанса в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="ab22d-270">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="ab22d-271">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ab22d-271">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="ab22d-272">Устранение проблем политики и предпочтений</span><span class="sxs-lookup"><span data-stu-id="ab22d-272">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="ab22d-273">В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с политиками и предпочтениями, заданными на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="ab22d-273">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="ab22d-274">Изменение политики выполнения для Import-PSSession и Import-Module</span><span class="sxs-lookup"><span data-stu-id="ab22d-274">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="ab22d-275">`Import-PSSession` `Export-PSSession` Командлеты и создают модули, которые содержат неподписанные файлы скриптов и файлы форматирования.</span><span class="sxs-lookup"><span data-stu-id="ab22d-275">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="ab22d-276">Чтобы импортировать модули, созданные этими командлетами, с помощью `Import-PSSession` или `Import-Module` , политика выполнения в текущем сеансе не может быть ограничена или AllSigned.</span><span class="sxs-lookup"><span data-stu-id="ab22d-276">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="ab22d-277">Дополнительные сведения о политиках выполнения PowerShell см. в разделе [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab22d-277">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="ab22d-278">Чтобы импортировать модули без изменения политики выполнения для локального компьютера, установленного в реестре, используйте параметр **Scope** параметра, `Set-ExecutionPolicy` чтобы задать менее ограниченную политику выполнения для одного процесса.</span><span class="sxs-lookup"><span data-stu-id="ab22d-278">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="ab22d-279">Например, следующая команда запускает процесс с `RemoteSigned` политикой выполнения.</span><span class="sxs-lookup"><span data-stu-id="ab22d-279">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="ab22d-280">Изменение политики выполнения влияет только на текущий процесс и не изменяет параметр реестра PowerShell **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-280">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="ab22d-281">Кроме того, с помощью параметра **ExecutionPolicy** можно `PowerShell.exe` запустить один сеанс с менее ограниченной политикой выполнения.</span><span class="sxs-lookup"><span data-stu-id="ab22d-281">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="ab22d-282">Дополнительные сведения о политиках выполнения см. в разделе [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab22d-282">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="ab22d-283">Для получения дополнительных сведений введите `PowerShell.exe -?`.</span><span class="sxs-lookup"><span data-stu-id="ab22d-283">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="ab22d-284">Как задать и изменить квоты</span><span class="sxs-lookup"><span data-stu-id="ab22d-284">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="ab22d-285">Квоты можно использовать для защиты локального компьютера и удаленного компьютера от чрезмерного использования ресурсов, как случайных, так и вредоносных.</span><span class="sxs-lookup"><span data-stu-id="ab22d-285">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="ab22d-286">В базовой конфигурации доступны следующие квоты.</span><span class="sxs-lookup"><span data-stu-id="ab22d-286">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="ab22d-287">Поставщик WSMan (WSMan:) предоставляет несколько параметров квот, таких как параметры **максенвелопесизекб** и **макспровидеррекуестс** в узле, `WSMan:<ComputerName>` а также параметры **максконкуррентоператионс**, **свойств maxconcurrentoperationsperuser** и **MaxConnections** в `WSMan:<ComputerName>\Service` узле.</span><span class="sxs-lookup"><span data-stu-id="ab22d-287">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations**, **MaxConcurrentOperationsPerUser**, and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="ab22d-288">Защитить локальный компьютер можно с помощью параметров **максимумрецеиведдатасизеперкомманд** и **максимумрецеиведобжектсизе** `New-PSSessionOption` командлета и `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="ab22d-288">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="ab22d-289">Защитить удаленный компьютер можно, добавив ограничения в конфигурации сеанса, например с помощью параметров **максимумрецеиведдатасизеперкоммандмб** и **максимумрецеиведобжектсиземб** `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="ab22d-289">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="ab22d-290">При конфликте квот с помощью команды PowerShell создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ab22d-290">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="ab22d-291">Чтобы устранить эту ошибку, измените удаленную команду так, чтобы она соответствовала квоте.</span><span class="sxs-lookup"><span data-stu-id="ab22d-291">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="ab22d-292">Или определите источник квоты, а затем увеличьте квоту, чтобы завершить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="ab22d-292">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="ab22d-293">Например, следующая команда увеличивает квоту размера объекта в конфигурации сеанса Microsoft. PowerShell на удаленном компьютере с 10 МБ (значение по умолчанию) до 11 МБ.</span><span class="sxs-lookup"><span data-stu-id="ab22d-293">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="ab22d-294">Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="ab22d-294">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="ab22d-295">Дополнительные сведения о WS-Management квотах см. в разделе [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="ab22d-295">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="ab22d-296">Устранение ошибок времени ожидания</span><span class="sxs-lookup"><span data-stu-id="ab22d-296">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="ab22d-297">Можно использовать время ожидания для защиты локального компьютера и удаленного компьютера от чрезмерного использования ресурсов, как случайных, так и вредоносных.</span><span class="sxs-lookup"><span data-stu-id="ab22d-297">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="ab22d-298">Если время ожидания задано как на локальном, так и на удаленном компьютере, PowerShell использует самые короткие параметры времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="ab22d-298">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="ab22d-299">В базовой конфигурации доступны следующие тайм-ауты.</span><span class="sxs-lookup"><span data-stu-id="ab22d-299">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="ab22d-300">Поставщик WSMan (WSMan:) предоставляет несколько параметров времени ожидания на стороне клиента и службы, например параметр **макстимеаутмс** в `WSMan:<ComputerName>` узле и параметры **енумератионтимеаутмс** и **макспаккетретриевалтимесекондс** в `WSMan:<ComputerName>\Service` узле.</span><span class="sxs-lookup"><span data-stu-id="ab22d-300">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="ab22d-301">Защитить локальный компьютер можно с помощью параметров **канцелтимеаут**, **IdleTimeout**, **OpenTimeout** и **OperationTimeout** `New-PSSessionOption` командлета и `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="ab22d-301">You can protect the local computer by using the **CancelTimeout**, **IdleTimeout**, **OpenTimeout**, and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="ab22d-302">Кроме того, можно защитить удаленный компьютер, задавая значения времени ожидания программным способом в конфигурации сеанса для сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab22d-302">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="ab22d-303">Если значение времени ожидания не позволяет завершить операцию, PowerShell завершает операцию и создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ab22d-303">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="ab22d-304">Чтобы устранить эту ошибку, измените команду для завершения в течение интервала времени ожидания или определите источник предельного времени ожидания и Увеличьте интервал времени ожидания, чтобы завершить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="ab22d-304">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="ab22d-305">Например, следующие команды используют `New-PSSessionOption` командлет для создания объекта параметра сеанса со значением **OperationTimeout** , равным 4 минутам (в мс), а затем используйте объект параметра сеанса для создания удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="ab22d-305">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="ab22d-306">Дополнительные сведения об истечении времени ожидания WS-Management см. в разделе справки по поставщику WSMan (тип `Get-Help WSMan` ).</span><span class="sxs-lookup"><span data-stu-id="ab22d-306">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="ab22d-307">Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="ab22d-307">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="ab22d-308">Устранение неполадок при неотвечающем взаимодействиях</span><span class="sxs-lookup"><span data-stu-id="ab22d-308">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="ab22d-309">В этом разделе обсуждаются проблемы удаленного взаимодействия, препятствующие выполнению команды и предотвращению или задержке возврата командной строки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab22d-309">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="ab22d-310">Прерывание команды</span><span class="sxs-lookup"><span data-stu-id="ab22d-310">How to interrupt a command</span></span>

<span data-ttu-id="ab22d-311">Некоторые программы Windows, такие как программы с пользовательским интерфейсом, консольные приложения, запрашивающие ввод, и консольные приложения, использующие API консоли Win32, не работают должным образом на удаленном узле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab22d-311">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="ab22d-312">При использовании этих программ может возникнуть непредвиденное поведение, например отсутствие выходных данных, частичный вывод или удаленная команда, которая не завершена.</span><span class="sxs-lookup"><span data-stu-id="ab22d-312">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="ab22d-313">Чтобы завершить работу программы, не отвечающей, введите <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ab22d-313">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="ab22d-314">Чтобы просмотреть сообщения об ошибках, которые могли быть получены, введите `$error` локальный узел и удаленный сеанс.</span><span class="sxs-lookup"><span data-stu-id="ab22d-314">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="ab22d-315">Восстановление после сбоя операции</span><span class="sxs-lookup"><span data-stu-id="ab22d-315">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="ab22d-316">Эта ошибка возвращается в случае завершения операции до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="ab22d-316">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="ab22d-317">Как правило, это происходит, когда служба WinRM останавливается или перезапускается во время выполнения других операций WinRM.</span><span class="sxs-lookup"><span data-stu-id="ab22d-317">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="ab22d-318">Чтобы устранить эту проблему, убедитесь, что служба WinRM запущена, и повторите команду.</span><span class="sxs-lookup"><span data-stu-id="ab22d-318">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="ab22d-319">Запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="ab22d-319">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="ab22d-320">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab22d-320">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="ab22d-321">Повторно выполните команду, вызвавшую ошибку.</span><span class="sxs-lookup"><span data-stu-id="ab22d-321">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="ab22d-322">Ограничения Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="ab22d-322">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="ab22d-323">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="ab22d-323">Authentication</span></span>

<span data-ttu-id="ab22d-324">В macOS работает только обычная проверка подлинности, и попытка использовать другие схемы проверки подлинности может привести к сбою процесса.</span><span class="sxs-lookup"><span data-stu-id="ab22d-324">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="ab22d-325">Ознакомьтесь с инструкциями по [проверке подлинности OMI](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .</span><span class="sxs-lookup"><span data-stu-id="ab22d-325">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab22d-326">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="ab22d-326">SEE ALSO</span></span>

[<span data-ttu-id="ab22d-327">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab22d-327">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="ab22d-328">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab22d-328">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="ab22d-329">Import-Module</span><span class="sxs-lookup"><span data-stu-id="ab22d-329">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="ab22d-330">about_Remote</span><span class="sxs-lookup"><span data-stu-id="ab22d-330">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="ab22d-331">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="ab22d-331">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="ab22d-332">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="ab22d-332">about_Remote_Variables</span></span>](about_Remote_Variables.md)
