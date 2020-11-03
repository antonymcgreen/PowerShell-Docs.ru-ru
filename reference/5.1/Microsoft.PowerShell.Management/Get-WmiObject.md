---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228361"
---
# <span data-ttu-id="9d32c-103">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9d32c-103">Get-WmiObject</span></span>

## <span data-ttu-id="9d32c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9d32c-104">SYNOPSIS</span></span>
<span data-ttu-id="9d32c-105">Получает экземпляры классов инструментария управления Windows (WMI) или сведения о доступных классах.</span><span class="sxs-lookup"><span data-stu-id="9d32c-105">Gets instances of Windows Management Instrumentation (WMI) classes or information about the available classes.</span></span>

## <span data-ttu-id="9d32c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9d32c-106">SYNTAX</span></span>

### <span data-ttu-id="9d32c-107">запрос (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9d32c-107">query (Default)</span></span>

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="9d32c-108">list</span><span class="sxs-lookup"><span data-stu-id="9d32c-108">list</span></span>

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="9d32c-109">вклкуери</span><span class="sxs-lookup"><span data-stu-id="9d32c-109">WQLQuery</span></span>

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="9d32c-110">class</span><span class="sxs-lookup"><span data-stu-id="9d32c-110">class</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="9d32c-111">path</span><span class="sxs-lookup"><span data-stu-id="9d32c-111">path</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="9d32c-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d32c-112">DESCRIPTION</span></span>

<span data-ttu-id="9d32c-113">Начиная с PowerShell 3,0 этот командлет был заменен `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="9d32c-113">Starting in PowerShell 3.0, this cmdlet has been superseded by `Get-CimInstance`.</span></span>

<span data-ttu-id="9d32c-114">`Get-WmiObject`Командлет получает экземпляры классов WMI или сведения о доступных классах WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-114">The `Get-WmiObject` cmdlet gets instances of WMI classes or information about the available WMI classes.</span></span> <span data-ttu-id="9d32c-115">Чтобы указать удаленный компьютер, используйте параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-115">To specify a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="9d32c-116">Если указан параметр **List** , командлет получает сведения о классах WMI, доступных в указанном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="9d32c-116">If the **List** parameter is specified, the cmdlet gets information about the WMI classes that are available in a specified namespace.</span></span> <span data-ttu-id="9d32c-117">Если указан параметр **Query** , командлет запускает инструкцию языка запросов WMI (WQL).</span><span class="sxs-lookup"><span data-stu-id="9d32c-117">If the **Query** parameter is specified, the cmdlet runs a WMI query language (WQL) statement.</span></span>

<span data-ttu-id="9d32c-118">`Get-WmiObject`Командлет не использует удаленное взаимодействие Windows PowerShell для выполнения удаленных операций.</span><span class="sxs-lookup"><span data-stu-id="9d32c-118">The `Get-WmiObject` cmdlet does not use Windows PowerShell remoting to perform remote operations.</span></span>
<span data-ttu-id="9d32c-119">Параметр **ComputerName** командлета можно использовать, `Get-WmiObject` даже если компьютер не соответствует требованиям для удаленного взаимодействия Windows PowerShell или не настроен для удаленного взаимодействия в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d32c-119">You can use the **ComputerName** parameter of the `Get-WmiObject` cmdlet even if your computer does not meet the requirements for Windows PowerShell remoting or is not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="9d32c-120">Начиная с Windows PowerShell 3,0, свойство **__Server** объекта, которое возвращает, `Get-WmiObject` имеет псевдоним **PSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-120">Beginning in Windows PowerShell 3.0, the **__Server** property of the object that `Get-WmiObject` returns has a **PSComputerName** alias.</span></span> <span data-ttu-id="9d32c-121">Это упрощает включение имени исходного компьютера во входные данные и отчеты.</span><span class="sxs-lookup"><span data-stu-id="9d32c-121">This makes it easier to include the source computer name in output and reports.</span></span>

## <span data-ttu-id="9d32c-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="9d32c-122">EXAMPLES</span></span>

### <span data-ttu-id="9d32c-123">Пример 1. получение процессов на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="9d32c-123">Example 1: Get processes on the local computer</span></span>

<span data-ttu-id="9d32c-124">В этом примере получаются процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9d32c-124">This example get the processes on the local computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Process
```

### <span data-ttu-id="9d32c-125">Пример 2. Получение служб на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="9d32c-125">Example 2: Gets services on a remote computer</span></span>

<span data-ttu-id="9d32c-126">Этот пример получает службы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9d32c-126">This example gets the services on a remote computer.</span></span> <span data-ttu-id="9d32c-127">Параметр **ComputerName** задает IP-адрес удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="9d32c-127">The **ComputerName** parameter specifies the IP address of a remote computer.</span></span> <span data-ttu-id="9d32c-128">По умолчанию текущая учетная запись пользователя должна быть членом группы **администраторов** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9d32c-128">By default, the current user account must be a member of the **Administrators** group on the remote computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### <span data-ttu-id="9d32c-129">Пример 3. получение классов WMI в корневом каталоге или пространстве имен по умолчанию локального компьютера</span><span class="sxs-lookup"><span data-stu-id="9d32c-129">Example 3: Get WMI classes in the root or default namespace of the local computer</span></span>

<span data-ttu-id="9d32c-130">В этом примере показано, как получить классы WMI в корневом пространстве имен или по умолчанию для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="9d32c-130">This example gets the WMI classes in the root or default namespace of the local computer.</span></span>

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### <span data-ttu-id="9d32c-131">Пример 4. получение именованной службы на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="9d32c-131">Example 4: Get a named service on multiple computers</span></span>

<span data-ttu-id="9d32c-132">В этом примере получается служба WinRM на компьютерах, указанных значением параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-132">This example gets the WinRM service on the computers specified by the value of the **ComputerName** parameter.</span></span>

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

<span data-ttu-id="9d32c-133">Оператор конвейера (|) отправляет выходные данные в `Format-List` командлет, который добавляет свойство **PSComputerName** к выходу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d32c-133">A pipeline operator (|) sends the output to the `Format-List` cmdlet, which adds the **PSComputerName** property to the default output.</span></span> <span data-ttu-id="9d32c-134">**PSComputerName** — это псевдоним свойства **__Server** объектов, которые `Get-WmiObject` возвращают.</span><span class="sxs-lookup"><span data-stu-id="9d32c-134">**PSComputerName** is an alias of the **__Server** property of the objects that `Get-WmiObject` returns.</span></span> <span data-ttu-id="9d32c-135">Этот псевдоним появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9d32c-135">This alias was introduced in PowerShell 3.0.</span></span>

### <span data-ttu-id="9d32c-136">Пример 5. Завершение службы на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="9d32c-136">Example 5: Stop a service on a remote computer</span></span>

<span data-ttu-id="9d32c-137">В этом примере служба WinRM останавливается на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9d32c-137">This example stops the WinRM service on a remote computer.</span></span> <span data-ttu-id="9d32c-138">`Get-WmiObject` Возвращает экземпляр объекта службы WinRM в Server01.</span><span class="sxs-lookup"><span data-stu-id="9d32c-138">`Get-WmiObject` gets the instance of the WinRM service object on Server01.</span></span> <span data-ttu-id="9d32c-139">Затем он **вызывает метод «начало» класса** WMI **Win32_Service** для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="9d32c-139">Then, it invokes the **StopService** method of the **Win32_Service** WMI class on that object.</span></span>

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

<span data-ttu-id="9d32c-140">Это эквивалентно использованию `Stop-Service` командлета.</span><span class="sxs-lookup"><span data-stu-id="9d32c-140">This is equivalent to using the `Stop-Service` cmdlet.</span></span>

### <span data-ttu-id="9d32c-141">Пример 6. получение BIOS на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="9d32c-141">Example 6: Get the BIOS on the local computer</span></span>

<span data-ttu-id="9d32c-142">Этот пример получает данные BIOS с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="9d32c-142">This example gets the BIOS information from the local computer.</span></span> <span data-ttu-id="9d32c-143">Параметр **Property** `Format-List` командлета используется для вывода всех свойств возвращенного объекта в списке.</span><span class="sxs-lookup"><span data-stu-id="9d32c-143">The **Property** parameter of the `Format-List` cmdlet is used to display all properties of the returned object in a list.</span></span> <span data-ttu-id="9d32c-144">По умолчанию отображаются только подмножество свойств, определенных в `Types.ps1xml` файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9d32c-144">By default, only the subset of properties defined in the `Types.ps1xml` configuration file are displayed.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### <span data-ttu-id="9d32c-145">Пример 7. Получение служб на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="9d32c-145">Example 7: Get the services on a remote computer</span></span>

<span data-ttu-id="9d32c-146">В этом примере используется параметр **Credential** `Get-WmiObject` командлета для получения служб на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9d32c-146">This example uses the **Credential** parameter of the `Get-WmiObject` cmdlet to get the services on a remote computer.</span></span> <span data-ttu-id="9d32c-147">Значение параметра **Credential** является именем учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="9d32c-147">The value of the **Credential** parameter is a user account name.</span></span> <span data-ttu-id="9d32c-148">Пользователю предлагается ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="9d32c-148">The user is prompted for a password.</span></span>

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> <span data-ttu-id="9d32c-149">Учетные данные нельзя использовать при нацеливании на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="9d32c-149">Credentials cannot be used when targeting the local computer.</span></span>

## <span data-ttu-id="9d32c-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9d32c-150">PARAMETERS</span></span>

### <span data-ttu-id="9d32c-151">— Исправлено</span><span class="sxs-lookup"><span data-stu-id="9d32c-151">-Amended</span></span>

<span data-ttu-id="9d32c-152">Получает или задает значение, которое указывает, должны ли объекты, возвращаемые из WMI, содержать измененные сведения.</span><span class="sxs-lookup"><span data-stu-id="9d32c-152">Gets or sets a value that indicates whether the objects that are returned from WMI should contain amended information.</span></span> <span data-ttu-id="9d32c-153">Обычно измененные сведения — это сведения, подлежащие локализации: например, описания объекта и свойства, вложенные в объект WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-153">Typically, amended information is localizable information, such as object and property descriptions, that is attached to the WMI object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-154">-AsJob</span><span class="sxs-lookup"><span data-stu-id="9d32c-154">-AsJob</span></span>

<span data-ttu-id="9d32c-155">Выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="9d32c-155">Runs the command as a background job.</span></span> <span data-ttu-id="9d32c-156">Используйте этот параметр для запуска команд, на завершение которых требуется много времени.</span><span class="sxs-lookup"><span data-stu-id="9d32c-156">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="9d32c-157">При использовании параметра **AsJob** команда возвращает объект, который представляет фоновое задание, а затем отображает командную строку.</span><span class="sxs-lookup"><span data-stu-id="9d32c-157">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="9d32c-158">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="9d32c-158">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="9d32c-159">Если `Get-WmiObject` используется на удаленном компьютере, задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="9d32c-159">If `Get-WmiObject` is used on a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="9d32c-160">Для управления заданием используйте командлеты, которые содержат командлеты задания.</span><span class="sxs-lookup"><span data-stu-id="9d32c-160">To manage the job, use the cmdlets that contain the Job cmdlets.</span></span> <span data-ttu-id="9d32c-161">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="9d32c-161">To get the job results, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="9d32c-162">Для использования этого параметра с удаленными компьютерами локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d32c-162">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="9d32c-163">Кроме того, необходимо запустить Windows PowerShell с параметром "Запуск от имени администратора" в Windows Vista и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="9d32c-163">Additionally, you must start Windows PowerShell by using the "Run as administrator" option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="9d32c-164">Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d32c-164">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="9d32c-165">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="9d32c-165">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-166">-Authentication</span><span class="sxs-lookup"><span data-stu-id="9d32c-166">-Authentication</span></span>

<span data-ttu-id="9d32c-167">Указывает уровень проверки подлинности, используемый для подключения к WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-167">Specifies the authentication level to be used with the WMI connection.</span></span>
<span data-ttu-id="9d32c-168">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9d32c-168">Valid values are:</span></span>

- <span data-ttu-id="9d32c-169">-1: без изменений</span><span class="sxs-lookup"><span data-stu-id="9d32c-169">-1: Unchanged</span></span>
- <span data-ttu-id="9d32c-170">0: по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9d32c-170">0: Default</span></span>
- <span data-ttu-id="9d32c-171">1: нет (проверка подлинности не выполняется).</span><span class="sxs-lookup"><span data-stu-id="9d32c-171">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="9d32c-172">2: Connect (проверка подлинности выполняется только в том случае, если клиент устанавливает связь с приложением.)</span><span class="sxs-lookup"><span data-stu-id="9d32c-172">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="9d32c-173">3: вызов (проверка подлинности выполняется только в начале каждого вызова, когда приложение получает запрос).</span><span class="sxs-lookup"><span data-stu-id="9d32c-173">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="9d32c-174">4: пакет (проверка подлинности выполняется для всех данных, полученных от клиента.)</span><span class="sxs-lookup"><span data-stu-id="9d32c-174">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="9d32c-175">5: Паккетинтегрити (все данные, передаваемые между клиентом и приложением, проходят проверку подлинности и проверяются.)</span><span class="sxs-lookup"><span data-stu-id="9d32c-175">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="9d32c-176">6: Паккетприваци (используются свойства других уровней проверки подлинности, и все данные шифруются).</span><span class="sxs-lookup"><span data-stu-id="9d32c-176">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-177">— Центр</span><span class="sxs-lookup"><span data-stu-id="9d32c-177">-Authority</span></span>

<span data-ttu-id="9d32c-178">Указывает центр сертификации, используемый для проверки подлинности подключения к WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-178">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="9d32c-179">Можно выбрать стандартную проверку подлинности NTLM или Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9d32c-179">You can specify standard NTLM or Kerberos authentication.</span></span> <span data-ttu-id="9d32c-180">Чтобы использовать NTLM, задайте для параметра центра сертификации значение `ntlmdomain:<DomainName>` , где `<DomainName>` определяет допустимое доменное имя NTLM.</span><span class="sxs-lookup"><span data-stu-id="9d32c-180">To use NTLM, set the authority setting to `ntlmdomain:<DomainName>`, where `<DomainName>` identifies a valid NTLM domain name.</span></span> <span data-ttu-id="9d32c-181">Чтобы использовать Kerberos, укажите `kerberos:<DomainName>\<ServerName>` .</span><span class="sxs-lookup"><span data-stu-id="9d32c-181">To use Kerberos, specify `kerberos:<DomainName>\<ServerName>`.</span></span> <span data-ttu-id="9d32c-182">Параметр authority не может быть указан при подключении к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="9d32c-182">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="9d32c-183">-Class</span><span class="sxs-lookup"><span data-stu-id="9d32c-183">-Class</span></span>

<span data-ttu-id="9d32c-184">Задает имя класса WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-184">Specifies the name of a WMI class.</span></span> <span data-ttu-id="9d32c-185">Если используется этот параметр, командлет возвращает экземпляры класса WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-185">When this parameter is used, the cmdlet retrieves instances of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-186">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9d32c-186">-ComputerName</span></span>

<span data-ttu-id="9d32c-187">Указывает целевой компьютер для операции управления.</span><span class="sxs-lookup"><span data-stu-id="9d32c-187">Specifies the target computer for the management operation.</span></span> <span data-ttu-id="9d32c-188">Введите полное доменное имя, имя NetBIOS или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="9d32c-188">Enter a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="9d32c-189">Если удаленный компьютер находится в домене, отличном от домена локального компьютера, необходимо указать полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="9d32c-189">When the remote computer is in a different domain than the local computer, the fully qualified domain name is required.</span></span>

<span data-ttu-id="9d32c-190">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="9d32c-190">The default is the local computer.</span></span> <span data-ttu-id="9d32c-191">Чтобы указать локальный компьютер (например, в списке имен компьютеров), используйте localhost, имя локального компьютера или точку (.).</span><span class="sxs-lookup"><span data-stu-id="9d32c-191">To specify the local computer, such as in a list of computer names, use "localhost", the local computer name, or a dot (.).</span></span>

<span data-ttu-id="9d32c-192">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell, которое использует командлет WS-Management.</span><span class="sxs-lookup"><span data-stu-id="9d32c-192">This parameter does not rely on Windows PowerShell remoting, which uses WS-Management.</span></span> <span data-ttu-id="9d32c-193">Параметр **ComputerName** можно использовать, `Get-WmiObject` даже если компьютер не настроен для выполнения WS-Management удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="9d32c-193">You can use the **ComputerName** parameter of `Get-WmiObject` even if your computer is not configured to run WS-Management remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-194">-Credential</span><span class="sxs-lookup"><span data-stu-id="9d32c-194">-Credential</span></span>

<span data-ttu-id="9d32c-195">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="9d32c-195">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="9d32c-196">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="9d32c-196">The default is the current user.</span></span> <span data-ttu-id="9d32c-197">Введите имя пользователя, например "User01", "Domain01\User01", или User@Contoso.com .</span><span class="sxs-lookup"><span data-stu-id="9d32c-197">Type a user name, such as "User01", "Domain01\User01", or User@Contoso.com.</span></span> <span data-ttu-id="9d32c-198">Или введите объект **PSCredential** , например объект, возвращаемый `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="9d32c-198">Or, enter a **PSCredential** object, such as an object that is returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="9d32c-199">При вводе имени пользователя запрашивается пароль.</span><span class="sxs-lookup"><span data-stu-id="9d32c-199">When you type a user name, you are prompted for a password.</span></span> <span data-ttu-id="9d32c-200">Учетные данные нельзя использовать при нацеливании на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="9d32c-200">Credentials cannot be used when targeting the local computer.</span></span>

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

### <span data-ttu-id="9d32c-201">-Директреад</span><span class="sxs-lookup"><span data-stu-id="9d32c-201">-DirectRead</span></span>

<span data-ttu-id="9d32c-202">Указывает, запрашивается ли прямой доступ к поставщику WMI для данного класса безотносительно базового класса или его наследуемых классов.</span><span class="sxs-lookup"><span data-stu-id="9d32c-202">Specifies whether direct access to the WMI provider is requested for the specified class without any regard to its base class or to its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-203">-Енаблеаллпривилежес</span><span class="sxs-lookup"><span data-stu-id="9d32c-203">-EnableAllPrivileges</span></span>

<span data-ttu-id="9d32c-204">Включает все привилегии текущего пользователя перед вызовом WMI в команде.</span><span class="sxs-lookup"><span data-stu-id="9d32c-204">Enables all the privileges of the current user before the command makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-205">-Filter</span><span class="sxs-lookup"><span data-stu-id="9d32c-205">-Filter</span></span>

<span data-ttu-id="9d32c-206">Указывает предложение **Where** для использования в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="9d32c-206">Specifies a **Where** clause to use as a filter.</span></span> <span data-ttu-id="9d32c-207">Использует синтаксис языка запросов WMI (WQL).</span><span class="sxs-lookup"><span data-stu-id="9d32c-207">Uses the syntax of the WMI Query Language (WQL).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d32c-208">Не включайте ключевое слово **Where** в значение параметра.</span><span class="sxs-lookup"><span data-stu-id="9d32c-208">Do not include the **Where** keyword in the value of the parameter.</span></span> <span data-ttu-id="9d32c-209">Например, следующие команды возвращают только логические диски с **DeviceID** для "c:" и службы с именем WinRM без использования ключевого слова **Where** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-209">For example, the following commands return only the logical disks that have a **DeviceID** of 'c:' and services that have the name 'WinRM' without using the **Where** keyword.</span></span>

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-210">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="9d32c-210">-Impersonation</span></span>

<span data-ttu-id="9d32c-211">Задает используемый уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="9d32c-211">Specifies the impersonation level to use.</span></span>

<span data-ttu-id="9d32c-212">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="9d32c-212">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9d32c-213">0: по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d32c-213">0: Default.</span></span> <span data-ttu-id="9d32c-214">Считывает локальный реестр для уровня олицетворения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d32c-214">Reads the local registry for the default impersonation level.</span></span> <span data-ttu-id="9d32c-215">По умолчанию обычно устанавливается **олицетворение** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-215">The default is usually set to **Impersonate** .</span></span>
- <span data-ttu-id="9d32c-216">1: анонимный.</span><span class="sxs-lookup"><span data-stu-id="9d32c-216">1: Anonymous.</span></span> <span data-ttu-id="9d32c-217">Скрывает учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="9d32c-217">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="9d32c-218">2: выявление.</span><span class="sxs-lookup"><span data-stu-id="9d32c-218">2: Identify.</span></span> <span data-ttu-id="9d32c-219">позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="9d32c-219">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="9d32c-220">3. олицетворение.</span><span class="sxs-lookup"><span data-stu-id="9d32c-220">3: Impersonate.</span></span> <span data-ttu-id="9d32c-221">позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="9d32c-221">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="9d32c-222">4: делегат.</span><span class="sxs-lookup"><span data-stu-id="9d32c-222">4: Delegate.</span></span> <span data-ttu-id="9d32c-223">Позволяет объектам разрешать другим объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="9d32c-223">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-224">-List</span><span class="sxs-lookup"><span data-stu-id="9d32c-224">-List</span></span>

<span data-ttu-id="9d32c-225">Получает имена классов WMI в пространстве имен репозитория WMI, который указан параметром **Namespace** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-225">Gets the names of the WMI classes in the WMI repository namespace that is specified by the **Namespace** parameter.</span></span>

<span data-ttu-id="9d32c-226">Если указать параметр **List** , но не параметр **Namespace** , `Get-WmiObject` по умолчанию использует пространство имен **Root\Cimv2** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-226">If you specify the **List** parameter, but not the **Namespace** parameter, `Get-WmiObject` uses the **Root\Cimv2** namespace by default.</span></span> <span data-ttu-id="9d32c-227">Этот командлет не использует запись реестра **по умолчанию для пространства имен** в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` реестра для определения пространства имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d32c-227">This cmdlet does not use the **Default Namespace** registry entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` registry key to determine the default namespace.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-228">-Locale</span><span class="sxs-lookup"><span data-stu-id="9d32c-228">-Locale</span></span>

<span data-ttu-id="9d32c-229">Указывает предпочтительный язык для объектов WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-229">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="9d32c-230">Введите значение в формате MS_\<LCID\>.</span><span class="sxs-lookup"><span data-stu-id="9d32c-230">Enter a value in MS_\<LCID\> format.</span></span>

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

### <span data-ttu-id="9d32c-231">-Namespace</span><span class="sxs-lookup"><span data-stu-id="9d32c-231">-Namespace</span></span>

<span data-ttu-id="9d32c-232">При использовании с параметром **Class** параметр **Namespace** указывает пространство имен репозитория WMI, где располагается указанный класс WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-232">When used with the **Class** parameter, the **Namespace** parameter specifies the WMI repository namespace where the specified WMI class is located.</span></span> <span data-ttu-id="9d32c-233">При использовании с параметром **List** указывается пространство имен, из которого собирается информация о классе WMI.</span><span class="sxs-lookup"><span data-stu-id="9d32c-233">When used with the **List** parameter, it specifies the namespace from which to gather WMI class information.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-234">-Property</span><span class="sxs-lookup"><span data-stu-id="9d32c-234">-Property</span></span>

<span data-ttu-id="9d32c-235">Указывает свойства класса WMI, из которого этот командлет получает сведения.</span><span class="sxs-lookup"><span data-stu-id="9d32c-235">Specifies the WMI class properties that this cmdlet gets information from.</span></span> <span data-ttu-id="9d32c-236">Введите имена свойств.</span><span class="sxs-lookup"><span data-stu-id="9d32c-236">Enter the property names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-237">-Query</span><span class="sxs-lookup"><span data-stu-id="9d32c-237">-Query</span></span>

<span data-ttu-id="9d32c-238">Запускает указанную инструкцию языка запросов WMI (WQL).</span><span class="sxs-lookup"><span data-stu-id="9d32c-238">Runs the specified WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="9d32c-239">Этот параметр не поддерживает очереди событий.</span><span class="sxs-lookup"><span data-stu-id="9d32c-239">This parameter does not support event queries.</span></span>

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-240">-Recurse</span><span class="sxs-lookup"><span data-stu-id="9d32c-240">-Recurse</span></span>

<span data-ttu-id="9d32c-241">Ищет текущее пространство имен и все остальные пространства имен для имени класса, указанного параметром **Class** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-241">Searches the current namespace and all other namespaces for the class name that is specified by the **Class** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-242">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9d32c-242">-ThrottleLimit</span></span>

<span data-ttu-id="9d32c-243">Указывает максимальное количество операций WMI, которые можно выполнить одновременно.</span><span class="sxs-lookup"><span data-stu-id="9d32c-243">Specifies the maximum number of WMI operations that can be executed simultaneously.</span></span> <span data-ttu-id="9d32c-244">Этот параметр допустим только в том случае, если в команде используется параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-244">This parameter is valid only when the **AsJob** parameter is used in the command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d32c-245">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9d32c-245">CommonParameters</span></span>

<span data-ttu-id="9d32c-246">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9d32c-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9d32c-247">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9d32c-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9d32c-248">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9d32c-248">INPUTS</span></span>

### <span data-ttu-id="9d32c-249">Нет</span><span class="sxs-lookup"><span data-stu-id="9d32c-249">None</span></span>

<span data-ttu-id="9d32c-250">Вы не можете передать входные данные в `Get-WmiObject` .</span><span class="sxs-lookup"><span data-stu-id="9d32c-250">You cannot pipe input to `Get-WmiObject`.</span></span>

## <span data-ttu-id="9d32c-251">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9d32c-251">OUTPUTS</span></span>

### <span data-ttu-id="9d32c-252">PSObject или System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="9d32c-252">PSObject or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="9d32c-253">При использовании параметра **AsJob** командлет возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="9d32c-253">When you use the **AsJob** parameter, the cmdlet returns a job object.</span></span> <span data-ttu-id="9d32c-254">В противном случае `Get-WmiObject` возвращаемый объект зависит от значения параметра **класса** .</span><span class="sxs-lookup"><span data-stu-id="9d32c-254">Otherwise, the object that `Get-WmiObject` returns depends on the value of the **Class** parameter.</span></span>

## <span data-ttu-id="9d32c-255">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9d32c-255">NOTES</span></span>

<span data-ttu-id="9d32c-256">Чтобы получить доступ к сведениям о WMI на удаленном компьютере, командлет необходимо запустить в рамках учетной записи, которая является членом группы локальных администраторов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9d32c-256">To access WMI information on a remote computer, the cmdlet must run under an account that is a member of the local administrators group on the remote computer.</span></span> <span data-ttu-id="9d32c-257">Кроме того, контроль доступа по умолчанию в пространстве имен WMI удаленного репозитория можно изменить, предоставив права доступа другим учетным записям.</span><span class="sxs-lookup"><span data-stu-id="9d32c-257">Or, the default access control on the WMI namespace of the remote repository can be changed to give access rights to other accounts.</span></span>

<span data-ttu-id="9d32c-258">Только некоторые свойства каждого класса WMI отображаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d32c-258">Only some of the properties of each WMI class are displayed by default.</span></span> <span data-ttu-id="9d32c-259">Набор свойств, который отображается для каждого класса WMI, указан в файле конфигурации Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="9d32c-259">The set of properties that is displayed for each WMI class is specified in the Types.ps1xml configuration file.</span></span> <span data-ttu-id="9d32c-260">Чтобы получить все свойства объекта WMI, используйте `Get-Member` `Format-List` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="9d32c-260">To get all properties of a WMI object, use the `Get-Member` or `Format-List` cmdlets.</span></span>

## <span data-ttu-id="9d32c-261">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9d32c-261">RELATED LINKS</span></span>

[<span data-ttu-id="9d32c-262">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="9d32c-262">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="9d32c-263">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9d32c-263">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="9d32c-264">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="9d32c-264">Set-WmiInstance</span></span>](Set-WmiInstance.md)

[<span data-ttu-id="9d32c-265">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9d32c-265">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="9d32c-266">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="9d32c-266">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="9d32c-267">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9d32c-267">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="9d32c-268">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9d32c-268">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
