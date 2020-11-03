---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228366"
---
# <span data-ttu-id="23586-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="23586-103">Get-Service</span></span>

## <span data-ttu-id="23586-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="23586-104">SYNOPSIS</span></span>
<span data-ttu-id="23586-105">Получает службы на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="23586-105">Gets the services on a local or remote computer.</span></span>

## <span data-ttu-id="23586-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23586-106">SYNTAX</span></span>

### <span data-ttu-id="23586-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="23586-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="23586-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="23586-108">DisplayName</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="23586-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="23586-109">InputObject</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="23586-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23586-110">DESCRIPTION</span></span>

<span data-ttu-id="23586-111">Командлет **Get-Service** возвращает объекты, представляющие службы на локальном компьютере или на удаленном компьютере, включая запуск и остановку служб.</span><span class="sxs-lookup"><span data-stu-id="23586-111">The **Get-Service** cmdlet gets objects that represent the services on a local computer or on a remote computer, including running and stopped services.</span></span>

<span data-ttu-id="23586-112">Вы можете направить этот командлет для получения только определенных служб, указав имя службы или отображаемое имя службы, либо можно передать объекты службы в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="23586-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="23586-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="23586-113">EXAMPLES</span></span>

### <span data-ttu-id="23586-114">Пример 1. получение всех служб на компьютере</span><span class="sxs-lookup"><span data-stu-id="23586-114">Example 1: Get all services on the computer</span></span>

```powershell
Get-Service
```

<span data-ttu-id="23586-115">Эта команда возвращает все службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="23586-115">This command gets all of the services on the computer.</span></span>
<span data-ttu-id="23586-116">Он ведет себя так, как будто вы ввели `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="23586-116">It behaves as though you typed `Get-Service *`.</span></span>
<span data-ttu-id="23586-117">По умолчанию отображается состояние, имя службы и отображаемое имя каждой службы.</span><span class="sxs-lookup"><span data-stu-id="23586-117">The default display shows the status, service name, and display name of each service.</span></span>

### <span data-ttu-id="23586-118">Пример 2. Получение служб, начинающихся со строки поиска</span><span class="sxs-lookup"><span data-stu-id="23586-118">Example 2: Get services that begin with a search string</span></span>

```powershell
Get-Service "wmi*"
```

<span data-ttu-id="23586-119">Эта команда извлекает службы с именами служб, которые начинаются с WMI (аббревиатура для инструментарий управления Windows (WMI)).</span><span class="sxs-lookup"><span data-stu-id="23586-119">This command retrieves services with service names that begin with WMI (the acronym for Windows Management Instrumentation).</span></span>

### <span data-ttu-id="23586-120">Пример 3. Отображение служб, содержащих строку поиска</span><span class="sxs-lookup"><span data-stu-id="23586-120">Example 3: Display services that include a search string</span></span>

```powershell
Get-Service -Displayname "*network*"
```

<span data-ttu-id="23586-121">Эта команда отображает службы с отображаемым именем, которое содержит слово Network.</span><span class="sxs-lookup"><span data-stu-id="23586-121">This command displays services with a display name that includes the word network.</span></span>
<span data-ttu-id="23586-122">При поиске отображаемого имени команда находит службы, связанные с сетью, даже если имя службы не включает слово Net. (Например, служба подготовки сети (Network Provisioning Service) имеет имя xmlprov.)</span><span class="sxs-lookup"><span data-stu-id="23586-122">Searching the display name finds network-related services even when the service name does not include "Net", such as xmlprov, the Network Provisioning Service.</span></span>

### <span data-ttu-id="23586-123">Пример 4. Получение служб, начинающихся со строки поиска и исключения</span><span class="sxs-lookup"><span data-stu-id="23586-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

<span data-ttu-id="23586-124">Эти команды получают только службы с именами служб, которые начинаются с Win, за исключением службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="23586-124">These commands get only the services with service names that begin with win, except for the WinRM service.</span></span>

### <span data-ttu-id="23586-125">Пример 5. отображение активных в данный момент служб</span><span class="sxs-lookup"><span data-stu-id="23586-125">Example 5: Display services that are currently active</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="23586-126">Эта команда отображает только те службы, которые активны в данный момент.</span><span class="sxs-lookup"><span data-stu-id="23586-126">This command displays only the services that are currently active.</span></span>
<span data-ttu-id="23586-127">Для получения всех служб на компьютере используется командлет **Get-Service** .</span><span class="sxs-lookup"><span data-stu-id="23586-127">It uses the **Get-Service** cmdlet to get all of the services on the computer.</span></span>
<span data-ttu-id="23586-128">Оператор конвейера (|) передает результаты в командлет Where-Object, который выбирает только службы со свойством Status, которое равно "выполняется".</span><span class="sxs-lookup"><span data-stu-id="23586-128">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects only the services with a Status property that equals Running.</span></span>

<span data-ttu-id="23586-129">Status — это лишь одно из свойств объектов служб.</span><span class="sxs-lookup"><span data-stu-id="23586-129">Status is only one property of service objects.</span></span>
<span data-ttu-id="23586-130">Чтобы просмотреть все свойства, введите `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="23586-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="23586-131">Пример 6. Получение служб на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="23586-131">Example 6: Get the services on a remote computer</span></span>

```powershell
Get-Service -ComputerName "Server02"
```

<span data-ttu-id="23586-132">Эта команда получает службы на удаленном компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="23586-132">This command gets the services on the Server02 remote computer.</span></span>

<span data-ttu-id="23586-133">Поскольку параметр *ComputerName* командлета **Get-Service** не использует удаленное взаимодействие Windows PowerShell, этот параметр можно использовать, даже если компьютер не настроен для удаленного взаимодействия в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23586-133">Because the *ComputerName* parameter of **Get-Service** does not use Windows PowerShell remoting, you can use this parameter even if the computer is not configured for remoting in Windows PowerShell.</span></span>

### <span data-ttu-id="23586-134">Пример 7. Перечисление служб на локальном компьютере с зависимыми службами</span><span class="sxs-lookup"><span data-stu-id="23586-134">Example 7: List the services on the local computer that have dependent services</span></span>

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

<span data-ttu-id="23586-135">Первая команда использует командлет **Get-Service** для получения служб на компьютере.</span><span class="sxs-lookup"><span data-stu-id="23586-135">The first command uses the **Get-Service** cmdlet to get the services on the computer.</span></span>
<span data-ttu-id="23586-136">Оператор конвейера (|) отправляет службы в командлет **Where-Object** , который выбирает службы, свойство **DependentServices** которых не равно null.</span><span class="sxs-lookup"><span data-stu-id="23586-136">A pipeline operator (|) sends the services to the **Where-Object** cmdlet, which selects the services whose **DependentServices** property is not null.</span></span>

<span data-ttu-id="23586-137">Другой оператор конвейера отправляет результаты в командлет Format-List.</span><span class="sxs-lookup"><span data-stu-id="23586-137">Another pipeline operator sends the results to the Format-List cmdlet.</span></span>
<span data-ttu-id="23586-138">В команде используется параметр *Property* для отображения имени службы, имени зависимых служб и вычисляемого свойства, отображающего количество зависимых служб, которые имеет каждая служба.</span><span class="sxs-lookup"><span data-stu-id="23586-138">The command uses its *Property* parameter to display the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services that each service has.</span></span>

### <span data-ttu-id="23586-139">Пример 8. Сортировка служб по значению свойства</span><span class="sxs-lookup"><span data-stu-id="23586-139">Example 8: Sort services by property value</span></span>

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

<span data-ttu-id="23586-140">Эта команда показывает, что при сортировке служб в возрастающем порядке по значению свойства **Status** остановленные службы отображаются перед запуском служб.</span><span class="sxs-lookup"><span data-stu-id="23586-140">This command shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span>
<span data-ttu-id="23586-141">Это происходит из-за того, что значение Status является перечислением, в котором значение Stopped равно 1, а параметру выполняется значение 4.</span><span class="sxs-lookup"><span data-stu-id="23586-141">This happens because the value of Status is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span>

<span data-ttu-id="23586-142">Чтобы сначала получить список выполняющихся служб, используйте параметр *сортировки* командлета Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="23586-142">To list running services first, use the *Descending* parameter of the Sort-Object cmdlet.</span></span>

### <span data-ttu-id="23586-143">Пример 9. Получение служб на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="23586-143">Example 9: Get services on multiple computers</span></span>

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

<span data-ttu-id="23586-144">Эта команда использует командлет **Get-Service** для выполнения команды Get-Service WinRM на двух удаленных компьютерах и на локальном компьютере ("localhost").</span><span class="sxs-lookup"><span data-stu-id="23586-144">This command uses the **Get-Service** cmdlet to run a Get-Service Winrm command on two remote computers and the local computer ("localhost").</span></span>

<span data-ttu-id="23586-145">Команда выполняется на удаленных компьютерах, а результаты возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="23586-145">The command runs on the remote computers, and the results are returned to the local computer.</span></span>
<span data-ttu-id="23586-146">Оператор конвейера (|) отправляет результаты в командлет **Format-Table** , который форматирует службы в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="23586-146">A pipeline operator (|) sends the results to the **Format-Table** cmdlet, which formats the services as a table.</span></span>
<span data-ttu-id="23586-147">Команда **Format-Table** использует параметр *Property* для указания свойств, отображаемых в таблице, включая свойство **MachineName** .</span><span class="sxs-lookup"><span data-stu-id="23586-147">The **Format-Table** command uses the *Property* parameter to specify the properties displayed in the table, including the **MachineName** property.</span></span>

### <span data-ttu-id="23586-148">Пример 10. получение зависимых служб Службы</span><span class="sxs-lookup"><span data-stu-id="23586-148">Example 10: Get the dependent services of a service</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

<span data-ttu-id="23586-149">Эта команда получает службы, которые требуются службе WinRM.</span><span class="sxs-lookup"><span data-stu-id="23586-149">This command gets the services that the WinRM service requires.</span></span>

<span data-ttu-id="23586-150">Команда возвращает значение свойства **ServicesDependedOn** службы.</span><span class="sxs-lookup"><span data-stu-id="23586-150">The command returns the value of the **ServicesDependedOn** property of the service.</span></span>

### <span data-ttu-id="23586-151">Пример 11. Получение службы с помощью оператора конвейера</span><span class="sxs-lookup"><span data-stu-id="23586-151">Example 11: Get a service through the pipeline operator</span></span>

```powershell
"WinRM" | Get-Service
```

<span data-ttu-id="23586-152">Эта команда получает службу WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="23586-152">This command gets the WinRM service on the local computer.</span></span>
<span data-ttu-id="23586-153">В этом примере показано, что для **Get-Service** можно передать строку имени службы (заключенную в кавычки).</span><span class="sxs-lookup"><span data-stu-id="23586-153">This example shows that you can pipe a service name string (enclosed in quotation marks) to **Get-Service** .</span></span>

## <span data-ttu-id="23586-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23586-154">PARAMETERS</span></span>

### <span data-ttu-id="23586-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="23586-155">-ComputerName</span></span>

<span data-ttu-id="23586-156">Получает службы, выполняемые на указанных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="23586-156">Gets the services running on the specified computers.</span></span>
<span data-ttu-id="23586-157">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="23586-157">The default is the local computer.</span></span>

<span data-ttu-id="23586-158">Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="23586-158">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="23586-159">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="23586-159">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="23586-160">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23586-160">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="23586-161">Параметр *ComputerName* командлета **Get-Service** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="23586-161">You can use the *ComputerName* parameter of **Get-Service** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23586-162">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="23586-162">-DependentServices</span></span>

<span data-ttu-id="23586-163">Указывает, что этот командлет возвращает только те службы, которые зависят от указанной службы.</span><span class="sxs-lookup"><span data-stu-id="23586-163">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

<span data-ttu-id="23586-164">По умолчанию этот командлет получает все службы.</span><span class="sxs-lookup"><span data-stu-id="23586-164">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23586-165">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="23586-165">-DisplayName</span></span>

<span data-ttu-id="23586-166">Указывает в виде массива строк отображаемые имена служб для извлечения.</span><span class="sxs-lookup"><span data-stu-id="23586-166">Specifies, as a string array, the display names of services to be retrieved.</span></span>
<span data-ttu-id="23586-167">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="23586-167">Wildcards are permitted.</span></span>
<span data-ttu-id="23586-168">По умолчанию этот командлет получает все службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="23586-168">By default, this cmdlet gets all services on the computer.</span></span>

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

### <span data-ttu-id="23586-169">-Exclude</span><span class="sxs-lookup"><span data-stu-id="23586-169">-Exclude</span></span>

<span data-ttu-id="23586-170">Указывает в виде массива строк, службы или служб, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="23586-170">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="23586-171">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="23586-171">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="23586-172">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="23586-172">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="23586-173">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="23586-173">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="23586-174">-Include</span><span class="sxs-lookup"><span data-stu-id="23586-174">-Include</span></span>

<span data-ttu-id="23586-175">Указывает в качестве массива строк, службы или службы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="23586-175">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="23586-176">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="23586-176">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="23586-177">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="23586-177">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="23586-178">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="23586-178">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="23586-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="23586-179">-InputObject</span></span>

<span data-ttu-id="23586-180">Указывает объекты **ServiceController** , представляющие извлекаемые службы.</span><span class="sxs-lookup"><span data-stu-id="23586-180">Specifies **ServiceController** objects representing the services to be retrieved.</span></span>
<span data-ttu-id="23586-181">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="23586-181">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>
<span data-ttu-id="23586-182">Объект службы также можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="23586-182">You can also pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="23586-183">-Name</span><span class="sxs-lookup"><span data-stu-id="23586-183">-Name</span></span>

<span data-ttu-id="23586-184">Задает имена получаемых служб.</span><span class="sxs-lookup"><span data-stu-id="23586-184">Specifies the service names of services to be retrieved.</span></span>
<span data-ttu-id="23586-185">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="23586-185">Wildcards are permitted.</span></span>
<span data-ttu-id="23586-186">По умолчанию этот командлет получает все службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="23586-186">By default, this cmdlet gets all of the services on the computer.</span></span>

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

### <span data-ttu-id="23586-187">-RequiredServices</span><span class="sxs-lookup"><span data-stu-id="23586-187">-RequiredServices</span></span>

<span data-ttu-id="23586-188">Указывает, что этот командлет получает только те службы, которые требуются этой службе.</span><span class="sxs-lookup"><span data-stu-id="23586-188">Indicates that this cmdlet gets only the services that this service requires.</span></span>

<span data-ttu-id="23586-189">Этот параметр возвращает значение свойства **ServicesDependedOn** службы.</span><span class="sxs-lookup"><span data-stu-id="23586-189">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>
<span data-ttu-id="23586-190">По умолчанию этот командлет получает все службы.</span><span class="sxs-lookup"><span data-stu-id="23586-190">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="23586-191">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="23586-191">CommonParameters</span></span>

<span data-ttu-id="23586-192">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23586-192">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23586-193">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23586-193">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23586-194">Входные данные</span><span class="sxs-lookup"><span data-stu-id="23586-194">INPUTS</span></span>

### <span data-ttu-id="23586-195">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="23586-195">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="23586-196">В этот командлет можно передать объект службы или имя службы.</span><span class="sxs-lookup"><span data-stu-id="23586-196">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="23586-197">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="23586-197">OUTPUTS</span></span>

### <span data-ttu-id="23586-198">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="23586-198">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="23586-199">Этот командлет возвращает объекты, представляющие службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="23586-199">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="23586-200">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="23586-200">NOTES</span></span>

<span data-ttu-id="23586-201">Можно также обратиться к **Get-Service** по встроенному псевдониму «ГСВ».</span><span class="sxs-lookup"><span data-stu-id="23586-201">You can also refer to **Get-Service** by its built-in alias, "gsv".</span></span> <span data-ttu-id="23586-202">Подробнее см. в разделе "about_Aliases".</span><span class="sxs-lookup"><span data-stu-id="23586-202">For more information, see about_Aliases.</span></span>

<span data-ttu-id="23586-203">Этот командлет может отображать службы только в том случае, если у текущего пользователя есть разрешение на их просмотр.</span><span class="sxs-lookup"><span data-stu-id="23586-203">This cmdlet can display services only when the current user has permission to see them.</span></span>
<span data-ttu-id="23586-204">Если этот командлет не отображает службы, возможно, у вас нет разрешения на их просмотр.</span><span class="sxs-lookup"><span data-stu-id="23586-204">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="23586-205">Чтобы найти имя службы и отображаемое имя каждой службы в системе, введите `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="23586-205">To find the service name and display name of each service on your system, type `Get-Service`.</span></span>
<span data-ttu-id="23586-206">Имена служб отображаются в столбце Name, а отображаемые имена — в столбце DisplayName.</span><span class="sxs-lookup"><span data-stu-id="23586-206">The service names appear in the Name column, and the display names appear in the DisplayName column.</span></span>

<span data-ttu-id="23586-207">При сортировке по возрастанию по значению состояния "остановленные" службы предшествуют "выполняющимся".</span><span class="sxs-lookup"><span data-stu-id="23586-207">When you sort in ascending order by status value, "Stopped" services appear before "Running" services.</span></span>
<span data-ttu-id="23586-208">Свойство Status службы — это перечисляемое значение, в котором имена состояний представляют целые значения.</span><span class="sxs-lookup"><span data-stu-id="23586-208">The Status property of a service is an enumerated value in which the names of the statuses represent integer values.</span></span>
<span data-ttu-id="23586-209">Порядок сортировки основан на целочисленном значении, а не на имени.</span><span class="sxs-lookup"><span data-stu-id="23586-209">The sort is based on the integer value, not the name.</span></span>
<span data-ttu-id="23586-210">"Выполняется" отображается до "Остановлена", так как состояние "Остановлена" имеет значение 1, а "Выполняется" — значение "4".</span><span class="sxs-lookup"><span data-stu-id="23586-210">"Running" appears before "Stopped" because "Stopped" has a value of "1", and "Running" has a value of "4".</span></span>

## <span data-ttu-id="23586-211">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="23586-211">RELATED LINKS</span></span>

[<span data-ttu-id="23586-212">New-Service</span><span class="sxs-lookup"><span data-stu-id="23586-212">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="23586-213">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="23586-213">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="23586-214">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="23586-214">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="23586-215">Set-Service</span><span class="sxs-lookup"><span data-stu-id="23586-215">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="23586-216">Start-Service</span><span class="sxs-lookup"><span data-stu-id="23586-216">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="23586-217">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="23586-217">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="23586-218">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="23586-218">Suspend-Service</span></span>](Suspend-Service.md)
