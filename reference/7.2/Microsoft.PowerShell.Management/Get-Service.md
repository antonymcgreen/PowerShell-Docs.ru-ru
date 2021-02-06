---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: c27dac11cdd8ebbf1705ac3bba0c0aa5147d4fa8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605270"
---
# <span data-ttu-id="3d260-102">Get-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-102">Get-Service</span></span>

## <span data-ttu-id="3d260-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3d260-103">SYNOPSIS</span></span>
<span data-ttu-id="3d260-104">Возвращает службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d260-104">Gets the services on the computer.</span></span>

## <span data-ttu-id="3d260-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d260-105">SYNTAX</span></span>

### <span data-ttu-id="3d260-106">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3d260-106">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3d260-107">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3d260-107">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3d260-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="3d260-108">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="3d260-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3d260-109">DESCRIPTION</span></span>

<span data-ttu-id="3d260-110">`Get-Service`Командлет возвращает объекты, представляющие службы на компьютере, включая запуск и остановку служб.</span><span class="sxs-lookup"><span data-stu-id="3d260-110">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="3d260-111">По умолчанию, если `Get-Service` выполняется без параметров, возвращаются все службы локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3d260-111">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="3d260-112">Вы можете направить этот командлет для получения только определенных служб, указав имя службы или отображаемое имя службы, либо можно передать объекты службы в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="3d260-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="3d260-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="3d260-113">EXAMPLES</span></span>

### <span data-ttu-id="3d260-114">Пример 1. получение всех служб на компьютере</span><span class="sxs-lookup"><span data-stu-id="3d260-114">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="3d260-115">Этот пример возвращает все службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d260-115">This example gets all of the services on the computer.</span></span> <span data-ttu-id="3d260-116">Он ведет себя так, как будто вы ввели `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="3d260-116">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="3d260-117">По умолчанию отображается состояние, имя службы и отображаемое имя каждой службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-117">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="3d260-118">Пример 2. Получение служб, начинающихся со строки поиска</span><span class="sxs-lookup"><span data-stu-id="3d260-118">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="3d260-119">В этом примере извлекаются службы с именами служб, которые начинаются с WMI (инструментарий управления Windows (WMI)).</span><span class="sxs-lookup"><span data-stu-id="3d260-119">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="3d260-120">Пример 3. Отображение служб, содержащих строку поиска</span><span class="sxs-lookup"><span data-stu-id="3d260-120">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="3d260-121">В этом примере отображаются службы с отображаемым именем, которое содержит слово Network.</span><span class="sxs-lookup"><span data-stu-id="3d260-121">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="3d260-122">При поиске отображаемого имени выполняется поиск служб, связанных с сетью, даже если имя службы не содержит NET, например ксмлпров, службы подготовки сети.</span><span class="sxs-lookup"><span data-stu-id="3d260-122">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="3d260-123">Пример 4. Получение служб, начинающихся со строки поиска и исключения</span><span class="sxs-lookup"><span data-stu-id="3d260-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="3d260-124">Этот пример получает только службы с именами служб, которые начинаются с **Win**, за исключением службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="3d260-124">This example only gets the services with service names that begin with **win**, except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="3d260-125">Пример 5. отображение активных в данный момент служб</span><span class="sxs-lookup"><span data-stu-id="3d260-125">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="3d260-126">В этом примере отображаются только службы с состоянием работает.</span><span class="sxs-lookup"><span data-stu-id="3d260-126">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="3d260-127">`Get-Service` Получает все службы на компьютере и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3d260-127">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="3d260-128">`Where-Object`Командлет выбирает только службы со свойством **Status** , которое равно "работает".</span><span class="sxs-lookup"><span data-stu-id="3d260-128">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="3d260-129">Status — это лишь одно из свойств объектов служб.</span><span class="sxs-lookup"><span data-stu-id="3d260-129">Status is only one property of service objects.</span></span> <span data-ttu-id="3d260-130">Чтобы просмотреть все свойства, введите `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="3d260-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="3d260-131">Пример 6. Перечисление служб на компьютере с зависимыми службами</span><span class="sxs-lookup"><span data-stu-id="3d260-131">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="3d260-132">Этот пример получает службы, имеющие зависимые службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-132">This example gets services that have dependent services.</span></span>

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

<span data-ttu-id="3d260-133">`Get-Service`Командлет получает все службы на компьютере и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3d260-133">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="3d260-134">`Where-Object`Командлет выбирает службы, свойство **DependentServices** которых не имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="3d260-134">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="3d260-135">Результаты отправляются в командлет по конвейеру `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="3d260-135">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="3d260-136">Параметр **Property** отображает имя службы, имя зависимых служб и вычисляемое свойство, которое отображает количество зависимых служб для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-136">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="3d260-137">Пример 7. Сортировка служб по значению свойства</span><span class="sxs-lookup"><span data-stu-id="3d260-137">Example 7: Sort services by property value</span></span>

<span data-ttu-id="3d260-138">В этом примере показано, что при сортировке служб в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед запуском служб.</span><span class="sxs-lookup"><span data-stu-id="3d260-138">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="3d260-139">Причина заключается в том, что значение **Status** — это перечисление, в котором Stopped имеет значение 1, а параметр выполняется значение 4.</span><span class="sxs-lookup"><span data-stu-id="3d260-139">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="3d260-140">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="3d260-140">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="3d260-141">Чтобы сначала получить список выполняющихся служб, используйте параметр по **убыванию** `Sort-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="3d260-141">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

### <span data-ttu-id="3d260-142">Пример 8. получение зависимых служб Службы</span><span class="sxs-lookup"><span data-stu-id="3d260-142">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="3d260-143">В этом примере получаются службы, необходимые службе WinRM.</span><span class="sxs-lookup"><span data-stu-id="3d260-143">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="3d260-144">Возвращается значение свойства **ServicesDependedOn** службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-144">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="3d260-145">Пример 9. Получение службы с помощью оператора конвейера</span><span class="sxs-lookup"><span data-stu-id="3d260-145">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="3d260-146">В этом примере получается служба WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d260-146">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="3d260-147">Строка имени службы, заключенная в кавычки, отправляется в конвейер в `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="3d260-147">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="3d260-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3d260-148">PARAMETERS</span></span>

### <span data-ttu-id="3d260-149">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="3d260-149">-DependentServices</span></span>

<span data-ttu-id="3d260-150">Указывает, что этот командлет возвращает только те службы, которые зависят от указанной службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-150">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d260-151">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="3d260-151">-DisplayName</span></span>

<span data-ttu-id="3d260-152">Указывает в виде массива строк отображаемые имена служб для извлечения.</span><span class="sxs-lookup"><span data-stu-id="3d260-152">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="3d260-153">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3d260-153">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3d260-154">-Exclude</span><span class="sxs-lookup"><span data-stu-id="3d260-154">-Exclude</span></span>

<span data-ttu-id="3d260-155">Указывает в виде массива строк, службы или служб, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="3d260-155">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="3d260-156">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="3d260-156">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="3d260-157">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="3d260-157">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="3d260-158">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3d260-158">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3d260-159">-Include</span><span class="sxs-lookup"><span data-stu-id="3d260-159">-Include</span></span>

<span data-ttu-id="3d260-160">Указывает в качестве массива строк, службы или службы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="3d260-160">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="3d260-161">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="3d260-161">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="3d260-162">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="3d260-162">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="3d260-163">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3d260-163">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3d260-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3d260-164">-InputObject</span></span>

<span data-ttu-id="3d260-165">Указывает объекты **ServiceController** , представляющие извлекаемые службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-165">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="3d260-166">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="3d260-166">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="3d260-167">Объект службы можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3d260-167">You can pipe a service object to this cmdlet.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3d260-168">-Name</span><span class="sxs-lookup"><span data-stu-id="3d260-168">-Name</span></span>

<span data-ttu-id="3d260-169">Задает имена получаемых служб.</span><span class="sxs-lookup"><span data-stu-id="3d260-169">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="3d260-170">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3d260-170">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="3d260-171">-RequiredServices</span><span class="sxs-lookup"><span data-stu-id="3d260-171">-RequiredServices</span></span>

<span data-ttu-id="3d260-172">Указывает, что этот командлет получает только те службы, которые требуются этой службе.</span><span class="sxs-lookup"><span data-stu-id="3d260-172">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="3d260-173">Этот параметр возвращает значение свойства **ServicesDependedOn** службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-173">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3d260-174">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3d260-174">CommonParameters</span></span>

<span data-ttu-id="3d260-175">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3d260-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d260-176">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3d260-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3d260-177">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3d260-177">INPUTS</span></span>

### <span data-ttu-id="3d260-178">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="3d260-178">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="3d260-179">В этот командлет можно передать объект службы или имя службы.</span><span class="sxs-lookup"><span data-stu-id="3d260-179">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="3d260-180">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3d260-180">OUTPUTS</span></span>

### <span data-ttu-id="3d260-181">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="3d260-181">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="3d260-182">Этот командлет возвращает объекты, представляющие службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d260-182">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="3d260-183">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3d260-183">NOTES</span></span>

<span data-ttu-id="3d260-184">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="3d260-184">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="3d260-185">Начиная с PowerShell 6,0 в объекты **ServiceController** добавляются следующие свойства: **username**, **Description**, **делайедаутостарт**, **бинарипаснаме** и **StartupType** .</span><span class="sxs-lookup"><span data-stu-id="3d260-185">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName**, **Description**, **DelayedAutoStart**, **BinaryPathName**, and **StartupType** .</span></span>

<span data-ttu-id="3d260-186">Также можно ссылаться `Get-Service` по встроенному псевдониму `gsv` .</span><span class="sxs-lookup"><span data-stu-id="3d260-186">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="3d260-187">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="3d260-187">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="3d260-188">Этот командлет может отображать службы только в том случае, если у текущего пользователя есть разрешение на их просмотр.</span><span class="sxs-lookup"><span data-stu-id="3d260-188">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="3d260-189">Если этот командлет не отображает службы, возможно, у вас нет разрешения на их просмотр.</span><span class="sxs-lookup"><span data-stu-id="3d260-189">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="3d260-190">Чтобы найти имя службы и отображаемое имя каждой службы в системе, введите `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="3d260-190">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="3d260-191">Имена служб отображаются в столбце имя, а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="3d260-191">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="3d260-192">При сортировке в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед выполнением служб.</span><span class="sxs-lookup"><span data-stu-id="3d260-192">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="3d260-193">Свойство **Status** службы имеет перечислимое значение, а имена состояний представляют целочисленные значения.</span><span class="sxs-lookup"><span data-stu-id="3d260-193">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="3d260-194">Порядок сортировки основан на целочисленном значении, а не на имени.</span><span class="sxs-lookup"><span data-stu-id="3d260-194">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="3d260-195">Остановлено перед запуском, так как параметр Stopped имеет значение 1, а для параметра работает значение 4.</span><span class="sxs-lookup"><span data-stu-id="3d260-195">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="3d260-196">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="3d260-196">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="3d260-197">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3d260-197">RELATED LINKS</span></span>

[<span data-ttu-id="3d260-198">New-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-198">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="3d260-199">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-199">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="3d260-200">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-200">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="3d260-201">Set-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-201">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="3d260-202">Start-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-202">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="3d260-203">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-203">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="3d260-204">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-204">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="3d260-205">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="3d260-205">Remove-Service</span></span>](Remove-Service.md)
