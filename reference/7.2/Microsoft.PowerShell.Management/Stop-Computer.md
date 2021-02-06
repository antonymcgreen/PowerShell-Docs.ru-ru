---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: f6d31980e27b73e884b46168606ab8255a64efb9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600462"
---
# <span data-ttu-id="b9ba1-102">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="b9ba1-102">Stop-Computer</span></span>

## <span data-ttu-id="b9ba1-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b9ba1-103">SYNOPSIS</span></span>
<span data-ttu-id="b9ba1-104">Останавливает (завершает работу) локальный и удаленные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-104">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="b9ba1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9ba1-105">SYNTAX</span></span>

### <span data-ttu-id="b9ba1-106">Все</span><span class="sxs-lookup"><span data-stu-id="b9ba1-106">All</span></span>

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b9ba1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9ba1-107">DESCRIPTION</span></span>

<span data-ttu-id="b9ba1-108">`Stop-Computer`Командлет завершает работу локального компьютера и удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-108">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="b9ba1-109">С помощью параметров можно `Stop-Computer` указать уровни проверки подлинности и альтернативные учетные данные, а также принудительно выполнить немедленное завершение работы.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-109">You can use the parameters of `Stop-Computer` to specify the authentication levels and alternate credentials, and to force an immediate shut down.</span></span>

<span data-ttu-id="b9ba1-110">В PowerShell 7,1 `Stop-Computer` был добавлен для Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-110">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="b9ba1-111">Параметры не влияют на эти платформы.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-111">The parameters have no effect on these platforms.</span></span> <span data-ttu-id="b9ba1-112">Командлет просто вызывает машинную команду `/sbin/shutdown` .</span><span class="sxs-lookup"><span data-stu-id="b9ba1-112">The cmdlet is just calling the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="b9ba1-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b9ba1-113">EXAMPLES</span></span>

### <span data-ttu-id="b9ba1-114">Пример 1. Завершение работы локального компьютера</span><span class="sxs-lookup"><span data-stu-id="b9ba1-114">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="b9ba1-115">В этом примере завершается работа локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-115">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="b9ba1-116">Пример 2. Завершение работы двух удаленных компьютеров и локального компьютера</span><span class="sxs-lookup"><span data-stu-id="b9ba1-116">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="b9ba1-117">В этом примере останавливаются два удаленных компьютера и локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-117">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="b9ba1-118">`Stop-Computer` использует параметр **ComputerName** для указания двух удаленных компьютеров и локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-118">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="b9ba1-119">Работа каждого компьютера завершена.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-119">Each computer is shut down.</span></span>

### <span data-ttu-id="b9ba1-120">Пример 3. Завершение работы удаленных компьютеров в качестве фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="b9ba1-120">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="b9ba1-121">В этом примере `Stop-Computer` выполняется как фоновое задание на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-121">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

<span data-ttu-id="b9ba1-122">Оператор Background `&` выполняет `Stop-Computer` команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-122">The background operator `&` runs the `Stop-Computer` command as a background job.</span></span> <span data-ttu-id="b9ba1-123">Дополнительные сведения см. в разделе [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="b9ba1-123">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

<span data-ttu-id="b9ba1-124">`Stop-Computer` использует параметр **ComputerName** для задания двух удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-124">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="b9ba1-125">`&`Оператор Background выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-125">The `&` background operator runs the command as a background job.</span></span> <span data-ttu-id="b9ba1-126">Объекты задания хранятся в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-126">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="b9ba1-127">Объекты задания в `$j` переменной отправляются по конвейеру в `Receive-Job` , который получает результаты задания.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-127">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="b9ba1-128">Объекты хранятся в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-128">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="b9ba1-129">`$results`Переменная отображает сведения о задании в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-129">The `$results` variable displays the job information in the PowerShell console.</span></span>

### <span data-ttu-id="b9ba1-130">Пример 4. Завершение работы удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="b9ba1-130">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="b9ba1-131">В этом примере завершается работа удаленного компьютера с использованием указанной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-131">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

<span data-ttu-id="b9ba1-132">`Stop-Computer` Задает удаленный компьютер с помощью параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="b9ba1-132">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="b9ba1-133">Параметр **всманаусентикатион** указывает, что для установления удаленного подключения используется протокол Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-133">The **WsmanAuthentication** parameter specifies to use Kerberos to establish a remote connection.</span></span>

### <span data-ttu-id="b9ba1-134">Пример 5. Завершение работы компьютеров в домене</span><span class="sxs-lookup"><span data-stu-id="b9ba1-134">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="b9ba1-135">В этом примере команды вынуждены немедленно завершить работу всех компьютеров в указанном домене.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-135">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

<span data-ttu-id="b9ba1-136">`Get-Content` использует параметр **path** для получения файла в текущем каталоге со списком компьютеров домена.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-136">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="b9ba1-137">Объекты хранятся в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-137">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="b9ba1-138">`Get-Credential` использует параметр **Credential** для указания учетных данных администратора домена.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-138">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="b9ba1-139">Учетные данные хранятся в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-139">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="b9ba1-140">`Stop-Computer` завершает работу компьютеров, указанных в списке компьютеров с параметром **ComputerName** , в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-140">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="b9ba1-141">Параметр **Force** принудительно вызывает немедленное завершение работы.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-141">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="b9ba1-142">Параметр **Credential** передает учетные данные, сохраненные в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-142">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="b9ba1-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9ba1-143">PARAMETERS</span></span>

### <span data-ttu-id="b9ba1-144">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b9ba1-144">-ComputerName</span></span>

<span data-ttu-id="b9ba1-145">Указывает компьютеры для отмены.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-145">Specifies the computers to stop.</span></span> <span data-ttu-id="b9ba1-146">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-146">The default is the local computer.</span></span>

<span data-ttu-id="b9ba1-147">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-147">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="b9ba1-148">Чтобы указать локальный компьютер, введите имя компьютера или localhost.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-148">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="b9ba1-149">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-149">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="b9ba1-150">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-150">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

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

### <span data-ttu-id="b9ba1-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b9ba1-151">-Confirm</span></span>

<span data-ttu-id="b9ba1-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b9ba1-153">-Credential</span><span class="sxs-lookup"><span data-stu-id="b9ba1-153">-Credential</span></span>

<span data-ttu-id="b9ba1-154">Указывает учетную запись пользователя, имеющую разрешение на это действие.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-154">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="b9ba1-155">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-155">The default is the current user.</span></span>

<span data-ttu-id="b9ba1-156">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-156">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b9ba1-157">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-157">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="b9ba1-158">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="b9ba1-158">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="b9ba1-159">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="b9ba1-159">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="b9ba1-160">-Force</span><span class="sxs-lookup"><span data-stu-id="b9ba1-160">-Force</span></span>

<span data-ttu-id="b9ba1-161">Принудительно выполняет немедленное завершение работы компьютера.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-161">Forces an immediate shut down of the computer.</span></span>

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

### <span data-ttu-id="b9ba1-162">-Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="b9ba1-162">-WsmanAuthentication</span></span>

<span data-ttu-id="b9ba1-163">Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-163">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="b9ba1-164">Значение по умолчанию ― **Default**.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-164">The default value is **Default**.</span></span>

<span data-ttu-id="b9ba1-165">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b9ba1-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b9ba1-166">Basic</span><span class="sxs-lookup"><span data-stu-id="b9ba1-166">Basic</span></span>
- <span data-ttu-id="b9ba1-167">CredSSP</span><span class="sxs-lookup"><span data-stu-id="b9ba1-167">CredSSP</span></span>
- <span data-ttu-id="b9ba1-168">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b9ba1-168">Default</span></span>
- <span data-ttu-id="b9ba1-169">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="b9ba1-169">Digest</span></span>
- <span data-ttu-id="b9ba1-170">Kerberos</span><span class="sxs-lookup"><span data-stu-id="b9ba1-170">Kerberos</span></span>
- <span data-ttu-id="b9ba1-171">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="b9ba1-171">Negotiate.</span></span>

<span data-ttu-id="b9ba1-172">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="b9ba1-172">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="b9ba1-173">Проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-173">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="b9ba1-174">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-174">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="b9ba1-175">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-175">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="b9ba1-176">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-176">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b9ba1-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b9ba1-177">-WhatIf</span></span>

<span data-ttu-id="b9ba1-178">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b9ba1-179">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-179">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="b9ba1-180">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b9ba1-180">CommonParameters</span></span>

<span data-ttu-id="b9ba1-181">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9ba1-182">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9ba1-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9ba1-183">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b9ba1-183">INPUTS</span></span>

### <span data-ttu-id="b9ba1-184">None</span><span class="sxs-lookup"><span data-stu-id="b9ba1-184">None</span></span>

<span data-ttu-id="b9ba1-185">Вы не можете передать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-185">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b9ba1-186">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b9ba1-186">OUTPUTS</span></span>

### <span data-ttu-id="b9ba1-187">None</span><span class="sxs-lookup"><span data-stu-id="b9ba1-187">None</span></span>

## <span data-ttu-id="b9ba1-188">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b9ba1-188">NOTES</span></span>

<span data-ttu-id="b9ba1-189">Этот командлет использует метод **Win32Shutdown** класса WMI **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="b9ba1-189">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="b9ba1-190">Для этого метода требуется, чтобы для учетной записи пользователя, используемой для перезагрузки компьютера, была включена привилегия **сешутдовнпривилеже** .</span><span class="sxs-lookup"><span data-stu-id="b9ba1-190">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="b9ba1-191">В PowerShell 7,1 `Stop-Computer` был добавлен для Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="b9ba1-191">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="b9ba1-192">Для этих платформ командлет вызывает собственную команду `/sbin/shutdown` .</span><span class="sxs-lookup"><span data-stu-id="b9ba1-192">For these platorms, the cmdlet calls the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="b9ba1-193">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b9ba1-193">RELATED LINKS</span></span>

[<span data-ttu-id="b9ba1-194">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="b9ba1-194">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="b9ba1-195">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="b9ba1-195">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="b9ba1-196">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="b9ba1-196">Test-Connection</span></span>](Test-Connection.md)

