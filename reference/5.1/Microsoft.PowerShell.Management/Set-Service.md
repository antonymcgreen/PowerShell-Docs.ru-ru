---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227873"
---
# <span data-ttu-id="5fb89-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-103">Set-Service</span></span>

## <span data-ttu-id="5fb89-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5fb89-104">SYNOPSIS</span></span>
<span data-ttu-id="5fb89-105">Запускает, останавливает и приостанавливает службу и изменяет ее свойства.</span><span class="sxs-lookup"><span data-stu-id="5fb89-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="5fb89-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5fb89-106">SYNTAX</span></span>

### <span data-ttu-id="5fb89-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5fb89-107">Name (Default)</span></span>

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5fb89-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="5fb89-108">InputObject</span></span>

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5fb89-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5fb89-109">DESCRIPTION</span></span>

<span data-ttu-id="5fb89-110">`Set-Service`Командлет изменяет свойства службы, такие как **Status** , **Description** , **DisplayName** и **StartupType** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="5fb89-111">`Set-Service` может запускать, останавливать, приостанавливать или прирывать работу службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="5fb89-112">Чтобы указать службу, введите ее имя службы или отправьте объект службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="5fb89-113">Или отправьте имя службы или объект службы по конвейеру в `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="5fb89-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="5fb89-114">EXAMPLES</span></span>

### <span data-ttu-id="5fb89-115">Пример 1. Изменение отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="5fb89-115">Example 1: Change a display name</span></span>

<span data-ttu-id="5fb89-116">В этом примере изменяется отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="5fb89-117">Чтобы просмотреть исходное отображаемое имя, используйте `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="5fb89-118">`Set-Service` использует параметр **Name** для указания имени службы **LanmanWorkstation** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="5fb89-119">Параметр **DisplayName** указывает новое отображаемое имя, **рабочую станцию LanMan** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="5fb89-120">Пример 2. изменение типа запуска служб</span><span class="sxs-lookup"><span data-stu-id="5fb89-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="5fb89-121">В этом примере показано, как изменить тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="5fb89-122">`Set-Service` использует параметр **Name** для указания имени службы ( **бит** ).</span><span class="sxs-lookup"><span data-stu-id="5fb89-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="5fb89-123">Параметр **StartupType** задает **Автоматический** режим службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="5fb89-124">`Get-Service` использует параметр **Name** , чтобы указать службу **BITS** и отправить объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5fb89-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="5fb89-125">`Select-Object` использует параметр **Property** для вывода состояния службы **BITS** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="5fb89-126">Пример 3. изменение описания службы</span><span class="sxs-lookup"><span data-stu-id="5fb89-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="5fb89-127">В этом примере изменяется описание службы BITS и отображается результат.</span><span class="sxs-lookup"><span data-stu-id="5fb89-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="5fb89-128">`Get-CimInstance`Используется командлет, так как он возвращает объект **Win32_Service** , содержащий **Описание** службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

<span data-ttu-id="5fb89-129">`Get-CimInstance` отправляет объект по конвейеру в `Format-List` и отображает имя и описание службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="5fb89-130">В целях сравнения команда выполняется до и после обновления описания.</span><span class="sxs-lookup"><span data-stu-id="5fb89-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="5fb89-131">`Set-Service` использует параметр **Name** для указания службы **BITS** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="5fb89-132">Параметр **Description** указывает обновленный текст для описания служб.</span><span class="sxs-lookup"><span data-stu-id="5fb89-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="5fb89-133">Пример 4. Запуск службы</span><span class="sxs-lookup"><span data-stu-id="5fb89-133">Example 4: Start a service</span></span>

<span data-ttu-id="5fb89-134">В этом примере запускается служба.</span><span class="sxs-lookup"><span data-stu-id="5fb89-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="5fb89-135">`Set-Service` использует параметр **Name** для указания службы, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="5fb89-136">Параметр **Status** использует значение **выполняется** для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="5fb89-137">Параметр **PassThru** выводит объект **ServiceController** , отображающий результаты.</span><span class="sxs-lookup"><span data-stu-id="5fb89-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="5fb89-138">Пример 5. Приостановка службы</span><span class="sxs-lookup"><span data-stu-id="5fb89-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="5fb89-139">В этом примере используется конвейер для приостановки к службе.</span><span class="sxs-lookup"><span data-stu-id="5fb89-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="5fb89-140">`Get-Service` использует параметр **Name** для указания службы **расписания** и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5fb89-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="5fb89-141">`Set-Service` использует параметр **Status** , чтобы настроить **приостановку** службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="5fb89-142">Пример 6. Завершение службы</span><span class="sxs-lookup"><span data-stu-id="5fb89-142">Example 6: Stop a service</span></span>

<span data-ttu-id="5fb89-143">В этом примере используется переменная для завершения службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="5fb89-144">`Get-Service` использует параметр **Name** для указания службы, **Schedule** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="5fb89-145">Объект хранится в переменной `$S` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="5fb89-146">`Set-Service` использует параметр **InputObject** и указывает хранимый объект `$S` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="5fb89-147">Параметр **Status** задает **остановку** службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-147">The **Status** parameter sets the service to **Stopped** .</span></span>

## <span data-ttu-id="5fb89-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5fb89-148">PARAMETERS</span></span>

### <span data-ttu-id="5fb89-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="5fb89-149">-ComputerName</span></span>

<span data-ttu-id="5fb89-150">Указывает один или несколько компьютеров.</span><span class="sxs-lookup"><span data-stu-id="5fb89-150">Specifies one or more computers.</span></span> <span data-ttu-id="5fb89-151">Для удаленных компьютеров введите имя NetBIOS, IP-адрес или полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="5fb89-151">For remote computers, type the NetBIOS name, an IP address, or a fully qualified domain name.</span></span> <span data-ttu-id="5fb89-152">Если параметр **ComputerName** не указан, команда выполняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5fb89-152">If the **ComputerName** parameter isn't specified, the command runs on the local computer.</span></span>

<span data-ttu-id="5fb89-153">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fb89-153">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="5fb89-154">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="5fb89-154">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5fb89-155">-Confirm</span></span>

<span data-ttu-id="5fb89-156">Запрашивает подтверждение перед запуском `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-156">Prompts you for confirmation before running `Set-Service`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-157">-Description</span><span class="sxs-lookup"><span data-stu-id="5fb89-157">-Description</span></span>

<span data-ttu-id="5fb89-158">Задает новое описание службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-158">Specifies a new description for the service.</span></span>

<span data-ttu-id="5fb89-159">Описание службы отображается в оснастке « **Управление компьютером», «службы** ».</span><span class="sxs-lookup"><span data-stu-id="5fb89-159">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="5fb89-160">**Описание** не является свойством `Get-Service` объекта **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-160">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="5fb89-161">Чтобы просмотреть описание службы, используйте метод `Get-CimInstance` , возвращающий объект **Win32_Service** , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="5fb89-161">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-162">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="5fb89-162">-DisplayName</span></span>

<span data-ttu-id="5fb89-163">Задает новое отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-163">Specifies a new display name for the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5fb89-164">-InputObject</span></span>

<span data-ttu-id="5fb89-165">Указывает объект **ServiceController** , представляющий службу, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5fb89-165">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="5fb89-166">Введите переменную, содержащую объект, или введите команду или выражение, которое получает объект, например `Get-Service` команду.</span><span class="sxs-lookup"><span data-stu-id="5fb89-166">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="5fb89-167">Для отправки объекта службы в можно использовать конвейер `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-167">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-168">-Name</span><span class="sxs-lookup"><span data-stu-id="5fb89-168">-Name</span></span>

<span data-ttu-id="5fb89-169">Указывает имя службы, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="5fb89-169">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="5fb89-170">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="5fb89-170">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="5fb89-171">Вы можете использовать конвейер для отправки имени службы в `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-171">You can use the pipeline to send a service name to `Set-Service`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-172">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5fb89-172">-PassThru</span></span>

<span data-ttu-id="5fb89-173">Возвращает объект **ServiceController** , представляющий измененные службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-173">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="5fb89-174">По умолчанию `Set-Service` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5fb89-174">By default, `Set-Service` doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-175">-StartupType</span><span class="sxs-lookup"><span data-stu-id="5fb89-175">-StartupType</span></span>

<span data-ttu-id="5fb89-176">Задает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-176">Sets the startup type of the service.</span></span> <span data-ttu-id="5fb89-177">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5fb89-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5fb89-178">**Автоматически** — служба запущена или была запущена операционной системой при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-178">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="5fb89-179">Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-179">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="5fb89-180">**Отключено** — служба отключена и не может быть запущена пользователем или приложением.</span><span class="sxs-lookup"><span data-stu-id="5fb89-180">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="5fb89-181">**Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.</span><span class="sxs-lookup"><span data-stu-id="5fb89-181">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="5fb89-182">**Загрузка** — указывает, что служба является драйвером устройства, запущенным загрузчиком системы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-182">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="5fb89-183">Это значение допустимо только для драйверов устройств.</span><span class="sxs-lookup"><span data-stu-id="5fb89-183">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="5fb89-184">**Система** — указывает, что служба является драйвером устройства, запущенным функцией "иоинитсистем ()".</span><span class="sxs-lookup"><span data-stu-id="5fb89-184">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="5fb89-185">Это значение допустимо только для драйверов устройств.</span><span class="sxs-lookup"><span data-stu-id="5fb89-185">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="5fb89-186">Значение по умолчанию — **Automatic** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-186">The default value is **Automatic** .</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-187">-Состояние</span><span class="sxs-lookup"><span data-stu-id="5fb89-187">-Status</span></span>

<span data-ttu-id="5fb89-188">Указывает состояние службы.</span><span class="sxs-lookup"><span data-stu-id="5fb89-188">Specifies the status for the service.</span></span>

<span data-ttu-id="5fb89-189">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5fb89-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="5fb89-190">**Приостановлено** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-190">**Paused** .</span></span> <span data-ttu-id="5fb89-191">приостанавливает службу.</span><span class="sxs-lookup"><span data-stu-id="5fb89-191">Suspends the service.</span></span>
- <span data-ttu-id="5fb89-192">**Работает** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-192">**Running** .</span></span> <span data-ttu-id="5fb89-193">запускает службу.</span><span class="sxs-lookup"><span data-stu-id="5fb89-193">Starts the service.</span></span>
- <span data-ttu-id="5fb89-194">**Остановлена** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-194">**Stopped** .</span></span> <span data-ttu-id="5fb89-195">останавливает службу.</span><span class="sxs-lookup"><span data-stu-id="5fb89-195">Stops the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5fb89-196">-WhatIf</span></span>

<span data-ttu-id="5fb89-197">Показывает, что произойдет при `Set-Service` запуске.</span><span class="sxs-lookup"><span data-stu-id="5fb89-197">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="5fb89-198">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5fb89-198">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fb89-199">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5fb89-199">CommonParameters</span></span>

<span data-ttu-id="5fb89-200">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5fb89-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5fb89-201">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5fb89-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5fb89-202">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5fb89-202">INPUTS</span></span>

### <span data-ttu-id="5fb89-203">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="5fb89-203">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="5fb89-204">Конвейер можно использовать для отправки объекта службы или строки, содержащей имя службы, в `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-204">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="5fb89-205">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5fb89-205">OUTPUTS</span></span>

### <span data-ttu-id="5fb89-206">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="5fb89-206">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="5fb89-207">По умолчанию `Set-Service` не возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="5fb89-207">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="5fb89-208">Используйте параметр **PassThru** для вывода объекта **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-208">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="5fb89-209">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5fb89-209">NOTES</span></span>

<span data-ttu-id="5fb89-210">`Set-Service` требуются повышенные разрешения.</span><span class="sxs-lookup"><span data-stu-id="5fb89-210">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="5fb89-211">Используйте команду **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-211">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="5fb89-212">`Set-Service` может управлять только службами, если у текущего пользователя есть разрешения на управление службами.</span><span class="sxs-lookup"><span data-stu-id="5fb89-212">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="5fb89-213">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="5fb89-213">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="5fb89-214">Чтобы найти имя службы или отображаемое имя службы, используйте `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb89-214">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="5fb89-215">Имена служб находятся в столбце **имя** , а отображаемые имена — в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="5fb89-215">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="5fb89-216">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5fb89-216">RELATED LINKS</span></span>

[<span data-ttu-id="5fb89-217">Get-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-217">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="5fb89-218">New-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-218">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="5fb89-219">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-219">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="5fb89-220">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-220">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="5fb89-221">Start-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-221">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="5fb89-222">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-222">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="5fb89-223">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="5fb89-223">Suspend-Service</span></span>](Suspend-Service.md)
