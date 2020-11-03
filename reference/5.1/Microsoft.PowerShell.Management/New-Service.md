---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 3249ce91a63417f2790997d37e2420c6fcb374d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227966"
---
# <span data-ttu-id="1013e-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-103">New-Service</span></span>

## <span data-ttu-id="1013e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1013e-104">SYNOPSIS</span></span>
<span data-ttu-id="1013e-105">Создает новую службу Windows.</span><span class="sxs-lookup"><span data-stu-id="1013e-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="1013e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1013e-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1013e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1013e-107">DESCRIPTION</span></span>

<span data-ttu-id="1013e-108">`New-Service`Командлет создает новую запись для службы Windows в реестре и в базе данных службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="1013e-109">Для новой службы требуется исполняемый файл, который выполняется во время работы службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="1013e-110">Параметры этого командлета позволяют задать отображаемое имя, описание, тип запуска и зависимости службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="1013e-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="1013e-111">EXAMPLES</span></span>

### <span data-ttu-id="1013e-112">Пример 1. Создание службы</span><span class="sxs-lookup"><span data-stu-id="1013e-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="1013e-113">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="1013e-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="1013e-114">Пример 2. Создание службы, включающей описание, тип запуска и отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="1013e-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="1013e-115">Эта команда создает службу с именем TestService.</span><span class="sxs-lookup"><span data-stu-id="1013e-115">This command creates a service named TestService.</span></span> <span data-ttu-id="1013e-116">В нем используются параметры `New-Service` для указания описания, типа запуска и отображаемого имени для новой службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="1013e-117">Пример 3. Просмотр новой службы</span><span class="sxs-lookup"><span data-stu-id="1013e-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="1013e-118">Эта команда использует `Get-CimInstance` для получения объекта **Win32_Service** для новой службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="1013e-119">Этот объект содержит режим запуска службы и описание службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="1013e-120">Пример 4. Удаление службы</span><span class="sxs-lookup"><span data-stu-id="1013e-120">Example 4: Delete a service</span></span>

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

<span data-ttu-id="1013e-121">В этом примере показано два способа удаления службы TestService.</span><span class="sxs-lookup"><span data-stu-id="1013e-121">This example shows two ways to delete the TestService service.</span></span> <span data-ttu-id="1013e-122">Первая команда использует параметр delete параметра `Sc.exe` .</span><span class="sxs-lookup"><span data-stu-id="1013e-122">The first command uses the delete option of `Sc.exe`.</span></span> <span data-ttu-id="1013e-123">Во второй команде используется метод **Delete** объектов **Win32_Service** , которые `Get-CimInstance` возвращают.</span><span class="sxs-lookup"><span data-stu-id="1013e-123">The second command uses the **Delete** method of the **Win32_Service** objects that `Get-CimInstance` returns.</span></span>

## <span data-ttu-id="1013e-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1013e-124">PARAMETERS</span></span>

### <span data-ttu-id="1013e-125">-Бинарипаснаме</span><span class="sxs-lookup"><span data-stu-id="1013e-125">-BinaryPathName</span></span>

<span data-ttu-id="1013e-126">Указывает путь к исполняемому файлу службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="1013e-127">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="1013e-127">This parameter is required.</span></span>

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

### <span data-ttu-id="1013e-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="1013e-128">-Credential</span></span>

<span data-ttu-id="1013e-129">Указывает учетную запись, используемую службой в качестве [учетной записи входа службы](/windows/desktop/ad/about-service-logon-accounts).</span><span class="sxs-lookup"><span data-stu-id="1013e-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="1013e-130">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="1013e-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1013e-131">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="1013e-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="1013e-132">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="1013e-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="1013e-133">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="1013e-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="1013e-134">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="1013e-134">-DependsOn</span></span>

<span data-ttu-id="1013e-135">Задает имена других служб, от которых зависит новая служба.</span><span class="sxs-lookup"><span data-stu-id="1013e-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="1013e-136">Чтобы ввести несколько имен служб, разделите их запятой.</span><span class="sxs-lookup"><span data-stu-id="1013e-136">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="1013e-137">-Description</span><span class="sxs-lookup"><span data-stu-id="1013e-137">-Description</span></span>

<span data-ttu-id="1013e-138">Указывает описание службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="1013e-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="1013e-139">-DisplayName</span></span>

<span data-ttu-id="1013e-140">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="1013e-141">-Name</span><span class="sxs-lookup"><span data-stu-id="1013e-141">-Name</span></span>

<span data-ttu-id="1013e-142">Указывает имя службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-142">Specifies the name of the service.</span></span>
<span data-ttu-id="1013e-143">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="1013e-143">This parameter is required.</span></span>

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

### <span data-ttu-id="1013e-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="1013e-144">-StartupType</span></span>

<span data-ttu-id="1013e-145">Задает тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-145">Sets the startup type of the service.</span></span> <span data-ttu-id="1013e-146">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="1013e-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1013e-147">**Автоматически** — служба запущена или была запущена операционной системой при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="1013e-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="1013e-148">Если служба, запускаемая автоматически, зависит от службы, запускаемой вручную, запускаемая вручную служба также запускается автоматически при запуске системы.</span><span class="sxs-lookup"><span data-stu-id="1013e-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="1013e-149">**Отключено** — служба отключена и не может быть запущена пользователем или приложением.</span><span class="sxs-lookup"><span data-stu-id="1013e-149">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="1013e-150">**Вручную** — служба запускается только вручную, пользователем, с помощью диспетчера управления службами или приложения.</span><span class="sxs-lookup"><span data-stu-id="1013e-150">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="1013e-151">**Загрузка** — указывает, что служба является драйвером устройства, запущенным загрузчиком системы.</span><span class="sxs-lookup"><span data-stu-id="1013e-151">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="1013e-152">Это значение допустимо только для драйверов устройств.</span><span class="sxs-lookup"><span data-stu-id="1013e-152">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="1013e-153">**Система** — указывает, что служба является драйвером устройства, запущенным функцией "иоинитсистем ()".</span><span class="sxs-lookup"><span data-stu-id="1013e-153">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="1013e-154">Это значение допустимо только для драйверов устройств.</span><span class="sxs-lookup"><span data-stu-id="1013e-154">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="1013e-155">Значение по умолчанию — **Automatic** .</span><span class="sxs-lookup"><span data-stu-id="1013e-155">The default value is **Automatic** .</span></span>

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

### <span data-ttu-id="1013e-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1013e-156">-Confirm</span></span>

<span data-ttu-id="1013e-157">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1013e-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1013e-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1013e-158">-WhatIf</span></span>

<span data-ttu-id="1013e-159">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1013e-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1013e-160">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1013e-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1013e-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1013e-161">CommonParameters</span></span>

<span data-ttu-id="1013e-162">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1013e-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1013e-163">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1013e-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1013e-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1013e-164">INPUTS</span></span>

### <span data-ttu-id="1013e-165">Нет</span><span class="sxs-lookup"><span data-stu-id="1013e-165">None</span></span>

<span data-ttu-id="1013e-166">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="1013e-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1013e-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1013e-167">OUTPUTS</span></span>

### <span data-ttu-id="1013e-168">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="1013e-168">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="1013e-169">Этот командлет возвращает объект, представляющий новую службу.</span><span class="sxs-lookup"><span data-stu-id="1013e-169">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="1013e-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1013e-170">NOTES</span></span>

<span data-ttu-id="1013e-171">Чтобы запустить этот командлет в Windows Vista и более поздних версиях операционной системы Windows, запустите PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="1013e-171">To run this cmdlet on Windows Vista and later versions of the Windows operating system, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="1013e-172">Чтобы удалить службу, используйте Sc.exe или `Get-CimInstance` командлет, чтобы получить объект **Win32_Service** , представляющий службу, а затем используйте метод **Delete** для удаления службы.</span><span class="sxs-lookup"><span data-stu-id="1013e-172">To delete a service, use Sc.exe, or use the `Get-CimInstance` cmdlet to get the **Win32_Service** object that represents the service and then use the **Delete** method to delete the service.</span></span> <span data-ttu-id="1013e-173">Объект, который `Get-Service` возвращает, не имеет метода Delete.</span><span class="sxs-lookup"><span data-stu-id="1013e-173">The object that `Get-Service` returns does not have a delete method.</span></span>

## <span data-ttu-id="1013e-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1013e-174">RELATED LINKS</span></span>

[<span data-ttu-id="1013e-175">Get-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-175">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="1013e-176">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-176">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="1013e-177">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-177">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="1013e-178">Set-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-178">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="1013e-179">Start-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-179">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="1013e-180">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-180">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="1013e-181">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="1013e-181">Suspend-Service</span></span>](Suspend-Service.md)
