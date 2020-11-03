---
description: Описание требований к системе и требований к конфигурации для выполнения удаленных команд в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: 63971aeaa92eb10a745f2a02e0c7cf00dbf65d8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232298"
---
# <a name="about-remote-requirements"></a><span data-ttu-id="ae456-104">Сведения о удаленных требованиях</span><span class="sxs-lookup"><span data-stu-id="ae456-104">About Remote Requirements</span></span>

## <a name="short-description"></a><span data-ttu-id="ae456-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ae456-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ae456-106">Описание требований к системе и требований к конфигурации для выполнения удаленных команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae456-106">Describes the system requirements and configuration requirements for running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ae456-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ae456-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ae456-108">В этом разделе описываются требования к системе, требования пользователей и требования к ресурсам для установки удаленных подключений и выполнения удаленных команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae456-108">This topic describes the system requirements, user requirements, and resource requirements for establishing remote connections and running remote commands in PowerShell.</span></span> <span data-ttu-id="ae456-109">В нем также приводятся инструкции по настройке удаленных операций.</span><span class="sxs-lookup"><span data-stu-id="ae456-109">It also provides instructions for configuring remote operations.</span></span>

<span data-ttu-id="ae456-110">Примечание. многие командлеты (включая командлеты Get-Service, Get-Process, Get-WMIObject, Get-EventLog и Get-WinEvent) получают объекты с удаленных компьютеров с помощью методов Microsoft .NET Framework для получения объектов.</span><span class="sxs-lookup"><span data-stu-id="ae456-110">Note: Many cmdlets (including the Get-Service, Get-Process, Get-WMIObject, Get-EventLog, and Get-WinEvent cmdlets) get objects from remote computers by using Microsoft .NET Framework methods to retrieve the objects.</span></span> <span data-ttu-id="ae456-111">Они не используют инфраструктуру удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae456-111">They do not use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="ae456-112">Требования, описанные в этом документе, не применяются к этим командлетам.</span><span class="sxs-lookup"><span data-stu-id="ae456-112">The requirements in this document do not apply to these cmdlets.</span></span>

<span data-ttu-id="ae456-113">Чтобы найти командлеты, имеющие параметр ComputerName, но не использующие удаленное взаимодействие Windows PowerShell, прочитайте описание параметра ComputerName командлетов.</span><span class="sxs-lookup"><span data-stu-id="ae456-113">To find the cmdlets that have a ComputerName parameter but do not use Windows PowerShell remoting, read the description of the ComputerName parameter of the cmdlets.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="ae456-114">ТРЕБОВАНИЯ К СИСТЕМЕ</span><span class="sxs-lookup"><span data-stu-id="ae456-114">SYSTEM REQUIREMENTS</span></span>

<span data-ttu-id="ae456-115">Для запуска удаленных сеансов в Windows PowerShell 3,0 на локальном и удаленном компьютерах должны быть выполнены следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ae456-115">To run remote sessions on Windows PowerShell 3.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="ae456-116">Windows PowerShell 3,0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ae456-116">Windows PowerShell 3.0 or later</span></span>
- <span data-ttu-id="ae456-117">Microsoft .NET Framework 4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ae456-117">The Microsoft .NET Framework 4 or later</span></span>
- <span data-ttu-id="ae456-118">Служба удаленного управления Windows 3,0</span><span class="sxs-lookup"><span data-stu-id="ae456-118">Windows Remote Management 3.0</span></span>

<span data-ttu-id="ae456-119">Для запуска удаленных сеансов в Windows PowerShell 2,0 на локальном и удаленном компьютерах должны быть выполнены следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ae456-119">To run remote sessions on Windows PowerShell 2.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="ae456-120">Windows PowerShell 2,0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ae456-120">Windows PowerShell 2.0 or later</span></span>
- <span data-ttu-id="ae456-121">Microsoft .NET Framework 2,0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ae456-121">The Microsoft .NET Framework 2.0 or later</span></span>
- <span data-ttu-id="ae456-122">Служба удаленного управления Windows 2,0</span><span class="sxs-lookup"><span data-stu-id="ae456-122">Windows Remote Management 2.0</span></span>

<span data-ttu-id="ae456-123">Можно создавать удаленные сеансы между компьютерами, на которых выполняется Windows PowerShell 2,0 и Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ae456-123">You can create remote sessions between computers running Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span> <span data-ttu-id="ae456-124">Однако функции, которые выполняются только в Windows PowerShell 3,0, такие как возможность отключения и повторного подключения к сеансам, доступны только в том случае, если оба компьютера работают под управлением Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ae456-124">However, features that run only on Windows PowerShell 3.0, such as the ability to disconnect and reconnect to sessions, are available only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="ae456-125">Чтобы узнать номер версии установленной версии PowerShell, используйте автоматическую переменную $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="ae456-125">To find the version number of an installed version of PowerShell, use the $PSVersionTable automatic variable.</span></span>

<span data-ttu-id="ae456-126">Служба удаленного управления Windows (WinRM) 3,0 и Microsoft .NET Framework 4 включены в Windows 8, Windows Server 2012 и более новые выпуски операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="ae456-126">Windows Remote Management (WinRM) 3.0 and Microsoft .NET Framework 4 are included in Windows 8, Windows Server 2012, and newer releases of the Windows operating system.</span></span> <span data-ttu-id="ae456-127">WinRM 3,0 входит в комплект Windows Management Framework 3,0 для старых операционных систем.</span><span class="sxs-lookup"><span data-stu-id="ae456-127">WinRM 3.0 is included in Windows Management Framework 3.0 for older operating systems.</span></span> <span data-ttu-id="ae456-128">Если на компьютере не установлена требуемая версия WinRM или платформа Microsoft .NET, установка завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="ae456-128">If the computer does not have the required version of WinRM or the Microsoft .NET Framework, the installation fails.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="ae456-129">РАЗРЕШЕНИЯ ПОЛЬЗОВАТЕЛЯ</span><span class="sxs-lookup"><span data-stu-id="ae456-129">USER PERMISSIONS</span></span>

<span data-ttu-id="ae456-130">Для создания удаленных сеансов и выполнения удаленных команд по умолчанию текущий пользователь должен быть членом группы "Администраторы" на удаленном компьютере или предоставлять учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="ae456-130">To create remote sessions and run remote commands, by default, the current user must be a member of the Administrators group on the remote computer or provide the credentials of an administrator.</span></span> <span data-ttu-id="ae456-131">В противном случае произойдет сбой команды.</span><span class="sxs-lookup"><span data-stu-id="ae456-131">Otherwise, the command fails.</span></span>

<span data-ttu-id="ae456-132">Разрешения, необходимые для создания сеансов и выполнения команд на удаленном компьютере (или в удаленном сеансе на локальном компьютере), устанавливаются конфигурацией сеанса (также называемой конечной точкой) на удаленном компьютере, к которому подключается сеанс.</span><span class="sxs-lookup"><span data-stu-id="ae456-132">The permissions required to create sessions and run commands on a remote computer (or in a remote session on the local computer) are established by the session configuration (also known as an "endpoint") on the remote computer to which the session connects.</span></span> <span data-ttu-id="ae456-133">В частности, дескриптор безопасности в конфигурации сеанса определяет, кто имеет доступ к конфигурации сеанса и кто может использовать его для подключения.</span><span class="sxs-lookup"><span data-stu-id="ae456-133">Specifically, the security descriptor on the session configuration determines who has access to the session configuration and who can use it to connect.</span></span>

<span data-ttu-id="ae456-134">Дескрипторы безопасности в конфигурациях сеансов по умолчанию, Microsoft. PowerShell, Microsoft. PowerShell32 и Microsoft. PowerShell. Workflow, разрешают доступ только членам группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="ae456-134">The security descriptors on the default session configurations, Microsoft.PowerShell, Microsoft.PowerShell32, and Microsoft.PowerShell.Workflow, allow access only to members of the Administrators group.</span></span>

<span data-ttu-id="ae456-135">Если у текущего пользователя нет разрешения на использование конфигурации сеанса, команда для выполнения команды (использующая временный сеанс) или создание постоянного сеанса на удаленном компьютере завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="ae456-135">If the current user doesn't have permission to use the session configuration, the command to run a command (which uses a temporary session) or create a persistent session on the remote computer fails.</span></span> <span data-ttu-id="ae456-136">Пользователь может использовать параметр ConfigurationName командлетов, которые создают сеансы, чтобы выбрать другую конфигурацию сеанса, если она доступна.</span><span class="sxs-lookup"><span data-stu-id="ae456-136">The user can use the ConfigurationName parameter of cmdlets that create sessions to select a different session configuration, if one is available.</span></span>

<span data-ttu-id="ae456-137">Члены группы "Администраторы" на компьютере могут определить, кто имеет разрешение на удаленное подключение к компьютеру, изменив дескрипторы безопасности в конфигурациях сеансов по умолчанию и создав новые конфигурации сеанса с разными дескрипторами безопасности.</span><span class="sxs-lookup"><span data-stu-id="ae456-137">Members of the Administrators group on a computer can determine who has permission to connect to the computer remotely by changing the security descriptors on the default session configurations and by creating new session configurations with different security descriptors.</span></span>

<span data-ttu-id="ae456-138">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ae456-138">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="windows-network-locations"></a><span data-ttu-id="ae456-139">СЕТЕВЫЕ РАСПОЛОЖЕНИЯ WINDOWS</span><span class="sxs-lookup"><span data-stu-id="ae456-139">WINDOWS NETWORK LOCATIONS</span></span>

<span data-ttu-id="ae456-140">Начиная с Windows PowerShell 3,0, командлет Enable-PSRemoting может включить удаленное взаимодействие на клиентских и серверных версиях Windows в частных, доменных и общедоступных сетях.</span><span class="sxs-lookup"><span data-stu-id="ae456-140">Beginning in Windows PowerShell 3.0, the Enable-PSRemoting cmdlet can enable remoting on client and server versions of Windows on private, domain, and public networks.</span></span>

<span data-ttu-id="ae456-141">В серверных версиях Windows с частными и доменными сетями командлет Enable-PSRemoting создает правила брандмауэра, которые допускают неограниченный удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="ae456-141">On server versions of Windows with private and domain networks, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span> <span data-ttu-id="ae456-142">Он также создает правило брандмауэра для общедоступных сетей, которое разрешает удаленный доступ только с компьютеров в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="ae456-142">It also creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="ae456-143">Это правило брандмауэра для локальной подсети включено по умолчанию для серверных версий Windows в общедоступных сетях, но Enable-PSRemoting повторно применяет правило, если оно было изменено или удалено.</span><span class="sxs-lookup"><span data-stu-id="ae456-143">This local subnet firewall rule is enabled by default on server versions of Windows on public networks, but Enable-PSRemoting reapplies the rule in case it was changed or deleted.</span></span>

<span data-ttu-id="ae456-144">В клиентских версиях Windows с частными и доменными сетями по умолчанию командлет Enable-PSRemoting создает правила брандмауэра, которые допускают неограниченный удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="ae456-144">On client versions of Windows with private and domain networks, by default, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span>

<span data-ttu-id="ae456-145">Чтобы включить удаленное взаимодействие для клиентских версий Windows с общедоступными сетями, используйте параметр SkipNetworkProfileCheck командлета Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="ae456-145">To enable remoting on client versions of Windows with public networks, use the SkipNetworkProfileCheck parameter of the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="ae456-146">Он создает правило брандмауэра, разрешающее удаленный доступ только с компьютеров в той же локальной подсети.</span><span class="sxs-lookup"><span data-stu-id="ae456-146">It creates a firewall rule that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="ae456-147">Чтобы удалить ограничение локальной подсети в общедоступных сетях и разрешить удаленный доступ из всех расположений в клиентских и серверных версиях Windows, используйте командлет Set-NetFirewallRule в модуле NetSecurity.</span><span class="sxs-lookup"><span data-stu-id="ae456-147">To remove the local subnet restriction on public networks and allow remote access from all locations on client and server versions of Windows, use the Set-NetFirewallRule cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="ae456-148">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ae456-148">Run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="ae456-149">В Windows PowerShell 2,0 в серверных версиях Windows Enable-PSRemoting создает правила брандмауэра, разрешив удаленный доступ ко всем сетям.</span><span class="sxs-lookup"><span data-stu-id="ae456-149">In Windows PowerShell 2.0, on server versions of Windows, Enable-PSRemoting creates firewall rules that permit remote access on all networks.</span></span>

<span data-ttu-id="ae456-150">В Windows PowerShell 2,0 на клиентских версиях Windows Enable-PSRemoting создает правила брандмауэра только для частных и доменных сетей.</span><span class="sxs-lookup"><span data-stu-id="ae456-150">In Windows PowerShell 2.0, on client versions of Windows, Enable-PSRemoting creates firewall rules only on private and domain networks.</span></span> <span data-ttu-id="ae456-151">Если сетевое расположение является общедоступным, Enable-PSRemoting завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="ae456-151">If the network location is public, Enable-PSRemoting fails.</span></span>

## <a name="run-as-administrator"></a><span data-ttu-id="ae456-152">ЗАПУСК ОТ ИМЕНИ АДМИНИСТРАТОРА</span><span class="sxs-lookup"><span data-stu-id="ae456-152">RUN AS ADMINISTRATOR</span></span>

<span data-ttu-id="ae456-153">Для следующих операций удаленного взаимодействия требуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="ae456-153">Administrator privileges are required for the following remoting operations:</span></span>

- <span data-ttu-id="ae456-154">Установление удаленного подключения к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="ae456-154">Establishing a remote connection to the local computer.</span></span> <span data-ttu-id="ae456-155">Такой сценарий обычно называется «замыканием на себя».</span><span class="sxs-lookup"><span data-stu-id="ae456-155">This is commonly known as a "loopback" scenario.</span></span>

- <span data-ttu-id="ae456-156">Управление конфигурациями сеансов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae456-156">Managing session configurations on the local computer.</span></span>

- <span data-ttu-id="ae456-157">Просмотр и изменение параметров WS-Management на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae456-157">Viewing and changing WS-Management settings on the local computer.</span></span> <span data-ttu-id="ae456-158">Это параметры в узле LocalHost на диске WSMAN:.</span><span class="sxs-lookup"><span data-stu-id="ae456-158">These are the settings in the LocalHost node of the WSMAN: drive.</span></span>

<span data-ttu-id="ae456-159">Для выполнения этих задач необходимо запустить PowerShell с параметром "Запуск от имени администратора", даже если вы являетесь членом группы "Администраторы" на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae456-159">To perform these tasks, you must start PowerShell with the "Run as administrator" option even if you are a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="ae456-160">В Windows 7 и Windows Server 2008 R2 для запуска Windows PowerShell с параметром "Запуск от имени администратора":</span><span class="sxs-lookup"><span data-stu-id="ae456-160">In Windows 7 and in Windows Server 2008 R2, to start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="ae456-161">Нажмите кнопку Пуск, выберите пункт Все программы, затем стандартные, а затем щелкните папку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae456-161">Click Start, click All Programs, click Accessories, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="ae456-162">Щелкните правой кнопкой мыши Windows PowerShell и выберите команду "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="ae456-162">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="ae456-163">Чтобы запустить Windows PowerShell с параметром "Запуск от имени администратора", выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ae456-163">To start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="ae456-164">Нажмите кнопку Пуск, выберите пункт Все программы, а затем щелкните папку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae456-164">Click Start, click All Programs, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="ae456-165">Щелкните правой кнопкой мыши Windows PowerShell и выберите команду "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="ae456-165">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="ae456-166">Параметр "Запуск от имени администратора" также доступен в других записях проводника Windows для Windows PowerShell, включая ярлыки.</span><span class="sxs-lookup"><span data-stu-id="ae456-166">The "Run as administrator" option is also available in other Windows Explorer entries for Windows PowerShell, including shortcuts.</span></span> <span data-ttu-id="ae456-167">Просто щелкните элемент правой кнопкой мыши и выберите команду "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="ae456-167">Just right-click the item, and then click "Run as administrator".</span></span>

<span data-ttu-id="ae456-168">При запуске Windows PowerShell из другой программы, например Cmd.exe, используйте параметр "Запуск от имени администратора" для запуска программы.</span><span class="sxs-lookup"><span data-stu-id="ae456-168">When you start Windows PowerShell from another program such as Cmd.exe, use the "Run as administrator" option to start the program.</span></span>

## <a name="how-to-configure-your-computer-for-remoting"></a><span data-ttu-id="ae456-169">НАСТРОЙКА КОМПЬЮТЕРА ДЛЯ УДАЛЕННОГО ВЗАИМОДЕЙСТВИЯ</span><span class="sxs-lookup"><span data-stu-id="ae456-169">HOW TO CONFIGURE YOUR COMPUTER FOR REMOTING</span></span>

<span data-ttu-id="ae456-170">Компьютеры, на которых работают все поддерживаемые версии Windows, могут устанавливать удаленные подключения к и выполнять удаленные команды в PowerShell без какой бы то ни было конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ae456-170">Computers running all supported versions of Windows can establish remote connections to and run remote commands in PowerShell without any configuration.</span></span> <span data-ttu-id="ae456-171">Однако для получения подключений и разрешения пользователям создавать локальные и удаленные сеансы PowerShell ("PSSession") и выполнять команды на локальном компьютере необходимо включить удаленное взаимодействие PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae456-171">However, to receive connections, and allow users to create local and remote user-managed PowerShell sessions ("PSSessions") and run commands on the local computer, you must enable PowerShell remoting on the computer.</span></span>

<span data-ttu-id="ae456-172">По умолчанию для Windows Server 2012 и более новых выпусков Windows Server включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae456-172">Windows Server 2012 and newer releases of Windows Server are enabled for PowerShell remoting by default.</span></span> <span data-ttu-id="ae456-173">Если параметры изменены, можно восстановить параметры по умолчанию, запустив командлет Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="ae456-173">If the settings are changed, you can restore the default settings by running the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="ae456-174">Во всех остальных поддерживаемых версиях Windows необходимо запустить командлет Enable-PSRemoting, чтобы включить удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae456-174">On all other supported versions of Windows, you need to run the Enable-PSRemoting cmdlet to enable PowerShell remoting.</span></span>

<span data-ttu-id="ae456-175">Функции удаленного взаимодействия PowerShell поддерживаются службой WinRM, которая является реализацией Майкрософт протокола веб-служб для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="ae456-175">The remoting features of PowerShell are supported by the WinRM service, which is the Microsoft implementation of the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="ae456-176">При включении удаленного взаимодействия PowerShell вы изменяете конфигурацию по умолчанию WS-Management и добавляете конфигурацию системы, позволяющую пользователям подключаться к WS-Management.</span><span class="sxs-lookup"><span data-stu-id="ae456-176">When you enable PowerShell remoting, you change the default configuration of WS-Management and add system configuration that allow users to connect to WS-Management.</span></span>

<span data-ttu-id="ae456-177">Чтобы настроить PowerShell для получения удаленных команд:</span><span class="sxs-lookup"><span data-stu-id="ae456-177">To configure PowerShell to receive remote commands:</span></span>

1. <span data-ttu-id="ae456-178">Запустите PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="ae456-178">Start PowerShell with the "Run as administrator" option.</span></span>
2. <span data-ttu-id="ae456-179">В командной строке введите следующий текст: `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="ae456-179">At the command prompt, type: `Enable-PSRemoting`</span></span>

<span data-ttu-id="ae456-180">Чтобы убедиться, что удаленное взаимодействие настроено правильно, выполните команду теста, например следующую команду, которая создает удаленный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae456-180">To verify that remoting is configured correctly, run a test command such as the following command, which creates a remote session on the local computer.</span></span>

```powershell
New-PSSession
```

<span data-ttu-id="ae456-181">Если удаленное взаимодействие настроено правильно, команда создаст сеанс на локальном компьютере и возвратит объект, представляющий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ae456-181">If remoting is configured correctly, the command will create a session on the local computer and return an object that represents the session.</span></span> <span data-ttu-id="ae456-182">Выходные данные должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ae456-182">The output should resemble the following sample output:</span></span>

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

<span data-ttu-id="ae456-183">Если команда завершается ошибкой, обратитесь к разделу [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ae456-183">If the command fails, for assistance, see [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span></span>

## <a name="understand-policies"></a><span data-ttu-id="ae456-184">ОБЩИЕ СВЕДЕНИЯ О ПОЛИТИКАХ</span><span class="sxs-lookup"><span data-stu-id="ae456-184">UNDERSTAND POLICIES</span></span>

<span data-ttu-id="ae456-185">При удаленной работе вы используете два экземпляра PowerShell: один на локальном компьютере и один на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae456-185">When you work remotely, you use two instances of PowerShell, one on the local computer and one on the remote computer.</span></span> <span data-ttu-id="ae456-186">В результате работа зависит от политик Windows и политик PowerShell на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="ae456-186">As a result, your work is affected by the Windows policies and the PowerShell policies on the local and remote computers.</span></span>

<span data-ttu-id="ae456-187">Как правило, перед подключением и установкой подключения действуют политики на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae456-187">In general, before you connect and as you are establishing the connection, the policies on the local computer are in effect.</span></span> <span data-ttu-id="ae456-188">При использовании подключения политики на удаленном компьютере вступают в действие.</span><span class="sxs-lookup"><span data-stu-id="ae456-188">When you are using the connection, the policies on the remote computer are in effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae456-189">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="ae456-189">SEE ALSO</span></span>

[<span data-ttu-id="ae456-190">about_Remote</span><span class="sxs-lookup"><span data-stu-id="ae456-190">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="ae456-191">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="ae456-191">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="ae456-192">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="ae456-192">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="ae456-193">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ae456-193">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="ae456-194">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="ae456-194">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="ae456-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="ae456-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
