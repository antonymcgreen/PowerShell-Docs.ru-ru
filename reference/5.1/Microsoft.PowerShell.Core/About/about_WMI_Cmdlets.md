---
description: Содержит общие сведения об инструментарии управления Windows (WMI) и Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232261"
---
# <a name="about-wmi-cmdlets"></a><span data-ttu-id="118f1-104">Сведения о командлетах WMI</span><span class="sxs-lookup"><span data-stu-id="118f1-104">About WMI Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="118f1-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="118f1-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="118f1-106">Содержит общие сведения об инструментарии управления Windows (WMI) и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="118f1-106">Provides background information about Windows Management Instrumentation (WMI) and Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="118f1-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="118f1-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="118f1-108">В этом разделе содержатся сведения о технологии WMI, командлетах WMI для Windows PowerShell, удаленном взаимодействии на основе WMI, ускорителях WMI и устранении неполадок WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-108">This topic provides information about WMI technology, the WMI cmdlets for Windows PowerShell, WMI-based remoting, WMI accelerators, and WMI troubleshooting.</span></span> <span data-ttu-id="118f1-109">В этом разделе также приведены ссылки на дополнительные сведения об инструментарии WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-109">This topic also provides links to more information about WMI.</span></span>

### <a name="about-wmi"></a><span data-ttu-id="118f1-110">СВЕДЕНИЯ ОБ ИНСТРУМЕНТАРИИ WMI</span><span class="sxs-lookup"><span data-stu-id="118f1-110">ABOUT WMI</span></span>

<span data-ttu-id="118f1-111">Инструментарий управления Windows (WMI) разработан корпорацией Майкрософт в рамках отраслевой инициативы управления предприятием через Интернет (WBEM), целью которой является создание стандартной технологии получения доступа к информации по управлению в среде предприятия.</span><span class="sxs-lookup"><span data-stu-id="118f1-111">Windows Management Instrumentation (WMI) is the Microsoft implementation of Web-Based Enterprise Management (WBEM), which is an industry initiative to develop a standard technology for accessing management information in an enterprise environment.</span></span> <span data-ttu-id="118f1-112">В инструментарии WMI используется модель CIM — отраслевой стандарт, служащий для представления систем, приложений, сетей, устройств и других управляемых компонентов.</span><span class="sxs-lookup"><span data-stu-id="118f1-112">WMI uses the Common Information Model (CIM) industry standard to represent systems, applications, networks, devices, and other managed components.</span></span> <span data-ttu-id="118f1-113">Модель CIM разработана и обслуживается организацией Distributed Management Task Force (DMTF).</span><span class="sxs-lookup"><span data-stu-id="118f1-113">CIM is developed and maintained by the Distributed Management Task Force (DMTF).</span></span> <span data-ttu-id="118f1-114">Инструментарий WMI можно использовать для управления локальными и удаленными компьютерами.</span><span class="sxs-lookup"><span data-stu-id="118f1-114">You can use WMI to manage both local and remote computers.</span></span> <span data-ttu-id="118f1-115">Например, Инструментарий WMI можно использовать для следующих задач:</span><span class="sxs-lookup"><span data-stu-id="118f1-115">For example, you can use WMI to do the following:</span></span>

- <span data-ttu-id="118f1-116">Запуск процесса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="118f1-116">Start a process on a remote computer.</span></span>
- <span data-ttu-id="118f1-117">Удаленная перезагрузка компьютера.</span><span class="sxs-lookup"><span data-stu-id="118f1-117">Restart a computer remotely.</span></span>
- <span data-ttu-id="118f1-118">Получение списка приложений, установленных на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="118f1-118">Get a list of the applications that are installed on a local or remote computer.</span></span>
- <span data-ttu-id="118f1-119">Запросите журналы событий Windows на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="118f1-119">Query the Windows event logs on a local or remote computer.</span></span>

### <a name="the-wmi-cmdlets-for-windows-powershell"></a><span data-ttu-id="118f1-120">КОМАНДЛЕТЫ WMI ДЛЯ WINDOWS POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="118f1-120">THE WMI CMDLETS FOR WINDOWS POWERSHELL</span></span>

<span data-ttu-id="118f1-121">Windows PowerShell реализует функциональные возможности WMI с помощью набора командлетов, которые по умолчанию доступны в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="118f1-121">Windows PowerShell implements WMI functionality through a set of cmdlets that are available in Windows PowerShell by default.</span></span> <span data-ttu-id="118f1-122">Эти командлеты можно использовать для выполнения комплексных задач, необходимых для управления локальными и удаленными компьютерами.</span><span class="sxs-lookup"><span data-stu-id="118f1-122">You can use these cmdlets to complete the end-to-end tasks necessary to manage local and remote computers.</span></span>

<span data-ttu-id="118f1-123">Включены следующие командлеты WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-123">The following WMI cmdlets are included.</span></span>

|<span data-ttu-id="118f1-124">Командлет</span><span class="sxs-lookup"><span data-stu-id="118f1-124">Cmdlet</span></span>           |<span data-ttu-id="118f1-125">Описание</span><span class="sxs-lookup"><span data-stu-id="118f1-125">Description</span></span>                                   |
|-----------------|----------------------------------------------|
|<span data-ttu-id="118f1-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="118f1-126">Get-WmiObject</span></span>    |<span data-ttu-id="118f1-127">Возвращает экземпляры классов или сведений WMI</span><span class="sxs-lookup"><span data-stu-id="118f1-127">Gets instances of WMI classes or information</span></span>  |
|                 |<span data-ttu-id="118f1-128">сведения о доступных классах.</span><span class="sxs-lookup"><span data-stu-id="118f1-128">about the available classes.</span></span>                  |
|<span data-ttu-id="118f1-129">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="118f1-129">Invoke-WmiMethod</span></span> |<span data-ttu-id="118f1-130">Вызывает методы WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-130">Calls WMI methods.</span></span>                            |
|<span data-ttu-id="118f1-131">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="118f1-131">Register-WmiEvent</span></span>|<span data-ttu-id="118f1-132">Подписывается на событие WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-132">Subscribes to a WMI event.</span></span>                    |
|<span data-ttu-id="118f1-133">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="118f1-133">Remove-WmiObject</span></span> |<span data-ttu-id="118f1-134">Удаляет классы и экземпляры WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-134">Deletes WMI classes and instances.</span></span>            |
|<span data-ttu-id="118f1-135">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="118f1-135">Set-WmiInstance</span></span>  |<span data-ttu-id="118f1-136">Создает или изменяет экземпляры классов WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-136">Creates or modifies instances of WMI classes.</span></span> |

### <a name="sample-commands"></a><span data-ttu-id="118f1-137">ПРИМЕРЫ КОМАНД</span><span class="sxs-lookup"><span data-stu-id="118f1-137">SAMPLE COMMANDS</span></span>
<span data-ttu-id="118f1-138">Следующая команда отображает сведения о BIOS для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="118f1-138">The following command displays the BIOS information for the local computer.</span></span>

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

<span data-ttu-id="118f1-139">Следующая команда отображает сведения о службе WinRM для трех удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="118f1-139">The following command displays information about the WinRM service for three remote computers.</span></span>

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

<span data-ttu-id="118f1-140">Следующая более сложная команда завершает работу всех экземпляров программы.</span><span class="sxs-lookup"><span data-stu-id="118f1-140">The following more complex command exits all instances of a program.</span></span>

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a><span data-ttu-id="118f1-141">УДАЛЕННОЕ ВЗАИМОДЕЙСТВИЕ НА ОСНОВЕ ИНСТРУМЕНТАРИЯ WMI</span><span class="sxs-lookup"><span data-stu-id="118f1-141">WMI-BASED REMOTING</span></span>

<span data-ttu-id="118f1-142">Хотя возможность управлять локальной системой через WMI полезна, она является возможностью удаленного взаимодействия, которая делает инструментарий WMI мощным средством администрирования.</span><span class="sxs-lookup"><span data-stu-id="118f1-142">While the ability to manage a local system through WMI is useful, it is the remoting capabilities that make WMI a powerful administrative tool.</span></span> <span data-ttu-id="118f1-143">WMI использует распределенную модель объектов (DCOM) Майкрософт для подключения к системам и управления ими.</span><span class="sxs-lookup"><span data-stu-id="118f1-143">WMI uses Microsoft's Distributed Component Object Model (DCOM) to connect to and manage systems.</span></span> <span data-ttu-id="118f1-144">Возможно, потребуется настроить некоторые системы, чтобы разрешить подключения DCOM.</span><span class="sxs-lookup"><span data-stu-id="118f1-144">You might have to configure some systems to allow DCOM connections.</span></span>
<span data-ttu-id="118f1-145">Параметры брандмауэра и заблокированные разрешения DCOM могут блокировать возможность инструментария WMI удаленно управлять системами.</span><span class="sxs-lookup"><span data-stu-id="118f1-145">Firewall settings and locked-down DCOM permissions can block WMI's ability to remotely manage systems.</span></span>

### <a name="wmi-type-accelerators"></a><span data-ttu-id="118f1-146">УСКОРИТЕЛИ ТИПОВ WMI</span><span class="sxs-lookup"><span data-stu-id="118f1-146">WMI TYPE ACCELERATORS</span></span>

<span data-ttu-id="118f1-147">Windows PowerShell включает в себя ускорители типов WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-147">Windows PowerShell includes WMI type accelerators.</span></span> <span data-ttu-id="118f1-148">Эти ускорители типов WMI (ярлыки) обеспечивают более прямой доступ к объектам WMI, чем при использовании ускорителя, отличного от типа.</span><span class="sxs-lookup"><span data-stu-id="118f1-148">These WMI type accelerators (shortcuts) allow more direct access to a WMI objects than a non-type accelerator approach would allow.</span></span>

<span data-ttu-id="118f1-149">Инструментарий WMI поддерживает следующие ускорители типов:</span><span class="sxs-lookup"><span data-stu-id="118f1-149">The following type accelerators are supported with WMI:</span></span>

<span data-ttu-id="118f1-150">[ВМИСЕАРЧЕР] — ярлык для поиска объектов WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-150">[WMISEARCHER] - A shortcut for searching for WMI objects.</span></span>

<span data-ttu-id="118f1-151">[WMICLASS] — ярлык для доступа к статическим свойствам и методам класса.</span><span class="sxs-lookup"><span data-stu-id="118f1-151">[WMICLASS] - A shortcut for accessing the static properties and methods of a class.</span></span>

<span data-ttu-id="118f1-152">[WMI] — ярлык для получения одного экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="118f1-152">[WMI] - A shortcut for getting a single instance of a class.</span></span>

<span data-ttu-id="118f1-153">[ВМИСЕАРЧЕР] — это ускоритель типов для Манажементобжектсеарчер.</span><span class="sxs-lookup"><span data-stu-id="118f1-153">[WMISEARCHER] is a type accelerator for a ManagementObjectSearcher.</span></span> <span data-ttu-id="118f1-154">Для создания поискового запроса, который затем можно выполнить с помощью инструкции GET (), можно воспользоваться конструктором строк.</span><span class="sxs-lookup"><span data-stu-id="118f1-154">It can take a string constructor to create a searcher that you can then do a GET() on.</span></span>

<span data-ttu-id="118f1-155">Пример:</span><span class="sxs-lookup"><span data-stu-id="118f1-155">For example:</span></span>

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

<span data-ttu-id="118f1-156">[WMICLASS] — это ускоритель типов для Манажементкласс.</span><span class="sxs-lookup"><span data-stu-id="118f1-156">[WMICLASS] is a type accelerator for ManagementClass.</span></span> <span data-ttu-id="118f1-157">Он имеет конструктор строк, который принимает локальный или абсолютный путь WMI к классу WMI и возвращает объект, привязанный к этому классу.</span><span class="sxs-lookup"><span data-stu-id="118f1-157">This has a string constructor that takes a local or absolute WMI path to a WMI class and returns an object that is bound to that class.</span></span>

<span data-ttu-id="118f1-158">Пример:</span><span class="sxs-lookup"><span data-stu-id="118f1-158">For example:</span></span>

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

<span data-ttu-id="118f1-159">[WMI] является ускорителем типов для ManagementObject.</span><span class="sxs-lookup"><span data-stu-id="118f1-159">[WMI] is a type accelerator for ManagementObject.</span></span> <span data-ttu-id="118f1-160">Он имеет конструктор строк, который принимает локальный или абсолютный путь WMI к экземпляру WMI и возвращает объект, привязанный к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="118f1-160">This has a string constructor that takes a local or absolute WMI path to a WMI instance and returns an object that is bound to that instance.</span></span>

<span data-ttu-id="118f1-161">Пример:</span><span class="sxs-lookup"><span data-stu-id="118f1-161">For example:</span></span>

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a><span data-ttu-id="118f1-162">УСТРАНЕНИЕ НЕПОЛАДОК WMI</span><span class="sxs-lookup"><span data-stu-id="118f1-162">WMI TROUBLESHOOTING</span></span>

<span data-ttu-id="118f1-163">Ниже перечислены наиболее распространенные проблемы, которые могут возникнуть при попытке подключения к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="118f1-163">The following problems are the most common problems that might occur when you try to connect to a remote computer.</span></span>

<span data-ttu-id="118f1-164">Проблема 1. удаленный компьютер не подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="118f1-164">Problem 1: The remote computer is not online.</span></span>

<span data-ttu-id="118f1-165">Если компьютер находится в автономном режиме, вы не сможете подключиться к нему с помощью инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-165">If a computer is offline, you will not be able to connect to it by using WMI.</span></span>
<span data-ttu-id="118f1-166">Может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="118f1-166">You may receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

<span data-ttu-id="118f1-167">При появлении этого сообщения об ошибке убедитесь, что компьютер подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="118f1-167">If you receive this error message, verify that the computer is online.</span></span> <span data-ttu-id="118f1-168">Попробуйте проверить связь с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="118f1-168">Try to ping the remote computer.</span></span>

<span data-ttu-id="118f1-169">Проблема 2. у вас нет прав локального администратора на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="118f1-169">Problem 2: You do not have local administrator rights on the remote computer.</span></span>

<span data-ttu-id="118f1-170">Чтобы использовать инструментарий WMI удаленно, необходимо иметь права локального администратора на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="118f1-170">To use WMI remotely, you must have local administrator rights on the remote computer.</span></span> <span data-ttu-id="118f1-171">В противном случае доступ к этому компьютеру будет запрещен.</span><span class="sxs-lookup"><span data-stu-id="118f1-171">If you do not, access to that computer will be denied.</span></span>

<span data-ttu-id="118f1-172">Чтобы проверить безопасность пространства имен, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="118f1-172">To verify namespace security:</span></span>

1. <span data-ttu-id="118f1-173">Нажмите кнопку Пуск, щелкните правой кнопкой мыши Мой компьютер, а затем выберите пункт Управление.</span><span class="sxs-lookup"><span data-stu-id="118f1-173">Click Start, right-click My Computer, and then click Manage.</span></span>
2. <span data-ttu-id="118f1-174">В окне "Управление компьютером" разверните узел "службы и приложения", щелкните правой кнопкой мыши элемент управления WMI и выберите пункт "Свойства".</span><span class="sxs-lookup"><span data-stu-id="118f1-174">In Computer Management, expand Services and Applications, right-click WMI Control, and then click Properties.</span></span>
3. <span data-ttu-id="118f1-175">В диалоговом окне Свойства элемента управления WMI перейдите на вкладку Безопасность.</span><span class="sxs-lookup"><span data-stu-id="118f1-175">In the WMI Control Properties dialog box, click  the Security tab.</span></span>

<span data-ttu-id="118f1-176">Проблема 3. брандмауэр блокирует доступ к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="118f1-176">Problem 3: A firewall is blocking access to the remote computer.</span></span>

<span data-ttu-id="118f1-177">Для обхода сети Инструментарий WMI использует протокол DCOM (Distributed COM) и RPC (удаленный вызов процедур).</span><span class="sxs-lookup"><span data-stu-id="118f1-177">WMI uses the DCOM (Distributed COM) and RPC (Remote Procedure Call) protocols to traverse the network.</span></span> <span data-ttu-id="118f1-178">По умолчанию многие брандмауэры блокируют трафик DCOM и RPC.</span><span class="sxs-lookup"><span data-stu-id="118f1-178">By default, many firewalls block DCOM and RPC traffic.</span></span> <span data-ttu-id="118f1-179">Если брандмауэр блокирует эти протоколы, произойдет сбой подключения.</span><span class="sxs-lookup"><span data-stu-id="118f1-179">If your firewall is blocking these protocols, your connection will fail.</span></span> <span data-ttu-id="118f1-180">Например, брандмауэр Windows в Microsoft Windows XP с пакетом обновления 2 (SP2) настроен на автоматическую блокировку всех нежелательных сетевых трафика, включая DCOM и WMI.</span><span class="sxs-lookup"><span data-stu-id="118f1-180">For example, Windows Firewall in Microsoft Windows XP Service Pack 2 is configured to automatically block all unsolicited network traffic, including DCOM and WMI.</span></span> <span data-ttu-id="118f1-181">В конфигурации по умолчанию брандмауэр Windows отклоняет входящий запрос WMI и появляется следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="118f1-181">In its default configuration, Windows Firewall rejects an incoming WMI request, and you receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a><span data-ttu-id="118f1-182">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="118f1-182">SEE ALSO</span></span>

[<span data-ttu-id="118f1-183">Сведения об инструментарии WMI</span><span class="sxs-lookup"><span data-stu-id="118f1-183">About WMI</span></span>](/windows/win32/wmisdk/about-wmi)

<span data-ttu-id="118f1-184">[Устранение неполадок WMI](/windows/win32/wmisdk/wmi-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="118f1-184">[WMI Troubleshooting](/windows/win32/wmisdk/wmi-troubleshooting)</span></span>

[<span data-ttu-id="118f1-185">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="118f1-185">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="118f1-186">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="118f1-186">Invoke-WmiMethod</span></span>](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[<span data-ttu-id="118f1-187">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="118f1-187">Register-WmiEvent</span></span>](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[<span data-ttu-id="118f1-188">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="118f1-188">Remove-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[<span data-ttu-id="118f1-189">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="118f1-189">Set-WmiInstance</span></span>](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
