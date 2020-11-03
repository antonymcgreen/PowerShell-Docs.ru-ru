---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pstransportoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSTransportOption
ms.openlocfilehash: 9257c0a1829cc9cc85029f7c6fdc8e61b0ed7e56
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229749"
---
# <span data-ttu-id="602d3-103">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="602d3-103">New-PSTransportOption</span></span>

## <span data-ttu-id="602d3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="602d3-104">SYNOPSIS</span></span>

<span data-ttu-id="602d3-105">Создает объект, содержащий дополнительные параметры для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-105">Creates an object that contains advanced options for a session configuration.</span></span>

## <span data-ttu-id="602d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="602d3-106">SYNTAX</span></span>

```
New-PSTransportOption [-MaxIdleTimeoutSec <Int32>] [-ProcessIdleTimeoutSec <Int32>] [-MaxSessions <Int32>]
 [-MaxConcurrentCommandsPerSession <Int32>] [-MaxSessionsPerUser <Int32>] [-MaxMemoryPerSessionMB <Int32>]
 [-MaxProcessesPerSession <Int32>] [-MaxConcurrentUsers <Int32>] [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [<CommonParameters>]
```

## <span data-ttu-id="602d3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="602d3-107">DESCRIPTION</span></span>

<span data-ttu-id="602d3-108">Командлет **New-PSTransportOption** создает объект, содержащий параметры транспорта для конфигураций сеансов.</span><span class="sxs-lookup"><span data-stu-id="602d3-108">The **New-PSTransportOption** cmdlet creates an object that contains transport options for session configurations.</span></span>
<span data-ttu-id="602d3-109">Объект можно использовать в качестве значения параметра *транспортоптион* командлетов, которые создают или изменяют конфигурацию сеанса, например командлеты Register-PSSessionConfiguration и Set-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="602d3-109">You can use the object as the value of the *TransportOption* parameter of cmdlets that create or change a session configuration, such as the Register-PSSessionConfiguration and Set-PSSessionConfiguration cmdlets.</span></span>

<span data-ttu-id="602d3-110">Кроме того, параметры транспорта можно менять, корректируя значения свойств конфигурации сеанса на диске WSMan:.</span><span class="sxs-lookup"><span data-stu-id="602d3-110">You can also change the transport option settings by editing the values of the session configuration properties in the WSMan: drive.</span></span>
<span data-ttu-id="602d3-111">Дополнительные сведения см. в разделе Поставщик WSMan.</span><span class="sxs-lookup"><span data-stu-id="602d3-111">For more information, see WSMan Provider.</span></span>

<span data-ttu-id="602d3-112">Параметры конфигурации сеанса представляют значения сеанса, заданные на стороне сервера или при получении конца удаленного соединения.</span><span class="sxs-lookup"><span data-stu-id="602d3-112">The session configuration options represent the session values set on the server-side, or receiving end of a remote connection.</span></span>
<span data-ttu-id="602d3-113">На стороне клиента или при отправке соединения можно задавать значения параметров сеанса при создании сеанса, а также при отключении или повторном подключении клиента к сеансу.</span><span class="sxs-lookup"><span data-stu-id="602d3-113">The client-side, or sending end of the connection, can set session option values when the session is created, or when the client disconnects from or reconnects to the session.</span></span>
<span data-ttu-id="602d3-114">Если не указано иное, то в случае конфликта между значениями параметров превалируют значения на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="602d3-114">Unless stated otherwise, when the setting values conflict, the client-side values take precedence.</span></span>
<span data-ttu-id="602d3-115">При этом значения на стороне клиента не могут превышать максимальные значения и квоты, установленные в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-115">However, the client-side values cannot violate maximum values and quotas set in the session configuration.</span></span>

<span data-ttu-id="602d3-116">Без параметров командлет **New-пстранспортоптион** создает объект параметра транспорта, который имеет значения NULL для всех параметров.</span><span class="sxs-lookup"><span data-stu-id="602d3-116">Without parameters, **New-PSTransportOption** generates a transport option object that has null values for all of the options.</span></span>
<span data-ttu-id="602d3-117">Если параметр не указан, свойство объекта, представляемое этим параметром, получает нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="602d3-117">If you omit a parameter, the object has a null value for the property that the parameter represents.</span></span>
<span data-ttu-id="602d3-118">Значение NULL не влияет на конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-118">A null value does not affect the session configuration.</span></span>

<span data-ttu-id="602d3-119">Дополнительные сведения о параметрах сеанса см. в разделе New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="602d3-119">For more information about session options, see New-PSSessionOption.</span></span>
<span data-ttu-id="602d3-120">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="602d3-120">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="602d3-121">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="602d3-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="602d3-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="602d3-122">EXAMPLES</span></span>

### <span data-ttu-id="602d3-123">Пример 1. Создание параметра транспорта по умолчанию</span><span class="sxs-lookup"><span data-stu-id="602d3-123">Example 1: Generate a default transport option</span></span>

```
PS C:\> New-PSTransportOption
ProcessIdleTimeoutSec           :
MaxIdleTimeoutSec               :
MaxSessions                     :
MaxConcurrentCommandsPerSession :
MaxSessionsPerUser              :
MaxMemoryPerSessionMB           :
MaxProcessesPerSession          :
MaxConcurrentUsers              :
IdleTimeoutSec                  :
OutputBufferingMode             :
```

<span data-ttu-id="602d3-124">Эта команда выполняет команду **New-пстранспортоптион** без параметров.</span><span class="sxs-lookup"><span data-stu-id="602d3-124">This command runs the **New-PSTransportOption** without parameters.</span></span>
<span data-ttu-id="602d3-125">Выходные данные показывают, что командлет создает объект параметра транспорта, который имеет значения NULL для всех свойств.</span><span class="sxs-lookup"><span data-stu-id="602d3-125">The output shows that the cmdlet generates a transport option object that has null values for all properties.</span></span>

### <span data-ttu-id="602d3-126">Пример 2. получение параметров конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="602d3-126">Example 2: Get session configuration options</span></span>

```
The first command uses the **New-PSTransportOption** cmdlet to create a transport options object, which it saves in the $t variable. The command uses the *MaxSessions* parameter to increase the maximum number of sessions to 40.
PS C:\> $t = New-PSTransportOption -MaxSessions 40

The second command uses the **Register-PSSessionConfiguration** cmdlet create the ITTasks session configuration. The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.
PS C:\> Register-PSSessionConfiguration -Name ITTasks -TransportOption $t

The third command uses the Get-PSSessionConfiguration cmdlet to get the ITTasks session configurations and the Format-List cmdlet to display all of the properties of the session configuration object in a list. The output shows that the value of the **MaxShells** property of the session configuration is 40.
PS C:\> Get-PSSessionConfiguration -Name ITTasks | Format-List -Property *
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITTasks
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 40
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 2
Name                          : ITTasks
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
Enabled                       : True
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="602d3-127">В этом примере показано, как использовать объект параметров транспорта для задания параметров конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-127">This example shows how to use a transport options object to set session configuration options.</span></span>

### <span data-ttu-id="602d3-128">Пример 3. Настройка параметра транспорта</span><span class="sxs-lookup"><span data-stu-id="602d3-128">Example 3: Setting a transport option</span></span>

```
The first command uses the **New-PSTransportOption** cmdlet to create a transport option object. The command uses the *IdleTimeoutSec* parameter to set the **IdleTimeoutSec** property value of the object to one hour (3600 seconds). The command saves the transport objects object in the $t variable.
PS C:\> $t = New-PSTransportOption -IdleTimeoutSec 3600

The second command uses the Set-PSSessionConfiguration cmdlet to change the transport options of the ITTasks session configuration. The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.
PS C:\> Set-PSSessionConfiguration -Name ITTasks -TransportOption $t

The third command uses the New-PSSession cmdlet to create the MyITTasks session on the local computer. The command uses the **ConfigurationName** property to specify the ITTasks session configuration. The command saves the session in the $s variable.Notice that the command does not use the *SessionOption* parameter of **New-PSSession** to set a custom idle time-out for the session. If it did, the idle time-out value set in the session option would take precedence over the idle time-out set in the session configuration.
PS C:\> $s = New-PSSession -Name MyITTasks -ConfigurationName ITTasks

The fourth command uses the Format-List cmdlet to display all properties of the session in the $s variable in a list. The output shows that the session has an idle time-out of one hour (360,000 milliseconds).
PS C:\> $s | Format-List -Property *
State                  : Opened
IdleTimeout            : 3600000
OutputBufferingMode    : Block
ComputerName           : localhost
ConfigurationName      : ITTasks
InstanceId             : 4110c3f5-68ea-40fa-9bbf-04a433dbb02d
Id                     : 1
Name                   : MyITTasks
Availability           : Available
ApplicationPrivateData : {PSVersionTable}
Runspace               : System.Management.Automation.RemoteRunspace
```

<span data-ttu-id="602d3-129">Эта команда показывает, как настройка параметра транспорта в конфигурации сеанса влияет на сеансы, в которых используется эта конфигурация.</span><span class="sxs-lookup"><span data-stu-id="602d3-129">This command shows the effect of setting a transport option in a session configuration on the sessions that use the session configuration.</span></span>

## <span data-ttu-id="602d3-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="602d3-130">PARAMETERS</span></span>

### <span data-ttu-id="602d3-131">-Идлетимеаутсек</span><span class="sxs-lookup"><span data-stu-id="602d3-131">-IdleTimeoutSec</span></span>

<span data-ttu-id="602d3-132">Определяет, как долго каждый сеанс остается открытым, если удаленный компьютер не получает никаких сообщений от локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="602d3-132">Determines how long each session stays open if the remote computer does not receive any communication from the local computer.</span></span>
<span data-ttu-id="602d3-133">Сюда входит сигнал пульса.</span><span class="sxs-lookup"><span data-stu-id="602d3-133">This includes the heartbeat signal.</span></span>
<span data-ttu-id="602d3-134">По истечении этого времени сеанс закрывается.</span><span class="sxs-lookup"><span data-stu-id="602d3-134">When the interval expires, the session closes.</span></span>

<span data-ttu-id="602d3-135">Значение времени ожидания простоя имеет значительную важность, когда пользователь намеревается отключиться и повторно подключиться к сеансу.</span><span class="sxs-lookup"><span data-stu-id="602d3-135">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="602d3-136">Пользователь может подключаться к сеансу только в том случае, если время ожидания не истекло.</span><span class="sxs-lookup"><span data-stu-id="602d3-136">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="602d3-137">Параметр *IdleTimeoutSec* соответствует свойству **IdleTimeoutMs** в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-137">The *IdleTimeoutSec* parameter corresponds to the **IdleTimeoutMs** property of a session configuration.</span></span>

<span data-ttu-id="602d3-138">Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="602d3-138">Enter a value in seconds.</span></span>
<span data-ttu-id="602d3-139">Значение по умолчанию составляет 7200 секунд (2 часа).</span><span class="sxs-lookup"><span data-stu-id="602d3-139">The default value is 7200 (2 hours).</span></span>
<span data-ttu-id="602d3-140">Минимальное значение — 60 секунд (1 минута).</span><span class="sxs-lookup"><span data-stu-id="602d3-140">The minimum value is 60 (1 minute).</span></span>
<span data-ttu-id="602d3-141">Максимальное значение является значением свойства **IdleTimeout** объектов оболочки в конфигурации WSMan ( `WSMan:\\\<ComputerName\>\Shell\IdleTimeout` ).</span><span class="sxs-lookup"><span data-stu-id="602d3-141">The maximum is the value of the **IdleTimeout** property of Shell objects in the WSMan configuration (`WSMan:\\\<ComputerName\>\Shell\IdleTimeout`).</span></span>
<span data-ttu-id="602d3-142">Значение по умолчанию составляет 7200000 миллисекунд (2 часа).</span><span class="sxs-lookup"><span data-stu-id="602d3-142">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="602d3-143">Если значение времени ожидания простоя задано в параметрах сеанса и в конфигурации сеанса, приоритет имеет значение, заданное в параметрах сеанса, но не может превышать значение свойства **максидлетимеаутмс** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-143">If an idle time-out value is set in the session options and in the session configuration, value set in the session options takes precedence, but it cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span>
<span data-ttu-id="602d3-144">Для установки значения свойства **MaxIdleTimeoutMs** используется параметр *MaxIdleTimeoutSec*.</span><span class="sxs-lookup"><span data-stu-id="602d3-144">To set the value of the **MaxIdleTimeoutMs** property, use the *MaxIdleTimeoutSec* parameter.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-145">-Максконкурренткоммандсперсессион</span><span class="sxs-lookup"><span data-stu-id="602d3-145">-MaxConcurrentCommandsPerSession</span></span>

<span data-ttu-id="602d3-146">Ограничивает количество команд, которые могут выполняться одновременно в каждом сеансе, с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="602d3-146">Limits the number of commands that can run at the same time in each session to the specified value.</span></span>
<span data-ttu-id="602d3-147">Значение по умолчанию ― 1000.</span><span class="sxs-lookup"><span data-stu-id="602d3-147">The default value is 1000.</span></span>

<span data-ttu-id="602d3-148">Параметр *максконкурренткоммандсперсессион* соответствует свойству **максконкурренткоммандспершелл** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-148">The *MaxConcurrentCommandsPerSession* parameter corresponds to the **MaxConcurrentCommandsPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-149">-Максконкуррентусерс</span><span class="sxs-lookup"><span data-stu-id="602d3-149">-MaxConcurrentUsers</span></span>

<span data-ttu-id="602d3-150">Ограничивает число пользователей, которые могут одновременно выполнять команды в каждом сеансе с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="602d3-150">Limits the number of users who can run commands at the same time in each session to the specified value.</span></span>
<span data-ttu-id="602d3-151">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="602d3-151">The default value is 5.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-152">-Максидлетимеаутсек</span><span class="sxs-lookup"><span data-stu-id="602d3-152">-MaxIdleTimeoutSec</span></span>

<span data-ttu-id="602d3-153">Ограничивает время ожидания простоя, установленное для каждого сеанса, на указанное значение.</span><span class="sxs-lookup"><span data-stu-id="602d3-153">Limits the idle time-out set for each session to the specified value.</span></span>
<span data-ttu-id="602d3-154">Значение по умолчанию — \[ int \] :: MaxValue (~ 25 дней).</span><span class="sxs-lookup"><span data-stu-id="602d3-154">The default value is \[Int\]::MaxValue (~25 days).</span></span>

<span data-ttu-id="602d3-155">Значение времени ожидания простоя имеет значительную важность, когда пользователь намеревается отключиться и повторно подключиться к сеансу.</span><span class="sxs-lookup"><span data-stu-id="602d3-155">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="602d3-156">Пользователь может подключаться к сеансу только в том случае, если время ожидания не истекло.</span><span class="sxs-lookup"><span data-stu-id="602d3-156">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="602d3-157">Параметр *максидлетимеаутсек* соответствует свойству **максидлетимеаутмс** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-157">The *MaxIdleTimeoutSec* parameter corresponds to the **MaxIdleTimeoutMs** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-158">-Максмемориперсессионмб</span><span class="sxs-lookup"><span data-stu-id="602d3-158">-MaxMemoryPerSessionMB</span></span>

<span data-ttu-id="602d3-159">Ограничивает максимальный объем памяти, который может использоваться каждым сеансом.</span><span class="sxs-lookup"><span data-stu-id="602d3-159">Limits the memory used by each session to the specified value.</span></span>
<span data-ttu-id="602d3-160">Введите значение в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="602d3-160">Enter a value in megabytes.</span></span>
<span data-ttu-id="602d3-161">Значение по умолчанию — 1024 МБ (1 ГБ).</span><span class="sxs-lookup"><span data-stu-id="602d3-161">The default value is 1024 megabytes (1 GB).</span></span>

<span data-ttu-id="602d3-162">Параметр *максмемориперсессионмб* соответствует свойству **максмеморипершеллмб** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-162">The *MaxMemoryPerSessionMB* parameter corresponds to the **MaxMemoryPerShellMB** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-163">-Макспроцессесперсессион</span><span class="sxs-lookup"><span data-stu-id="602d3-163">-MaxProcessesPerSession</span></span>

<span data-ttu-id="602d3-164">Устанавливает максимальное количество процессов, которые могут выполняться в одном сеансе.</span><span class="sxs-lookup"><span data-stu-id="602d3-164">Limits the number of processes running in each session to the specified value.</span></span>
<span data-ttu-id="602d3-165">Значение по умолчанию — 15.</span><span class="sxs-lookup"><span data-stu-id="602d3-165">The default value is 15.</span></span>

<span data-ttu-id="602d3-166">Параметр *макспроцессесперсессион* соответствует свойству **макспроцессеспершелл** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-166">The *MaxProcessesPerSession* parameter corresponds to the **MaxProcessesPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-167">-Макссессионс</span><span class="sxs-lookup"><span data-stu-id="602d3-167">-MaxSessions</span></span>

<span data-ttu-id="602d3-168">Ограничивает количество сеансов, которые могут использовать соответствующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="602d3-168">Limits the number of sessions that use the session configuration.</span></span>
<span data-ttu-id="602d3-169">По умолчанию используется значение 25.</span><span class="sxs-lookup"><span data-stu-id="602d3-169">The default value is 25.</span></span>

<span data-ttu-id="602d3-170">Параметр *макссессионс* соответствует свойству **максшеллс** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-170">The *MaxSessions* parameter corresponds to the **MaxShells** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-171">-Макссессионсперусер</span><span class="sxs-lookup"><span data-stu-id="602d3-171">-MaxSessionsPerUser</span></span>

<span data-ttu-id="602d3-172">Ограничивает максимальное количество сеансов с использованием соответствующей конфигурации и учетных данных указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="602d3-172">Limits the number of sessions that use the session configuration and run with the credentials of a given user to the specified value.</span></span>
<span data-ttu-id="602d3-173">По умолчанию используется значение 25.</span><span class="sxs-lookup"><span data-stu-id="602d3-173">The default value is 25.</span></span>

<span data-ttu-id="602d3-174">При указании этого значения следует учесть, что многие пользователи могут использовать учетные данные пользователя запуска от имени.</span><span class="sxs-lookup"><span data-stu-id="602d3-174">When you specify this value, consider that many users might be using the credentials of a run as user.</span></span>

<span data-ttu-id="602d3-175">Параметр *макссессионсперусер* соответствует свойству **максшеллсперусер** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="602d3-175">The *MaxSessionsPerUser* parameter corresponds to the **MaxShellsPerUser** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-176">-Аутпутбуфферингмоде</span><span class="sxs-lookup"><span data-stu-id="602d3-176">-OutputBufferingMode</span></span>

<span data-ttu-id="602d3-177">Определяет порядок управления выходным потоком команды в отключенных сеансах при заполнении .</span><span class="sxs-lookup"><span data-stu-id="602d3-177">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>
<span data-ttu-id="602d3-178">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="602d3-178">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="602d3-179">Блокировка.</span><span class="sxs-lookup"><span data-stu-id="602d3-179">Block.</span></span>
<span data-ttu-id="602d3-180">при заполнении выходного буфера выполнение команды приостанавливается до тех пор, пока буфер не будет очищен.</span><span class="sxs-lookup"><span data-stu-id="602d3-180">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="602d3-181">Drop.</span><span class="sxs-lookup"><span data-stu-id="602d3-181">Drop.</span></span>
<span data-ttu-id="602d3-182">при заполнении выходного буфера выполнение команды продолжается.</span><span class="sxs-lookup"><span data-stu-id="602d3-182">When the output buffer is full, execution continues.</span></span>
<span data-ttu-id="602d3-183">Новые выходные данные сохраняются вместо наиболее старых.</span><span class="sxs-lookup"><span data-stu-id="602d3-183">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="602d3-184">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="602d3-184">None.</span></span>
<span data-ttu-id="602d3-185">порядок действий в случае переполнения выходного буфера не установлен.</span><span class="sxs-lookup"><span data-stu-id="602d3-185">No output buffering mode is specified.</span></span>

<span data-ttu-id="602d3-186">Значение свойства **аутпутбуфферингмоде** в сеансах по умолчанию — Block.</span><span class="sxs-lookup"><span data-stu-id="602d3-186">The default value of the **OutputBufferingMode** property of sessions is Block.</span></span>

```yaml
Type: System.Nullable`1[System.Management.Automation.Runspaces.OutputBufferingMode]
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-187">-Процессидлетимеаутсек</span><span class="sxs-lookup"><span data-stu-id="602d3-187">-ProcessIdleTimeoutSec</span></span>

<span data-ttu-id="602d3-188">Ограничивает время ожидания для каждого хост-процесса указанным значением.</span><span class="sxs-lookup"><span data-stu-id="602d3-188">Limits the time-out for each host process to the specified value.</span></span>
<span data-ttu-id="602d3-189">Значение по умолчанию 0 означает отсутствие значения времени ожидания для процесса.</span><span class="sxs-lookup"><span data-stu-id="602d3-189">The default value, 0, means that there is no time-out value for the process.</span></span>

<span data-ttu-id="602d3-190">Другие конфигурации сеанса имеют значения времени ожидания для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="602d3-190">Other session configurations have per-process time-out values.</span></span>
<span data-ttu-id="602d3-191">Например, конфигурация сеанса **Microsoft. PowerShell. Workflow** имеет значение времени ожидания для каждого процесса, равное 28800 секундам (8 часов).</span><span class="sxs-lookup"><span data-stu-id="602d3-191">For example, the **Microsoft.PowerShell.Workflow** session configuration has a per-process time-out value of 28800 seconds (8 hours).</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="602d3-192">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="602d3-192">CommonParameters</span></span>
<span data-ttu-id="602d3-193">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="602d3-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="602d3-194">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="602d3-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="602d3-195">Входные данные</span><span class="sxs-lookup"><span data-stu-id="602d3-195">INPUTS</span></span>

### <span data-ttu-id="602d3-196">Нет</span><span class="sxs-lookup"><span data-stu-id="602d3-196">None</span></span>

<span data-ttu-id="602d3-197">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="602d3-197">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="602d3-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="602d3-198">OUTPUTS</span></span>

### <span data-ttu-id="602d3-199">Microsoft. PowerShell. Commands. Всманконфигуратионоптион</span><span class="sxs-lookup"><span data-stu-id="602d3-199">Microsoft.PowerShell.Commands.WSManConfigurationOption</span></span>

## <span data-ttu-id="602d3-200">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="602d3-200">NOTES</span></span>

- <span data-ttu-id="602d3-201">Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров.</span><span class="sxs-lookup"><span data-stu-id="602d3-201">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="602d3-202">Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="602d3-202">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="602d3-203">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="602d3-203">RELATED LINKS</span></span>

[<span data-ttu-id="602d3-204">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="602d3-204">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="602d3-205">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="602d3-205">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="602d3-206">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="602d3-206">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="602d3-207">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="602d3-207">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)
