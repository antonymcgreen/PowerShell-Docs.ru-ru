---
description: Содержит описание конфигураций сеансов, определяющих, какие пользователи могут подключаться к компьютеру удаленно и какие команды они могут запускать.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 0956e2e96cb67d1c4b8c3ef245c6fa084b781351
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231249"
---
# <a name="about-session-configurations"></a><span data-ttu-id="db949-104">Сведения о конфигурациях сеансов</span><span class="sxs-lookup"><span data-stu-id="db949-104">About Session Configurations</span></span>

## <a name="short-description"></a><span data-ttu-id="db949-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="db949-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="db949-106">Содержит описание конфигураций сеансов, определяющих, какие пользователи могут подключаться к компьютеру удаленно и какие команды они могут запускать.</span><span class="sxs-lookup"><span data-stu-id="db949-106">Describes session configurations, which determine the users who can connect to the computer remotely and the commands they can run.</span></span>

## <a name="long-description"></a><span data-ttu-id="db949-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="db949-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="db949-108">Конфигурация сеанса, также известная как "конечная точка", представляет собой группу параметров на локальном компьютере, которые определяют среду для сеансов PowerShell, создаваемых при подключении удаленных или локальных пользователей к PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-108">A session configuration, also known as an "endpoint" is a group of settings on the local computer that define the environment for the PowerShell sessions that are created when remote or local users connect to PowerShell on the local computer.</span></span>

<span data-ttu-id="db949-109">Администраторы компьютера могут использовать конфигурации сеанса для защиты компьютера и определения пользовательских сред для пользователей, подключающихся к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="db949-109">Administrators of the computer can use session configurations to protect the computer and to define custom environments for users who connect to the computer.</span></span>

<span data-ttu-id="db949-110">Администраторы также могут использовать конфигурации сеанса для определения разрешений, необходимых для удаленного подключения к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="db949-110">Administrators can also use session configurations to determine the permissions that are required to connect to the computer remotely.</span></span> <span data-ttu-id="db949-111">По умолчанию только члены группы "Администраторы" имеют разрешение на использование конфигурации сеанса для удаленного подключения, но можно изменить параметры по умолчанию, чтобы разрешить удаленное подключение к компьютеру всем пользователям или выбранным пользователям.</span><span class="sxs-lookup"><span data-stu-id="db949-111">By default, only members of the Administrators group have permission to use the session configuration to connect remotely, but you can change the default settings to allow all users, or selected users, to connect remotely to your computer.</span></span>

<span data-ttu-id="db949-112">Начиная с версии PowerShell 3,0 можно использовать файл конфигурации сеанса для определения элементов конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-112">Beginning in PowerShell 3.0, you can use a session configuration file to define the elements of a session configuration.</span></span> <span data-ttu-id="db949-113">Эта функция упрощает настройку сеансов без написания кода и обнаружение свойств конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-113">This feature makes it easy to customize sessions without writing code and to discover the properties of a session configuration.</span></span> <span data-ttu-id="db949-114">Чтобы создать файл конфигурации сеанса, используйте командлет New-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-114">To create a session configuration file, use the New-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="db949-115">Дополнительные сведения о файлах конфигураций сеансов см. в разделе [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="db949-115">For more information about session configuration files, see [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="db949-116">Конфигурации сеансов — это функция веб-служб для удаленного взаимодействия PowerShell на основе управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="db949-116">Session configurations are a feature of Web Services for Management (WS-Management) based PowerShell remoting.</span></span> <span data-ttu-id="db949-117">Они используются только при использовании командлетов New-PSSession, Invoke-Command или Enter-PSSession для подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="db949-117">They are used only when you use the New-PSSession, Invoke-Command, or Enter-PSSession cmdlets to connect to a remote computer.</span></span>

<span data-ttu-id="db949-118">Примечание. для управления конфигурациями сеансов запустите PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="db949-118">Note: To manage the session configurations, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="db949-119">Сведения о конфигурациях сеансов</span><span class="sxs-lookup"><span data-stu-id="db949-119">About Session Configurations</span></span>

<span data-ttu-id="db949-120">Каждый сеанс PowerShell использует конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-120">Every PowerShell session uses a session configuration.</span></span> <span data-ttu-id="db949-121">Сюда входят постоянные сеансы, создаваемые с помощью командлетов New-PSSession или Enter-PSSession, а также временные сеансы, создаваемые PowerShell при использовании параметра ComputerName командлета, использующего технологию удаленного взаимодействия на основе WS-Management, например Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="db949-121">This includes persistent sessions that you create by using the New-PSSession or Enter-PSSession cmdlets, and the temporary sessions that PowerShell creates when you use the ComputerName parameter of a cmdlet that uses WS-Management-based remoting technology, such as Invoke-Command.</span></span>

<span data-ttu-id="db949-122">Администраторы могут использовать конфигурации сеанса для защиты ресурсов компьютера и создания пользовательских сред для пользователей, подключающихся к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="db949-122">Administrators can use session configurations to protect the resources of the computer and to create custom environments for users who connect to the computer.</span></span> <span data-ttu-id="db949-123">Например, можно использовать конфигурацию сеанса для ограничения размера объектов, получаемых компьютером в сеансе, определения языкового режима сеанса и указания командлетов, поставщиков и функций, доступных в сеансе.</span><span class="sxs-lookup"><span data-stu-id="db949-123">For example, you can use a session configuration to limit the size of objects that the computer receives in the session, to define the language mode of the session, and to specify the cmdlets, providers, and functions that are available in the session.</span></span>

<span data-ttu-id="db949-124">Настроив дескриптор безопасности конфигурации сеанса, вы определяете, кто может использовать конфигурацию сеанса для подключения к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="db949-124">By configuring the security descriptor of a session configuration, you determine who can use the session configuration to connect to the computer.</span></span>
<span data-ttu-id="db949-125">Пользователи должны иметь разрешение EXECUTE на конфигурацию сеанса, чтобы использовать их в сеансе.</span><span class="sxs-lookup"><span data-stu-id="db949-125">Users must have Execute permission to a session configuration to use it in a session.</span></span> <span data-ttu-id="db949-126">Если у пользователя нет необходимых разрешений на использование каких-либо конфигураций сеанса на компьютере, пользователь не сможет удаленно подключиться к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="db949-126">If a user does not have the required permissions to use any of the session configurations on a computer, the user cannot connect to the computer remotely.</span></span>

<span data-ttu-id="db949-127">По умолчанию разрешения на использование конфигураций сеансов по умолчанию имеют только администраторы компьютера.</span><span class="sxs-lookup"><span data-stu-id="db949-127">By default, only Administrators of the computer have permission to use the default session configurations.</span></span> <span data-ttu-id="db949-128">Однако можно изменить дескрипторы безопасности, чтобы разрешить всем, ни одному пользователю или только выбранным пользователям использовать конфигурации сеанса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-128">But, you can change the security descriptors to allow everyone, no one, or only selected users to use the session configurations on your computer.</span></span>

<span data-ttu-id="db949-129">Встроенные конфигурации сеансов</span><span class="sxs-lookup"><span data-stu-id="db949-129">Built-in Session Configurations</span></span>

<span data-ttu-id="db949-130">PowerShell 3,0 включает встроенные конфигурации сеансов с именами Microsoft. PowerShell и Microsoft. PowerShell. Workflow.</span><span class="sxs-lookup"><span data-stu-id="db949-130">PowerShell 3.0 includes built-in session configurations named Microsoft.PowerShell and Microsoft.PowerShell.Workflow.</span></span> <span data-ttu-id="db949-131">На компьютерах под управлением 64-разрядных версий Windows PowerShell также предоставляет конфигурацию сеанса Microsoft. PowerShell32, 32-bit.</span><span class="sxs-lookup"><span data-stu-id="db949-131">On computers running 64-bit versions of Windows, PowerShell also provides Microsoft.PowerShell32, a 32-bit session configuration.</span></span>

<span data-ttu-id="db949-132">Конфигурация сеанса Microsoft. PowerShell используется для сеансов по умолчанию, то есть если команда для создания сеанса не включает параметр ConfigurationName командлета New-PSSession, Enter-PSSession или Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="db949-132">The Microsoft.PowerShell session configuration is used for sessions by default, that is, when a command to create a session does not include the ConfigurationName parameter of the New-PSSession, Enter-PSSession, or Invoke-Command cmdlet.</span></span>

<span data-ttu-id="db949-133">Дескрипторы безопасности для конфигураций сеансов по умолчанию позволяют использовать их только членам группы «Администраторы» на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-133">The security descriptors for the default session configurations allow only members of the Administrators group on the local computer to use them.</span></span> <span data-ttu-id="db949-134">Таким образом, только члены группы «Администраторы» могут подключаться к компьютеру удаленно, если не изменить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db949-134">As such, only members of the Administrators group can connect to the computer remotely unless you change the default settings.</span></span>

<span data-ttu-id="db949-135">Конфигурации сеансов по умолчанию можно изменить с помощью переменной предпочтений $PSSessionConfigurationName.</span><span class="sxs-lookup"><span data-stu-id="db949-135">You can change the default session configurations by using the $PSSessionConfigurationName preference variable.</span></span> <span data-ttu-id="db949-136">Дополнительные сведения см. в разделе about_Preference_Variables.</span><span class="sxs-lookup"><span data-stu-id="db949-136">For more information, see about_Preference_Variables.</span></span>

<span data-ttu-id="db949-137">Просмотр конфигураций сеансов на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="db949-137">Viewing Session Configurations on the Local Computer</span></span>

<span data-ttu-id="db949-138">Чтобы получить конфигурации сеанса на локальном компьютере, используйте командлет Get-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-138">To get the session configurations on your local computer, use the Get-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="db949-139">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="db949-139">For example, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="db949-140">Объект конфигурации сеанса разворачивается в PowerShell 3,0, чтобы отобразить свойства конфигурации сеанса, настроенные с помощью файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-140">The session configuration object is expanded in PowerShell 3.0 to display the properties of the session configuration that are configured by using a session configuration file.</span></span>

<span data-ttu-id="db949-141">Например, чтобы просмотреть все свойства объекта конфигурации сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="db949-141">For example, to see all of the properties of a session configuration object, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

<span data-ttu-id="db949-142">Для просмотра конфигураций сеансов можно также использовать поставщик WSMan в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db949-142">You can also use the WSMan provider in PowerShell to view session configurations.</span></span> <span data-ttu-id="db949-143">Поставщик WSMan создает на вашем сеансе диск WSMAN:.</span><span class="sxs-lookup"><span data-stu-id="db949-143">The WSMan provider creates a WSMAN: drive in your session.</span></span>

<span data-ttu-id="db949-144">На диске WSMAN: конфигурации сеансов находятся в узле подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="db949-144">In the WSMAN: drive, session configurations are in the Plugin node.</span></span> <span data-ttu-id="db949-145">(Все конфигурации сеансов находятся в узле подключаемого модуля, но в узле подключаемого модуля имеются элементы, которые не являются конфигурациями сеанса.)</span><span class="sxs-lookup"><span data-stu-id="db949-145">(All session configurations are in the Plugin node, but there are items in the Plugin node that are not session configurations.)</span></span>

<span data-ttu-id="db949-146">Например, чтобы просмотреть конфигурации сеанса на локальном компьютере, введите:</span><span class="sxs-lookup"><span data-stu-id="db949-146">For example, to view the session configurations on the local computer, type:</span></span>

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="db949-147">Просмотр конфигураций сеансов на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="db949-147">Viewing Session Configurations on a Remote Computer</span></span>

<span data-ttu-id="db949-148">Чтобы просмотреть конфигурации сеанса на удаленном компьютере, используйте командлет Connect-WSMan, чтобы добавить примечание для удаленного компьютера на диск WSMAN: на локальном компьютере, а затем используйте команду WSMAN: Drive для просмотра конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-148">To view the session configurations on a remote computer, use the Connect-WSMan cmdlet to add a note for the remote computer to the WSMAN: drive on your local computer, and then use the WSMAN: drive to view the session configurations.</span></span>

<span data-ttu-id="db949-149">Например, следующая команда добавляет узел для удаленного компьютера Server01 к диску WSMAN: на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-149">For example, the following command adds a node for the Server01 remote computer to the WSMAN: drive on the local computer.</span></span>

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

<span data-ttu-id="db949-150">После выполнения команды можно перейти к узлу Server01, чтобы просмотреть конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-150">When the command is complete, you can navigate to the node for the Server01 computer to view the session configurations.</span></span>

<span data-ttu-id="db949-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="db949-151">For example:</span></span>

```powershell
PS C:> cd wsman:

PS WSMan:> dir

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01.corp.fabrikam.com                    Container

PS WSMan:> dir server01\plugin\

WSManConfig: Microsoft.WSMan.Management\WSMan::server01.corp.fabrikam.com\Pl
ugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="db949-152">Изменение дескриптора безопасности конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="db949-152">Changing the Security Descriptor of a Session Configuration</span></span>

<span data-ttu-id="db949-153">В Windows Server 2012 и более новых выпусках Windows Server встроенные конфигурации сеансов по умолчанию включены для удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="db949-153">In Windows Server 2012 and newer releases of Windows Server, the built-in session configurations are enabled for remote users by default.</span></span> <span data-ttu-id="db949-154">В других поддерживаемых версиях Windows необходимо изменить дескрипторы безопасности конфигураций сеанса, чтобы разрешить удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="db949-154">In other supported versions of Windows, you must change the security descriptors of the session configurations to allow remote access.</span></span>

<span data-ttu-id="db949-155">Чтобы включить удаленный доступ к конфигурациям сеансов на компьютере, используйте командлет Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="db949-155">To enable remote access to the session configurations on the computer, use the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="db949-156">Этот командлет создает две конфигурации сеанса:</span><span class="sxs-lookup"><span data-stu-id="db949-156">This cmdlet creates two session configurations:</span></span>

- <span data-ttu-id="db949-157">с именем, определенным как "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="db949-157">with the name defined as: "PowerShell."</span></span> <span data-ttu-id="db949-158">+ "Текущая версия PowerShell"</span><span class="sxs-lookup"><span data-stu-id="db949-158">+ "current PowerShell version"</span></span>
- <span data-ttu-id="db949-159">с именем "PowerShell. 6", без привязки к любой конкретной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db949-159">with name "PowerShell.6", untied to any specific PowerShell version.</span></span>

<span data-ttu-id="db949-160">Кроме того, по умолчанию только члены группы "Администраторы" на компьютере имеют разрешение на выполнение конфигураций сеансов по умолчанию, но вы можете изменить дескрипторы безопасности в конфигурациях сеансов по умолчанию и во всех создаваемых конфигурациях сеансов.</span><span class="sxs-lookup"><span data-stu-id="db949-160">Also, by default, only members of the Administrators group on the computer have Execute permission to the default session configurations, but you can change the security descriptors on the default session configurations and on any session configurations that you create.</span></span>

<span data-ttu-id="db949-161">Чтобы предоставить другим пользователям разрешение на удаленное подключение к компьютеру, используйте командлет Set-PSSessionConfiguration, чтобы добавить разрешения на выполнение для этих пользователей в дескрипторы безопасности в конфигурациях сеанса Microsoft. PowerShell и Microsoft. PowerShell32.</span><span class="sxs-lookup"><span data-stu-id="db949-161">To give other users permission to connect to the computer remotely, use the Set-PSSessionConfiguration cmdlet to add "Execute" permissions for those users to the security descriptors of the Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span>

<span data-ttu-id="db949-162">Например, следующая команда открывает страницу свойств, которая позволяет изменить дескриптор безопасности для конфигурации сеанса Microsoft. PowerShell по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db949-162">For example, the following command opens a property page that lets you change the security descriptor for the Microsoft.PowerShell default session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="db949-163">Чтобы запретить доступ всем конфигурациям сеансов на компьютере, используйте командлет Disable-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-163">To deny everyone permission to all the session configurations on the computer, use the Disable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="db949-164">Например, следующая команда отключает конфигурации сеанса по умолчанию на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-164">For example, the following command disables the default session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

<span data-ttu-id="db949-165">Чтобы запретить удаленным пользователям подключаться к компьютеру, но разрешить локальным пользователям подключаться, используйте командлет Disable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="db949-165">To prevent remote users from connecting to the computer, but allow local users to connect, use the Disable-PSRemoting cmdlet.</span></span> <span data-ttu-id="db949-166">Disable-PSRemoting добавляет запись "Network_Deny_All" во все конфигурации сеанса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-166">Disable-PSRemoting adds a "Network_Deny_All" entry to all session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSRemoting
```

<span data-ttu-id="db949-167">Чтобы разрешить удаленным пользователям использовать все конфигурации сеансов на компьютере, используйте командлет Enable-PSRemoting или Enable-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-167">To allow remote users to use all session configurations on the computer, use the Enable-PSRemoting or Enable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="db949-168">Например, следующая команда включает удаленный доступ к встроенным конфигурациям сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-168">For example, the following command enables remote access to the built-in session configurations.</span></span>

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

<span data-ttu-id="db949-169">Чтобы внести другие изменения в дескриптор безопасности конфигурации сеанса, используйте командлет Set-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-169">To make other changes to the security descriptor of a session configuration, use the Set-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="db949-170">Используйте параметр SecurityDescriptorSDDL для отправки строкового значения SDDL.</span><span class="sxs-lookup"><span data-stu-id="db949-170">Use the SecurityDescriptorSDDL parameter to submit an SDDL string value.</span></span> <span data-ttu-id="db949-171">Используйте параметр ShowSecurityDescriptorUI для вывода страницы свойств пользовательского интерфейса, помогающей создать новый SDDL.</span><span class="sxs-lookup"><span data-stu-id="db949-171">Use the ShowSecurityDescriptorUI parameter to display a user interface property sheet that helps you to create a new SDDL.</span></span>

<span data-ttu-id="db949-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="db949-172">For example:</span></span>

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="db949-173">Создание новой конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="db949-173">Creating a New Session Configuration</span></span>

<span data-ttu-id="db949-174">Чтобы создать новую конфигурацию сеанса на локальном компьютере, используйте командлет Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-174">To create a new session configuration on the local computer, use the Register-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="db949-175">Чтобы определить новую конфигурацию сеанса, можно использовать сборку C#, сценарий PowerShell и параметры командлета Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-175">To define the new session configuration, you can use a C# assembly, a PowerShell script, and the parameters of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="db949-176">Например, следующая команда создает конфигурацию сеанса, идентичную конфигурации сеанса Microsoft. PowerShell, за исключением того, что она ограничивает данные, получаемые от удаленной команды, до 20 мегабайт (МБ).</span><span class="sxs-lookup"><span data-stu-id="db949-176">For example, the following command creates a session configuration that is identical the Microsoft.PowerShell session configuration, except that it limits the data received from a remote command to 20 megabytes (MB).</span></span> <span data-ttu-id="db949-177">(Значение по умолчанию — 50 МБ).</span><span class="sxs-lookup"><span data-stu-id="db949-177">(The default is 50 MB).</span></span>

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

<span data-ttu-id="db949-178">При создании конфигурации сеанса ее можно управлять с помощью других командлетов конфигурации сеанса, которые отображаются на диске WSMAN:.</span><span class="sxs-lookup"><span data-stu-id="db949-178">When you create a session configuration, you can manage it by using the other session configuration cmdlets, and it appears in the WSMAN: drive.</span></span>

<span data-ttu-id="db949-179">Дополнительные сведения см. в разделе Register-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-179">For more information, see Register-PSSessionConfiguration.</span></span>

<span data-ttu-id="db949-180">Удаление конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="db949-180">Removing a Session Configuration</span></span>

<span data-ttu-id="db949-181">Чтобы удалить конфигурацию сеанса с локального компьютера, используйте командлет Unregister-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-181">To remove a session configuration from the local computer, use the Unregister-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="db949-182">Например, следующая команда удаляет конфигурацию сеанса документе newconfig с компьютера.</span><span class="sxs-lookup"><span data-stu-id="db949-182">For example, the following command removes the NewConfig session configuration from the computer.</span></span>

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

<span data-ttu-id="db949-183">Дополнительные сведения см. в разделе Unregister-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db949-183">For more information, see Unregister-PSSessionConfiguration.</span></span>

<span data-ttu-id="db949-184">Восстановление конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="db949-184">Restoring a Session Configuration</span></span>

<span data-ttu-id="db949-185">Чтобы восстановить конфигурацию сеанса по умолчанию, которая была случайно удалена (отменена), используйте командлет Enable-PSRemoting.</span><span class="sxs-lookup"><span data-stu-id="db949-185">To restore a default session configuration that was deleted (unregistered) accidentally, use the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="db949-186">Командлет Enable-PSRemoting воссоздает все конфигурации сеансов по умолчанию, которые не существуют на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-186">The Enable-PSRemoting cmdlet recreates all default sessions configurations that do not exist on the computer.</span></span> <span data-ttu-id="db949-187">Он не перезаписывает или не изменяет значения свойств существующих конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="db949-187">It does not overwrite or change the property values of existing session configurations.</span></span>

<span data-ttu-id="db949-188">Чтобы восстановить исходные значения свойств конфигурации сеанса по умолчанию, используйте Unregister-PSSessionConfiguration, чтобы удалить конфигурацию сеанса, а затем используйте командлет Enable-PSRemoting, чтобы создать его заново.</span><span class="sxs-lookup"><span data-stu-id="db949-188">To restore the original property values of a default session configuration, use the Unregister-PSSessionConfiguration to delete the session configuration and then use the Enable-PSRemoting cmdlet to recreate it.</span></span>

<span data-ttu-id="db949-189">Выбор конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="db949-189">Selecting a Session Configuration</span></span>

<span data-ttu-id="db949-190">Чтобы выбрать определенную конфигурацию сеанса для сеанса, используйте параметр ConfigurationName командлета New-PSSession, введите-PSSession или Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="db949-190">To select a particular session configuration for a session, use the ConfigurationName parameter of New-PSSession, Enter-PSSession, or Invoke-Command.</span></span>

<span data-ttu-id="db949-191">Например, эта команда использует командлет New-PSSession для запуска PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="db949-191">For example, this command uses the New-PSSession cmdlet to start a PSSession on the Server01 computer.</span></span> <span data-ttu-id="db949-192">Команда использует параметр ConfigurationName для выбора конфигурации WithProfile на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="db949-192">The command uses the ConfigurationName parameter to select the WithProfile configuration on the Server01 computer.</span></span>

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

<span data-ttu-id="db949-193">Эта команда будет выполнена успешно только в том случае, если текущий пользователь имеет разрешение на использование конфигурации сеанса WithProfile или если вы можете указать учетные данные пользователя, имеющего необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="db949-193">This command will succeed only if the current user has permission to use the WithProfile session configuration or can supply the credentials of a user who has the required permissions.</span></span>

<span data-ttu-id="db949-194">Можно также использовать переменную предпочтения $PSSessionConfigurationName, чтобы изменить конфигурацию сеанса по умолчанию на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db949-194">You can also use the $PSSessionConfigurationName preference variable to change the default session configuration on the computer.</span></span> <span data-ttu-id="db949-195">Дополнительные сведения о переменной настройки $PSSessionConfigurationName см. в разделе about_Preference_Variables.</span><span class="sxs-lookup"><span data-stu-id="db949-195">For more information about the $PSSessionConfigurationName preference variable, see about_Preference_Variables.</span></span>

## <a name="keywords"></a><span data-ttu-id="db949-196">СЛОВАМИ</span><span class="sxs-lookup"><span data-stu-id="db949-196">KEYWORDS</span></span>

<span data-ttu-id="db949-197">about_Endpoints about_SessionConfigurations</span><span class="sxs-lookup"><span data-stu-id="db949-197">about_Endpoints about_SessionConfigurations</span></span>

## <a name="see-also"></a><span data-ttu-id="db949-198">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="db949-198">SEE ALSO</span></span>

[<span data-ttu-id="db949-199">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="db949-199">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="db949-200">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="db949-200">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="db949-201">about_Remote</span><span class="sxs-lookup"><span data-stu-id="db949-201">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="db949-202">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="db949-202">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)

[<span data-ttu-id="db949-203">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="db949-203">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="db949-204">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="db949-204">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="db949-205">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="db949-205">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="db949-206">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="db949-206">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="db949-207">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="db949-207">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="db949-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="db949-208">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="db949-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="db949-209">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="db949-210">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="db949-210">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="db949-211">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="db949-211">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)
