---
description: Windows PowerShell создает журнал событий Windows с именем "Windows PowerShell" для записи событий Windows PowerShell. Этот журнал можно просмотреть в Просмотр событий или с помощью командлетов, получающих события, например `Get-EventLog` командлет. По умолчанию обработчики и события поставщика Windows PowerShell записываются в журнал событий, но можно использовать переменные предпочтений журнала событий для настройки журнала событий. Например, можно добавить события о командах Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232418"
---
# <a name="about-eventlogs"></a><span data-ttu-id="7634c-107">О журналах событий</span><span class="sxs-lookup"><span data-stu-id="7634c-107">About Eventlogs</span></span>

## <a name="short-description"></a><span data-ttu-id="7634c-108">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="7634c-108">Short Description</span></span>

<span data-ttu-id="7634c-109">Windows PowerShell создает журнал событий Windows с именем "Windows PowerShell" для записи событий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7634c-109">Windows PowerShell creates a Windows event log that is named "Windows PowerShell" to record Windows PowerShell events.</span></span> <span data-ttu-id="7634c-110">Этот журнал можно просмотреть в Просмотр событий или с помощью командлетов, получающих события, например `Get-EventLog` командлет.</span><span class="sxs-lookup"><span data-stu-id="7634c-110">You can view this log in Event Viewer or by using cmdlets that get events, such as the `Get-EventLog` cmdlet.</span></span> <span data-ttu-id="7634c-111">По умолчанию обработчики и события поставщика Windows PowerShell записываются в журнал событий, но можно использовать переменные предпочтений журнала событий для настройки журнала событий.</span><span class="sxs-lookup"><span data-stu-id="7634c-111">By default, Windows PowerShell engine and provider events are recorded in the event log, but you can use the event log preference variables to customize the event log.</span></span> <span data-ttu-id="7634c-112">Например, можно добавить события о командах Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7634c-112">For example, you can add events about Windows PowerShell commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="7634c-113">Полное описание</span><span class="sxs-lookup"><span data-stu-id="7634c-113">Long Description</span></span>

<span data-ttu-id="7634c-114">В журнале событий Windows PowerShell записываются сведения об операциях Windows PowerShell, таких как запуск и остановка ядра программы, а также запуск и остановка поставщиков Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7634c-114">The Windows PowerShell event log records details of Windows PowerShell operations, such as starting and stopping the program engine and starting and stopping the Windows PowerShell providers.</span></span> <span data-ttu-id="7634c-115">Можно также заносить в журнал сведения о командах Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7634c-115">You can also log details about Windows PowerShell commands.</span></span>

<span data-ttu-id="7634c-116">Журнал событий Windows PowerShell находится в группе Журналы приложений и служб.</span><span class="sxs-lookup"><span data-stu-id="7634c-116">The Windows PowerShell event log is in the Application and Services Logs group.</span></span> <span data-ttu-id="7634c-117">Журнал Windows PowerShell — это классический журнал событий, который не использует технологию событий Windows.</span><span class="sxs-lookup"><span data-stu-id="7634c-117">The Windows PowerShell log is a classic event log that does not use the Windows Eventing technology.</span></span> <span data-ttu-id="7634c-118">Чтобы просмотреть журнал, используйте командлеты, предназначенные для классических журналов событий, например `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="7634c-118">To view the log, use the cmdlets designed for classic event logs, such as `Get-EventLog`.</span></span>

## <a name="viewing-the-windows-powershell-event-log"></a><span data-ttu-id="7634c-119">Просмотр журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7634c-119">Viewing the Windows PowerShell Event Log</span></span>

<span data-ttu-id="7634c-120">Журнал событий Windows PowerShell можно просмотреть в Просмотр событий или с помощью `Get-EventLog` `Get-WmiObject` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="7634c-120">You can view the Windows PowerShell event log in Event Viewer or by using the `Get-EventLog` and `Get-WmiObject` cmdlets.</span></span> <span data-ttu-id="7634c-121">Чтобы просмотреть содержимое журнала Windows PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-121">To view the contents of the Windows PowerShell log, type:</span></span>

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

<span data-ttu-id="7634c-122">Чтобы проверить события и их свойства, используйте `Sort-Object` командлет, `Group-Object` командлет и командлеты, которые содержат `Format` команду ( `Format` командлеты).</span><span class="sxs-lookup"><span data-stu-id="7634c-122">To examine the events and their properties, use the `Sort-Object` cmdlet, the `Group-Object` cmdlet, and the cmdlets that contain the `Format` verb (the `Format` cmdlets).</span></span>

<span data-ttu-id="7634c-123">Например, чтобы просмотреть события в журнале, сгруппированные по ИДЕНТИФИКАТОРу события, введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-123">For example, to view the events in the log grouped by the event ID, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

<span data-ttu-id="7634c-124">Или введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-124">Or, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

<span data-ttu-id="7634c-125">Чтобы просмотреть все классические журналы событий, введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-125">To view all the classic event logs, type:</span></span>

```powershell
Get-EventLog -List
```

<span data-ttu-id="7634c-126">Кроме того, с помощью `Get-WmiObject` командлета можно использовать классы инструментарий управления Windows (WMI) (WMI), связанные с событиями, для просмотра журнала событий.</span><span class="sxs-lookup"><span data-stu-id="7634c-126">You can also use the `Get-WmiObject` cmdlet to use the event-related Windows Management Instrumentation (WMI) classes to examine the event log.</span></span> <span data-ttu-id="7634c-127">Например, чтобы просмотреть все свойства файла журнала событий, введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-127">For example, to view all the properties of the event log file, type:</span></span>

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

<span data-ttu-id="7634c-128">Чтобы найти классы WMI, связанные с событиями Win32, введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-128">To find the Win32 event-related WMI classes, type:</span></span>

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

<span data-ttu-id="7634c-129">Для получения дополнительных сведений введите «Get-Help Get-EventLog» и «Get-Help Get-WmiObject».</span><span class="sxs-lookup"><span data-stu-id="7634c-129">For more information, type "Get-Help Get-EventLog" and "Get-Help Get-WmiObject".</span></span>

## <a name="selecting-events-for-the-windows-powershell-event-log"></a><span data-ttu-id="7634c-130">Выбор событий для журнала событий Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7634c-130">Selecting Events for the Windows PowerShell Event Log</span></span>

<span data-ttu-id="7634c-131">Можно использовать переменные предпочтений журнала событий, чтобы определить, какие события записываются в журнал событий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7634c-131">You can use the event log preference variables to determine which events are recorded in the Windows PowerShell event log.</span></span>

<span data-ttu-id="7634c-132">Существует шесть переменных предпочтений журнала событий. две переменные для каждого из трех компонентов ведения журнала: ядро (программа Windows PowerShell), поставщики и команды.</span><span class="sxs-lookup"><span data-stu-id="7634c-132">There are six event log preference variables; two variables for each of the three logging components: the engine (the Windows PowerShell program), the providers, and the commands.</span></span> <span data-ttu-id="7634c-133">Переменные Лифецикливент зарегистрируют нормальные события запуска и остановки.</span><span class="sxs-lookup"><span data-stu-id="7634c-133">The LifeCycleEvent variables log normal starting and stopping events.</span></span> <span data-ttu-id="7634c-134">Переменные работоспособности регистрируют события ошибок.</span><span class="sxs-lookup"><span data-stu-id="7634c-134">The Health variables log error events.</span></span>

<span data-ttu-id="7634c-135">В следующей таблице перечислены переменные предпочтений журнала событий.</span><span class="sxs-lookup"><span data-stu-id="7634c-135">The following table lists the event log preference variables.</span></span>

|<span data-ttu-id="7634c-136">Переменная</span><span class="sxs-lookup"><span data-stu-id="7634c-136">Variable</span></span>                  |<span data-ttu-id="7634c-137">Описание</span><span class="sxs-lookup"><span data-stu-id="7634c-137">Description</span></span>                                    |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="7634c-138">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-138">$LogEngineLifeCycleEvent</span></span>  |<span data-ttu-id="7634c-139">Заносит в журнал начало и конец PowerShell</span><span class="sxs-lookup"><span data-stu-id="7634c-139">Logs the start and stop of PowerShell</span></span>          |
|<span data-ttu-id="7634c-140">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-140">$LogEngineHealthEvent</span></span>     |<span data-ttu-id="7634c-141">Журналы ошибок программы PowerShell</span><span class="sxs-lookup"><span data-stu-id="7634c-141">Logs PowerShell program errors</span></span>                 |
|<span data-ttu-id="7634c-142">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-142">$LogProviderLifeCycleEvent</span></span>|<span data-ttu-id="7634c-143">Записывает в журнал начало и конец поставщиков PowerShell</span><span class="sxs-lookup"><span data-stu-id="7634c-143">Logs the start and stop of PowerShell providers</span></span>|
|<span data-ttu-id="7634c-144">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-144">$LogProviderHealthEvent</span></span>   |<span data-ttu-id="7634c-145">Регистрирует ошибки поставщика PowerShell</span><span class="sxs-lookup"><span data-stu-id="7634c-145">Logs PowerShell provider errors</span></span>                |
|<span data-ttu-id="7634c-146">$LogCommandLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-146">$LogCommandLifeCycleEvent</span></span> |<span data-ttu-id="7634c-147">Записывает в журнал запуск и завершение команд</span><span class="sxs-lookup"><span data-stu-id="7634c-147">Logs the starting and completion of commands</span></span>   |
|<span data-ttu-id="7634c-148">$LogCommandHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-148">$LogCommandHealthEvent</span></span>    |<span data-ttu-id="7634c-149">Регистрирует ошибки команды</span><span class="sxs-lookup"><span data-stu-id="7634c-149">Logs command errors</span></span>                            |

<span data-ttu-id="7634c-150">(Дополнительные сведения о поставщиках Windows PowerShell см. в разделе [about_Providers](about_Providers.md).)</span><span class="sxs-lookup"><span data-stu-id="7634c-150">(For information about Windows PowerShell providers, see [about_Providers](about_Providers.md).)</span></span>

<span data-ttu-id="7634c-151">По умолчанию включены только следующие типы событий:</span><span class="sxs-lookup"><span data-stu-id="7634c-151">By default, only the following event types are enabled:</span></span>

* <span data-ttu-id="7634c-152">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-152">$LogEngineLifeCycleEvent</span></span>
* <span data-ttu-id="7634c-153">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-153">$LogEngineHealthEvent</span></span>
* <span data-ttu-id="7634c-154">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-154">$LogProviderLifeCycleEvent</span></span>
* <span data-ttu-id="7634c-155">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7634c-155">$LogProviderHealthEvent</span></span>

<span data-ttu-id="7634c-156">Чтобы включить тип событий, задайте для него переменную предпочтение $true.</span><span class="sxs-lookup"><span data-stu-id="7634c-156">To enable an event type, set the preference variable for that event type to $true.</span></span> <span data-ttu-id="7634c-157">Например, чтобы включить события жизненного цикла команды, введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-157">For example, to enable command life-cycle events, type:</span></span>

```powershell
$LogCommandLifeCycleEvent
```

<span data-ttu-id="7634c-158">Или введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-158">Or, type:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="7634c-159">Чтобы отключить тип события, задайте для него переменную предпочтение $false.</span><span class="sxs-lookup"><span data-stu-id="7634c-159">To disable an event type, set the preference variable for that event type to $false.</span></span> <span data-ttu-id="7634c-160">Например, чтобы отключить события жизненного цикла команды, введите:</span><span class="sxs-lookup"><span data-stu-id="7634c-160">For example, to disable command life-cycle events, type:</span></span>

```powershell
$LogProviderLifeCycleEvent = $false
```

<span data-ttu-id="7634c-161">Можно отключить любое событие, за исключением событий, указывающих на то, что ядро Windows PowerShell и основные поставщики запущены.</span><span class="sxs-lookup"><span data-stu-id="7634c-161">You can disable any event, except for the events that indicate that the Windows PowerShell engine and the core providers are started.</span></span> <span data-ttu-id="7634c-162">Эти события создаются до запуска профилей Windows PowerShell и перед тем, как программа размещения готова принять команды.</span><span class="sxs-lookup"><span data-stu-id="7634c-162">These events are generated before the Windows PowerShell profiles are run and before the host program is ready to accept commands.</span></span>

<span data-ttu-id="7634c-163">Параметры переменных применяются только к текущему сеансу Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7634c-163">The variable settings apply only for the current Windows PowerShell session.</span></span>
<span data-ttu-id="7634c-164">Чтобы применить их ко всем сеансам Windows PowerShell, добавьте их в профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7634c-164">To apply them to all Windows PowerShell sessions, add them to your Windows PowerShell profile.</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="7634c-165">События модуля ведения журнала</span><span class="sxs-lookup"><span data-stu-id="7634c-165">Logging Module Events</span></span>

<span data-ttu-id="7634c-166">Начиная с Windows PowerShell 3,0, вы можете записывать события выполнения командлетов и функций в модулях и оснастках Windows PowerShell, установив для свойства LogPipelineExecutionDetails модулей и оснасток значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="7634c-166">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets and functions in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="7634c-167">В Windows PowerShell 2,0 эта функция доступна только для оснасток.</span><span class="sxs-lookup"><span data-stu-id="7634c-167">In Windows PowerShell 2.0, this feature is available only for snap-ins.</span></span>

<span data-ttu-id="7634c-168">Если значение свойства LogPipelineExecutionDetails равно TRUE ( `$true` ), Windows PowerShell записывает события командлета и выполнения функции в сеансе в журнал Windows PowerShell в Просмотр событий.</span><span class="sxs-lookup"><span data-stu-id="7634c-168">When the LogPipelineExecutionDetails property value is TRUE (`$true`), Windows PowerShell writes cmdlet and function execution events in the session to the Windows PowerShell log in Event Viewer.</span></span> <span data-ttu-id="7634c-169">Параметр действует только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="7634c-169">The setting is effective only in the current session.</span></span>

<span data-ttu-id="7634c-170">Чтобы включить ведение журнала событий выполнения командлетов и функций в модуле, используйте следующую последовательность команд.</span><span class="sxs-lookup"><span data-stu-id="7634c-170">To enable logging of execution events of cmdlets and functions in a module, use the following command sequence.</span></span>

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

<span data-ttu-id="7634c-171">Чтобы включить ведение журнала событий выполнения командлетов в оснастке, используйте следующую последовательность команд.</span><span class="sxs-lookup"><span data-stu-id="7634c-171">To enable logging of execution events of cmdlets in a snap-in, use the following command sequence.</span></span>

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

<span data-ttu-id="7634c-172">Чтобы отключить ведение журнала, используйте ту же последовательность команд, чтобы задать для свойства значение FALSE ( `$false` ).</span><span class="sxs-lookup"><span data-stu-id="7634c-172">To disable logging, use the same command sequence to set the property value to FALSE (`$false`).</span></span>

<span data-ttu-id="7634c-173">Можно также использовать параметр групповая политика "включить ведение журнала модуля", чтобы включить и отключить ведение журнала модуля и оснастки.</span><span class="sxs-lookup"><span data-stu-id="7634c-173">You can also use the "Turn on Module Logging" Group Policy setting to enable and disable module and snap-in logging.</span></span> <span data-ttu-id="7634c-174">Значение политики включает список имен модулей и оснасток.</span><span class="sxs-lookup"><span data-stu-id="7634c-174">The policy value includes a list of module and snap-in names.</span></span> <span data-ttu-id="7634c-175">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="7634c-175">Wildcards are supported.</span></span>

<span data-ttu-id="7634c-176">Если параметр "включить ведение журнала модуля" установлен для модуля, значение свойства LogPipelineExecutionDetails модуля равно TRUE во всех сеансах, и его нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="7634c-176">When "Turn on Module Logging" is set for a module, the value of the LogPipelineExecutionDetails property of the module is TRUE in all sessions and it cannot be changed.</span></span>

<span data-ttu-id="7634c-177">Параметр групповой политики включить ведение журнала модуля находится в следующих групповая политика путях:</span><span class="sxs-lookup"><span data-stu-id="7634c-177">The Turn On Module Logging group policy setting is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

<span data-ttu-id="7634c-178">Политика конфигурации пользователя имеет приоритет над политикой конфигурации компьютера, и обе политики имеют предпочтение по отношению к значению свойства LogPipelineExecutionDetails модулей и оснасток.</span><span class="sxs-lookup"><span data-stu-id="7634c-178">The User Configuration policy takes precedence over the Computer Configuration policy, and both policies take preference over the value of the LogPipelineExecutionDetails property of modules and snap-ins.</span></span>

<span data-ttu-id="7634c-179">Дополнительные сведения об этом параметре групповая политика см. в разделе [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="7634c-179">For more information about this Group Policy setting, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="security-and-auditing"></a><span data-ttu-id="7634c-180">Безопасность и аудит</span><span class="sxs-lookup"><span data-stu-id="7634c-180">Security and Auditing</span></span>

<span data-ttu-id="7634c-181">Журнал событий Windows PowerShell предназначен для указания активности и предоставления оперативных сведений для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="7634c-181">The Windows PowerShell event log is designed to indicate activity and to provide operational details for troubleshooting.</span></span>

<span data-ttu-id="7634c-182">Однако, подобно большинству журналов событий приложений на базе Windows, журнал событий Windows PowerShell не обеспечивает безопасность.</span><span class="sxs-lookup"><span data-stu-id="7634c-182">However, like most Windows-based application event logs, the Windows PowerShell event log is not designed to be secure.</span></span> <span data-ttu-id="7634c-183">Его не следует использовать для аудита безопасности или записи конфиденциальных или собственных сведений.</span><span class="sxs-lookup"><span data-stu-id="7634c-183">It should not be used to audit security or to record confidential or proprietary information.</span></span>

<span data-ttu-id="7634c-184">Журналы событий предназначены для чтения и понимания пользователями.</span><span class="sxs-lookup"><span data-stu-id="7634c-184">Event logs are designed to be read and understood by users.</span></span> <span data-ttu-id="7634c-185">Пользователи могут выполнять чтение и запись в журнал.</span><span class="sxs-lookup"><span data-stu-id="7634c-185">Users can read from and write to the log.</span></span> <span data-ttu-id="7634c-186">Пользователь-злоумышленник может прочитать журнал событий на локальном или удаленном компьютере, записать ложные данные, а затем предотвратить ведение журнала действий.</span><span class="sxs-lookup"><span data-stu-id="7634c-186">A malicious user could read an event log on a local or remote computer, record false data, and then prevent the logging of their activities.</span></span>

## <a name="notes"></a><span data-ttu-id="7634c-187">Примечания</span><span class="sxs-lookup"><span data-stu-id="7634c-187">Notes</span></span>

<span data-ttu-id="7634c-188">Авторы модулей могут добавлять функции ведения журнала в свои модули.</span><span class="sxs-lookup"><span data-stu-id="7634c-188">Authors of module authors can add logging features to their modules.</span></span> <span data-ttu-id="7634c-189">Дополнительные сведения см. [в разделе Написание модуля Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="7634c-189">For more information, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="see-also"></a><span data-ttu-id="7634c-190">См. также:</span><span class="sxs-lookup"><span data-stu-id="7634c-190">See Also</span></span>

[<span data-ttu-id="7634c-191">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="7634c-191">Get-EventLog</span></span>](xref:Microsoft.PowerShell.Management.Get-EventLog)

[<span data-ttu-id="7634c-192">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="7634c-192">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="7634c-193">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="7634c-193">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="7634c-194">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="7634c-194">about_Preference_Variables</span></span>](about_Preference_Variables.md)
