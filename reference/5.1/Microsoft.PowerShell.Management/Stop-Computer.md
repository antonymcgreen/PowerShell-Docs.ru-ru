---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229793"
---
# <span data-ttu-id="bb0f8-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="bb0f8-103">Stop-Computer</span></span>

## <span data-ttu-id="bb0f8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bb0f8-104">SYNOPSIS</span></span>
<span data-ttu-id="bb0f8-105">Останавливает (завершает работу) локальный и удаленные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="bb0f8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb0f8-106">SYNTAX</span></span>

### <span data-ttu-id="bb0f8-107">Все</span><span class="sxs-lookup"><span data-stu-id="bb0f8-107">All</span></span>

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="bb0f8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bb0f8-108">DESCRIPTION</span></span>

<span data-ttu-id="bb0f8-109">`Stop-Computer`Командлет завершает работу локального компьютера и удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="bb0f8-110">Параметры можно использовать `Stop-Computer` для запуска операций завершения работы в качестве фоновых заданий, для указания уровней проверки подлинности и альтернативных учетных данных, чтобы ограничить количество параллельных подключений, создаваемых для выполнения команды, и принудительно выполнить немедленное завершение работы.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-110">You can use the parameters of `Stop-Computer` to run the shutdown operations as a background job, to specify the authentication levels and alternate credentials, to limit the concurrent connections that are created to run the command, and to force an immediate shut down.</span></span>

<span data-ttu-id="bb0f8-111">Этот командлет не требует удаленного взаимодействия PowerShell, если не используется параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="bb0f8-111">This cmdlet doesn't require PowerShell remoting unless you use the **AsJob** parameter.</span></span>

## <span data-ttu-id="bb0f8-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="bb0f8-112">EXAMPLES</span></span>

### <span data-ttu-id="bb0f8-113">Пример 1. Завершение работы локального компьютера</span><span class="sxs-lookup"><span data-stu-id="bb0f8-113">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="bb0f8-114">В этом примере завершается работа локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-114">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="bb0f8-115">Пример 2. Завершение работы двух удаленных компьютеров и локального компьютера</span><span class="sxs-lookup"><span data-stu-id="bb0f8-115">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="bb0f8-116">В этом примере останавливаются два удаленных компьютера и локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-116">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="bb0f8-117">`Stop-Computer` использует параметр **ComputerName** для указания двух удаленных компьютеров и локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-117">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="bb0f8-118">Работа каждого компьютера завершена.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-118">Each computer is shut down.</span></span>

### <span data-ttu-id="bb0f8-119">Пример 3. Завершение работы удаленных компьютеров в качестве фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="bb0f8-119">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="bb0f8-120">В этом примере `Stop-Computer` выполняется как фоновое задание на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-120">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

<span data-ttu-id="bb0f8-121">`Stop-Computer` использует параметр **ComputerName** для задания двух удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-121">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="bb0f8-122">Параметр **AsJob** выполняет команду в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-122">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="bb0f8-123">Объекты задания хранятся в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-123">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="bb0f8-124">Объекты задания в `$j` переменной отправляются по конвейеру в `Receive-Job` , который получает результаты задания.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-124">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="bb0f8-125">Объекты хранятся в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-125">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="bb0f8-126">`$results`Переменная отображает сведения о задании в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-126">The `$results` variable displays the job information in the PowerShell console.</span></span>

<span data-ttu-id="bb0f8-127">Поскольку функция **AsJob** создает задание на локальном компьютере и автоматически возвращает результаты на локальный компьютер, можно выполнить `Receive-Job` локальную команду.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-127">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

### <span data-ttu-id="bb0f8-128">Пример 4. Завершение работы удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="bb0f8-128">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="bb0f8-129">В этом примере завершается работа удаленного компьютера с использованием указанной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-129">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="bb0f8-130">`Stop-Computer` Задает удаленный компьютер с помощью параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="bb0f8-130">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="bb0f8-131">Параметр **олицетворения** задает настраиваемое олицетворение, а параметр **дкомаусентикатион** задает параметры уровня проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-131">The **Impersonation** parameter specifies a customized impersonation and the **DcomAuthentication** parameter specifies authentication-level settings.</span></span>

### <span data-ttu-id="bb0f8-132">Пример 5. Завершение работы компьютеров в домене</span><span class="sxs-lookup"><span data-stu-id="bb0f8-132">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="bb0f8-133">В этом примере команды вынуждены немедленно завершить работу всех компьютеров в указанном домене.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-133">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

<span data-ttu-id="bb0f8-134">`Get-Content` использует параметр **path** для получения файла в текущем каталоге со списком компьютеров домена.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-134">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="bb0f8-135">Объекты хранятся в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-135">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="bb0f8-136">`Get-Credential` использует параметр **Credential** для указания учетных данных администратора домена.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-136">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="bb0f8-137">Учетные данные хранятся в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-137">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="bb0f8-138">`Stop-Computer` завершает работу компьютеров, указанных в списке компьютеров с параметром **ComputerName** , в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-138">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="bb0f8-139">Параметр **Force** принудительно вызывает немедленное завершение работы.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-139">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="bb0f8-140">Параметр **ThrottleLimit** ограничивает команду до 10 одновременных подключений.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-140">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span> <span data-ttu-id="bb0f8-141">Параметр **Credential** передает учетные данные, сохраненные в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-141">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="bb0f8-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb0f8-142">PARAMETERS</span></span>

### <span data-ttu-id="bb0f8-143">-AsJob</span><span class="sxs-lookup"><span data-stu-id="bb0f8-143">-AsJob</span></span>

<span data-ttu-id="bb0f8-144">Указывает, что этот командлет выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-144">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="bb0f8-145">Чтобы использовать этот параметр, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие, а в Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="bb0f8-145">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="bb0f8-146">Дополнительные сведения см. в разделе [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb0f8-146">For more information, see [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="bb0f8-147">При указании параметра **AsJob** команда немедленно возвращает объект, представляющий фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-147">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="bb0f8-148">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-148">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="bb0f8-149">Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-149">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="bb0f8-150">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-150">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="bb0f8-151">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) и [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bb0f8-151">For more information about PowerShell background jobs, see [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) and [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span></span>

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

### <span data-ttu-id="bb0f8-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="bb0f8-152">-ComputerName</span></span>

<span data-ttu-id="bb0f8-153">Указывает компьютеры для отмены.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-153">Specifies the computers to stop.</span></span> <span data-ttu-id="bb0f8-154">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-154">The default is the local computer.</span></span>

<span data-ttu-id="bb0f8-155">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-155">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="bb0f8-156">Чтобы указать локальный компьютер, введите имя компьютера или localhost.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-156">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="bb0f8-157">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-157">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="bb0f8-158">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-158">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bb0f8-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bb0f8-159">-Confirm</span></span>

<span data-ttu-id="bb0f8-160">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bb0f8-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="bb0f8-161">-Credential</span></span>

<span data-ttu-id="bb0f8-162">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-162">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="bb0f8-163">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-163">The default is the current user.</span></span>

<span data-ttu-id="bb0f8-164">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-164">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="bb0f8-165">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-165">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="bb0f8-166">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="bb0f8-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="bb0f8-167">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="bb0f8-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bb0f8-168">-Дкомаусентикатион</span><span class="sxs-lookup"><span data-stu-id="bb0f8-168">-DcomAuthentication</span></span>

<span data-ttu-id="bb0f8-169">Указывает уровень проверки подлинности, используемый этим командлетом с WMI.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-169">Specifies the authentication level that this cmdlet uses with WMI.</span></span> <span data-ttu-id="bb0f8-170">`Stop-Computer` использует WMI.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-170">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="bb0f8-171">По умолчанию используется значение **Packet**.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-171">The default value is **Packet**.</span></span>

<span data-ttu-id="bb0f8-172">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bb0f8-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bb0f8-173">**По умолчанию** : проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-173">**Default** : Windows Authentication.</span></span>
- <span data-ttu-id="bb0f8-174">**Нет** : проверка подлинности COM отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-174">**None** : No COM authentication.</span></span>
- <span data-ttu-id="bb0f8-175">**Подключение** : проверка подлинности COM на уровне подключения.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-175">**Connect** : Connect-level COM authentication.</span></span>
- <span data-ttu-id="bb0f8-176">**Вызов** : проверка подлинности COM на уровне вызова.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-176">**Call** : Call-level COM authentication.</span></span>
- <span data-ttu-id="bb0f8-177">**Пакет** : проверка подлинности COM на уровне пакетов.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-177">**Packet** : Packet-level COM authentication.</span></span>
- <span data-ttu-id="bb0f8-178">**Паккетинтегрити** : проверка подлинности COM на уровне целостности пакетов.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-178">**PacketIntegrity** : Packet Integrity-level COM authentication.</span></span>
- <span data-ttu-id="bb0f8-179">**Паккетприваци** : проверка подлинности COM уровня конфиденциальности пакета.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-179">**PacketPrivacy** : Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="bb0f8-180">**Без изменений** : то же, что и Предыдущая команда.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-180">**Unchanged** : Same as the previous command.</span></span>

<span data-ttu-id="bb0f8-181">Дополнительные сведения о значениях этого параметра см. в разделе [аусентикатионлевел](/dotnet/api/system.management.authenticationlevel).</span><span class="sxs-lookup"><span data-stu-id="bb0f8-181">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bb0f8-182">-Force</span><span class="sxs-lookup"><span data-stu-id="bb0f8-182">-Force</span></span>

<span data-ttu-id="bb0f8-183">Принудительно выполняет немедленное завершение работы компьютера.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-183">Forces an immediate shut down of the computer.</span></span>

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

### <span data-ttu-id="bb0f8-184">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="bb0f8-184">-Impersonation</span></span>

<span data-ttu-id="bb0f8-185">Задает уровень олицетворения, используемый при вызове WMI этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-185">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="bb0f8-186">Значение по умолчанию — **impersonate**.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-186">The default value is **Impersonate**.</span></span>

<span data-ttu-id="bb0f8-187">`Stop-Computer` использует WMI.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-187">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="bb0f8-188">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bb0f8-188">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bb0f8-189">**По умолчанию** : олицетворение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-189">**Default** : Default impersonation.</span></span>
- <span data-ttu-id="bb0f8-190">**Anonymous** : скрывает удостоверение вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-190">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="bb0f8-191">**Identify** : позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-191">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="bb0f8-192">**Impersonate** : позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-192">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bb0f8-193">-Protocol</span><span class="sxs-lookup"><span data-stu-id="bb0f8-193">-Protocol</span></span>

<span data-ttu-id="bb0f8-194">Указывает, какой протокол следует использовать для перезагрузки компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-194">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="bb0f8-195">Допустимые значения для этого параметра: **WSMan** и **DCOM**.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-195">The acceptable values for this parameter are: **WSMan** and **DCOM**.</span></span> <span data-ttu-id="bb0f8-196">Значение по умолчанию — **DCOM**.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-196">The default value is **DCOM**.</span></span>

<span data-ttu-id="bb0f8-197">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-197">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bb0f8-198">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="bb0f8-198">-ThrottleLimit</span></span>

<span data-ttu-id="bb0f8-199">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-199">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="bb0f8-200">Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-200">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="bb0f8-201">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-201">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="bb0f8-202">-Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="bb0f8-202">-WsmanAuthentication</span></span>

<span data-ttu-id="bb0f8-203">Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-203">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="bb0f8-204">Значение по умолчанию ― **Default**.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-204">The default value is **Default**.</span></span>

<span data-ttu-id="bb0f8-205">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bb0f8-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bb0f8-206">Базовый</span><span class="sxs-lookup"><span data-stu-id="bb0f8-206">Basic</span></span>
- <span data-ttu-id="bb0f8-207">CredSSP</span><span class="sxs-lookup"><span data-stu-id="bb0f8-207">CredSSP</span></span>
- <span data-ttu-id="bb0f8-208">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="bb0f8-208">Default</span></span>
- <span data-ttu-id="bb0f8-209">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="bb0f8-209">Digest</span></span>
- <span data-ttu-id="bb0f8-210">Kerberos</span><span class="sxs-lookup"><span data-stu-id="bb0f8-210">Kerberos</span></span>
- <span data-ttu-id="bb0f8-211">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="bb0f8-211">Negotiate.</span></span>

<span data-ttu-id="bb0f8-212">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="bb0f8-212">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="bb0f8-213">Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-213">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="bb0f8-214">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-214">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="bb0f8-215">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-215">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="bb0f8-216">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bb0f8-217">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bb0f8-217">-WhatIf</span></span>

<span data-ttu-id="bb0f8-218">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-218">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="bb0f8-219">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-219">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="bb0f8-220">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bb0f8-220">CommonParameters</span></span>

<span data-ttu-id="bb0f8-221">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb0f8-222">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bb0f8-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb0f8-223">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bb0f8-223">INPUTS</span></span>

### <span data-ttu-id="bb0f8-224">Нет</span><span class="sxs-lookup"><span data-stu-id="bb0f8-224">None</span></span>

<span data-ttu-id="bb0f8-225">Вы не можете передать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-225">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bb0f8-226">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bb0f8-226">OUTPUTS</span></span>

### <span data-ttu-id="bb0f8-227">None или System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="bb0f8-227">None or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="bb0f8-228">Командлет возвращает объект **System. Management. Automation. ремотингжоб** , если указан параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="bb0f8-228">The cmdlet returns a **System.Management.Automation.RemotingJob** object, if you specify the **AsJob** parameter.</span></span> <span data-ttu-id="bb0f8-229">В противном случае он не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bb0f8-229">Otherwise, it doesn't generate any output.</span></span>

## <span data-ttu-id="bb0f8-230">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bb0f8-230">NOTES</span></span>

<span data-ttu-id="bb0f8-231">Этот командлет использует метод **Win32Shutdown** класса WMI **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="bb0f8-231">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="bb0f8-232">Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .</span><span class="sxs-lookup"><span data-stu-id="bb0f8-232">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="bb0f8-233">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bb0f8-233">RELATED LINKS</span></span>

[<span data-ttu-id="bb0f8-234">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="bb0f8-234">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="bb0f8-235">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="bb0f8-235">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="bb0f8-236">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="bb0f8-236">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="bb0f8-237">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="bb0f8-237">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="bb0f8-238">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="bb0f8-238">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="bb0f8-239">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="bb0f8-239">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="bb0f8-240">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="bb0f8-240">Test-Connection</span></span>](Test-Connection.md)
