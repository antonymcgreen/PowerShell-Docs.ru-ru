---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 7ba9bf66295bcbc2d8f7b7f94007b3fb673882fb
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890980"
---
# <span data-ttu-id="0e621-102">New-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-102">New-Service</span></span>

## <span data-ttu-id="0e621-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0e621-103">SYNOPSIS</span></span>
<span data-ttu-id="0e621-104">Создает новую службу Windows.</span><span class="sxs-lookup"><span data-stu-id="0e621-104">Creates a new Windows service.</span></span>

## <span data-ttu-id="0e621-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e621-105">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e621-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e621-106">DESCRIPTION</span></span>

<span data-ttu-id="0e621-107">`New-Service`Командлет создает новую запись для службы Windows в реестре и в базе данных службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-107">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="0e621-108">Для новой службы требуется исполняемый файл, который выполняется во время работы службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-108">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="0e621-109">Параметры этого командлета позволяют задать отображаемое имя, описание, тип запуска и зависимости службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-109">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="0e621-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="0e621-110">EXAMPLES</span></span>

### <span data-ttu-id="0e621-111">Пример 1. Создание службы</span><span class="sxs-lookup"><span data-stu-id="0e621-111">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

<span data-ttu-id="0e621-112">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="0e621-112">This command creates a service named TestService.</span></span>

### <span data-ttu-id="0e621-113">Пример 2. Создание службы, включающей описание, тип запуска и отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="0e621-113">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="0e621-114">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="0e621-114">This command creates a service named TestService.</span></span> <span data-ttu-id="0e621-115">В нем используются параметры `New-Service` для указания описания, типа запуска и отображаемого имени для новой службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-115">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="0e621-116">Пример 3. Просмотр новой службы</span><span class="sxs-lookup"><span data-stu-id="0e621-116">Example 3: View the new service</span></span>

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

<span data-ttu-id="0e621-117">Эта команда использует `Get-CimInstance` для получения объекта **Win32_Service** для новой службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-117">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="0e621-118">Этот объект содержит режим запуска службы и описание службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-118">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="0e621-119">Пример 4. Настройка SecurityDescriptor службы при создании.</span><span class="sxs-lookup"><span data-stu-id="0e621-119">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="0e621-120">В этом примере добавляется **SecurityDescriptor** создаваемой службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-120">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="0e621-121">**SecurityDescriptor** хранится в `$SDDLToSet` переменной.</span><span class="sxs-lookup"><span data-stu-id="0e621-121">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="0e621-122">Параметр **SecurityDescriptorSddl** использует, `$SDDL` чтобы задать **SecurityDescriptor** для новой службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-122">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="0e621-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e621-123">PARAMETERS</span></span>

### <span data-ttu-id="0e621-124">-Бинарипаснаме</span><span class="sxs-lookup"><span data-stu-id="0e621-124">-BinaryPathName</span></span>

<span data-ttu-id="0e621-125">Указывает путь к исполняемому файлу службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-125">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="0e621-126">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="0e621-126">This parameter is required.</span></span>

<span data-ttu-id="0e621-127">Полный путь к двоичному файлу службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-127">The fully qualified path to the service binary file.</span></span> <span data-ttu-id="0e621-128">Если путь содержит пробел, он должен быть заключен в кавычки, чтобы правильно интерпретировать его.</span><span class="sxs-lookup"><span data-stu-id="0e621-128">If the path contains a space, it must be quoted so that it is correctly interpreted.</span></span> <span data-ttu-id="0e621-129">Например, `d:\my share\myservice.exe` необходимо указать как `'"d:\my share\myservice.exe"'` .</span><span class="sxs-lookup"><span data-stu-id="0e621-129">For example, `d:\my share\myservice.exe` should be specified as `'"d:\my share\myservice.exe"'`.</span></span>

<span data-ttu-id="0e621-130">Путь также может включать аргументы для автоматической запуска службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-130">The path can also include arguments for an auto-start service.</span></span> <span data-ttu-id="0e621-131">Например, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span><span class="sxs-lookup"><span data-stu-id="0e621-131">For example, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span></span> <span data-ttu-id="0e621-132">Эти аргументы передаются в точку входа службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-132">These arguments are passed to the service entry point.</span></span>

<span data-ttu-id="0e621-133">Дополнительные сведения см. в описании параметра **лпбинарипаснаме** API [креатесервицев](/windows/win32/api/winsvc/nf-winsvc-createservicew) .</span><span class="sxs-lookup"><span data-stu-id="0e621-133">For more information, see the **lpBinaryPathName** parameter of [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API.</span></span>

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

### <span data-ttu-id="0e621-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="0e621-134">-Credential</span></span>

<span data-ttu-id="0e621-135">Указывает учетную запись, используемую службой в качестве [учетной записи входа службы](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="0e621-135">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="0e621-136">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="0e621-136">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0e621-137">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="0e621-137">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="0e621-138">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="0e621-138">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0e621-139">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0e621-139">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="0e621-140">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="0e621-140">-DependsOn</span></span>

<span data-ttu-id="0e621-141">Задает имена других служб, от которых зависит новая служба.</span><span class="sxs-lookup"><span data-stu-id="0e621-141">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="0e621-142">Чтобы ввести несколько имен служб, разделите их запятой.</span><span class="sxs-lookup"><span data-stu-id="0e621-142">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="0e621-143">-Description</span><span class="sxs-lookup"><span data-stu-id="0e621-143">-Description</span></span>

<span data-ttu-id="0e621-144">Указывает описание службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-144">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="0e621-145">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="0e621-145">-DisplayName</span></span>

<span data-ttu-id="0e621-146">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-146">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="0e621-147">-Name</span><span class="sxs-lookup"><span data-stu-id="0e621-147">-Name</span></span>

<span data-ttu-id="0e621-148">Указывает имя службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-148">Specifies the name of the service.</span></span> <span data-ttu-id="0e621-149">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="0e621-149">This parameter is required.</span></span>

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

### <span data-ttu-id="0e621-150">-StartupType</span><span class="sxs-lookup"><span data-stu-id="0e621-150">-StartupType</span></span>

<span data-ttu-id="0e621-151">Задает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="0e621-151">Sets the startup type of the service.</span></span> <span data-ttu-id="0e621-152">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="0e621-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0e621-153">**Автоматически** — служба запущена или была запущена операционной системой при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="0e621-153">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="0e621-154">Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="0e621-154">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="0e621-155">**Аутоматикделайедстарт** — запускается вскоре после загрузки системы.</span><span class="sxs-lookup"><span data-stu-id="0e621-155">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="0e621-156">**Отключено** — служба отключена и не может быть запущена пользователем или приложением.</span><span class="sxs-lookup"><span data-stu-id="0e621-156">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="0e621-157">**Инвалидвалуе** — это значение не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0e621-157">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="0e621-158">Использование этого значения приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="0e621-158">Using this value results in an error.</span></span>
- <span data-ttu-id="0e621-159">**Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.</span><span class="sxs-lookup"><span data-stu-id="0e621-159">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="0e621-160">Значение по умолчанию — **Automatic**.</span><span class="sxs-lookup"><span data-stu-id="0e621-160">The default value is **Automatic**.</span></span>

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

### <span data-ttu-id="0e621-161">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="0e621-161">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="0e621-162">Указывает **SecurityDescriptor** для службы в формате **SDDL** .</span><span class="sxs-lookup"><span data-stu-id="0e621-162">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

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

### <span data-ttu-id="0e621-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e621-163">-Confirm</span></span>

<span data-ttu-id="0e621-164">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0e621-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e621-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e621-165">-WhatIf</span></span>

<span data-ttu-id="0e621-166">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0e621-166">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0e621-167">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0e621-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e621-168">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0e621-168">CommonParameters</span></span>

<span data-ttu-id="0e621-169">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e621-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e621-170">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0e621-170">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e621-171">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0e621-171">INPUTS</span></span>

### <span data-ttu-id="0e621-172">Нет</span><span class="sxs-lookup"><span data-stu-id="0e621-172">None</span></span>

<span data-ttu-id="0e621-173">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="0e621-173">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0e621-174">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0e621-174">OUTPUTS</span></span>

### <span data-ttu-id="0e621-175">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="0e621-175">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="0e621-176">Этот командлет возвращает объект, представляющий новую службу.</span><span class="sxs-lookup"><span data-stu-id="0e621-176">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="0e621-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0e621-177">NOTES</span></span>

<span data-ttu-id="0e621-178">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="0e621-178">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="0e621-179">Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="0e621-179">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="0e621-180">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0e621-180">RELATED LINKS</span></span>

[<span data-ttu-id="0e621-181">Get-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-181">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="0e621-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="0e621-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="0e621-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="0e621-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="0e621-186">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-186">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="0e621-187">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-187">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="0e621-188">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="0e621-188">Remove-Service</span></span>](Remove-Service.md)
