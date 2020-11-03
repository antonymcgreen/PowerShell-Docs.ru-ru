---
description: Описывает устранение неполадок удаленных операций в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Сведения об удаленной диагностике
ms.openlocfilehash: acf4f86d8c20f5a8059be48623255696afabbefb
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "93233309"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="34bcf-104">Об устранении неполадок удаленного поиска</span><span class="sxs-lookup"><span data-stu-id="34bcf-104">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="34bcf-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="34bcf-105">Short description</span></span>
<span data-ttu-id="34bcf-106">Описывает устранение неполадок удаленных операций в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34bcf-106">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="34bcf-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="34bcf-107">Long description</span></span>

<span data-ttu-id="34bcf-108">В этом разделе описываются некоторые проблемы, которые могут возникнуть при использовании функций удаленного взаимодействия PowerShell, основанных на технологии WS-Management и предлагающих решения этих проблем.</span><span class="sxs-lookup"><span data-stu-id="34bcf-108">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="34bcf-109">Прежде чем использовать удаленное взаимодействие PowerShell, ознакомьтесь со статьей [about_Remote](about_remote.md) и [about_Remote_Requirements](about_Remote_Requirements.md) , где приведены рекомендации по настройке и базовому использованию.</span><span class="sxs-lookup"><span data-stu-id="34bcf-109">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="34bcf-110">Кроме того, разделы справки по каждому из командлетов удаленного взаимодействия, в особенности описания параметров, содержат полезную информацию, которая поможет избежать проблем.</span><span class="sxs-lookup"><span data-stu-id="34bcf-110">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="34bcf-111">Чтобы просмотреть или изменить параметры локального компьютера на диске WSMan:, включая изменения в конфигурациях сеансов, доверенных узлах, портах или прослушивателях, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-111">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="34bcf-112">Устранение неполадок разрешений и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="34bcf-112">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="34bcf-113">В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с разрешениями пользователя и компьютера и требованиями удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="34bcf-113">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="34bcf-114">Запуск от имени администратора</span><span class="sxs-lookup"><span data-stu-id="34bcf-114">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="34bcf-115">Чтобы запустить удаленный сеанс на локальном компьютере или просмотреть или изменить параметры для локального компьютера на диске WSMan:, включая изменения в конфигурациях сеансов, доверенных узлах, портах или прослушивателях, запустите Windows PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-115">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="34bcf-116">Чтобы запустить Windows PowerShell с параметром **Запуск от имени администратора** , выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34bcf-116">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="34bcf-117">Щелкните правой кнопкой мыши значок Windows PowerShell (интегрированная среда сценариев Windows PowerShell) и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="34bcf-117">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator**.</span></span>

  <span data-ttu-id="34bcf-118">Для запуска Windows PowerShell с параметром **Запуск от имени администратора** в Windows 7 и windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="34bcf-118">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="34bcf-119">На панели задач Windows щелкните правой кнопкой мыши значок Windows PowerShell и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="34bcf-119">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator**.</span></span>

  <span data-ttu-id="34bcf-120">В Windows Server 2008 R2 значок Windows PowerShell закреплен на панели задач по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34bcf-120">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="34bcf-121">Как включить удаленное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="34bcf-121">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="34bcf-122">Для включения отправки удаленных команд на компьютере не требуется настраивать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="34bcf-122">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="34bcf-123">Однако для получения удаленных команд на компьютере должна быть включена служба удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34bcf-123">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="34bcf-124">Включение включает запуск службы WinRM, задание для типа запуска службы WinRM значения автоматически, создание прослушивателей для соединений HTTP и HTTPS и создание конфигураций сеансов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34bcf-124">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="34bcf-125">Удаленное взаимодействие Windows PowerShell включено в Windows Server 2012 и более новых выпусках Windows Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34bcf-125">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="34bcf-126">Во всех остальных системах выполните командлет, `Enable-PSRemoting` чтобы включить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="34bcf-126">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="34bcf-127">Можно также выполнить командлет, `Enable-PSRemoting` чтобы повторно включить удаленное взаимодействие на Windows server 2012 и более поздних выпусках Windows Server, если удаленное взаимодействие отключено.</span><span class="sxs-lookup"><span data-stu-id="34bcf-127">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="34bcf-128">Чтобы настроить компьютер для получения удаленных команд, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="34bcf-128">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="34bcf-129">Следующая команда включает все необходимые удаленные параметры, включает конфигурации сеанса и перезапускает службу WinRM, чтобы изменения были эффективными.</span><span class="sxs-lookup"><span data-stu-id="34bcf-129">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="34bcf-130">Чтобы отключить все запросы пользователя, введите:</span><span class="sxs-lookup"><span data-stu-id="34bcf-130">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="34bcf-131">Дополнительные сведения см. в разделе [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span><span class="sxs-lookup"><span data-stu-id="34bcf-131">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="34bcf-132">Как включить удаленное взаимодействие на предприятии</span><span class="sxs-lookup"><span data-stu-id="34bcf-132">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="34bcf-133">Чтобы разрешить одному компьютеру получать удаленные команды PowerShell и принимать подключения, используйте `Enable-PSRemoting` командлет.</span><span class="sxs-lookup"><span data-stu-id="34bcf-133">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="34bcf-134">Чтобы включить удаленное взаимодействие для нескольких компьютеров в Организации, можно использовать следующие масштабируемые параметры.</span><span class="sxs-lookup"><span data-stu-id="34bcf-134">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="34bcf-135">Чтобы настроить прослушиватели для удаленного взаимодействия, включите групповую политику **Разрешить автоматическую настройку прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-135">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="34bcf-136">Чтобы задать автоматический тип запуска служба удаленного управления Windows (WinRM) на нескольких компьютерах, используйте `Set-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="34bcf-136">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="34bcf-137">Чтобы включить исключение брандмауэра, воспользуйтесь групповой политикой **Брандмауэр Windows: разрешить исключения локальных портов** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-137">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="34bcf-138">Включение прослушивателей с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="34bcf-138">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="34bcf-139">Чтобы настроить прослушиватели для всех компьютеров в домене, включите политику **Разрешить автоматическую настройку прослушивателей** в следующем групповая политика пути:</span><span class="sxs-lookup"><span data-stu-id="34bcf-139">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="34bcf-140">Включите политику и укажите фильтры IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="34bcf-140">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="34bcf-141">Допускаются подстановочные знаки ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="34bcf-141">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="34bcf-142">Включение удаленного взаимодействия в общедоступных сетях</span><span class="sxs-lookup"><span data-stu-id="34bcf-142">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="34bcf-143">`Enable-PSRemoting`Командлет возвращает эту ошибку, если локальная сеть является общедоступной, а параметр **SkipNetworkProfileCheck** не используется в команде.</span><span class="sxs-lookup"><span data-stu-id="34bcf-143">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="34bcf-144">В серверных версиях Windows работает `Enable-PSRemoting` на всех типах сетевых расположений.</span><span class="sxs-lookup"><span data-stu-id="34bcf-144">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="34bcf-145">Он создает правила брандмауэра, разрешающие удаленный доступ к частным и доменным (домашним и рабочим) сетям.</span><span class="sxs-lookup"><span data-stu-id="34bcf-145">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="34bcf-146">Для общедоступных сетей он создает правила брандмауэра, разрешающие удаленный доступ из той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="34bcf-146">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="34bcf-147">В клиентских версиях Windows работает `Enable-PSRemoting` в частных и доменных сетях.</span><span class="sxs-lookup"><span data-stu-id="34bcf-147">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="34bcf-148">По умолчанию он завершается сбоем в общедоступных сетях, но если вы используете параметр **SkipNetworkProfileCheck** , то `Enable-PSRemoting` завершается и создается правило брандмауэра, разрешающее трафик из той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="34bcf-148">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="34bcf-149">Чтобы удалить ограничение локальной подсети в общедоступных сетях и разрешить удаленный доступ из любого расположения, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34bcf-149">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="34bcf-150">`Set-NetFirewallRule`Командлет экспортируется модулем NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="34bcf-150">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="34bcf-151">В Windows PowerShell 2,0 на компьютерах под управлением серверных версий Windows `Enable-PSRemoting` создаются правила брандмауэра, обеспечивающие удаленный доступ к частным, доменным и общедоступным сетям.</span><span class="sxs-lookup"><span data-stu-id="34bcf-151">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="34bcf-152">На компьютерах с клиентскими версиями Windows `Enable-PSRemoting` создает правила брандмауэра, разрешающие удаленный доступ только в частных и доменных сетях.</span><span class="sxs-lookup"><span data-stu-id="34bcf-152">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="34bcf-153">Как включить исключение брандмауэра с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="34bcf-153">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="34bcf-154">Чтобы включить исключение брандмауэра на всех компьютерах в домене, включите политику **брандмауэра Windows: разрешить исключения локальных портов** в следующем групповая политика пути:</span><span class="sxs-lookup"><span data-stu-id="34bcf-154">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="34bcf-155">Эта политика позволяет членам группы администраторов на компьютере использовать **Брандмауэр Windows** на **панели управления** для создания исключения брандмауэра для службы Служба удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="34bcf-155">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="34bcf-156">Если конфигурация политики неверна, может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="34bcf-156">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="34bcf-157">Ошибка конфигурации в политике приводит к пустому значению свойства **листенингон** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-157">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="34bcf-158">Для проверки значения используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="34bcf-158">Use the following command to check the value.</span></span>

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

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="34bcf-159">Как задать тип запуска службы WinRM</span><span class="sxs-lookup"><span data-stu-id="34bcf-159">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="34bcf-160">Удаленное взаимодействие PowerShell зависит от службы служба удаленного управления Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="34bcf-160">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="34bcf-161">Служба должна быть запущена для поддержки удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="34bcf-161">The service must be running to support remote commands.</span></span>

<span data-ttu-id="34bcf-162">В серверных версиях Windows тип запуска службы служба удаленного управления Windows (WinRM) — автоматически.</span><span class="sxs-lookup"><span data-stu-id="34bcf-162">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="34bcf-163">Однако в клиентских версиях Windows служба WinRM по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="34bcf-163">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="34bcf-164">Чтобы задать тип запуска службы на удаленном компьютере, используйте `Set-Service` командлет.</span><span class="sxs-lookup"><span data-stu-id="34bcf-164">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="34bcf-165">Чтобы выполнить команду на нескольких компьютерах, можно создать текстовый файл или CSV-файл с именами компьютеров.</span><span class="sxs-lookup"><span data-stu-id="34bcf-165">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="34bcf-166">Например, следующие команды получают список имен компьютеров из `Servers.txt` файла, а затем задает для всех компьютеров **Автоматический** тип запуска службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="34bcf-166">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic**.</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="34bcf-167">Чтобы просмотреть результаты, используйте `Get-WMIObject` командлет с объектом **Win32_Service** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-167">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="34bcf-168">Дополнительные сведения см. в разделе [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span><span class="sxs-lookup"><span data-stu-id="34bcf-168">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="34bcf-169">Повторное создание конфигураций сеансов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="34bcf-169">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="34bcf-170">Чтобы подключиться к локальному компьютеру и выполнить команды удаленно, локальный компьютер должен включать конфигурации сеанса для удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="34bcf-170">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="34bcf-171">При использовании `Enable-PSRemoting` он создает конфигурации сеансов по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-171">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="34bcf-172">Удаленные пользователи используют эти конфигурации сеанса каждый раз, когда удаленная команда не включает параметр **configurationName** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-172">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="34bcf-173">Если конфигурации по умолчанию на компьютере не зарегистрированы или удалены, используйте `Enable-PSRemoting` командлет для их повторного создания.</span><span class="sxs-lookup"><span data-stu-id="34bcf-173">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="34bcf-174">Этот командлет можно использовать многократно.</span><span class="sxs-lookup"><span data-stu-id="34bcf-174">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="34bcf-175">Если функция уже настроена, она не создает ошибок.</span><span class="sxs-lookup"><span data-stu-id="34bcf-175">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="34bcf-176">При изменении конфигураций сеансов по умолчанию и необходимости восстановления исходных конфигураций сеансов по умолчанию используйте `Unregister-PSSessionConfiguration` командлет для удаления измененных конфигураций сеанса, а затем используйте `Enable-PSRemoting` командлет для их восстановления.</span><span class="sxs-lookup"><span data-stu-id="34bcf-176">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="34bcf-177">`Enable-PSRemoting` не изменяет существующие конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="34bcf-177">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="34bcf-178">При `Enable-PSRemoting` восстановлении конфигурации сеанса по умолчанию не создаются явные дескрипторы безопасности для конфигураций.</span><span class="sxs-lookup"><span data-stu-id="34bcf-178">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="34bcf-179">Вместо этого конфигурации наследуют дескриптор безопасности Рутсддл, который является безопасным по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34bcf-179">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="34bcf-180">Чтобы просмотреть дескриптор безопасности Рутсддл, введите:</span><span class="sxs-lookup"><span data-stu-id="34bcf-180">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="34bcf-181">Чтобы изменить Рутсддл, используйте `Set-Item` командлет на диске WSMan:.</span><span class="sxs-lookup"><span data-stu-id="34bcf-181">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="34bcf-182">Чтобы изменить дескриптор безопасности конфигурации сеанса, используйте `Set-PSSessionConfiguration` командлет с параметрами **SecurityDescriptorSDDL** или **ShowSecurityDescriptorUI** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-182">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="34bcf-183">Дополнительные сведения о диске WSMan: см. в разделе справки по поставщику WSMan ("Get-Help WSMAN").</span><span class="sxs-lookup"><span data-stu-id="34bcf-183">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="34bcf-184">Как указать учетные данные администратора</span><span class="sxs-lookup"><span data-stu-id="34bcf-184">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="34bcf-185">Чтобы создать сеанс PSSession или выполнить команды на удаленном компьютере, по умолчанию текущий пользователь должен быть членом группы администраторов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-185">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="34bcf-186">Учетные данные иногда требуются даже при входе текущего пользователя в учетную запись, которая является членом группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="34bcf-186">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="34bcf-187">Если текущий пользователь является членом группы "Администраторы" на удаленном компьютере или может предоставить учетные данные члена группы "Администраторы", используйте параметр **Credential** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлета или, чтобы подключиться удаленно.</span><span class="sxs-lookup"><span data-stu-id="34bcf-187">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="34bcf-188">Например, следующая команда предоставляет учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="34bcf-188">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="34bcf-189">Дополнительные сведения о параметре **Credential** см. в разделе [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) или [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span><span class="sxs-lookup"><span data-stu-id="34bcf-189">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="34bcf-190">Включение удаленного взаимодействия для пользователей, не являющихся администраторами</span><span class="sxs-lookup"><span data-stu-id="34bcf-190">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="34bcf-191">Чтобы установить PSSession или выполнить команду на удаленном компьютере, пользователь должен иметь разрешение на использование конфигураций сеансов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-191">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="34bcf-192">По умолчанию разрешения на использование конфигураций сеансов по умолчанию имеют только члены группы «Администраторы» на компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-192">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="34bcf-193">Таким образом, только члены группы «Администраторы» могут подключаться к компьютеру удаленно.</span><span class="sxs-lookup"><span data-stu-id="34bcf-193">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="34bcf-194">Чтобы разрешить другим пользователям подключаться к локальному компьютеру, предоставьте пользователю разрешения на выполнение конфигураций сеансов по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-194">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="34bcf-195">Следующая команда открывает страницу свойств, которая позволяет изменить дескриптор безопасности конфигурации сеанса Microsoft. PowerShell по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-195">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="34bcf-196">Дополнительные сведения см. в разделе [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="34bcf-196">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="34bcf-197">Включение удаленного взаимодействия для администраторов в других доменах</span><span class="sxs-lookup"><span data-stu-id="34bcf-197">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="34bcf-198">Если пользователь в другом домене входит в группу администраторов на локальном компьютере, он не может удаленно подключиться к локальному компьютеру с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="34bcf-198">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="34bcf-199">По умолчанию удаленные подключения из других доменов выполняются только с маркерами прав обычного пользователя.</span><span class="sxs-lookup"><span data-stu-id="34bcf-199">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="34bcf-200">Однако можно использовать запись реестра **LocalAccountTokenFilterPolicy** , чтобы изменить поведение по умолчанию и разрешить удаленным пользователям, которые являются членами группы "Администраторы", работать с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="34bcf-200">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="34bcf-201">Запись **LocalAccountTokenFilterPolicy** отключает удаленные ограничения контроля учетных записей (UAC) для всех пользователей всех затронутых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="34bcf-201">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="34bcf-202">Прежде чем изменять политику, внимательно изучите последствия этого параметра.</span><span class="sxs-lookup"><span data-stu-id="34bcf-202">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="34bcf-203">Чтобы изменить политику, используйте следующую команду, чтобы присвоить параметру реестра **LocalAccountTokenFilterPolicy** значение 1.</span><span class="sxs-lookup"><span data-stu-id="34bcf-203">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="34bcf-204">Использование IP-адреса в удаленной команде</span><span class="sxs-lookup"><span data-stu-id="34bcf-204">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="34bcf-205">Параметр **ComputerName** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, и принимает IP-адрес как допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="34bcf-205">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="34bcf-206">Однако так как проверка подлинности Kerberos не поддерживает IP-адреса, проверка подлинности NTLM используется по умолчанию при указании IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="34bcf-206">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="34bcf-207">При использовании проверки подлинности NTLM для удаленного взаимодействия требуется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="34bcf-207">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="34bcf-208">Настройте компьютер для транспорта HTTPS или добавьте IP-адреса удаленных компьютеров в список TrustedHosts на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-208">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="34bcf-209">Используйте параметр **Credential** во всех удаленных командах.</span><span class="sxs-lookup"><span data-stu-id="34bcf-209">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="34bcf-210">Это необходимо даже при отправке учетных данных текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="34bcf-210">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="34bcf-211">Удаленное подключение с компьютера, созданного в Рабочей группе</span><span class="sxs-lookup"><span data-stu-id="34bcf-211">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="34bcf-212">Если локальный компьютер не входит в домен, для удаленного взаимодействия требуется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="34bcf-212">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="34bcf-213">Настройте компьютер для транспорта HTTPS или добавьте имена удаленных компьютеров в список TrustedHosts на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-213">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="34bcf-214">Убедитесь, что пароль установлен на компьютере рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="34bcf-214">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="34bcf-215">Если пароль не задан или значение пароля пусто, то нельзя выполнять удаленные команды.</span><span class="sxs-lookup"><span data-stu-id="34bcf-215">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="34bcf-216">Чтобы задать пароль для учетной записи пользователя, используйте учетные записи пользователей в панели управления.</span><span class="sxs-lookup"><span data-stu-id="34bcf-216">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="34bcf-217">Используйте параметр **Credential** во всех удаленных командах.</span><span class="sxs-lookup"><span data-stu-id="34bcf-217">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="34bcf-218">Это необходимо даже при отправке учетных данных текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="34bcf-218">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="34bcf-219">Добавление компьютера в список надежных узлов</span><span class="sxs-lookup"><span data-stu-id="34bcf-219">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="34bcf-220">Элемент TrustedHosts может содержать разделенный запятыми список имен компьютеров, IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="34bcf-220">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="34bcf-221">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="34bcf-221">Wildcards are permitted.</span></span>

<span data-ttu-id="34bcf-222">Чтобы просмотреть или изменить список надежных узлов, используйте диск WSMan:.</span><span class="sxs-lookup"><span data-stu-id="34bcf-222">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="34bcf-223">Элемент Трустедхост находится в `WSMan:\localhost\Client` узле.</span><span class="sxs-lookup"><span data-stu-id="34bcf-223">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="34bcf-224">Только члены группы "Администраторы" на компьютере имеют разрешение на изменение списка доверенных узлов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-224">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="34bcf-225">Внимание! значение, заданное для элемента TrustedHosts, влияет на всех пользователей компьютера.</span><span class="sxs-lookup"><span data-stu-id="34bcf-225">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="34bcf-226">Чтобы просмотреть список доверенных узлов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34bcf-226">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="34bcf-227">Можно также использовать `Set-Location` командлет (Alias = CD) для перемещения по адресу WSMan: Drive в расположение.</span><span class="sxs-lookup"><span data-stu-id="34bcf-227">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="34bcf-228">Пример:</span><span class="sxs-lookup"><span data-stu-id="34bcf-228">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="34bcf-229">Чтобы добавить все компьютеры в список доверенных узлов, используйте следующую команду, которая помещает в ComputerName значение \* (ALL).</span><span class="sxs-lookup"><span data-stu-id="34bcf-229">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="34bcf-230">Можно также использовать подстановочный знак ( `*` ) для добавления всех компьютеров в определенном домене в список доверенных узлов.</span><span class="sxs-lookup"><span data-stu-id="34bcf-230">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="34bcf-231">Например, следующая команда добавляет все компьютеры из домена Fabrikam в список доверенных узлов.</span><span class="sxs-lookup"><span data-stu-id="34bcf-231">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="34bcf-232">Чтобы добавить имена определенных компьютеров в список доверенных узлов, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="34bcf-232">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="34bcf-233">где каждое значение `<ComputerName>` должно иметь следующий формат:</span><span class="sxs-lookup"><span data-stu-id="34bcf-233">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="34bcf-234">Пример:</span><span class="sxs-lookup"><span data-stu-id="34bcf-234">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="34bcf-235">Чтобы добавить имя компьютера в существующий список доверенных узлов, сначала сохраните текущее значение в переменной, а затем задайте в качестве значения список с разделителями-запятыми, включающий текущие и новые значения.</span><span class="sxs-lookup"><span data-stu-id="34bcf-235">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="34bcf-236">Например, чтобы добавить компьютер Server01 в существующий список доверенных узлов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34bcf-236">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="34bcf-237">Чтобы добавить IP-адреса определенных компьютеров в список доверенных узлов, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="34bcf-237">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="34bcf-238">Пример:</span><span class="sxs-lookup"><span data-stu-id="34bcf-238">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="34bcf-239">Чтобы добавить компьютер в список TrustedHosts на удаленном компьютере, используйте `Connect-WSMan` командлет, чтобы добавить узел для удаленного компьютера на диск WSMan: на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="34bcf-239">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="34bcf-240">Затем используйте `Set-Item` команду, чтобы добавить компьютер.</span><span class="sxs-lookup"><span data-stu-id="34bcf-240">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="34bcf-241">Дополнительные сведения о `Connect-WSMan` командлете см. в разделе [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="34bcf-241">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="34bcf-242">Устранение проблем с конфигурацией компьютера</span><span class="sxs-lookup"><span data-stu-id="34bcf-242">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="34bcf-243">В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с определенными конфигурациями компьютера, домена или предприятия.</span><span class="sxs-lookup"><span data-stu-id="34bcf-243">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="34bcf-244">Настройка удаленного взаимодействия на альтернативных портах</span><span class="sxs-lookup"><span data-stu-id="34bcf-244">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="34bcf-245">Удаленное взаимодействие PowerShell по умолчанию использует порт 80 для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="34bcf-245">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="34bcf-246">Порт по умолчанию используется каждый раз, когда пользователь не задает параметры **ConnectionURI** или **Port** в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="34bcf-246">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="34bcf-247">Чтобы изменить порт по умолчанию, используемый PowerShell, используйте `Set-Item` командлет на диске WSMan:, чтобы изменить значение порта на конечном узле прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="34bcf-247">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="34bcf-248">Например, следующая команда изменяет порт по умолчанию на 8080.</span><span class="sxs-lookup"><span data-stu-id="34bcf-248">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="34bcf-249">Настройка удаленного взаимодействия с помощью прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="34bcf-249">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="34bcf-250">Поскольку удаленное взаимодействие PowerShell использует протокол HTTP, на него влияют параметры HTTP-прокси.</span><span class="sxs-lookup"><span data-stu-id="34bcf-250">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="34bcf-251">В организациях, имеющих прокси-серверы, пользователи не могут напрямую получить доступ к удаленному компьютеру PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34bcf-251">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="34bcf-252">Чтобы устранить эту проблему, используйте параметры настройки прокси-сервера в удаленной команде.</span><span class="sxs-lookup"><span data-stu-id="34bcf-252">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="34bcf-253">Доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="34bcf-253">The following settings are available:</span></span>

- <span data-ttu-id="34bcf-254">проксякцесстипе</span><span class="sxs-lookup"><span data-stu-id="34bcf-254">ProxyAccessType</span></span>
- <span data-ttu-id="34bcf-255">проксяусентикатион</span><span class="sxs-lookup"><span data-stu-id="34bcf-255">ProxyAuthentication</span></span>
- <span data-ttu-id="34bcf-256">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="34bcf-256">ProxyCredential</span></span>

<span data-ttu-id="34bcf-257">Чтобы задать эти параметры для определенной команды, выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="34bcf-257">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="34bcf-258">Используйте параметры **проксякцесстипе** , **проксяусентикатион** и **ProxyCredential** `New-PSSessionOption` командлета, чтобы создать объект параметров сеанса с параметрами прокси-сервера для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="34bcf-258">Use the **ProxyAccessType** , **ProxyAuthentication** , and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="34bcf-259">Сохраните объект параметра — это переменная.</span><span class="sxs-lookup"><span data-stu-id="34bcf-259">Save the option object is a variable.</span></span>

1. <span data-ttu-id="34bcf-260">Используйте переменную, содержащую объект Option, в качестве значения параметра **SessionOption** `New-PSSession` `Enter-PSSession` команды, или `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="34bcf-260">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="34bcf-261">Например, следующая команда создает объект параметра сеанса с параметрами сеанса прокси-сервера, а затем использует объект для создания удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="34bcf-261">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="34bcf-262">Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="34bcf-262">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="34bcf-263">Чтобы задать эти параметры для всех удаленных команд в текущем сеансе, используйте объект параметра, который `New-PSSessionOption` создает в значении `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="34bcf-263">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="34bcf-264">Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="34bcf-264">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="34bcf-265">Чтобы задать эти параметры для всех удаленных команд, всех сеансов PowerShell на локальном компьютере, добавьте `$PSSessionOption` переменную предпочтений в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34bcf-265">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="34bcf-266">Дополнительные сведения о профилях PowerShell см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="34bcf-266">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="34bcf-267">Обнаружение 32-разрядного сеанса на 64-разрядном компьютере</span><span class="sxs-lookup"><span data-stu-id="34bcf-267">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="34bcf-268">Если удаленный компьютер работает под управлением 64-разрядной версии Windows, а удаленная команда использует конфигурацию с 32-битным сеансом, например Microsoft. PowerShell32, служба удаленного управления Windows (WinRM) загружает процесс WOW64 и Windows автоматически перенаправляет все ссылки на `$env:Windir\System32` каталог в `$env:Windir\SysWOW64` каталог.</span><span class="sxs-lookup"><span data-stu-id="34bcf-268">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="34bcf-269">В результате, если вы попытаетесь использовать в каталоге System32 средства, не имеющие аналога в каталоге SysWow64, например `Defrag.exe` , эти средства не найдены в каталоге.</span><span class="sxs-lookup"><span data-stu-id="34bcf-269">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="34bcf-270">Чтобы найти архитектуру процессора, используемую в сеансе, используйте значение переменной среды **PROCESSOR_ARCHITECTURE** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-270">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="34bcf-271">Следующая команда находит архитектуру процессора для сеанса в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="34bcf-271">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="34bcf-272">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="34bcf-272">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="34bcf-273">Устранение проблем политики и предпочтений</span><span class="sxs-lookup"><span data-stu-id="34bcf-273">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="34bcf-274">В этом разделе обсуждаются проблемы удаленного взаимодействия, связанные с политиками и предпочтениями, заданными на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="34bcf-274">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="34bcf-275">Изменение политики выполнения для Import-PSSession и Import-Module</span><span class="sxs-lookup"><span data-stu-id="34bcf-275">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="34bcf-276">`Import-PSSession` `Export-PSSession` Командлеты и создают модули, которые содержат неподписанные файлы скриптов и файлы форматирования.</span><span class="sxs-lookup"><span data-stu-id="34bcf-276">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="34bcf-277">Чтобы импортировать модули, созданные этими командлетами, с помощью `Import-PSSession` или `Import-Module` , политика выполнения в текущем сеансе не может быть ограничена или AllSigned.</span><span class="sxs-lookup"><span data-stu-id="34bcf-277">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="34bcf-278">Дополнительные сведения о политиках выполнения PowerShell см. в разделе [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="34bcf-278">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="34bcf-279">Чтобы импортировать модули без изменения политики выполнения для локального компьютера, установленного в реестре, используйте параметр **Scope** параметра, `Set-ExecutionPolicy` чтобы задать менее ограниченную политику выполнения для одного процесса.</span><span class="sxs-lookup"><span data-stu-id="34bcf-279">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="34bcf-280">Например, следующая команда запускает процесс с `RemoteSigned` политикой выполнения.</span><span class="sxs-lookup"><span data-stu-id="34bcf-280">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="34bcf-281">Изменение политики выполнения влияет только на текущий процесс и не изменяет параметр реестра PowerShell **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-281">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="34bcf-282">Кроме того, с помощью параметра **ExecutionPolicy** можно `PowerShell.exe` запустить один сеанс с менее ограниченной политикой выполнения.</span><span class="sxs-lookup"><span data-stu-id="34bcf-282">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="34bcf-283">Дополнительные сведения о политиках выполнения см. в разделе [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="34bcf-283">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="34bcf-284">Для получения дополнительных сведений введите `PowerShell.exe -?`.</span><span class="sxs-lookup"><span data-stu-id="34bcf-284">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="34bcf-285">Как задать и изменить квоты</span><span class="sxs-lookup"><span data-stu-id="34bcf-285">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="34bcf-286">Квоты можно использовать для защиты локального компьютера и удаленного компьютера от чрезмерного использования ресурсов, как случайных, так и вредоносных.</span><span class="sxs-lookup"><span data-stu-id="34bcf-286">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="34bcf-287">В базовой конфигурации доступны следующие квоты.</span><span class="sxs-lookup"><span data-stu-id="34bcf-287">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="34bcf-288">Поставщик WSMan (WSMan:) предоставляет несколько параметров квот, таких как параметры **максенвелопесизекб** и **макспровидеррекуестс** в узле, `WSMan:<ComputerName>` а также параметры **максконкуррентоператионс** , **свойств maxconcurrentoperationsperuser** и **MaxConnections** в `WSMan:<ComputerName>\Service` узле.</span><span class="sxs-lookup"><span data-stu-id="34bcf-288">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations** , **MaxConcurrentOperationsPerUser** , and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="34bcf-289">Защитить локальный компьютер можно с помощью параметров **максимумрецеиведдатасизеперкомманд** и **максимумрецеиведобжектсизе** `New-PSSessionOption` командлета и `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="34bcf-289">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="34bcf-290">Защитить удаленный компьютер можно, добавив ограничения в конфигурации сеанса, например с помощью параметров **максимумрецеиведдатасизеперкоммандмб** и **максимумрецеиведобжектсиземб** `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="34bcf-290">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="34bcf-291">При конфликте квот с помощью команды PowerShell создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="34bcf-291">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="34bcf-292">Чтобы устранить эту ошибку, измените удаленную команду так, чтобы она соответствовала квоте.</span><span class="sxs-lookup"><span data-stu-id="34bcf-292">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="34bcf-293">Или определите источник квоты, а затем увеличьте квоту, чтобы завершить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="34bcf-293">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="34bcf-294">Например, следующая команда увеличивает квоту размера объекта в конфигурации сеанса Microsoft. PowerShell на удаленном компьютере с 10 МБ (значение по умолчанию) до 11 МБ.</span><span class="sxs-lookup"><span data-stu-id="34bcf-294">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="34bcf-295">Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="34bcf-295">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="34bcf-296">Дополнительные сведения о WS-Management квотах см. в разделе [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="34bcf-296">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="34bcf-297">Устранение ошибок времени ожидания</span><span class="sxs-lookup"><span data-stu-id="34bcf-297">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="34bcf-298">Можно использовать время ожидания для защиты локального компьютера и удаленного компьютера от чрезмерного использования ресурсов, как случайных, так и вредоносных.</span><span class="sxs-lookup"><span data-stu-id="34bcf-298">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="34bcf-299">Если время ожидания задано как на локальном, так и на удаленном компьютере, PowerShell использует самые короткие параметры времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="34bcf-299">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="34bcf-300">В базовой конфигурации доступны следующие тайм-ауты.</span><span class="sxs-lookup"><span data-stu-id="34bcf-300">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="34bcf-301">Поставщик WSMan (WSMan:) предоставляет несколько параметров времени ожидания на стороне клиента и службы, например параметр **макстимеаутмс** в `WSMan:<ComputerName>` узле и параметры **енумератионтимеаутмс** и **макспаккетретриевалтимесекондс** в `WSMan:<ComputerName>\Service` узле.</span><span class="sxs-lookup"><span data-stu-id="34bcf-301">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="34bcf-302">Защитить локальный компьютер можно с помощью параметров **канцелтимеаут** , **IdleTimeout** , **OpenTimeout** и **OperationTimeout** `New-PSSessionOption` командлета и `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="34bcf-302">You can protect the local computer by using the **CancelTimeout** , **IdleTimeout** , **OpenTimeout** , and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="34bcf-303">Кроме того, можно защитить удаленный компьютер, задавая значения времени ожидания программным способом в конфигурации сеанса для сеанса.</span><span class="sxs-lookup"><span data-stu-id="34bcf-303">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="34bcf-304">Если значение времени ожидания не позволяет завершить операцию, PowerShell завершает операцию и создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="34bcf-304">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="34bcf-305">Чтобы устранить эту ошибку, измените команду для завершения в течение интервала времени ожидания или определите источник предельного времени ожидания и Увеличьте интервал времени ожидания, чтобы завершить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="34bcf-305">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="34bcf-306">Например, следующие команды используют `New-PSSessionOption` командлет для создания объекта параметра сеанса со значением **OperationTimeout** , равным 4 минутам (в мс), а затем используйте объект параметра сеанса для создания удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="34bcf-306">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="34bcf-307">Дополнительные сведения об истечении времени ожидания WS-Management см. в разделе справки по поставщику WSMan (тип `Get-Help WSMan` ).</span><span class="sxs-lookup"><span data-stu-id="34bcf-307">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="34bcf-308">Дополнительные сведения о `New-PSSessionOption` командлете см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="34bcf-308">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="34bcf-309">Устранение неполадок при неотвечающем взаимодействиях</span><span class="sxs-lookup"><span data-stu-id="34bcf-309">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="34bcf-310">В этом разделе обсуждаются проблемы удаленного взаимодействия, препятствующие выполнению команды и предотвращению или задержке возврата командной строки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34bcf-310">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="34bcf-311">Прерывание команды</span><span class="sxs-lookup"><span data-stu-id="34bcf-311">How to interrupt a command</span></span>

<span data-ttu-id="34bcf-312">Некоторые программы Windows, такие как программы с пользовательским интерфейсом, консольные приложения, запрашивающие ввод, и консольные приложения, использующие API консоли Win32, не работают должным образом на удаленном узле PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34bcf-312">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="34bcf-313">При использовании этих программ может возникнуть непредвиденное поведение, например отсутствие выходных данных, частичный вывод или удаленная команда, которая не завершена.</span><span class="sxs-lookup"><span data-stu-id="34bcf-313">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="34bcf-314">Чтобы завершить работу программы, не отвечающей, введите <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="34bcf-314">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="34bcf-315">Чтобы просмотреть сообщения об ошибках, которые могли быть получены, введите `$error` локальный узел и удаленный сеанс.</span><span class="sxs-lookup"><span data-stu-id="34bcf-315">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="34bcf-316">Восстановление после сбоя операции</span><span class="sxs-lookup"><span data-stu-id="34bcf-316">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="34bcf-317">Эта ошибка возвращается в случае завершения операции до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="34bcf-317">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="34bcf-318">Как правило, это происходит, когда служба WinRM останавливается или перезапускается во время выполнения других операций WinRM.</span><span class="sxs-lookup"><span data-stu-id="34bcf-318">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="34bcf-319">Чтобы устранить эту проблему, убедитесь, что служба WinRM запущена, и повторите команду.</span><span class="sxs-lookup"><span data-stu-id="34bcf-319">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="34bcf-320">Запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="34bcf-320">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="34bcf-321">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34bcf-321">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="34bcf-322">Повторно выполните команду, вызвавшую ошибку.</span><span class="sxs-lookup"><span data-stu-id="34bcf-322">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="34bcf-323">Ограничения Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="34bcf-323">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="34bcf-324">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="34bcf-324">Authentication</span></span>

<span data-ttu-id="34bcf-325">В macOS работает только обычная проверка подлинности, и попытка использовать другие схемы проверки подлинности может привести к сбою процесса.</span><span class="sxs-lookup"><span data-stu-id="34bcf-325">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="34bcf-326">Ознакомьтесь с инструкциями по [проверке подлинности OMI](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .</span><span class="sxs-lookup"><span data-stu-id="34bcf-326">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="34bcf-327">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="34bcf-327">SEE ALSO</span></span>

[<span data-ttu-id="34bcf-328">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="34bcf-328">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="34bcf-329">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="34bcf-329">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="34bcf-330">Import-Module</span><span class="sxs-lookup"><span data-stu-id="34bcf-330">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="34bcf-331">about_Remote</span><span class="sxs-lookup"><span data-stu-id="34bcf-331">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="34bcf-332">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="34bcf-332">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="34bcf-333">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="34bcf-333">about_Remote_Variables</span></span>](about_Remote_Variables.md)
