---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: ad1fd47291cbe8977bd2f2ada4981589714c93a3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226794"
---
# <span data-ttu-id="4b790-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-103">Set-Service</span></span>

## <span data-ttu-id="4b790-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b790-104">SYNOPSIS</span></span>
<span data-ttu-id="4b790-105">Запускает, останавливает и приостанавливает службу и изменяет ее свойства.</span><span class="sxs-lookup"><span data-stu-id="4b790-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="4b790-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b790-106">SYNTAX</span></span>

### <span data-ttu-id="4b790-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4b790-107">Name (Default)</span></span>

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4b790-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="4b790-108">InputObject</span></span>

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4b790-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b790-109">DESCRIPTION</span></span>

<span data-ttu-id="4b790-110">`Set-Service`Командлет изменяет свойства службы, такие как **Status** , **Description** , **DisplayName** и **StartupType**.</span><span class="sxs-lookup"><span data-stu-id="4b790-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType**.</span></span> <span data-ttu-id="4b790-111">`Set-Service` может запускать, останавливать, приостанавливать или прирывать работу службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="4b790-112">Чтобы указать службу, введите ее имя службы или отправьте объект службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="4b790-113">Или отправьте имя службы или объект службы по конвейеру в `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="4b790-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b790-114">EXAMPLES</span></span>

### <span data-ttu-id="4b790-115">Пример 1. Изменение отображаемого имени</span><span class="sxs-lookup"><span data-stu-id="4b790-115">Example 1: Change a display name</span></span>

<span data-ttu-id="4b790-116">В этом примере изменяется отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="4b790-117">Чтобы просмотреть исходное отображаемое имя, используйте `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="4b790-118">`Set-Service` использует параметр **Name** для указания имени службы **LanmanWorkstation**.</span><span class="sxs-lookup"><span data-stu-id="4b790-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation**.</span></span> <span data-ttu-id="4b790-119">Параметр **DisplayName** указывает новое отображаемое имя, **рабочую станцию LanMan**.</span><span class="sxs-lookup"><span data-stu-id="4b790-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation**.</span></span>

### <span data-ttu-id="4b790-120">Пример 2. изменение типа запуска служб</span><span class="sxs-lookup"><span data-stu-id="4b790-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="4b790-121">В этом примере показано, как изменить тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="4b790-122">`Set-Service` использует параметр **Name** для указания имени службы ( **бит** ).</span><span class="sxs-lookup"><span data-stu-id="4b790-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS**.</span></span> <span data-ttu-id="4b790-123">Параметр **StartupType** задает **Автоматический** режим службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-123">The **StartupType** parameter sets the service to **Automatic**.</span></span>

<span data-ttu-id="4b790-124">`Get-Service` использует параметр **Name** , чтобы указать службу **BITS** и отправить объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4b790-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="4b790-125">`Select-Object` использует параметр **Property** для вывода состояния службы **BITS** .</span><span class="sxs-lookup"><span data-stu-id="4b790-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="4b790-126">Пример 3. изменение описания службы</span><span class="sxs-lookup"><span data-stu-id="4b790-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="4b790-127">В этом примере изменяется описание службы BITS и отображается результат.</span><span class="sxs-lookup"><span data-stu-id="4b790-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="4b790-128">`Get-CimInstance`Используется командлет, так как он возвращает объект **Win32_Service** , содержащий **Описание** службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description**.</span></span>

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

<span data-ttu-id="4b790-129">`Get-CimInstance` отправляет объект по конвейеру в `Format-List` и отображает имя и описание службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="4b790-130">В целях сравнения команда выполняется до и после обновления описания.</span><span class="sxs-lookup"><span data-stu-id="4b790-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="4b790-131">`Set-Service` использует параметр **Name** для указания службы **BITS** .</span><span class="sxs-lookup"><span data-stu-id="4b790-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="4b790-132">Параметр **Description** указывает обновленный текст для описания служб.</span><span class="sxs-lookup"><span data-stu-id="4b790-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="4b790-133">Пример 4. Запуск службы</span><span class="sxs-lookup"><span data-stu-id="4b790-133">Example 4: Start a service</span></span>

<span data-ttu-id="4b790-134">В этом примере запускается служба.</span><span class="sxs-lookup"><span data-stu-id="4b790-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="4b790-135">`Set-Service` использует параметр **Name** для указания службы, **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="4b790-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM**.</span></span> <span data-ttu-id="4b790-136">Параметр **Status** использует значение **выполняется** для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="4b790-137">Параметр **PassThru** выводит объект **ServiceController** , отображающий результаты.</span><span class="sxs-lookup"><span data-stu-id="4b790-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="4b790-138">Пример 5. Приостановка службы</span><span class="sxs-lookup"><span data-stu-id="4b790-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="4b790-139">В этом примере используется конвейер для приостановки к службе.</span><span class="sxs-lookup"><span data-stu-id="4b790-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="4b790-140">`Get-Service` использует параметр **Name** для указания службы **расписания** и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4b790-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="4b790-141">`Set-Service` использует параметр **Status** , чтобы настроить **приостановку** службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-141">`Set-Service` uses the **Status** parameter to set the service to **Paused**.</span></span>

### <span data-ttu-id="4b790-142">Пример 6. Завершение службы</span><span class="sxs-lookup"><span data-stu-id="4b790-142">Example 6: Stop a service</span></span>

<span data-ttu-id="4b790-143">В этом примере используется переменная для завершения службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="4b790-144">`Get-Service` использует параметр **Name** для указания службы, **Schedule**.</span><span class="sxs-lookup"><span data-stu-id="4b790-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule**.</span></span> <span data-ttu-id="4b790-145">Объект хранится в переменной `$S` .</span><span class="sxs-lookup"><span data-stu-id="4b790-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="4b790-146">`Set-Service` использует параметр **InputObject** и указывает хранимый объект `$S` .</span><span class="sxs-lookup"><span data-stu-id="4b790-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="4b790-147">Параметр **Status** задает **остановку** службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-147">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="4b790-148">Пример 7. Завершение службы в удаленной системе</span><span class="sxs-lookup"><span data-stu-id="4b790-148">Example 7: Stop a service on a remote system</span></span>

<span data-ttu-id="4b790-149">В этом примере останавливается служба на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4b790-149">This example stops a service on a remote computer.</span></span>
<span data-ttu-id="4b790-150">Дополнительные сведения см. в разделе [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="4b790-150">For more information, see [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

<span data-ttu-id="4b790-151">`Get-Credential` запрашивает имя пользователя и пароль и сохраняет учетные данные в `$Cred` переменной.</span><span class="sxs-lookup"><span data-stu-id="4b790-151">`Get-Credential` prompts for a username and password, and stores the credentials in the `$Cred` variable.</span></span> <span data-ttu-id="4b790-152">`Get-Service` использует параметр **Name** для указания службы **расписания** .</span><span class="sxs-lookup"><span data-stu-id="4b790-152">`Get-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="4b790-153">Объект хранится в переменной `$S` .</span><span class="sxs-lookup"><span data-stu-id="4b790-153">The object is stored in the variable, `$S`.</span></span>

<span data-ttu-id="4b790-154">`Invoke-Command` Задает удаленный компьютер с помощью параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="4b790-154">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer.</span></span> <span data-ttu-id="4b790-155">Параметр **Credential** использует `$Cred` переменную для входа на компьютер.</span><span class="sxs-lookup"><span data-stu-id="4b790-155">The **Credential** parameter uses the `$Cred` variable to sign on to the computer.</span></span> <span data-ttu-id="4b790-156">Блок **ScriptBlock** вызывает `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-156">The **ScriptBlock** calls `Set-Service`.</span></span> <span data-ttu-id="4b790-157">Параметр **InputObject** указывает хранимый объект службы `$S` .</span><span class="sxs-lookup"><span data-stu-id="4b790-157">The **InputObject** parameter specifies the service object stored `$S`.</span></span> <span data-ttu-id="4b790-158">Параметр **Status** задает **остановку** службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-158">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="4b790-159">Пример 8. изменение учетных данных службы</span><span class="sxs-lookup"><span data-stu-id="4b790-159">Example 8: Change credential of a service</span></span>

<span data-ttu-id="4b790-160">В этом примере изменяются учетные данные, используемые для управления службой.</span><span class="sxs-lookup"><span data-stu-id="4b790-160">This example changes the credentials that are used to manage a service.</span></span>

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

<span data-ttu-id="4b790-161">`Get-Credential` запрашивает имя пользователя и пароль и сохраняет учетные данные в `$credential` переменной.</span><span class="sxs-lookup"><span data-stu-id="4b790-161">`Get-Credential` prompts for a username and password, and stores the credentials in the `$credential` variable.</span></span> <span data-ttu-id="4b790-162">`Set-Service` использует параметр **Name** для указания службы **расписания** .</span><span class="sxs-lookup"><span data-stu-id="4b790-162">`Set-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="4b790-163">Параметр **Credential** использует `$credential` переменную и обновляет службу **расписания** .</span><span class="sxs-lookup"><span data-stu-id="4b790-163">The **Credential** parameter uses the `$credential` variable and updates the **Schedule** service.</span></span>

## <span data-ttu-id="4b790-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b790-164">PARAMETERS</span></span>

### <span data-ttu-id="4b790-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4b790-165">-Confirm</span></span>

<span data-ttu-id="4b790-166">Запрашивает подтверждение перед запуском `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-166">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="4b790-167">-Credential</span><span class="sxs-lookup"><span data-stu-id="4b790-167">-Credential</span></span>

<span data-ttu-id="4b790-168">Указывает учетную запись, используемую службой в качестве [учетной записи входа службы](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="4b790-168">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="4b790-169">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="4b790-169">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="4b790-170">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="4b790-170">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="4b790-171">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="4b790-171">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="4b790-172">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="4b790-172">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="4b790-173">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="4b790-173">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b790-174">-Description</span><span class="sxs-lookup"><span data-stu-id="4b790-174">-Description</span></span>

<span data-ttu-id="4b790-175">Задает новое описание службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-175">Specifies a new description for the service.</span></span>

<span data-ttu-id="4b790-176">Описание службы отображается в оснастке « **Управление компьютером», «службы** ».</span><span class="sxs-lookup"><span data-stu-id="4b790-176">The service description appears in **Computer Management, Services**.</span></span> <span data-ttu-id="4b790-177">**Описание** не является свойством `Get-Service` объекта **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="4b790-177">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="4b790-178">Чтобы просмотреть описание службы, используйте метод `Get-CimInstance` , возвращающий объект **Win32_Service** , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="4b790-178">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="4b790-179">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="4b790-179">-DisplayName</span></span>

<span data-ttu-id="4b790-180">Задает новое отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-180">Specifies a new display name for the service.</span></span>

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

### <span data-ttu-id="4b790-181">-Force</span><span class="sxs-lookup"><span data-stu-id="4b790-181">-Force</span></span>

<span data-ttu-id="4b790-182">Указывает режим отмены службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-182">Specifies the Stop mode of the service.</span></span> <span data-ttu-id="4b790-183">Этот параметр работает, только если `-Status Stopped` используется.</span><span class="sxs-lookup"><span data-stu-id="4b790-183">This parameter only works when `-Status Stopped` is used.</span></span> <span data-ttu-id="4b790-184">Если параметр включен, `Set-Service` зависимые службы останавливаются до того, как целевая служба будет остановлена.</span><span class="sxs-lookup"><span data-stu-id="4b790-184">If enabled, `Set-Service` stops the dependent services before the target service is stopped.</span></span> <span data-ttu-id="4b790-185">По умолчанию исключения возникают, когда другие работающие службы зависят от целевой службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-185">By default, exceptions are raised when other running services depend on the target service.</span></span>

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

### <span data-ttu-id="4b790-186">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4b790-186">-InputObject</span></span>

<span data-ttu-id="4b790-187">Указывает объект **ServiceController** , представляющий службу, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="4b790-187">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="4b790-188">Введите переменную, содержащую объект, или введите команду или выражение, которое получает объект, например `Get-Service` команду.</span><span class="sxs-lookup"><span data-stu-id="4b790-188">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="4b790-189">Для отправки объекта службы в можно использовать конвейер `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-189">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4b790-190">-Name</span><span class="sxs-lookup"><span data-stu-id="4b790-190">-Name</span></span>

<span data-ttu-id="4b790-191">Указывает имя службы, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="4b790-191">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="4b790-192">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="4b790-192">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="4b790-193">Вы можете использовать конвейер для отправки имени службы в `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-193">You can use the pipeline to send a service name to `Set-Service`.</span></span>

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

### <span data-ttu-id="4b790-194">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4b790-194">-PassThru</span></span>

<span data-ttu-id="4b790-195">Возвращает объект **ServiceController** , представляющий измененные службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-195">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="4b790-196">По умолчанию `Set-Service` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4b790-196">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="4b790-197">-StartupType</span><span class="sxs-lookup"><span data-stu-id="4b790-197">-StartupType</span></span>

<span data-ttu-id="4b790-198">Указывает режим запуска службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-198">Specifies the start mode of the service.</span></span>

<span data-ttu-id="4b790-199">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4b790-199">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4b790-200">**Автоматически** — служба запущена или была запущена операционной системой при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="4b790-200">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="4b790-201">Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="4b790-201">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="4b790-202">**Аутоматикделайедстарт** — запускается вскоре после загрузки системы.</span><span class="sxs-lookup"><span data-stu-id="4b790-202">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="4b790-203">**Отключено** — служба отключена и не может быть запущена пользователем или приложением.</span><span class="sxs-lookup"><span data-stu-id="4b790-203">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="4b790-204">**Инвалидвалуе** — не действует.</span><span class="sxs-lookup"><span data-stu-id="4b790-204">**InvalidValue** - Has no effect.</span></span> <span data-ttu-id="4b790-205">Командлет не возвращает ошибку, но StartupType службы не изменяется.</span><span class="sxs-lookup"><span data-stu-id="4b790-205">The cmdlet does not return an error but the StartupType of the service is not changed.</span></span>
- <span data-ttu-id="4b790-206">**Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.</span><span class="sxs-lookup"><span data-stu-id="4b790-206">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b790-207">-Состояние</span><span class="sxs-lookup"><span data-stu-id="4b790-207">-Status</span></span>

<span data-ttu-id="4b790-208">Указывает состояние службы.</span><span class="sxs-lookup"><span data-stu-id="4b790-208">Specifies the status for the service.</span></span>

<span data-ttu-id="4b790-209">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4b790-209">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4b790-210">**Приостановлено**.</span><span class="sxs-lookup"><span data-stu-id="4b790-210">**Paused**.</span></span> <span data-ttu-id="4b790-211">приостанавливает службу.</span><span class="sxs-lookup"><span data-stu-id="4b790-211">Suspends the service.</span></span>
- <span data-ttu-id="4b790-212">**Работает**.</span><span class="sxs-lookup"><span data-stu-id="4b790-212">**Running**.</span></span> <span data-ttu-id="4b790-213">запускает службу.</span><span class="sxs-lookup"><span data-stu-id="4b790-213">Starts the service.</span></span>
- <span data-ttu-id="4b790-214">**Остановлена**.</span><span class="sxs-lookup"><span data-stu-id="4b790-214">**Stopped**.</span></span> <span data-ttu-id="4b790-215">останавливает службу.</span><span class="sxs-lookup"><span data-stu-id="4b790-215">Stops the service.</span></span>

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

### <span data-ttu-id="4b790-216">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4b790-216">-WhatIf</span></span>

<span data-ttu-id="4b790-217">Показывает, что произойдет при `Set-Service` запуске.</span><span class="sxs-lookup"><span data-stu-id="4b790-217">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="4b790-218">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4b790-218">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="4b790-219">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4b790-219">CommonParameters</span></span>

<span data-ttu-id="4b790-220">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b790-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b790-221">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b790-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b790-222">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4b790-222">INPUTS</span></span>

### <span data-ttu-id="4b790-223">System.ServiceProcess.ServiceController, System.String</span><span class="sxs-lookup"><span data-stu-id="4b790-223">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="4b790-224">Конвейер можно использовать для отправки объекта службы или строки, содержащей имя службы, в `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-224">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="4b790-225">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4b790-225">OUTPUTS</span></span>

### <span data-ttu-id="4b790-226">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="4b790-226">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="4b790-227">По умолчанию `Set-Service` не возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="4b790-227">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="4b790-228">Используйте параметр **PassThru** для вывода объекта **ServiceController** .</span><span class="sxs-lookup"><span data-stu-id="4b790-228">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="4b790-229">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4b790-229">NOTES</span></span>

<span data-ttu-id="4b790-230">`Set-Service` требуются повышенные разрешения.</span><span class="sxs-lookup"><span data-stu-id="4b790-230">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="4b790-231">Используйте команду **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="4b790-231">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="4b790-232">`Set-Service` может управлять только службами, если у текущего пользователя есть разрешения на управление службами.</span><span class="sxs-lookup"><span data-stu-id="4b790-232">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="4b790-233">Если команда работает неправильно, возможно, у вас нет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="4b790-233">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="4b790-234">Чтобы найти имя службы или отображаемое имя службы, используйте `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="4b790-234">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="4b790-235">Имена служб находятся в столбце **имя** , а отображаемые имена — в столбце **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="4b790-235">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="4b790-236">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4b790-236">RELATED LINKS</span></span>

[<span data-ttu-id="4b790-237">Get-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-237">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="4b790-238">New-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-238">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="4b790-239">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-239">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="4b790-240">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-240">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="4b790-241">Start-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-241">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="4b790-242">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-242">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="4b790-243">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-243">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="4b790-244">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="4b790-244">Remove-Service</span></span>](Remove-Service.md)
