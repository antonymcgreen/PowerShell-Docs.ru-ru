---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "93229661"
---
# <span data-ttu-id="01066-103">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="01066-103">Invoke-WmiMethod</span></span>

## <span data-ttu-id="01066-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="01066-104">SYNOPSIS</span></span>
<span data-ttu-id="01066-105">Вызывает методы WMI.</span><span class="sxs-lookup"><span data-stu-id="01066-105">Calls WMI methods.</span></span>

## <span data-ttu-id="01066-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01066-106">SYNTAX</span></span>

### <span data-ttu-id="01066-107">Класс (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="01066-107">class (Default)</span></span>

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01066-108">объект</span><span class="sxs-lookup"><span data-stu-id="01066-108">object</span></span>

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01066-109">path</span><span class="sxs-lookup"><span data-stu-id="01066-109">path</span></span>

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01066-110">вклкуери</span><span class="sxs-lookup"><span data-stu-id="01066-110">WQLQuery</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01066-111">query</span><span class="sxs-lookup"><span data-stu-id="01066-111">query</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01066-112">list</span><span class="sxs-lookup"><span data-stu-id="01066-112">list</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="01066-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01066-113">DESCRIPTION</span></span>

<span data-ttu-id="01066-114">`Invoke-WmiMethod`Командлет вызывает методы объектов инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="01066-114">The `Invoke-WmiMethod` cmdlet calls the methods of Windows Management Instrumentation (WMI) objects.</span></span>

<span data-ttu-id="01066-115">Новые командлеты модель CIM (CIM), появившиеся в Windows PowerShell 3,0, выполняют те же задачи, что и командлеты WMI.</span><span class="sxs-lookup"><span data-stu-id="01066-115">New Common Information Model (CIM) cmdlets, introduced in Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="01066-116">Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту CIM, который позволяет командлетам использовать те же методы для управления компьютерами Windows и другими операционными системами.</span><span class="sxs-lookup"><span data-stu-id="01066-116">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage Windows computers and those running other operating systems.</span></span> <span data-ttu-id="01066-117">Вместо использования `Invoke-WmiMethod` рекомендуется использовать [командлет Invoke-Циммесод](../cimcmdlets/invoke-cimmethod.md).</span><span class="sxs-lookup"><span data-stu-id="01066-117">Instead of using `Invoke-WmiMethod`, consider using [Invoke-CimMethod](../cimcmdlets/invoke-cimmethod.md).</span></span>

## <span data-ttu-id="01066-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="01066-118">EXAMPLES</span></span>

### <span data-ttu-id="01066-119">Пример 1. вывод необходимого порядка объектов WMI</span><span class="sxs-lookup"><span data-stu-id="01066-119">Example 1: List the required order of WMI objects</span></span>

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

<span data-ttu-id="01066-120">Эта команда указывает нужный порядок объектов.</span><span class="sxs-lookup"><span data-stu-id="01066-120">This command lists the required order of the objects.</span></span> <span data-ttu-id="01066-121">Вызов WMI в PowerShell 3.0 отличается от других методов и требует, чтобы значения объекта вводились в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="01066-121">To invoke WMI in PowerShell 3.0 differs from alternate methods, and requires that object values are entered in a specific order.</span></span>

### <span data-ttu-id="01066-122">Пример 2. Запуск экземпляра приложения</span><span class="sxs-lookup"><span data-stu-id="01066-122">Example 2: Start an instance of an application</span></span>

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

<span data-ttu-id="01066-123">Эта команда запускает экземпляр блокнота, вызывая `Create` метод класса **Win32_Process** .</span><span class="sxs-lookup"><span data-stu-id="01066-123">This command starts an instance of Notepad by calling the `Create` method of the **Win32_Process** class.</span></span>

<span data-ttu-id="01066-124">Свойство **ReturnValue** заполняется значением 0, а свойство **ProcessID** заполняется ЦЕЛЫМ числом (идентификатором следующего процесса), если команда выполнена.</span><span class="sxs-lookup"><span data-stu-id="01066-124">The **ReturnValue** property is populated with a 0, and the **ProcessId** property is populated with an integer (the next process ID number) if the command is completed.</span></span>

### <span data-ttu-id="01066-125">Пример 3. Переименование файла</span><span class="sxs-lookup"><span data-stu-id="01066-125">Example 3: Rename a file</span></span>

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

<span data-ttu-id="01066-126">Эта команда переименовывает файл.</span><span class="sxs-lookup"><span data-stu-id="01066-126">This command renames a file.</span></span> <span data-ttu-id="01066-127">Он использует параметр **path** для ссылки на экземпляр класса **CIM_DataFile** .</span><span class="sxs-lookup"><span data-stu-id="01066-127">It uses the **Path** parameter to reference an instance of the **CIM_DataFile** class.</span></span> <span data-ttu-id="01066-128">Затем она применяет метод Rename к этому конкретному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="01066-128">Then, it applies the Rename method to that particular instance.</span></span>

<span data-ttu-id="01066-129">Если команда выполнена, свойство **ReturnValue** заполняется 0.</span><span class="sxs-lookup"><span data-stu-id="01066-129">The **ReturnValue** property is populated with a 0 if the command is completed.</span></span>

### <span data-ttu-id="01066-130">Пример 4. Передача массива значений с помощью `-ArgumentList`</span><span class="sxs-lookup"><span data-stu-id="01066-130">Example 4: Passing an array of values using `-ArgumentList`</span></span>

<span data-ttu-id="01066-131">Пример использования массива объектов `$binSD` , за которым следует `$null` значение.</span><span class="sxs-lookup"><span data-stu-id="01066-131">An example using an array of objects `$binSD` followed by a `$null` value.</span></span>

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## <span data-ttu-id="01066-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01066-132">PARAMETERS</span></span>

### <span data-ttu-id="01066-133">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="01066-133">-ArgumentList</span></span>

<span data-ttu-id="01066-134">Задает параметры для передачи в вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="01066-134">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="01066-135">Значение этого параметра должно быть массивом объектов и должно находиться в том порядке, который требуется вызываемому методу.</span><span class="sxs-lookup"><span data-stu-id="01066-135">The value of this parameter must be an array of objects, and they must appear in the order required by the called method.</span></span> <span data-ttu-id="01066-136">У `Invoke-CimCommand` командлета нет этих ограничений.</span><span class="sxs-lookup"><span data-stu-id="01066-136">The `Invoke-CimCommand` cmdlet does not have these limitations.</span></span>

<span data-ttu-id="01066-137">Чтобы определить порядок перечисления этих объектов, запустите `GetMethodParameters()` метод класса WMI, как показано в примере 1 в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="01066-137">To determine the order in which to list those objects, run the `GetMethodParameters()` method on the WMI class, as illustrated in Example 1, near the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01066-138">Если первое значение является массивом, который содержит более одного элемента, требуется второе значение $null.</span><span class="sxs-lookup"><span data-stu-id="01066-138">If the first value is an array that contains more than one element, a second value of $null is required.</span></span> <span data-ttu-id="01066-139">В противном случае команда вызывает ошибку: например, «Не удалось привести объект типа System.Byte к типу System.Array».</span><span class="sxs-lookup"><span data-stu-id="01066-139">Otherwise, the command generates an error, such as "Unable to cast object of type 'System.Byte' to type 'System.Array'.".</span></span> <span data-ttu-id="01066-140">См. Пример 4 выше.</span><span class="sxs-lookup"><span data-stu-id="01066-140">See example 4 above.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01066-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="01066-141">-AsJob</span></span>

<span data-ttu-id="01066-142">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="01066-142">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="01066-143">Используйте этот параметр для запуска команд, на завершение которых требуется много времени.</span><span class="sxs-lookup"><span data-stu-id="01066-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="01066-144">При использовании параметра **AsJob** команда возвращает объект, который представляет фоновое задание, а затем отображает командную строку.</span><span class="sxs-lookup"><span data-stu-id="01066-144">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="01066-145">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="01066-145">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="01066-146">Если `Invoke-WmiMethod` используется на удаленном компьютере, задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="01066-146">If `Invoke-WmiMethod` is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="01066-147">Чтобы управлять заданием, используйте командлеты, которые содержат существительное Job (командлеты Job).</span><span class="sxs-lookup"><span data-stu-id="01066-147">To manage the job, use the cmdlets that contain the Job noun (the Job cmdlets).</span></span> <span data-ttu-id="01066-148">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="01066-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="01066-149">Для использования этого параметра с удаленными компьютерами локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="01066-149">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="01066-150">Кроме того, необходимо запустить Windows PowerShell с помощью команды Запуск от имени администратора в Windows Vista и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="01066-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="01066-151">Дополнительные сведения см. в разделе about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="01066-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="01066-152">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах about_Jobs и about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="01066-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="01066-153">-Authentication</span><span class="sxs-lookup"><span data-stu-id="01066-153">-Authentication</span></span>

<span data-ttu-id="01066-154">Указывает уровень проверки подлинности, используемый для подключения к WMI.</span><span class="sxs-lookup"><span data-stu-id="01066-154">Specifies the authentication level to be used with the WMI connection.</span></span> <span data-ttu-id="01066-155">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="01066-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="01066-156">-1: без изменений</span><span class="sxs-lookup"><span data-stu-id="01066-156">-1: Unchanged</span></span>
- <span data-ttu-id="01066-157">0: по умолчанию</span><span class="sxs-lookup"><span data-stu-id="01066-157">0: Default</span></span>
- <span data-ttu-id="01066-158">1: нет (проверка подлинности не выполняется).</span><span class="sxs-lookup"><span data-stu-id="01066-158">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="01066-159">2: Connect (проверка подлинности выполняется только в том случае, если клиент устанавливает связь с приложением.)</span><span class="sxs-lookup"><span data-stu-id="01066-159">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="01066-160">3: вызов (проверка подлинности выполняется только в начале каждого вызова, когда приложение получает запрос).</span><span class="sxs-lookup"><span data-stu-id="01066-160">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="01066-161">4: пакет (проверка подлинности выполняется для всех данных, полученных от клиента.)</span><span class="sxs-lookup"><span data-stu-id="01066-161">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="01066-162">5: Паккетинтегрити (все данные, передаваемые между клиентом и приложением, проходят проверку подлинности и проверяются.)</span><span class="sxs-lookup"><span data-stu-id="01066-162">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="01066-163">6: Паккетприваци (используются свойства других уровней проверки подлинности, и все данные шифруются).</span><span class="sxs-lookup"><span data-stu-id="01066-163">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

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

### <span data-ttu-id="01066-164">— Центр</span><span class="sxs-lookup"><span data-stu-id="01066-164">-Authority</span></span>

<span data-ttu-id="01066-165">Указывает центр сертификации, используемый для проверки подлинности подключения к WMI.</span><span class="sxs-lookup"><span data-stu-id="01066-165">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="01066-166">Можно указать стандартную проверку подлинности Windows NT LAN Manager (NTLM) или Kerberos.</span><span class="sxs-lookup"><span data-stu-id="01066-166">You can specify standard Windows NT LAN Manager (NTLM) or Kerberos authentication.</span></span> <span data-ttu-id="01066-167">Чтобы использовать NTLM, установите для параметра authority значение ntlmdomain:\<DomainName\>, где \<DomainName\> указывает допустимое доменное имя NTLM.</span><span class="sxs-lookup"><span data-stu-id="01066-167">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span> <span data-ttu-id="01066-168">Чтобы использовать Kerberos, укажите kerberos:\<DomainName\ServerName\>.</span><span class="sxs-lookup"><span data-stu-id="01066-168">To use Kerberos, specify kerberos:\<DomainName\ServerName\>.</span></span> <span data-ttu-id="01066-169">Параметр authority не может быть указан при подключении к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="01066-169">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="01066-170">-Class</span><span class="sxs-lookup"><span data-stu-id="01066-170">-Class</span></span>

<span data-ttu-id="01066-171">Указывает класс WMI, который содержит вызываемый статический метод.</span><span class="sxs-lookup"><span data-stu-id="01066-171">Specifies the WMI class that contains a static method to call.</span></span>

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

### <span data-ttu-id="01066-172">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="01066-172">-ComputerName</span></span>

<span data-ttu-id="01066-173">Указывает в виде массива строк компьютеры, на которых этот командлет выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="01066-173">Specifies, as a string array, the computers that this cmdlet runs the command on.</span></span> <span data-ttu-id="01066-174">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="01066-174">The default is the local computer.</span></span>

<span data-ttu-id="01066-175">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="01066-175">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span> <span data-ttu-id="01066-176">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="01066-176">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="01066-177">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01066-177">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="01066-178">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="01066-178">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="01066-179">-Credential</span><span class="sxs-lookup"><span data-stu-id="01066-179">-Credential</span></span>

<span data-ttu-id="01066-180">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="01066-180">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="01066-181">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="01066-181">The default is the current user.</span></span> <span data-ttu-id="01066-182">Введите имя пользователя, например `User01` , `Domain01\User01` или `User@Contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="01066-182">Type a user name, such as `User01`, `Domain01\User01`, or `User@Contoso.com`.</span></span> <span data-ttu-id="01066-183">Или введите объект **PSCredential** , например объект, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="01066-183">Or, enter a **PSCredential** object, such as an object that is returned by the Get-Credential cmdlet.</span></span> <span data-ttu-id="01066-184">При вводе имени пользователя появится приглашение ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="01066-184">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="01066-185">-Енаблеаллпривилежес</span><span class="sxs-lookup"><span data-stu-id="01066-185">-EnableAllPrivileges</span></span>

<span data-ttu-id="01066-186">Указывает, что этот командлет включает все привилегии текущего пользователя, прежде чем команда сделает вызов WMI.</span><span class="sxs-lookup"><span data-stu-id="01066-186">Indicates that this cmdlet enables all the privileges of the current user before the command makes the WMI call.</span></span>

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

### <span data-ttu-id="01066-187">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="01066-187">-Impersonation</span></span>

<span data-ttu-id="01066-188">Задает используемый уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="01066-188">Specifies the impersonation level to use.</span></span> <span data-ttu-id="01066-189">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="01066-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="01066-190">0: по умолчанию (считывает локальный реестр для уровня олицетворения по умолчанию, который обычно имеет значение "3: IMPERSONATE".)</span><span class="sxs-lookup"><span data-stu-id="01066-190">0: Default (Reads the local registry for the default impersonation level, which is usually set to "3: Impersonate".)</span></span>
- <span data-ttu-id="01066-191">1: anonymous (скрывает учетные данные вызывающей стороны).</span><span class="sxs-lookup"><span data-stu-id="01066-191">1: Anonymous (Hides the credentials of the caller.)</span></span>
- <span data-ttu-id="01066-192">2: Identify (позволяет объектам запрашивать учетные данные вызывающей стороны).</span><span class="sxs-lookup"><span data-stu-id="01066-192">2: Identify (Allows objects to query the credentials of the caller.)</span></span>
- <span data-ttu-id="01066-193">3. олицетворение (позволяет объектам использовать учетные данные вызывающей стороны).</span><span class="sxs-lookup"><span data-stu-id="01066-193">3: Impersonate (Allows objects to use the credentials of the caller.)</span></span>
- <span data-ttu-id="01066-194">4: делегат (позволяет объектам разрешить другим объектам использовать учетные данные вызывающей стороны).</span><span class="sxs-lookup"><span data-stu-id="01066-194">4: Delegate (Allows objects to permit other objects to use the credentials of the caller.)</span></span>

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

### <span data-ttu-id="01066-195">-InputObject</span><span class="sxs-lookup"><span data-stu-id="01066-195">-InputObject</span></span>

<span data-ttu-id="01066-196">Указывает объект **ManagementObject** для использования в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="01066-196">Specifies a **ManagementObject** object to use as input.</span></span> <span data-ttu-id="01066-197">При использовании этого параметра все остальные параметры, за исключением параметров **Flag** и **Argument** , игнорируются.</span><span class="sxs-lookup"><span data-stu-id="01066-197">When this parameter is used, all other parameters except the **Flag** and **Argument** parameters are ignored.</span></span>

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

### <span data-ttu-id="01066-198">-Locale</span><span class="sxs-lookup"><span data-stu-id="01066-198">-Locale</span></span>

<span data-ttu-id="01066-199">Указывает предпочтительный язык для объектов WMI.</span><span class="sxs-lookup"><span data-stu-id="01066-199">Specifies the preferred locale for WMI objects.</span></span> <span data-ttu-id="01066-200">Укажите значение параметра **locale** в формате массива в `MS_<LCID>` предпочтительном порядке.</span><span class="sxs-lookup"><span data-stu-id="01066-200">Specify the value of the **Locale** parameter as an array in the `MS_<LCID>` format in the preferred order.</span></span>

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

### <span data-ttu-id="01066-201">-Name</span><span class="sxs-lookup"><span data-stu-id="01066-201">-Name</span></span>

<span data-ttu-id="01066-202">Указывает имя вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="01066-202">Specifies the name of the method to be invoked.</span></span> <span data-ttu-id="01066-203">Этот параметр является обязательным и не может быть NULL или пустым.</span><span class="sxs-lookup"><span data-stu-id="01066-203">This parameter is mandatory and cannot be null or empty.</span></span>

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

### <span data-ttu-id="01066-204">-Namespace</span><span class="sxs-lookup"><span data-stu-id="01066-204">-Namespace</span></span>

<span data-ttu-id="01066-205">При использовании с параметром **класса** этот параметр указывает пространство имен репозитория WMI, в котором находится упоминаемый класс WMI или объект.</span><span class="sxs-lookup"><span data-stu-id="01066-205">When used with the **Class** parameter, this parameter specifies the WMI repository namespace where the referenced WMI class or object is located.</span></span>

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

### <span data-ttu-id="01066-206">-Path</span><span class="sxs-lookup"><span data-stu-id="01066-206">-Path</span></span>

<span data-ttu-id="01066-207">Указывает путь к объекту WMI класса WMI или указывает путь к объекту WMI экземпляра класса WMI.</span><span class="sxs-lookup"><span data-stu-id="01066-207">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class.</span></span> <span data-ttu-id="01066-208">Заданный класс или экземпляр должны содержать метод, указанный в параметре **Name** .</span><span class="sxs-lookup"><span data-stu-id="01066-208">The class or the instance that you specify must contain the method that is specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="01066-209">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="01066-209">-ThrottleLimit</span></span>

<span data-ttu-id="01066-210">Указывает значение регулирования для количества операций WMI, которые могут выполняться одновременно.</span><span class="sxs-lookup"><span data-stu-id="01066-210">Specifies a throttle value for the number of WMI operations that can be executed simultaneously.</span></span>
<span data-ttu-id="01066-211">Этот параметр используется вместе с параметром **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="01066-211">This parameter is used together with the **AsJob** parameter.</span></span> <span data-ttu-id="01066-212">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="01066-212">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="01066-213">-Confirm</span><span class="sxs-lookup"><span data-stu-id="01066-213">-Confirm</span></span>

<span data-ttu-id="01066-214">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="01066-214">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="01066-215">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="01066-215">-WhatIf</span></span>

<span data-ttu-id="01066-216">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="01066-216">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="01066-217">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="01066-217">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="01066-218">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="01066-218">CommonParameters</span></span>

<span data-ttu-id="01066-219">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01066-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01066-220">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="01066-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01066-221">Входные данные</span><span class="sxs-lookup"><span data-stu-id="01066-221">INPUTS</span></span>

### <span data-ttu-id="01066-222">Нет</span><span class="sxs-lookup"><span data-stu-id="01066-222">None</span></span>

<span data-ttu-id="01066-223">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="01066-223">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="01066-224">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="01066-224">OUTPUTS</span></span>

### <span data-ttu-id="01066-225">Нет</span><span class="sxs-lookup"><span data-stu-id="01066-225">None</span></span>

<span data-ttu-id="01066-226">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="01066-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="01066-227">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="01066-227">NOTES</span></span>

## <span data-ttu-id="01066-228">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="01066-228">RELATED LINKS</span></span>

[<span data-ttu-id="01066-229">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="01066-229">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="01066-230">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="01066-230">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="01066-231">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="01066-231">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="01066-232">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="01066-232">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[<span data-ttu-id="01066-233">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="01066-233">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="01066-234">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="01066-234">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="01066-235">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="01066-235">Set-WmiInstance</span></span>](Set-WmiInstance.md)
