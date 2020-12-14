---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 758b0a8ef9a5f65f0e7cfa7f3633086cf9f0445d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891774"
---
# <span data-ttu-id="bc5b3-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-103">New-Service</span></span>

## <span data-ttu-id="bc5b3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bc5b3-104">SYNOPSIS</span></span>
<span data-ttu-id="bc5b3-105">Создает новую службу Windows.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="bc5b3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc5b3-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bc5b3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc5b3-107">DESCRIPTION</span></span>

<span data-ttu-id="bc5b3-108">`New-Service`Командлет создает новую запись для службы Windows в реестре и в базе данных службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="bc5b3-109">Для новой службы требуется исполняемый файл, который выполняется во время работы службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="bc5b3-110">Параметры этого командлета позволяют задать отображаемое имя, описание, тип запуска и зависимости службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="bc5b3-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="bc5b3-111">EXAMPLES</span></span>

### <span data-ttu-id="bc5b3-112">Пример 1. Создание службы</span><span class="sxs-lookup"><span data-stu-id="bc5b3-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

<span data-ttu-id="bc5b3-113">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="bc5b3-114">Пример 2. Создание службы, включающей описание, тип запуска и отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="bc5b3-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="bc5b3-115">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-115">This command creates a service named TestService.</span></span> <span data-ttu-id="bc5b3-116">В нем используются параметры `New-Service` для указания описания, типа запуска и отображаемого имени для новой службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="bc5b3-117">Пример 3. Просмотр новой службы</span><span class="sxs-lookup"><span data-stu-id="bc5b3-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="bc5b3-118">Эта команда использует `Get-CimInstance` для получения объекта **Win32_Service** для новой службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="bc5b3-119">Этот объект содержит режим запуска службы и описание службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="bc5b3-120">Пример 4. Удаление службы</span><span class="sxs-lookup"><span data-stu-id="bc5b3-120">Example 4: Delete a service</span></span>

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

<span data-ttu-id="bc5b3-121">В этом примере показано два способа удаления службы TestService.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-121">This example shows two ways to delete the TestService service.</span></span> <span data-ttu-id="bc5b3-122">Первая команда использует параметр delete параметра `Sc.exe` .</span><span class="sxs-lookup"><span data-stu-id="bc5b3-122">The first command uses the delete option of `Sc.exe`.</span></span> <span data-ttu-id="bc5b3-123">Во второй команде используется метод **Delete** объектов **Win32_Service** , которые `Get-CimInstance` возвращают.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-123">The second command uses the **Delete** method of the **Win32_Service** objects that `Get-CimInstance` returns.</span></span>

## <span data-ttu-id="bc5b3-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc5b3-124">PARAMETERS</span></span>

### <span data-ttu-id="bc5b3-125">-Бинарипаснаме</span><span class="sxs-lookup"><span data-stu-id="bc5b3-125">-BinaryPathName</span></span>

<span data-ttu-id="bc5b3-126">Указывает путь к исполняемому файлу службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="bc5b3-127">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-127">This parameter is required.</span></span>

<span data-ttu-id="bc5b3-128">Полный путь к двоичному файлу службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-128">The fully qualified path to the service binary file.</span></span> <span data-ttu-id="bc5b3-129">Если путь содержит пробел, он должен быть заключен в кавычки, чтобы правильно интерпретировать его.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-129">If the path contains a space, it must be quoted so that it is correctly interpreted.</span></span> <span data-ttu-id="bc5b3-130">Например, `d:\my share\myservice.exe` необходимо указать как `'"d:\my share\myservice.exe"'` .</span><span class="sxs-lookup"><span data-stu-id="bc5b3-130">For example, `d:\my share\myservice.exe` should be specified as `'"d:\my share\myservice.exe"'`.</span></span>

<span data-ttu-id="bc5b3-131">Путь также может включать аргументы для автоматической запуска службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-131">The path can also include arguments for an auto-start service.</span></span> <span data-ttu-id="bc5b3-132">Например, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-132">For example, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span></span> <span data-ttu-id="bc5b3-133">Эти аргументы передаются в точку входа службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-133">These arguments are passed to the service entry point.</span></span>

<span data-ttu-id="bc5b3-134">Дополнительные сведения см. в описании параметра **лпбинарипаснаме** API [креатесервицев](/windows/win32/api/winsvc/nf-winsvc-createservicew) .</span><span class="sxs-lookup"><span data-stu-id="bc5b3-134">For more information, see the **lpBinaryPathName** parameter of [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc5b3-135">-Credential</span><span class="sxs-lookup"><span data-stu-id="bc5b3-135">-Credential</span></span>

<span data-ttu-id="bc5b3-136">Указывает учетную запись, используемую службой в качестве [учетной записи входа службы](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="bc5b3-136">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="bc5b3-137">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-137">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="bc5b3-138">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-138">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="bc5b3-139">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="bc5b3-139">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="bc5b3-140">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="bc5b3-140">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="bc5b3-141">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="bc5b3-141">-DependsOn</span></span>

<span data-ttu-id="bc5b3-142">Задает имена других служб, от которых зависит новая служба.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-142">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="bc5b3-143">Чтобы ввести несколько имен служб, разделите их запятой.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-143">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="bc5b3-144">-Description</span><span class="sxs-lookup"><span data-stu-id="bc5b3-144">-Description</span></span>

<span data-ttu-id="bc5b3-145">Указывает описание службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-145">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="bc5b3-146">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="bc5b3-146">-DisplayName</span></span>

<span data-ttu-id="bc5b3-147">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-147">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="bc5b3-148">-Name</span><span class="sxs-lookup"><span data-stu-id="bc5b3-148">-Name</span></span>

<span data-ttu-id="bc5b3-149">Указывает имя службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-149">Specifies the name of the service.</span></span> <span data-ttu-id="bc5b3-150">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-150">This parameter is required.</span></span>

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

### <span data-ttu-id="bc5b3-151">-StartupType</span><span class="sxs-lookup"><span data-stu-id="bc5b3-151">-StartupType</span></span>

<span data-ttu-id="bc5b3-152">Задает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-152">Sets the startup type of the service.</span></span> <span data-ttu-id="bc5b3-153">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bc5b3-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bc5b3-154">**Автоматически** — служба запущена или была запущена операционной системой при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-154">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="bc5b3-155">Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-155">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="bc5b3-156">**Отключено** — служба отключена и не может быть запущена пользователем или приложением.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-156">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="bc5b3-157">**Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-157">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="bc5b3-158">**Загрузка** — указывает, что служба является драйвером устройства, запущенным загрузчиком системы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-158">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="bc5b3-159">Это значение допустимо только для драйверов устройств.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-159">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="bc5b3-160">**Система** — указывает, что служба является драйвером устройства, запущенным функцией "иоинитсистем ()".</span><span class="sxs-lookup"><span data-stu-id="bc5b3-160">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="bc5b3-161">Это значение допустимо только для драйверов устройств.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-161">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="bc5b3-162">Значение по умолчанию — **Automatic**.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-162">The default value is **Automatic**.</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases:
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc5b3-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bc5b3-163">-Confirm</span></span>

<span data-ttu-id="bc5b3-164">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bc5b3-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bc5b3-165">-WhatIf</span></span>

<span data-ttu-id="bc5b3-166">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-166">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="bc5b3-167">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bc5b3-168">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bc5b3-168">CommonParameters</span></span>

<span data-ttu-id="bc5b3-169">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc5b3-170">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bc5b3-170">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc5b3-171">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bc5b3-171">INPUTS</span></span>

### <span data-ttu-id="bc5b3-172">Нет</span><span class="sxs-lookup"><span data-stu-id="bc5b3-172">None</span></span>

<span data-ttu-id="bc5b3-173">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-173">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bc5b3-174">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bc5b3-174">OUTPUTS</span></span>

### <span data-ttu-id="bc5b3-175">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="bc5b3-175">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="bc5b3-176">Этот командлет возвращает объект, представляющий новую службу.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-176">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="bc5b3-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bc5b3-177">NOTES</span></span>

<span data-ttu-id="bc5b3-178">Чтобы запустить этот командлет, запустите PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="bc5b3-178">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="bc5b3-179">Чтобы удалить службу, используйте Sc.exe или `Get-CimInstance` командлет, чтобы получить объект **Win32_Service** , представляющий службу, а затем используйте метод **Delete** для удаления службы.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-179">To delete a service, use Sc.exe, or use the `Get-CimInstance` cmdlet to get the **Win32_Service** object that represents the service and then use the **Delete** method to delete the service.</span></span> <span data-ttu-id="bc5b3-180">Объект, который `Get-Service` возвращает, не имеет метода Delete.</span><span class="sxs-lookup"><span data-stu-id="bc5b3-180">The object that `Get-Service` returns does not have a delete method.</span></span>

## <span data-ttu-id="bc5b3-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bc5b3-181">RELATED LINKS</span></span>

[<span data-ttu-id="bc5b3-182">Get-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-182">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="bc5b3-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="bc5b3-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="bc5b3-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="bc5b3-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="bc5b3-187">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-187">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="bc5b3-188">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="bc5b3-188">Suspend-Service</span></span>](Suspend-Service.md)
