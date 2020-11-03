---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227937"
---
# <span data-ttu-id="021b6-103">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="021b6-103">Remove-WmiObject</span></span>

## <span data-ttu-id="021b6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="021b6-104">SYNOPSIS</span></span>
<span data-ttu-id="021b6-105">Удаляет экземпляр существующего класса инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="021b6-105">Deletes an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="021b6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="021b6-106">SYNTAX</span></span>

### <span data-ttu-id="021b6-107">Класс (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="021b6-107">class (Default)</span></span>

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="021b6-108">объект</span><span class="sxs-lookup"><span data-stu-id="021b6-108">object</span></span>

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="021b6-109">path</span><span class="sxs-lookup"><span data-stu-id="021b6-109">path</span></span>

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="021b6-110">вклкуери</span><span class="sxs-lookup"><span data-stu-id="021b6-110">WQLQuery</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="021b6-111">query</span><span class="sxs-lookup"><span data-stu-id="021b6-111">query</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="021b6-112">list</span><span class="sxs-lookup"><span data-stu-id="021b6-112">list</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="021b6-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="021b6-113">DESCRIPTION</span></span>
<span data-ttu-id="021b6-114">Командлет **Remove-WmiObject** удаляет экземпляр существующего класса инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="021b6-114">The **Remove-WmiObject** cmdlet deletes an instance of an existing Windows Management Instrumentation (WMI)class.</span></span>

## <span data-ttu-id="021b6-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="021b6-115">EXAMPLES</span></span>

### <span data-ttu-id="021b6-116">Пример 1. Закрытие всех экземпляров процесса Win32</span><span class="sxs-lookup"><span data-stu-id="021b6-116">Example 1: Close all instances of a Win32 process</span></span>

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

<span data-ttu-id="021b6-117">В этом примере закрываются все экземпляры Notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="021b6-117">This example closes all the instances of Notepad.exe.</span></span>

<span data-ttu-id="021b6-118">Первая команда запускает экземпляр Блокнота.</span><span class="sxs-lookup"><span data-stu-id="021b6-118">The first command starts an instance of Notepad.</span></span>

<span data-ttu-id="021b6-119">Вторая команда использует командлет Get-WmiObject для получения экземпляров Win32_Process, соответствующих Notepad.exe, а затем сохраняет их в переменной $np.</span><span class="sxs-lookup"><span data-stu-id="021b6-119">The second command uses the Get-WmiObject cmdlet to retrieve the instances of the Win32_Process that correspond to Notepad.exe, and then stores them in the $np variable.</span></span>

<span data-ttu-id="021b6-120">Третья команда передает объект в переменную $np в **Remove-WmiObject** , удаляя все экземпляры Notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="021b6-120">The third command passes the object in the $np variable to **Remove-WmiObject** , which deletes all the instances of Notepad.exe.</span></span>

### <span data-ttu-id="021b6-121">Пример 2. Удаление папки</span><span class="sxs-lookup"><span data-stu-id="021b6-121">Example 2: Delete a folder</span></span>

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

<span data-ttu-id="021b6-122">Эта команда удаляет папку C:\Test.</span><span class="sxs-lookup"><span data-stu-id="021b6-122">This command deletes the C:\Test folder.</span></span>

<span data-ttu-id="021b6-123">Первая команда использует **Get-WmiObject** для запроса папки C:\test, а затем сохраняет объект в переменной $a.</span><span class="sxs-lookup"><span data-stu-id="021b6-123">The first command uses **Get-WMIObject** to query for the C:\Test folder, and then stores the object in the $a variable.</span></span>

<span data-ttu-id="021b6-124">Вторая команда передает переменную $a в **Remove-WmiObject** , которая удаляет папку.</span><span class="sxs-lookup"><span data-stu-id="021b6-124">The second command pipes the $a variable to **Remove-WMIObject** , which deletes the folder.</span></span>

## <span data-ttu-id="021b6-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="021b6-125">PARAMETERS</span></span>

### <span data-ttu-id="021b6-126">-AsJob</span><span class="sxs-lookup"><span data-stu-id="021b6-126">-AsJob</span></span>
<span data-ttu-id="021b6-127">Указывает, что этот командлет запускается как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="021b6-127">Indicates that this cmdlet run as a background job.</span></span>
<span data-ttu-id="021b6-128">Используйте этот параметр для запуска команд, на завершение которых требуется много времени.</span><span class="sxs-lookup"><span data-stu-id="021b6-128">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="021b6-129">В Windows PowerShell 3.0 появились новые командлеты CIM, которые выполняют те же задачи, что и командлеты WMI.</span><span class="sxs-lookup"><span data-stu-id="021b6-129">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="021b6-130">Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту модель CIM (CIM), который позволяет командлетам использовать те же методы для управления компьютерами под управлением операционной системы Windows и другими операционными системами.</span><span class="sxs-lookup"><span data-stu-id="021b6-130">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those running other operating systems.</span></span>
<span data-ttu-id="021b6-131">Вместо использования **Remove-WmiObject** рассмотрите возможность использования командлета Remove-CimInstance https://go.microsoft.com/fwlink/?LinkId=227964 .</span><span class="sxs-lookup"><span data-stu-id="021b6-131">Instead of using **Remove-WmiObject** , consider using the Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 cmdlet.</span></span>

<span data-ttu-id="021b6-132">При использовании параметра *AsJob* команда возвращает объект, который представляет фоновое задание, а затем отображает командную строку.</span><span class="sxs-lookup"><span data-stu-id="021b6-132">When you use the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="021b6-133">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="021b6-133">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="021b6-134">Если для удаленного компьютера используется **Remove-WmiObject** , задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="021b6-134">If **Remove-WmiObject** is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="021b6-135">Для управления заданием используйте командлеты, которые содержат существительное **задания** (командлеты **задания** ).</span><span class="sxs-lookup"><span data-stu-id="021b6-135">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="021b6-136">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="021b6-136">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="021b6-137">Чтобы использовать этот параметр для удаленных компьютеров, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="021b6-137">To use this parameter for remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="021b6-138">Запустите Windows PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="021b6-138">Start Windows PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="021b6-139">Дополнительные сведения см. в разделе about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="021b6-139">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="021b6-140">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах about_Jobs и about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="021b6-140">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="021b6-141">-Authentication</span><span class="sxs-lookup"><span data-stu-id="021b6-141">-Authentication</span></span>
<span data-ttu-id="021b6-142">Указывает уровень проверки подлинности, используемый для WMI-соединения.</span><span class="sxs-lookup"><span data-stu-id="021b6-142">Specifies the authentication level to use for the WMI connection.</span></span>
<span data-ttu-id="021b6-143">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="021b6-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="021b6-144">-1: без изменений.</span><span class="sxs-lookup"><span data-stu-id="021b6-144">-1: Unchanged.</span></span>
- <span data-ttu-id="021b6-145">0: по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="021b6-145">0: Default.</span></span>
- <span data-ttu-id="021b6-146">1: нет.</span><span class="sxs-lookup"><span data-stu-id="021b6-146">1: None.</span></span>
<span data-ttu-id="021b6-147">Проверка подлинности не выполняется.</span><span class="sxs-lookup"><span data-stu-id="021b6-147">No authentication in performed.</span></span>
- <span data-ttu-id="021b6-148">2: подключение.</span><span class="sxs-lookup"><span data-stu-id="021b6-148">2: Connect.</span></span>
<span data-ttu-id="021b6-149">Проверка подлинности выполняется только в том случае, если клиент устанавливает связь с приложением.</span><span class="sxs-lookup"><span data-stu-id="021b6-149">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="021b6-150">3: вызов.</span><span class="sxs-lookup"><span data-stu-id="021b6-150">3: Call.</span></span>
<span data-ttu-id="021b6-151">Проверка подлинности выполняется только в начале каждого вызова, когда приложение получает запрос.</span><span class="sxs-lookup"><span data-stu-id="021b6-151">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="021b6-152">4: пакет.</span><span class="sxs-lookup"><span data-stu-id="021b6-152">4: Packet.</span></span>
<span data-ttu-id="021b6-153">Проверка подлинности выполняется для всех данных, получаемых от клиента.</span><span class="sxs-lookup"><span data-stu-id="021b6-153">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="021b6-154">5: Паккетинтегрити.</span><span class="sxs-lookup"><span data-stu-id="021b6-154">5: PacketIntegrity.</span></span>
<span data-ttu-id="021b6-155">Все данные, передаваемые между клиентом и приложением, проходят проверку подлинности и проверяются.</span><span class="sxs-lookup"><span data-stu-id="021b6-155">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="021b6-156">6: Паккетприваци.</span><span class="sxs-lookup"><span data-stu-id="021b6-156">6: PacketPrivacy.</span></span>
<span data-ttu-id="021b6-157">Используются свойства других уровней проверки подлинности, а все данные шифруются.</span><span class="sxs-lookup"><span data-stu-id="021b6-157">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-158">— Центр</span><span class="sxs-lookup"><span data-stu-id="021b6-158">-Authority</span></span>
<span data-ttu-id="021b6-159">Указывает центр сертификации, используемый для проверки подлинности подключения к WMI.</span><span class="sxs-lookup"><span data-stu-id="021b6-159">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="021b6-160">Можно выбрать стандартную проверку подлинности NTLM или Kerberos.</span><span class="sxs-lookup"><span data-stu-id="021b6-160">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="021b6-161">Чтобы использовать NTLM, установите для параметра authority значение ntlmdomain:\<DomainName\>, где \<DomainName\> указывает допустимое доменное имя NTLM.</span><span class="sxs-lookup"><span data-stu-id="021b6-161">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="021b6-162">Чтобы использовать Kerberos, укажите Kerberos: \<DomainName\> \\ \<ServerName\> .</span><span class="sxs-lookup"><span data-stu-id="021b6-162">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="021b6-163">Параметр authority не может быть указан при подключении к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="021b6-163">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-164">-Class</span><span class="sxs-lookup"><span data-stu-id="021b6-164">-Class</span></span>
<span data-ttu-id="021b6-165">Указывает имя класса WMI, который удаляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="021b6-165">Specifies the name of a WMI class that this cmdlet deletes.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-166">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="021b6-166">-ComputerName</span></span>
<span data-ttu-id="021b6-167">Указывает имя компьютера, на котором выполняется этот командлет.</span><span class="sxs-lookup"><span data-stu-id="021b6-167">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="021b6-168">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="021b6-168">The default is the local computer.</span></span>

<span data-ttu-id="021b6-169">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="021b6-169">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="021b6-170">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="021b6-170">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="021b6-171">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="021b6-171">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="021b6-172">Параметр *ComputerName* можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="021b6-172">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="021b6-173">-Credential</span></span>
<span data-ttu-id="021b6-174">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="021b6-174">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="021b6-175">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="021b6-175">The default is the current user.</span></span>

<span data-ttu-id="021b6-176">Введите имя пользователя, например User01 или Domain01\User01, либо укажите объект **PSCredential** , например формируемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="021b6-176">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="021b6-177">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="021b6-177">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-178">-Енаблеаллпривилежес</span><span class="sxs-lookup"><span data-stu-id="021b6-178">-EnableAllPrivileges</span></span>
<span data-ttu-id="021b6-179">Указывает, что этот командлет включает все разрешения текущего пользователя перед выполнением команды WMI.</span><span class="sxs-lookup"><span data-stu-id="021b6-179">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-180">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="021b6-180">-Impersonation</span></span>
<span data-ttu-id="021b6-181">Задает используемый уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="021b6-181">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="021b6-182">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="021b6-182">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="021b6-183">0: по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="021b6-183">0: Default.</span></span>
<span data-ttu-id="021b6-184">Считывает локальный реестр для уровня олицетворения по умолчанию, который обычно имеет значение 3: IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="021b6-184">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="021b6-185">1: анонимный.</span><span class="sxs-lookup"><span data-stu-id="021b6-185">1: Anonymous.</span></span>
<span data-ttu-id="021b6-186">Скрывает учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="021b6-186">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="021b6-187">2: выявление.</span><span class="sxs-lookup"><span data-stu-id="021b6-187">2: Identify.</span></span>
<span data-ttu-id="021b6-188">позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="021b6-188">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="021b6-189">3. олицетворение.</span><span class="sxs-lookup"><span data-stu-id="021b6-189">3: Impersonate.</span></span>
<span data-ttu-id="021b6-190">позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="021b6-190">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="021b6-191">4: делегат.</span><span class="sxs-lookup"><span data-stu-id="021b6-191">4: Delegate.</span></span>
<span data-ttu-id="021b6-192">Позволяет объектам разрешать другим объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="021b6-192">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-193">-InputObject</span><span class="sxs-lookup"><span data-stu-id="021b6-193">-InputObject</span></span>
<span data-ttu-id="021b6-194">Указывает объект **ManagementObject** для использования в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="021b6-194">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="021b6-195">Если параметр используется, все остальные параметры пропускаются.</span><span class="sxs-lookup"><span data-stu-id="021b6-195">When this parameter is used, all other parameters are ignored.</span></span>

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-196">-Locale</span><span class="sxs-lookup"><span data-stu-id="021b6-196">-Locale</span></span>
<span data-ttu-id="021b6-197">Указывает предпочтительный язык для объектов WMI.</span><span class="sxs-lookup"><span data-stu-id="021b6-197">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="021b6-198">Параметр *locale* указывается в виде массива в \<LCID\> формате MS_ в предпочтительном порядке.</span><span class="sxs-lookup"><span data-stu-id="021b6-198">The *Locale* parameter is specified as an array in the MS_\<LCID\> format in the preferred order.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-199">-Namespace</span><span class="sxs-lookup"><span data-stu-id="021b6-199">-Namespace</span></span>
<span data-ttu-id="021b6-200">Указывает пространство имен репозитория WMI, в котором расположен ссылочный класс WMI, если он используется с параметром *класса* .</span><span class="sxs-lookup"><span data-stu-id="021b6-200">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-201">-Path</span><span class="sxs-lookup"><span data-stu-id="021b6-201">-Path</span></span>
<span data-ttu-id="021b6-202">Указывает путь объекта WMI класса WMI или указывает путь объекта WMI удаляемого экземпляра класса WMI.</span><span class="sxs-lookup"><span data-stu-id="021b6-202">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class to delete.</span></span>

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021b6-203">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="021b6-203">-ThrottleLimit</span></span>
<span data-ttu-id="021b6-204">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="021b6-204">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="021b6-205">Этот параметр используется вместе с параметром *AsJob* .</span><span class="sxs-lookup"><span data-stu-id="021b6-205">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="021b6-206">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="021b6-206">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="021b6-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="021b6-207">-Confirm</span></span>
<span data-ttu-id="021b6-208">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="021b6-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="021b6-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="021b6-209">-WhatIf</span></span>
<span data-ttu-id="021b6-210">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="021b6-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="021b6-211">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="021b6-211">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="021b6-212">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="021b6-212">CommonParameters</span></span>
<span data-ttu-id="021b6-213">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="021b6-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="021b6-214">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="021b6-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="021b6-215">Входные данные</span><span class="sxs-lookup"><span data-stu-id="021b6-215">INPUTS</span></span>

### <span data-ttu-id="021b6-216">System. Management. ManagementObject</span><span class="sxs-lookup"><span data-stu-id="021b6-216">System.Management.ManagementObject</span></span>
<span data-ttu-id="021b6-217">Объект управления можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="021b6-217">You can pipe a management object to this cmdlet.</span></span>

## <span data-ttu-id="021b6-218">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="021b6-218">OUTPUTS</span></span>

### <span data-ttu-id="021b6-219">Нет, System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="021b6-219">None, System.Management.Automation.RemotingJob</span></span>
<span data-ttu-id="021b6-220">Этот командлет возвращает объект задания, если указан параметр *AsJob* .</span><span class="sxs-lookup"><span data-stu-id="021b6-220">This cmdlet returns a job object, if you specify the *AsJob* parameter.</span></span>
<span data-ttu-id="021b6-221">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="021b6-221">Otherwise, it does not generate any output.</span></span>

## <span data-ttu-id="021b6-222">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="021b6-222">NOTES</span></span>

## <span data-ttu-id="021b6-223">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="021b6-223">RELATED LINKS</span></span>

[<span data-ttu-id="021b6-224">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="021b6-224">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="021b6-225">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="021b6-225">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="021b6-226">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="021b6-226">Set-WmiInstance</span></span>](Set-WmiInstance.md)
