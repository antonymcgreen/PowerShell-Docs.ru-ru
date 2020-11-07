---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 81920303d130a306674033b2b1ba57a3e71c949c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347437"
---
# <span data-ttu-id="47e00-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-103">New-Service</span></span>

## <span data-ttu-id="47e00-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="47e00-104">SYNOPSIS</span></span>
<span data-ttu-id="47e00-105">Создает новую службу Windows.</span><span class="sxs-lookup"><span data-stu-id="47e00-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="47e00-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47e00-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="47e00-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47e00-107">DESCRIPTION</span></span>

<span data-ttu-id="47e00-108">`New-Service`Командлет создает новую запись для службы Windows в реестре и в базе данных службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="47e00-109">Для новой службы требуется исполняемый файл, который выполняется во время работы службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="47e00-110">Параметры этого командлета позволяют задать отображаемое имя, описание, тип запуска и зависимости службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="47e00-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="47e00-111">EXAMPLES</span></span>

### <span data-ttu-id="47e00-112">Пример 1. Создание службы</span><span class="sxs-lookup"><span data-stu-id="47e00-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="47e00-113">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="47e00-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="47e00-114">Пример 2. Создание службы, включающей описание, тип запуска и отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="47e00-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="47e00-115">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="47e00-115">This command creates a service named TestService.</span></span> <span data-ttu-id="47e00-116">В нем используются параметры `New-Service` для указания описания, типа запуска и отображаемого имени для новой службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="47e00-117">Пример 3. Просмотр новой службы</span><span class="sxs-lookup"><span data-stu-id="47e00-117">Example 3: View the new service</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service -Filter "Name='testservice'"
```

```Output
ExitCode  : 0
Name      : testservice
ProcessId : 0
StartMode : Auto
State     : Stopped
Status    : OK
```

<span data-ttu-id="47e00-118">Эта команда использует `Get-CimInstance` для получения объекта **Win32_Service** для новой службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="47e00-119">Этот объект содержит режим запуска службы и описание службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="47e00-120">Пример 4. Настройка SecurityDescriptor службы при создании.</span><span class="sxs-lookup"><span data-stu-id="47e00-120">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="47e00-121">В этом примере добавляется **SecurityDescriptor** создаваемой службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-121">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="47e00-122">**SecurityDescriptor** хранится в `$SDDLToSet` переменной.</span><span class="sxs-lookup"><span data-stu-id="47e00-122">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="47e00-123">Параметр **SecurityDescriptorSddl** использует, `$SDDL` чтобы задать **SecurityDescriptor** для новой службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-123">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="47e00-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47e00-124">PARAMETERS</span></span>

### <span data-ttu-id="47e00-125">-Бинарипаснаме</span><span class="sxs-lookup"><span data-stu-id="47e00-125">-BinaryPathName</span></span>

<span data-ttu-id="47e00-126">Указывает путь к исполняемому файлу службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="47e00-127">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="47e00-127">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47e00-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="47e00-128">-Credential</span></span>

<span data-ttu-id="47e00-129">Указывает учетную запись, используемую службой в качестве [учетной записи входа службы](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="47e00-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="47e00-130">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="47e00-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="47e00-131">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="47e00-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="47e00-132">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="47e00-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="47e00-133">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="47e00-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="47e00-134">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="47e00-134">-DependsOn</span></span>

<span data-ttu-id="47e00-135">Задает имена других служб, от которых зависит новая служба.</span><span class="sxs-lookup"><span data-stu-id="47e00-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="47e00-136">Чтобы ввести несколько имен служб, разделите их запятой.</span><span class="sxs-lookup"><span data-stu-id="47e00-136">To enter multiple service names, use a comma to separate the names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47e00-137">-Description</span><span class="sxs-lookup"><span data-stu-id="47e00-137">-Description</span></span>

<span data-ttu-id="47e00-138">Указывает описание службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="47e00-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="47e00-139">-DisplayName</span></span>

<span data-ttu-id="47e00-140">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="47e00-141">-Name</span><span class="sxs-lookup"><span data-stu-id="47e00-141">-Name</span></span>

<span data-ttu-id="47e00-142">Указывает имя службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-142">Specifies the name of the service.</span></span> <span data-ttu-id="47e00-143">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="47e00-143">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47e00-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="47e00-144">-StartupType</span></span>

<span data-ttu-id="47e00-145">Задает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="47e00-145">Sets the startup type of the service.</span></span> <span data-ttu-id="47e00-146">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="47e00-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="47e00-147">**Автоматически** — служба запущена или была запущена операционной системой при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="47e00-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="47e00-148">Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="47e00-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="47e00-149">**Аутоматикделайедстарт** — запускается вскоре после загрузки системы.</span><span class="sxs-lookup"><span data-stu-id="47e00-149">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="47e00-150">**Отключено** — служба отключена и не может быть запущена пользователем или приложением.</span><span class="sxs-lookup"><span data-stu-id="47e00-150">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="47e00-151">**Инвалидвалуе** — это значение не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="47e00-151">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="47e00-152">Использование этого значения приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="47e00-152">Using this value results in an error.</span></span>
- <span data-ttu-id="47e00-153">**Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.</span><span class="sxs-lookup"><span data-stu-id="47e00-153">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="47e00-154">Значение по умолчанию — **Automatic**.</span><span class="sxs-lookup"><span data-stu-id="47e00-154">The default value is **Automatic**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47e00-155">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="47e00-155">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="47e00-156">Указывает **SecurityDescriptor** для службы в формате **SDDL** .</span><span class="sxs-lookup"><span data-stu-id="47e00-156">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47e00-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="47e00-157">-Confirm</span></span>

<span data-ttu-id="47e00-158">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="47e00-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="47e00-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="47e00-159">-WhatIf</span></span>

<span data-ttu-id="47e00-160">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="47e00-160">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="47e00-161">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="47e00-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="47e00-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="47e00-162">CommonParameters</span></span>

<span data-ttu-id="47e00-163">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="47e00-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47e00-164">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="47e00-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47e00-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="47e00-165">INPUTS</span></span>

### <span data-ttu-id="47e00-166">Нет</span><span class="sxs-lookup"><span data-stu-id="47e00-166">None</span></span>

<span data-ttu-id="47e00-167">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="47e00-167">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="47e00-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="47e00-168">OUTPUTS</span></span>

### <span data-ttu-id="47e00-169">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="47e00-169">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="47e00-170">Этот командлет возвращает объект, представляющий новую службу.</span><span class="sxs-lookup"><span data-stu-id="47e00-170">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="47e00-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="47e00-171">NOTES</span></span>

<span data-ttu-id="47e00-172">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="47e00-172">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="47e00-173">Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="47e00-173">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="47e00-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="47e00-174">RELATED LINKS</span></span>

[<span data-ttu-id="47e00-175">Get-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-175">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="47e00-176">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-176">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="47e00-177">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-177">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="47e00-178">Set-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-178">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="47e00-179">Start-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-179">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="47e00-180">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-180">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="47e00-181">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-181">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="47e00-182">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="47e00-182">Remove-Service</span></span>](Remove-Service.md)
