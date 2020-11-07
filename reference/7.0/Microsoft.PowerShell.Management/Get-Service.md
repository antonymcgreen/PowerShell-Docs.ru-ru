---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 15bfe1123ba005a7b326c234fad360d6d9d6cc4d
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345737"
---
# <span data-ttu-id="eaa70-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-103">Get-Service</span></span>

## <span data-ttu-id="eaa70-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="eaa70-104">SYNOPSIS</span></span>
<span data-ttu-id="eaa70-105">Возвращает службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eaa70-105">Gets the services on the computer.</span></span>

## <span data-ttu-id="eaa70-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eaa70-106">SYNTAX</span></span>

### <span data-ttu-id="eaa70-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="eaa70-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="eaa70-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="eaa70-108">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="eaa70-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="eaa70-109">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="eaa70-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eaa70-110">DESCRIPTION</span></span>

<span data-ttu-id="eaa70-111">`Get-Service`Командлет возвращает объекты, представляющие службы на компьютере, включая запуск и остановку служб.</span><span class="sxs-lookup"><span data-stu-id="eaa70-111">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="eaa70-112">По умолчанию, если `Get-Service` выполняется без параметров, возвращаются все службы локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="eaa70-112">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="eaa70-113">Вы можете направить этот командлет для получения только определенных служб, указав имя службы или отображаемое имя службы, либо можно передать объекты службы в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="eaa70-113">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="eaa70-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="eaa70-114">EXAMPLES</span></span>

### <span data-ttu-id="eaa70-115">Пример 1. получение всех служб на компьютере</span><span class="sxs-lookup"><span data-stu-id="eaa70-115">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="eaa70-116">Этот пример возвращает все службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eaa70-116">This example gets all of the services on the computer.</span></span> <span data-ttu-id="eaa70-117">Он ведет себя так, как будто вы ввели `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-117">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="eaa70-118">По умолчанию отображается состояние, имя службы и отображаемое имя каждой службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-118">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="eaa70-119">Пример 2. Получение служб, начинающихся со строки поиска</span><span class="sxs-lookup"><span data-stu-id="eaa70-119">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="eaa70-120">В этом примере извлекаются службы с именами служб, которые начинаются с WMI (инструментарий управления Windows (WMI)).</span><span class="sxs-lookup"><span data-stu-id="eaa70-120">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="eaa70-121">Пример 3. Отображение служб, содержащих строку поиска</span><span class="sxs-lookup"><span data-stu-id="eaa70-121">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="eaa70-122">В этом примере отображаются службы с отображаемым именем, которое содержит слово Network.</span><span class="sxs-lookup"><span data-stu-id="eaa70-122">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="eaa70-123">При поиске отображаемого имени выполняется поиск служб, связанных с сетью, даже если имя службы не содержит NET, например ксмлпров, службы подготовки сети.</span><span class="sxs-lookup"><span data-stu-id="eaa70-123">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="eaa70-124">Пример 4. Получение служб, начинающихся со строки поиска и исключения</span><span class="sxs-lookup"><span data-stu-id="eaa70-124">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="eaa70-125">Этот пример получает только службы с именами служб, которые начинаются с **Win** , за исключением службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="eaa70-125">This example only gets the services with service names that begin with **win** , except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="eaa70-126">Пример 5. отображение активных в данный момент служб</span><span class="sxs-lookup"><span data-stu-id="eaa70-126">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="eaa70-127">В этом примере отображаются только службы с состоянием работает.</span><span class="sxs-lookup"><span data-stu-id="eaa70-127">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="eaa70-128">`Get-Service` Получает все службы на компьютере и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="eaa70-128">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="eaa70-129">`Where-Object`Командлет выбирает только службы со свойством **Status** , которое равно "работает".</span><span class="sxs-lookup"><span data-stu-id="eaa70-129">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="eaa70-130">Status — это лишь одно из свойств объектов служб.</span><span class="sxs-lookup"><span data-stu-id="eaa70-130">Status is only one property of service objects.</span></span> <span data-ttu-id="eaa70-131">Чтобы просмотреть все свойства, введите `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-131">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="eaa70-132">Пример 6. Перечисление служб на компьютере с зависимыми службами</span><span class="sxs-lookup"><span data-stu-id="eaa70-132">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="eaa70-133">Этот пример получает службы, имеющие зависимые службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-133">This example gets services that have dependent services.</span></span>

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

<span data-ttu-id="eaa70-134">`Get-Service`Командлет получает все службы на компьютере и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="eaa70-134">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="eaa70-135">`Where-Object`Командлет выбирает службы, свойство **DependentServices** которых не имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="eaa70-135">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="eaa70-136">Результаты отправляются в командлет по конвейеру `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-136">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="eaa70-137">Параметр **Property** отображает имя службы, имя зависимых служб и вычисляемое свойство, которое отображает количество зависимых служб для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-137">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="eaa70-138">Пример 7. Сортировка служб по значению свойства</span><span class="sxs-lookup"><span data-stu-id="eaa70-138">Example 7: Sort services by property value</span></span>

<span data-ttu-id="eaa70-139">В этом примере показано, что при сортировке служб в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед запуском служб.</span><span class="sxs-lookup"><span data-stu-id="eaa70-139">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="eaa70-140">Причина заключается в том, что значение **Status** — это перечисление, в котором Stopped имеет значение 1, а параметр выполняется значение 4.</span><span class="sxs-lookup"><span data-stu-id="eaa70-140">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="eaa70-141">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="eaa70-141">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="eaa70-142">Чтобы сначала получить список выполняющихся служб, используйте параметр по **убыванию** `Sort-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="eaa70-142">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

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

### <span data-ttu-id="eaa70-143">Пример 8. получение зависимых служб Службы</span><span class="sxs-lookup"><span data-stu-id="eaa70-143">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="eaa70-144">В этом примере получаются службы, необходимые службе WinRM.</span><span class="sxs-lookup"><span data-stu-id="eaa70-144">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="eaa70-145">Возвращается значение свойства **ServicesDependedOn** службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-145">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="eaa70-146">Пример 9. Получение службы с помощью оператора конвейера</span><span class="sxs-lookup"><span data-stu-id="eaa70-146">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="eaa70-147">В этом примере получается служба WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="eaa70-147">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="eaa70-148">Строка имени службы, заключенная в кавычки, отправляется в конвейер в `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-148">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="eaa70-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eaa70-149">PARAMETERS</span></span>

### <span data-ttu-id="eaa70-150">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="eaa70-150">-DependentServices</span></span>

<span data-ttu-id="eaa70-151">Указывает, что этот командлет возвращает только те службы, которые зависят от указанной службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-151">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

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

### <span data-ttu-id="eaa70-152">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="eaa70-152">-DisplayName</span></span>

<span data-ttu-id="eaa70-153">Указывает в виде массива строк отображаемые имена служб для извлечения.</span><span class="sxs-lookup"><span data-stu-id="eaa70-153">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="eaa70-154">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="eaa70-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="eaa70-155">-Exclude</span><span class="sxs-lookup"><span data-stu-id="eaa70-155">-Exclude</span></span>

<span data-ttu-id="eaa70-156">Указывает в виде массива строк, службы или служб, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="eaa70-156">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="eaa70-157">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="eaa70-157">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="eaa70-158">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-158">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="eaa70-159">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="eaa70-159">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="eaa70-160">-Include</span><span class="sxs-lookup"><span data-stu-id="eaa70-160">-Include</span></span>

<span data-ttu-id="eaa70-161">Указывает в качестве массива строк, службы или службы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="eaa70-161">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="eaa70-162">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="eaa70-162">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="eaa70-163">Введите элемент имени или шаблон, например `s*` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-163">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="eaa70-164">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="eaa70-164">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="eaa70-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="eaa70-165">-InputObject</span></span>

<span data-ttu-id="eaa70-166">Указывает объекты **ServiceController** , представляющие извлекаемые службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-166">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="eaa70-167">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="eaa70-167">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="eaa70-168">Объект службы можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="eaa70-168">You can pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="eaa70-169">-Name</span><span class="sxs-lookup"><span data-stu-id="eaa70-169">-Name</span></span>

<span data-ttu-id="eaa70-170">Задает имена получаемых служб.</span><span class="sxs-lookup"><span data-stu-id="eaa70-170">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="eaa70-171">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="eaa70-171">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="eaa70-172">-RequiredServices</span><span class="sxs-lookup"><span data-stu-id="eaa70-172">-RequiredServices</span></span>

<span data-ttu-id="eaa70-173">Указывает, что этот командлет получает только те службы, которые требуются этой службе.</span><span class="sxs-lookup"><span data-stu-id="eaa70-173">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="eaa70-174">Этот параметр возвращает значение свойства **ServicesDependedOn** службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-174">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

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

### <span data-ttu-id="eaa70-175">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="eaa70-175">CommonParameters</span></span>

<span data-ttu-id="eaa70-176">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eaa70-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eaa70-177">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eaa70-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eaa70-178">Входные данные</span><span class="sxs-lookup"><span data-stu-id="eaa70-178">INPUTS</span></span>

### <span data-ttu-id="eaa70-179">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="eaa70-179">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="eaa70-180">В этот командлет можно передать объект службы или имя службы.</span><span class="sxs-lookup"><span data-stu-id="eaa70-180">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="eaa70-181">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="eaa70-181">OUTPUTS</span></span>

### <span data-ttu-id="eaa70-182">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="eaa70-182">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="eaa70-183">Этот командлет возвращает объекты, представляющие службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eaa70-183">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="eaa70-184">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="eaa70-184">NOTES</span></span>

<span data-ttu-id="eaa70-185">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="eaa70-185">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="eaa70-186">Начиная с PowerShell 6,0 в объекты **ServiceController** добавляются следующие свойства: **username** , **Description** , **делайедаутостарт** , **бинарипаснаме** и **StartupType** .</span><span class="sxs-lookup"><span data-stu-id="eaa70-186">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName** , **Description** , **DelayedAutoStart** , **BinaryPathName** , and **StartupType** .</span></span>

<span data-ttu-id="eaa70-187">Также можно ссылаться `Get-Service` по встроенному псевдониму `gsv` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-187">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="eaa70-188">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="eaa70-188">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="eaa70-189">Этот командлет может отображать службы только в том случае, если у текущего пользователя есть разрешение на их просмотр.</span><span class="sxs-lookup"><span data-stu-id="eaa70-189">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="eaa70-190">Если этот командлет не отображает службы, возможно, у вас нет разрешения на их просмотр.</span><span class="sxs-lookup"><span data-stu-id="eaa70-190">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="eaa70-191">Чтобы найти имя службы и отображаемое имя каждой службы в системе, введите `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="eaa70-191">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="eaa70-192">Имена служб отображаются в столбце имя, а отображаемые имена отображаются в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="eaa70-192">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="eaa70-193">При сортировке в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед выполнением служб.</span><span class="sxs-lookup"><span data-stu-id="eaa70-193">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="eaa70-194">Свойство **Status** службы имеет перечислимое значение, а имена состояний представляют целочисленные значения.</span><span class="sxs-lookup"><span data-stu-id="eaa70-194">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="eaa70-195">Порядок сортировки основан на целочисленном значении, а не на имени.</span><span class="sxs-lookup"><span data-stu-id="eaa70-195">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="eaa70-196">Остановлено перед запуском, так как параметр Stopped имеет значение 1, а для параметра работает значение 4.</span><span class="sxs-lookup"><span data-stu-id="eaa70-196">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="eaa70-197">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="eaa70-197">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="eaa70-198">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="eaa70-198">RELATED LINKS</span></span>

[<span data-ttu-id="eaa70-199">New-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-199">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="eaa70-200">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-200">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="eaa70-201">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-201">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="eaa70-202">Set-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-202">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="eaa70-203">Start-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-203">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="eaa70-204">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-204">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="eaa70-205">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-205">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="eaa70-206">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="eaa70-206">Remove-Service</span></span>](Remove-Service.md)
