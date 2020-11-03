---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227870"
---
# <span data-ttu-id="53990-103">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="53990-103">Set-WmiInstance</span></span>

## <span data-ttu-id="53990-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="53990-104">SYNOPSIS</span></span>
<span data-ttu-id="53990-105">Создает или обновляет экземпляр существующего класса WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-105">Creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="53990-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53990-106">SYNTAX</span></span>

### <span data-ttu-id="53990-107">Класс (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="53990-107">class (Default)</span></span>

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53990-108">объект</span><span class="sxs-lookup"><span data-stu-id="53990-108">object</span></span>

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53990-109">path</span><span class="sxs-lookup"><span data-stu-id="53990-109">path</span></span>

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53990-110">вклкуери</span><span class="sxs-lookup"><span data-stu-id="53990-110">WQLQuery</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53990-111">query</span><span class="sxs-lookup"><span data-stu-id="53990-111">query</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53990-112">list</span><span class="sxs-lookup"><span data-stu-id="53990-112">list</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="53990-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="53990-113">DESCRIPTION</span></span>
<span data-ttu-id="53990-114">`Set-WmiInstance`Командлет создает или обновляет экземпляр существующего класса инструментарий управления Windows (WMI) (WMI).</span><span class="sxs-lookup"><span data-stu-id="53990-114">The `Set-WmiInstance` cmdlet creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>
<span data-ttu-id="53990-115">Созданный или обновленный экземпляр записывается в репозиторий WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-115">The created or updated instance is written to the WMI repository.</span></span>

<span data-ttu-id="53990-116">В Windows PowerShell 3.0 появились новые командлеты CIM, которые выполняют те же задачи, что и командлеты WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-116">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="53990-117">Командлеты CIM соответствуют стандартам WS-Management (WSMan) и стандарту модель CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="53990-117">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard.</span></span>
<span data-ttu-id="53990-118">Это позволяет командлетам использовать те же методы для управления компьютерами под управлением Windows и с другими операционными системами.</span><span class="sxs-lookup"><span data-stu-id="53990-118">this enables cmdlets to use the same techniques to manage Windows-based computers and those running other operating systems.</span></span>
<span data-ttu-id="53990-119">Вместо использования `Set-WmiInstance` , рассмотрите возможность использования командлетов [Set-Ciminstance](/powershell/module/cimcmdlets/set-ciminstance) или [New-ciminstance](/powershell/module/cimcmdlets/new-ciminstance) .</span><span class="sxs-lookup"><span data-stu-id="53990-119">Instead of using `Set-WmiInstance`, consider using the [Set-CimInstance](/powershell/module/cimcmdlets/set-ciminstance) or [New-CimInstance](/powershell/module/cimcmdlets/new-ciminstance) cmdlets.</span></span>

## <span data-ttu-id="53990-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="53990-120">EXAMPLES</span></span>

### <span data-ttu-id="53990-121">Пример 1. Настройка уровня ведения журнала WMI</span><span class="sxs-lookup"><span data-stu-id="53990-121">Example 1: Set WMI logging level</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

<span data-ttu-id="53990-122">Эта команда задает 2 уровень ведения журнала WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-122">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="53990-123">Команда передает свойство в значение, которое вместе считается парой значений в параметре argument.</span><span class="sxs-lookup"><span data-stu-id="53990-123">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="53990-124">Параметр принимает хэш-таблицу, которая определяется конструкцией @{property = value}.</span><span class="sxs-lookup"><span data-stu-id="53990-124">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="53990-125">Возвращаемые сведения о классе отражают новое значение.</span><span class="sxs-lookup"><span data-stu-id="53990-125">The class information that is returned reflects the new value.</span></span>

### <span data-ttu-id="53990-126">Пример 2. Создание переменной среды и ее значения</span><span class="sxs-lookup"><span data-stu-id="53990-126">Example 2: Create an environment variable and its value</span></span>

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

<span data-ttu-id="53990-127">Эта команда создает переменную среды testvar, которая имеет значение testValue.</span><span class="sxs-lookup"><span data-stu-id="53990-127">This command creates the testvar environment variable that has the value testvalue.</span></span>
<span data-ttu-id="53990-128">Для этого создается новый экземпляр класса **Win32_Environment** WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-128">It does this by creating a new instance of the **Win32_Environment** WMI class.</span></span>
<span data-ttu-id="53990-129">Для этой операции требуются соответствующие учетные данные, поэтому для просмотра новой переменной среды может потребоваться перезапустить Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53990-129">This operation requires appropriate credentials and that you may have to restart Windows PowerShell to see the new environment variable.</span></span>

### <span data-ttu-id="53990-130">Пример 3. Настройка уровня ведения журнала WMI для нескольких удаленных компьютеров</span><span class="sxs-lookup"><span data-stu-id="53990-130">Example 3: Set WMI logging level for several remote computers</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

<span data-ttu-id="53990-131">Эта команда задает 2 уровень ведения журнала WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-131">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="53990-132">Команда передает свойство в значение, которое вместе считается парой значений в параметре argument.</span><span class="sxs-lookup"><span data-stu-id="53990-132">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="53990-133">Параметр принимает хэш-таблицу, которая определяется конструкцией @{property = value}.</span><span class="sxs-lookup"><span data-stu-id="53990-133">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="53990-134">Возвращаемые сведения о классе отражают новое значение.</span><span class="sxs-lookup"><span data-stu-id="53990-134">The returned class information reflects the new value.</span></span>

## <span data-ttu-id="53990-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53990-135">PARAMETERS</span></span>

### <span data-ttu-id="53990-136">-Arguments</span><span class="sxs-lookup"><span data-stu-id="53990-136">-Arguments</span></span>
<span data-ttu-id="53990-137">Указывает имя свойства, которое необходимо изменить, и новое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="53990-137">Specifies the name of the property to be changed and the new value for that property.</span></span>
<span data-ttu-id="53990-138">Имя и значение должны быть парой "имя-значение".</span><span class="sxs-lookup"><span data-stu-id="53990-138">The name and value must be a name-value pair.</span></span>
<span data-ttu-id="53990-139">Пара "имя-значение" передается в командной строке в виде хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="53990-139">The name-value pair is passed on the command line as a hash table.</span></span>
<span data-ttu-id="53990-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="53990-140">For example:</span></span>

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53990-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="53990-141">-AsJob</span></span>
<span data-ttu-id="53990-142">Указывает, что этот кмдкет выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="53990-142">Indicates that this cmdket runs as a background job.</span></span>
<span data-ttu-id="53990-143">Используйте этот параметр для запуска команд, на завершение которых требуется много времени.</span><span class="sxs-lookup"><span data-stu-id="53990-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="53990-144">При указании параметра *AsJob* команда возвращает объект, представляющий фоновое задание, а затем отображает командную строку.</span><span class="sxs-lookup"><span data-stu-id="53990-144">When you specify the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="53990-145">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="53990-145">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="53990-146">Если для удаленного компьютера используется **Set-WmiInstance** , задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="53990-146">If **Set-WmiInstance** is used for a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="53990-147">Для управления заданием используйте командлеты, которые содержат существительное **задания** (командлеты **задания** ).</span><span class="sxs-lookup"><span data-stu-id="53990-147">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="53990-148">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="53990-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="53990-149">Чтобы использовать этот параметр вместе с удаленными компьютерами, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="53990-149">To use this parameter together with remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="53990-150">Кроме того, необходимо запустить Windows PowerShell с помощью команды Запуск от имени администратора в Windows Vista и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="53990-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of the Windows operating system.</span></span>
<span data-ttu-id="53990-151">Дополнительные сведения см. в разделе about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="53990-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="53990-152">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах about_Jobs и about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="53990-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="53990-153">-Authentication</span><span class="sxs-lookup"><span data-stu-id="53990-153">-Authentication</span></span>
<span data-ttu-id="53990-154">Указывает уровень проверки подлинности, который должен использоваться с WMI Connection.</span><span class="sxs-lookup"><span data-stu-id="53990-154">Specifies the authentication level that must be used with the WMI connection.</span></span>
<span data-ttu-id="53990-155">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="53990-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="53990-156">-1: без изменений.</span><span class="sxs-lookup"><span data-stu-id="53990-156">-1: Unchanged.</span></span>
- <span data-ttu-id="53990-157">0: по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="53990-157">0: Default.</span></span>
- <span data-ttu-id="53990-158">1: нет.</span><span class="sxs-lookup"><span data-stu-id="53990-158">1: None.</span></span>
<span data-ttu-id="53990-159">Проверка подлинности не выполняется.</span><span class="sxs-lookup"><span data-stu-id="53990-159">No authentication in performed.</span></span>
- <span data-ttu-id="53990-160">2: подключение.</span><span class="sxs-lookup"><span data-stu-id="53990-160">2: Connect.</span></span>
<span data-ttu-id="53990-161">Проверка подлинности выполняется только в том случае, если клиент устанавливает связь с приложением.</span><span class="sxs-lookup"><span data-stu-id="53990-161">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="53990-162">3: вызов.</span><span class="sxs-lookup"><span data-stu-id="53990-162">3: Call.</span></span>
<span data-ttu-id="53990-163">Проверка подлинности выполняется только в начале каждого вызова, когда приложение получает запрос.</span><span class="sxs-lookup"><span data-stu-id="53990-163">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="53990-164">4: пакет.</span><span class="sxs-lookup"><span data-stu-id="53990-164">4: Packet.</span></span>
<span data-ttu-id="53990-165">Проверка подлинности выполняется для всех данных, получаемых от клиента.</span><span class="sxs-lookup"><span data-stu-id="53990-165">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="53990-166">5: Паккетинтегрити.</span><span class="sxs-lookup"><span data-stu-id="53990-166">5: PacketIntegrity.</span></span>
<span data-ttu-id="53990-167">Все данные, передаваемые между клиентом и приложением, проходят проверку подлинности и проверяются.</span><span class="sxs-lookup"><span data-stu-id="53990-167">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="53990-168">6: Паккетприваци.</span><span class="sxs-lookup"><span data-stu-id="53990-168">6: PacketPrivacy.</span></span>
<span data-ttu-id="53990-169">Используются свойства других уровней проверки подлинности, а все данные шифруются.</span><span class="sxs-lookup"><span data-stu-id="53990-169">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

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

### <span data-ttu-id="53990-170">— Центр</span><span class="sxs-lookup"><span data-stu-id="53990-170">-Authority</span></span>
<span data-ttu-id="53990-171">Указывает центр сертификации, используемый для проверки подлинности подключения к WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-171">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="53990-172">Можно выбрать стандартную проверку подлинности NTLM или Kerberos.</span><span class="sxs-lookup"><span data-stu-id="53990-172">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="53990-173">Чтобы использовать NTLM, установите для параметра authority значение ntlmdomain:\<DomainName\>, где \<DomainName\> указывает допустимое доменное имя NTLM.</span><span class="sxs-lookup"><span data-stu-id="53990-173">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="53990-174">Чтобы использовать Kerberos, укажите Kerberos: \<DomainName\> \\ \<ServerName\> .</span><span class="sxs-lookup"><span data-stu-id="53990-174">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="53990-175">Параметр authority не может быть указан при подключении к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="53990-175">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="53990-176">-Class</span><span class="sxs-lookup"><span data-stu-id="53990-176">-Class</span></span>
<span data-ttu-id="53990-177">Задает имя класса WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-177">Specifies the name of a WMI class.</span></span>

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

### <span data-ttu-id="53990-178">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="53990-178">-ComputerName</span></span>
<span data-ttu-id="53990-179">Указывает имя компьютера, на котором выполняется этот командлет.</span><span class="sxs-lookup"><span data-stu-id="53990-179">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="53990-180">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="53990-180">The default is the local computer.</span></span>

<span data-ttu-id="53990-181">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="53990-181">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="53990-182">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="53990-182">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="53990-183">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53990-183">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="53990-184">Параметр *ComputerName* можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="53990-184">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="53990-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="53990-185">-Credential</span></span>
<span data-ttu-id="53990-186">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="53990-186">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="53990-187">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="53990-187">The default is the current user.</span></span>

<span data-ttu-id="53990-188">Введите имя пользователя, например User01 или Domain01\User01, либо укажите объект **PSCredential** , например формируемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="53990-188">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="53990-189">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="53990-189">If you type a user name, this cmdlet prompts for a password.</span></span>

<span data-ttu-id="53990-190">Этот параметр не поддерживается поставщиками, установленными с параметром, не поддерживается какими-либо поставщиками, установленными с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53990-190">This parameter is not supported by any providers installed with parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="53990-191">-Енаблеаллпривилежес</span><span class="sxs-lookup"><span data-stu-id="53990-191">-EnableAllPrivileges</span></span>
<span data-ttu-id="53990-192">Указывает, что этот командлет включает все разрешения текущего пользователя перед выполнением команды WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-192">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

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

### <span data-ttu-id="53990-193">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="53990-193">-Impersonation</span></span>
<span data-ttu-id="53990-194">Задает используемый уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="53990-194">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="53990-195">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="53990-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="53990-196">0: по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="53990-196">0: Default.</span></span>
<span data-ttu-id="53990-197">Считывает локальный реестр для уровня олицетворения по умолчанию, который обычно имеет значение 3: IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="53990-197">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="53990-198">1: анонимный.</span><span class="sxs-lookup"><span data-stu-id="53990-198">1: Anonymous.</span></span>
<span data-ttu-id="53990-199">Скрывает учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="53990-199">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="53990-200">2: выявление.</span><span class="sxs-lookup"><span data-stu-id="53990-200">2: Identify.</span></span>
<span data-ttu-id="53990-201">позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="53990-201">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="53990-202">3. олицетворение.</span><span class="sxs-lookup"><span data-stu-id="53990-202">3: Impersonate.</span></span>
<span data-ttu-id="53990-203">позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="53990-203">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="53990-204">4: делегат.</span><span class="sxs-lookup"><span data-stu-id="53990-204">4: Delegate.</span></span>
<span data-ttu-id="53990-205">Позволяет объектам разрешать другим объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="53990-205">Allows objects to permit other objects to use the credentials of the caller.</span></span>

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

### <span data-ttu-id="53990-206">-InputObject</span><span class="sxs-lookup"><span data-stu-id="53990-206">-InputObject</span></span>
<span data-ttu-id="53990-207">Указывает объект **ManagementObject** для использования в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="53990-207">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="53990-208">При использовании этого параметра все остальные параметры, за исключением параметра *arguments* , игнорируются.</span><span class="sxs-lookup"><span data-stu-id="53990-208">When this parameter is used, all other parameters ,except the *Arguments* parameter, are ignored.</span></span>

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

### <span data-ttu-id="53990-209">-Locale</span><span class="sxs-lookup"><span data-stu-id="53990-209">-Locale</span></span>
<span data-ttu-id="53990-210">Указывает предпочтительный язык для объектов WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-210">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="53990-211">Параметр *locale* указывается в массиве в \<LCID\> формате MS_ в предпочтительном порядке.</span><span class="sxs-lookup"><span data-stu-id="53990-211">The *Locale* parameter is specified in an array in the MS_\<LCID\> format in the preferred order.</span></span>

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

### <span data-ttu-id="53990-212">-Namespace</span><span class="sxs-lookup"><span data-stu-id="53990-212">-Namespace</span></span>
<span data-ttu-id="53990-213">Указывает пространство имен репозитория WMI, в котором расположен ссылочный класс WMI, если он используется с параметром *класса* .</span><span class="sxs-lookup"><span data-stu-id="53990-213">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

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

### <span data-ttu-id="53990-214">-Path</span><span class="sxs-lookup"><span data-stu-id="53990-214">-Path</span></span>
<span data-ttu-id="53990-215">Указывает путь к объекту WMI экземпляра, который необходимо создать или обновить.</span><span class="sxs-lookup"><span data-stu-id="53990-215">Specifies a WMI object path of the instance that you want to create or update.</span></span>

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

### <span data-ttu-id="53990-216">-Путтипе</span><span class="sxs-lookup"><span data-stu-id="53990-216">-PutType</span></span>
<span data-ttu-id="53990-217">Указывает, следует ли создать или обновить экземпляр WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-217">Indicates whether to create or update the WMI instance.</span></span>
<span data-ttu-id="53990-218">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="53990-218">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="53990-219">Упдатеонли.</span><span class="sxs-lookup"><span data-stu-id="53990-219">UpdateOnly.</span></span>
<span data-ttu-id="53990-220">обновляет существующий экземпляр WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-220">Updates an existing WMI instance.</span></span>
- <span data-ttu-id="53990-221">Креатеонли.</span><span class="sxs-lookup"><span data-stu-id="53990-221">CreateOnly.</span></span>
<span data-ttu-id="53990-222">создает новый экземпляр WMI.</span><span class="sxs-lookup"><span data-stu-id="53990-222">Creates a new WMI instance.</span></span>
- <span data-ttu-id="53990-223">Упдатеоркреате.</span><span class="sxs-lookup"><span data-stu-id="53990-223">UpdateOrCreate.</span></span>
<span data-ttu-id="53990-224">обновляет экземпляр WMI, если он существует, или создает новый экземпляр, если экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="53990-224">Updates the WMI instance if it exists or creates a new instance if an instance does not exist.</span></span>

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53990-225">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="53990-225">-ThrottleLimit</span></span>
<span data-ttu-id="53990-226">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="53990-226">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="53990-227">Этот параметр используется вместе с параметром *AsJob* .</span><span class="sxs-lookup"><span data-stu-id="53990-227">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="53990-228">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="53990-228">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="53990-229">-Confirm</span><span class="sxs-lookup"><span data-stu-id="53990-229">-Confirm</span></span>
<span data-ttu-id="53990-230">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="53990-230">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="53990-231">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="53990-231">-WhatIf</span></span>
<span data-ttu-id="53990-232">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="53990-232">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="53990-233">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="53990-233">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="53990-234">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="53990-234">CommonParameters</span></span>
<span data-ttu-id="53990-235">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="53990-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53990-236">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="53990-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="53990-237">Входные данные</span><span class="sxs-lookup"><span data-stu-id="53990-237">INPUTS</span></span>

### <span data-ttu-id="53990-238">Нет</span><span class="sxs-lookup"><span data-stu-id="53990-238">None</span></span>
<span data-ttu-id="53990-239">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="53990-239">This cmdlet does not accept input.</span></span>

## <span data-ttu-id="53990-240">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="53990-240">OUTPUTS</span></span>

### <span data-ttu-id="53990-241">Нет</span><span class="sxs-lookup"><span data-stu-id="53990-241">None</span></span>
<span data-ttu-id="53990-242">Этот командлет не создает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="53990-242">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="53990-243">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="53990-243">NOTES</span></span>

## <span data-ttu-id="53990-244">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="53990-244">RELATED LINKS</span></span>

[<span data-ttu-id="53990-245">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="53990-245">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="53990-246">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="53990-246">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="53990-247">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="53990-247">Remove-WmiObject</span></span>](Remove-WmiObject.md)
