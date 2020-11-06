---
description: Содержит общие сведения о веб-службах для управления (WS-Management) в качестве фона для использования командлетов WS-Management в Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: 9e1042247b54bb7bde2451adb5344003bbf26ca0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232525"
---
# <a name="about-ws-management-cmdlets"></a><span data-ttu-id="a9f9a-104">О командлетах WS-Management</span><span class="sxs-lookup"><span data-stu-id="a9f9a-104">About WS-Management Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="a9f9a-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="a9f9a-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="a9f9a-106">Содержит общие сведения о веб-службах для управления (WS-Management) в качестве фона для использования командлетов WS-Management в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-106">Provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a9f9a-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="a9f9a-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="a9f9a-108">В этом разделе представлен обзор веб-служб для управления (WS-Management) в качестве фона для использования командлетов WS-Management в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-108">This topic provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span> <span data-ttu-id="a9f9a-109">В этом разделе также приведены ссылки на дополнительные сведения о WS-Management.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-109">This topic also provides links to more information about WS-Management.</span></span> <span data-ttu-id="a9f9a-110">Реализация WS-Management Майкрософт также называется служба удаленного управления Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="a9f9a-110">The Microsoft implementation of WS-Management is also known as Windows Remote Management (WinRM).</span></span>

## <a name="about-ws-management"></a><span data-ttu-id="a9f9a-111">О WS-Management</span><span class="sxs-lookup"><span data-stu-id="a9f9a-111">About WS-Management</span></span>

<span data-ttu-id="a9f9a-112">Служба удаленного управления Windows является реализацией протокола WS-Management (Майкрософт), стандартным протоколом на основе протокола SOAP, который позволяет различным поставщикам взаимодействовать с оборудованием и операционными системами различных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-112">Windows Remote Management is the Microsoft implementation of the WS-Management protocol, a standard SOAP-based, firewall-friendly protocol that allows hardware and operating systems from different vendors to interoperate.</span></span> <span data-ttu-id="a9f9a-113">Спецификация протокола WS-Management предоставляет системам общий способ доступа и обмена данными управления в инфраструктуре информационных технологий (ИТ).</span><span class="sxs-lookup"><span data-stu-id="a9f9a-113">The WS-Management protocol specification provides a common way for systems to access and exchange management information across an information technology (IT) infrastructure.</span></span> <span data-ttu-id="a9f9a-114">WS-Management и интеллектуальный интерфейс управления платформой (IPMI) вместе с сборщиком событий являются компонентами функций управления оборудованием Windows.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-114">WS-Management and Intelligent Platform Management Interface (IPMI), along with the Event Collector, are components of the Windows Hardware Management features.</span></span>

<span data-ttu-id="a9f9a-115">Протокол WS-Management основан на следующих стандартных спецификациях веб-служб: HTTPS, SOAP по HTTP (WS-I Profile), SOAP 1,2, WS-Addressing, WS-передачи, WS-enumeration и WS-Eventing.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-115">The WS-Management protocol is based on the following standard Web service specifications: HTTPS, SOAP over HTTP (WS-I profile), SOAP 1.2, WS-Addressing, WS-Transfer, WS-Enumeration, and WS-Eventing.</span></span>

## <a name="ws-management-and-wmi"></a><span data-ttu-id="a9f9a-116">WS-Management и WMI</span><span class="sxs-lookup"><span data-stu-id="a9f9a-116">WS-Management and WMI</span></span>

<span data-ttu-id="a9f9a-117">WS-Management можно использовать для получения данных, предоставляемых инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="a9f9a-117">WS-Management can be used to retrieve data exposed by Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="a9f9a-118">Данные WMI можно получить с помощью скриптов или приложений, использующих API WS-Management сценариев или с помощью средства командной строки WinRM.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-118">You can obtain WMI data with scripts or applications that use the WS-Management Scripting API or through the WinRM command-line tool.</span></span> <span data-ttu-id="a9f9a-119">WS-Management поддерживает большинство знакомых классов и операций WMI, включая внедренные объекты.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-119">WS-Management supports most of the familiar WMI classes and operations, including embedded objects.</span></span> <span data-ttu-id="a9f9a-120">WS-Management может использовать инструментарий WMI для получения данных о ресурсах или управлении ресурсами на компьютерах под управлением Windows.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-120">WS-Management can leverage WMI to collect data about resources or to manage resources on a Windows-based computers.</span></span> <span data-ttu-id="a9f9a-121">Это означает, что вы можете получать данные об объектах, таких как диски, сетевые адаптеры, службы или процессы в Организации, с помощью существующего набора классов WMI.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-121">That means that you can obtain data about objects such as disks, network adapters, services, or processes in your enterprise through the existing set of WMI classes.</span></span> <span data-ttu-id="a9f9a-122">Вы также можете получить доступ к данным оборудования, доступным в стандартном поставщике IPMI WMI.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-122">You can also access the hardware data that is available from the standard WMI IPMI provider.</span></span>

## <a name="ws-management-windows-powershell-provider-wsman"></a><span data-ttu-id="a9f9a-123">WS-Management поставщика Windows PowerShell (WSMan)</span><span class="sxs-lookup"><span data-stu-id="a9f9a-123">WS-Management Windows PowerShell Provider (WSMan)</span></span>

<span data-ttu-id="a9f9a-124">Поставщик WSMan предоставляет иерархическое представление о доступных параметрах конфигурации WS-Management.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-124">The WSMan provider provides a hierarchical view into the available WS-Management configuration settings.</span></span> <span data-ttu-id="a9f9a-125">Поставщик позволяет исследовать и задавать различные параметры конфигурации WS-Management.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-125">The provider allows you to explore and set the various WS-Management configuration options.</span></span>

## <a name="ws-management-configuration"></a><span data-ttu-id="a9f9a-126">Конфигурация WS-Management</span><span class="sxs-lookup"><span data-stu-id="a9f9a-126">WS-Management Configuration</span></span>

<span data-ttu-id="a9f9a-127">Если WS-Management не установлен и не настроен, удаленное взаимодействие Windows PowerShell недоступно, командлеты WS-Management не выполняются, WS-Management сценарии не выполняются, а поставщик WSMan не может выполнять операции с данными.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-127">If WS-Management is not installed and configured, Windows PowerShell remoting is not available, the WS-Management cmdlets do not run, WS-Management scripts do not run, and the WSMan provider cannot perform data operations.</span></span> <span data-ttu-id="a9f9a-128">WS-Management программа командной строки, WinRM и пересылка событий также зависят от конфигурации WS-Management.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-128">The WS-Management command-line tool, WinRM, and event forwarding also depend on the WS-Management configuration.</span></span>

## <a name="ws-management-cmdlets"></a><span data-ttu-id="a9f9a-129">Командлеты WS-Management</span><span class="sxs-lookup"><span data-stu-id="a9f9a-129">WS-Management Cmdlets</span></span>

<span data-ttu-id="a9f9a-130">Функции WS-Management реализованы в Windows PowerShell с помощью модуля, содержащего набор командлетов и поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-130">WS-Management functionality is implemented in Windows PowerShell through a module that contains a set of cmdlets and the WSMan provider.</span></span> <span data-ttu-id="a9f9a-131">Эти командлеты можно использовать для выполнения комплексных задач, необходимых для управления параметрами WS-Management на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-131">You can use these cmdlets to complete the end-to-end tasks necessary to manage WS-Management settings on local and remote computers.</span></span>

<span data-ttu-id="a9f9a-132">Доступны следующие командлеты WS-Management.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-132">The following WS-Management cmdlets are available.</span></span>

## <a name="connection-cmdlets"></a><span data-ttu-id="a9f9a-133">Командлеты подключения</span><span class="sxs-lookup"><span data-stu-id="a9f9a-133">Connection Cmdlets</span></span>

- <span data-ttu-id="a9f9a-134">Connect-WSMan: подключает локальный компьютер к службе WS-Management (WinRM) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-134">Connect-WSMan: Connects the local computer to the WS-Management (WinRM) service on a remote computer.</span></span>

- <span data-ttu-id="a9f9a-135">Disconnect-WSMan: отключает локальный компьютер от службы WS-Management (WinRM) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-135">Disconnect-WSMan: Disconnects the local computer from the WS-Management (WinRM) service on a remote computer.</span></span>

## <a name="management-data-cmdlets"></a><span data-ttu-id="a9f9a-136">Командлеты Management-Data</span><span class="sxs-lookup"><span data-stu-id="a9f9a-136">Management-Data Cmdlets</span></span>

- <span data-ttu-id="a9f9a-137">Get-WSManInstance: отображает сведения об управлении для экземпляра ресурса, который указан с помощью URI ресурса.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-137">Get-WSManInstance: Displays management information for a resource instance that is specified by a resource URI.</span></span>

- <span data-ttu-id="a9f9a-138">Invoke-WSManAction: вызывает действие для целевого объекта, заданного универсальным кодом ресурса (URI) и селекторами.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-138">Invoke-WSManAction: Invokes an action on the target object that is specified by the resource URI and by the selectors.</span></span>

- <span data-ttu-id="a9f9a-139">New-WSManInstance: создает новый экземпляр ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-139">New-WSManInstance: Creates a new management resource instance.</span></span>

- <span data-ttu-id="a9f9a-140">Remove-WSManInstance — удаляет экземпляр ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-140">Remove-WSManInstance: Deletes a management resource instance.</span></span>

- <span data-ttu-id="a9f9a-141">Set-WSManInstance: изменяет сведения об управлении, связанные с ресурсом.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-141">Set-WSManInstance: Modifies the management information that is related to a resource.</span></span>

## <a name="setup-and-configuration-cmdlets"></a><span data-ttu-id="a9f9a-142">Командлеты установки и настройки</span><span class="sxs-lookup"><span data-stu-id="a9f9a-142">Setup and Configuration Cmdlets</span></span>

- <span data-ttu-id="a9f9a-143">Set-WSManQuickConfig: настраивает локальный компьютер для удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-143">Set-WSManQuickConfig: Configures the local computer for remote management.</span></span>
  <span data-ttu-id="a9f9a-144">С помощью командлета Set-WSManQuickConfig можно настроить WS-Management, чтобы разрешить удаленные подключения к службе WS-Management (WinRM).</span><span class="sxs-lookup"><span data-stu-id="a9f9a-144">You can use the Set-WSManQuickConfig cmdlet to configure WS-Management to allow remote connections to the WS-Management (WinRM) service.</span></span> <span data-ttu-id="a9f9a-145">Командлет Set-WSManQuickConfig выполняет следующие операции:</span><span class="sxs-lookup"><span data-stu-id="a9f9a-145">The Set-WSManQuickConfig cmdlet performs the following operations:</span></span>
  - <span data-ttu-id="a9f9a-146">Он определяет, запущена ли служба WS-Management (WinRM).</span><span class="sxs-lookup"><span data-stu-id="a9f9a-146">It determines whether the WS-Management (WinRM) service is running.</span></span> <span data-ttu-id="a9f9a-147">Если служба WinRM не запущена, командлет Set-WSManQuickConfig запускает службу.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-147">If the WinRM service is not running, the Set-WSManQuickConfig cmdlet starts the service.</span></span>
  - <span data-ttu-id="a9f9a-148">Он задает автоматический тип запуска службы WS-Management (WinRM).</span><span class="sxs-lookup"><span data-stu-id="a9f9a-148">It sets the WS-Management (WinRM) service startup type to automatic.</span></span>
  - <span data-ttu-id="a9f9a-149">Он создает прослушиватель, который принимает запросы с любого IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-149">It creates a listener that accepts requests from any IP address.</span></span> <span data-ttu-id="a9f9a-150">Транспортным протоколом по умолчанию является HTTP.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-150">The default transport protocol is HTTP.</span></span>
  - <span data-ttu-id="a9f9a-151">Он включает исключение брандмауэра для трафика WS-Management.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-151">It enables a firewall exception for WS-Management traffic.</span></span>

  <span data-ttu-id="a9f9a-152">Примечание. для запуска этого командлета в Windows Vista, Windows Server 2008 и более поздних версиях Windows необходимо запустить Windows PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="a9f9a-152">Note: To run this cmdlet in Windows Vista, Windows Server 2008, and later versions of Windows, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

- <span data-ttu-id="a9f9a-153">Test-WSMan: проверяет, что WS-Management установлен и настроен.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-153">Test-WSMan: Verifies that WS-Management is installed and configured.</span></span> <span data-ttu-id="a9f9a-154">Командлет Test-WSMan проверяет, работает ли служба WS-Management (WinRM) и настроена на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-154">The Test-WSMan cmdlet tests whether the WS-Management (WinRM) service is running and configured on a local or remote computer.</span></span>

- <span data-ttu-id="a9f9a-155">Disable-WSManCredSSP: отключает проверку подлинности CredSSP на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-155">Disable-WSManCredSSP: Disables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="a9f9a-156">Enable-WSManCredSSP: включает проверку подлинности CredSSP на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-156">Enable-WSManCredSSP: Enables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="a9f9a-157">Get-WSManCredSSP: получает конфигурацию, связанную с CredSSP, для клиентского компьютера.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-157">Get-WSManCredSSP: Gets the CredSSP-related configuration for a client computer.</span></span>

## <a name="ws-management-specific-cmdlets"></a><span data-ttu-id="a9f9a-158">Командлеты, относящиеся к службе WS-Management</span><span class="sxs-lookup"><span data-stu-id="a9f9a-158">WS-Management-Specific Cmdlets</span></span>

- <span data-ttu-id="a9f9a-159">New-WSManSessionOption: создает объект WSManSessionOption для использования в качестве входных данных для одного или нескольких параметров командлета WS-Management.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-159">New-WSManSessionOption: Creates a WSManSessionOption object to use as input to one or more parameters of a WS-Management cmdlet.</span></span>

## <a name="additional-ws-management-information"></a><span data-ttu-id="a9f9a-160">Дополнительные сведения о WS-Management</span><span class="sxs-lookup"><span data-stu-id="a9f9a-160">Additional WS-Management Information</span></span>

<span data-ttu-id="a9f9a-161">Дополнительные сведения о WS-Management см. в следующих разделах библиотеки MSDN (сеть разработчиков Microsoft Developer).</span><span class="sxs-lookup"><span data-stu-id="a9f9a-161">For more information about WS-Management, see the following topics in the MSDN (Microsoft Developer Network) library.</span></span>

[<span data-ttu-id="a9f9a-162">Удаленное управление Windows</span><span class="sxs-lookup"><span data-stu-id="a9f9a-162">Windows Remote Management</span></span>](/windows/win32/winrm/portal)

[<span data-ttu-id="a9f9a-163">О служба удаленного управления Windows</span><span class="sxs-lookup"><span data-stu-id="a9f9a-163">About Windows Remote Management</span></span>](/windows/win32/winrm/about-windows-remote-management)

[<span data-ttu-id="a9f9a-164">Установка и настройка для служба удаленного управления Windows</span><span class="sxs-lookup"><span data-stu-id="a9f9a-164">Installation and Configuration for Windows Remote Management</span></span>](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[<span data-ttu-id="a9f9a-165">Архитектура служба удаленного управления Windows</span><span class="sxs-lookup"><span data-stu-id="a9f9a-165">Windows Remote Management Architecture</span></span>](/windows/win32/winrm/windows-remote-management-architecture)

[<span data-ttu-id="a9f9a-166">Протокол WS-Management</span><span class="sxs-lookup"><span data-stu-id="a9f9a-166">WS-Management Protocol</span></span>](/windows/win32/winrm/ws-management-protocol)

[<span data-ttu-id="a9f9a-167">служба удаленного управления Windows и WMI</span><span class="sxs-lookup"><span data-stu-id="a9f9a-167">Windows Remote Management and WMI</span></span>](/windows/win32/winrm/windows-remote-management-and-wmi)

[<span data-ttu-id="a9f9a-168">URI ресурсов</span><span class="sxs-lookup"><span data-stu-id="a9f9a-168">Resource URIs</span></span>](/windows/win32/winrm/resource-uris)

[<span data-ttu-id="a9f9a-169">Удаленное управление оборудованием</span><span class="sxs-lookup"><span data-stu-id="a9f9a-169">Remote Hardware Management</span></span>](/windows/win32/winrm/remote-hardware-management)

[<span data-ttu-id="a9f9a-170">События</span><span class="sxs-lookup"><span data-stu-id="a9f9a-170">Events</span></span>](/windows/win32/winrm/events)

## <a name="see-also"></a><span data-ttu-id="a9f9a-171">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="a9f9a-171">SEE ALSO</span></span>

[<span data-ttu-id="a9f9a-172">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a9f9a-172">Connect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Connect-WSMan)

[<span data-ttu-id="a9f9a-173">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a9f9a-173">Disable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[<span data-ttu-id="a9f9a-174">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a9f9a-174">Disconnect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[<span data-ttu-id="a9f9a-175">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a9f9a-175">Enable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[<span data-ttu-id="a9f9a-176">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a9f9a-176">Get-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[<span data-ttu-id="a9f9a-177">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a9f9a-177">Get-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[<span data-ttu-id="a9f9a-178">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="a9f9a-178">Invoke-WSManAction</span></span>](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[<span data-ttu-id="a9f9a-179">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a9f9a-179">New-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.New-WSManInstance)

[<span data-ttu-id="a9f9a-180">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a9f9a-180">Remove-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[<span data-ttu-id="a9f9a-181">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a9f9a-181">Set-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[<span data-ttu-id="a9f9a-182">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="a9f9a-182">Set-WSManQuickConfig</span></span>](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[<span data-ttu-id="a9f9a-183">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="a9f9a-183">Test-WSMan</span></span>](xref:Microsoft.WSMan.Management.Test-WSMan)