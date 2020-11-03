---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: 3936fb0a68b029ca2fcacbd2ab04853fccf09f0c
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233073"
---
# <span data-ttu-id="da69c-103">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="da69c-103">New-WSManInstance</span></span>

## <span data-ttu-id="da69c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="da69c-104">SYNOPSIS</span></span>
<span data-ttu-id="da69c-105">Создает новый экземпляр ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="da69c-105">Creates a new instance of a management resource.</span></span>

## <span data-ttu-id="da69c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da69c-106">SYNTAX</span></span>

### <span data-ttu-id="da69c-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="da69c-107">ComputerName (Default)</span></span>

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="da69c-108">URI</span><span class="sxs-lookup"><span data-stu-id="da69c-108">URI</span></span>

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="da69c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="da69c-109">DESCRIPTION</span></span>

<span data-ttu-id="da69c-110">`New-WSManInstance`Командлет создает новый экземпляр ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="da69c-110">The `New-WSManInstance` cmdlet creates a new instance of a management resource.</span></span> <span data-ttu-id="da69c-111">Для создания нового экземпляра ресурса управления он использует URI ресурса и заданное значение или входной файл.</span><span class="sxs-lookup"><span data-stu-id="da69c-111">It uses a resource URI and a value set or input file to create the new instance of the management resource.</span></span>

<span data-ttu-id="da69c-112">Для создания экземпляра ресурса управления этот командлет использует соединение/транспортный уровень службы удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="da69c-112">This cmdlet uses the WinRM connection/transport layer to create the management resource instance.</span></span>

## <span data-ttu-id="da69c-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="da69c-113">EXAMPLES</span></span>

### <span data-ttu-id="da69c-114">Пример 1. Создание прослушивателя HTTPS</span><span class="sxs-lookup"><span data-stu-id="da69c-114">Example 1: Create a HTTPS listener</span></span>

<span data-ttu-id="da69c-115">Эта команда создает экземпляр прослушивателя HTTPS WS-Management для всех IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="da69c-115">This command creates an instance of a WS-Management HTTPS listener on all IP addresses.</span></span>

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## <span data-ttu-id="da69c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da69c-116">PARAMETERS</span></span>

### <span data-ttu-id="da69c-117">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="da69c-117">-ApplicationName</span></span>

<span data-ttu-id="da69c-118">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="da69c-118">Specifies the application name in the connection.</span></span> <span data-ttu-id="da69c-119">Значением параметра **applicationName** по умолчанию является **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="da69c-119">The default value of the **ApplicationName** parameter is **WSMAN** .</span></span> <span data-ttu-id="da69c-120">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="da69c-120">The complete identifier for the remote endpoint is in the following format:</span></span>

`<transport>://<server>:<port>/<ApplicationName>`

<span data-ttu-id="da69c-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="da69c-121">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="da69c-122">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="da69c-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span> <span data-ttu-id="da69c-123">Этот параметр по умолчанию **WSMan** подходит для большинства применений.</span><span class="sxs-lookup"><span data-stu-id="da69c-123">This default setting of **WSMAN** is appropriate for most uses.</span></span> <span data-ttu-id="da69c-124">Он предназначен для использования в ситуации, когда много компьютеров устанавливают удаленное подключение к одному компьютеру, на котором выполняется Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da69c-124">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span> <span data-ttu-id="da69c-125">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="da69c-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-126">-Authentication</span><span class="sxs-lookup"><span data-stu-id="da69c-126">-Authentication</span></span>

<span data-ttu-id="da69c-127">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="da69c-127">Specifies the authentication mechanism to be used at the server.</span></span> <span data-ttu-id="da69c-128">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="da69c-128">Possible values are:</span></span>

- <span data-ttu-id="da69c-129">Базовый: базовый — это схема, в которой имя пользователя и пароль отправляются открытым текстом на сервер или на прокси.</span><span class="sxs-lookup"><span data-stu-id="da69c-129">Basic: Basic is a scheme in which the username and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="da69c-130">По умолчанию: используйте метод проверки подлинности, реализованный протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="da69c-130">Default: Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="da69c-131">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da69c-131">This is the default.</span></span>
- <span data-ttu-id="da69c-132">Digest — это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="da69c-132">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="da69c-133">Kerberos: клиентский компьютер и сервер выполняют взаимную проверку подлинности с помощью сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="da69c-133">Kerberos: The client computer and the server mutually authenticate using Kerberos certificates.</span></span>
- <span data-ttu-id="da69c-134">Negotiate — это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="da69c-134">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="da69c-135">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="da69c-135">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="da69c-136">CredSSP — использование аутентификации CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="da69c-136">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="da69c-137">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="da69c-137">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

> [!CAUTION]
> <span data-ttu-id="da69c-138">CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="da69c-138">CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="da69c-139">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="da69c-139">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="da69c-140">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="da69c-140">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="da69c-141">-CertificateThumbprint</span></span>

<span data-ttu-id="da69c-142">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="da69c-142">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="da69c-143">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="da69c-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="da69c-144">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="da69c-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="da69c-145">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="da69c-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="da69c-146">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="da69c-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="da69c-147">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="da69c-147">-ComputerName</span></span>

<span data-ttu-id="da69c-148">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="da69c-148">Specifies the computer against which you want to run the management operation.</span></span> <span data-ttu-id="da69c-149">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="da69c-149">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="da69c-150">Используйте имя локального компьютера, localhost или точку ( `.` ), чтобы указать локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="da69c-150">Use the local computer name, use localhost, or use a dot (`.`) to specify the local computer.</span></span> <span data-ttu-id="da69c-151">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da69c-151">The local computer is the default.</span></span> <span data-ttu-id="da69c-152">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="da69c-152">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span> <span data-ttu-id="da69c-153">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="da69c-153">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-154">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="da69c-154">-ConnectionURI</span></span>

<span data-ttu-id="da69c-155">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="da69c-155">Specifies the connection endpoint.</span></span>
<span data-ttu-id="da69c-156">Строки имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="da69c-156">The format of this string is:</span></span>

`<Transport>://<Server>:<Port>/<ApplicationName>`

<span data-ttu-id="da69c-157">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="da69c-157">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="da69c-158">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="da69c-158">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="da69c-159">-Credential</span></span>

<span data-ttu-id="da69c-160">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="da69c-160">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="da69c-161">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="da69c-161">The default is the current user.</span></span> <span data-ttu-id="da69c-162">Введите имя пользователя, например "User01", "Domain01\User01" или " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="da69c-162">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span> <span data-ttu-id="da69c-163">Или введите объект PSCredential, например, возвращаемый `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="da69c-163">Or, enter a PSCredential object, such as one returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="da69c-164">При вводе имени пользователя появится приглашение ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="da69c-164">When you type a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-165">-FilePath</span><span class="sxs-lookup"><span data-stu-id="da69c-165">-FilePath</span></span>

<span data-ttu-id="da69c-166">Указывает путь к файлу, который используется для создания ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="da69c-166">Specifies the path of a file that is used to create a management resource.</span></span> <span data-ttu-id="da69c-167">Ресурс управления указывается с помощью параметра **resourceUri** и параметра **selector** .</span><span class="sxs-lookup"><span data-stu-id="da69c-167">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter .</span></span> <span data-ttu-id="da69c-168">Например, следующая команда использует параметр **File** :</span><span class="sxs-lookup"><span data-stu-id="da69c-168">For example, the following command uses the **File** parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

<span data-ttu-id="da69c-169">Эта команда вызывает метод **«не используется» в** службе диспетчера очереди, используя входные данные из файла.</span><span class="sxs-lookup"><span data-stu-id="da69c-169">This command calls the **StopService** method on the Spooler service using input from a file.</span></span> <span data-ttu-id="da69c-170">Файл `Input.xml` содержит следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="da69c-170">The file, `Input.xml`, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

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

### <span data-ttu-id="da69c-171">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="da69c-171">-OptionSet</span></span>

<span data-ttu-id="da69c-172">Передает набор параметров в службу, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="da69c-172">Passes a set of switches to a service to modify or refine the nature of the request.</span></span> <span data-ttu-id="da69c-173">Это похоже на ключи, используемые в оболочках командной строки, поскольку они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="da69c-173">These are similar to switches used in command-line shells because they are service specific.</span></span> <span data-ttu-id="da69c-174">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="da69c-174">Any number of options can be specified.</span></span>

<span data-ttu-id="da69c-175">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="da69c-175">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-176">-Port</span><span class="sxs-lookup"><span data-stu-id="da69c-176">-Port</span></span>

<span data-ttu-id="da69c-177">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="da69c-177">Specifies the port to use when the client connects to the WinRM service.</span></span> <span data-ttu-id="da69c-178">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="da69c-178">When the transport is HTTP, the default port is 80.</span></span> <span data-ttu-id="da69c-179">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="da69c-179">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="da69c-180">При использовании протокола HTTPS в качестве транспорта значение параметра **ComputerName** должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="da69c-180">When you use HTTPS as the transport, the value of the **ComputerName** parameter must match the server's certificate common name (CN).</span></span> <span data-ttu-id="da69c-181">Но если параметр **SkipCNCheck** указан в составе параметра **SessionOption** , то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="da69c-181">However, if the **SkipCNCheck** parameter is specified as part of the **SessionOption** parameter, the certificate common name of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="da69c-182">Параметр **SkipCNCheck** следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="da69c-182">The **SkipCNCheck** parameter should be used only for trusted computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-183">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="da69c-183">-ResourceURI</span></span>

<span data-ttu-id="da69c-184">Содержит универсальный код ресурса (URI) для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="da69c-184">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="da69c-185">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="da69c-185">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="da69c-186">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="da69c-186">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="da69c-187">Пример:</span><span class="sxs-lookup"><span data-stu-id="da69c-187">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-188">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="da69c-188">-SelectorSet</span></span>

<span data-ttu-id="da69c-189">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="da69c-189">Specifies a set of value pairs that are used to select particular management resource instances.</span></span> <span data-ttu-id="da69c-190">Параметр **selector** используется, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="da69c-190">The **SelectorSet** parameter is used when more than one instance of the resource exists.</span></span> <span data-ttu-id="da69c-191">Значение параметра набора **selector** должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="da69c-191">The value of the **SelectorSet** parameter must be a hash table.</span></span>

<span data-ttu-id="da69c-192">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="da69c-192">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-193">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="da69c-193">-SessionOption</span></span>

<span data-ttu-id="da69c-194">Определяет набор расширенных параметров для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="da69c-194">Defines a set of extended options for the WS-Management session.</span></span> <span data-ttu-id="da69c-195">Введите объект **SessionOption** , созданный с помощью `New-WSManSessionOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="da69c-195">Enter a **SessionOption** object that you create using the `New-WSManSessionOption` cmdlet.</span></span> <span data-ttu-id="da69c-196">Дополнительные сведения о доступных параметрах см. в разделе `New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="da69c-196">For more information about the options that are available, see `New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-197">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="da69c-197">-UseSSL</span></span>

<span data-ttu-id="da69c-198">Указывает, что для подключения к удаленному компьютеру следует использовать протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="da69c-198">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="da69c-199">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="da69c-199">By default, SSL is not used.</span></span>

<span data-ttu-id="da69c-200">WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="da69c-200">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="da69c-201">Параметр **UseSSL** позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="da69c-201">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="da69c-202">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="da69c-202">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-203">-Value</span><span class="sxs-lookup"><span data-stu-id="da69c-203">-ValueSet</span></span>

<span data-ttu-id="da69c-204">Указывает хэш-таблицу, помогающую изменить ресурс управления.</span><span class="sxs-lookup"><span data-stu-id="da69c-204">Specifies a hash table that helps modify a management resource.</span></span> <span data-ttu-id="da69c-205">Ресурс управления указывается с помощью параметра **resourceUri** и параметра **selector** .</span><span class="sxs-lookup"><span data-stu-id="da69c-205">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter.</span></span> <span data-ttu-id="da69c-206">Значение параметра набора **значений** должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="da69c-206">The value of the **ValueSet** parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da69c-207">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="da69c-207">CommonParameters</span></span>

<span data-ttu-id="da69c-208">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="da69c-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da69c-209">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="da69c-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="da69c-210">Входные данные</span><span class="sxs-lookup"><span data-stu-id="da69c-210">INPUTS</span></span>

### <span data-ttu-id="da69c-211">Нет</span><span class="sxs-lookup"><span data-stu-id="da69c-211">None</span></span>

<span data-ttu-id="da69c-212">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="da69c-212">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="da69c-213">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="da69c-213">OUTPUTS</span></span>

### <span data-ttu-id="da69c-214">Нет</span><span class="sxs-lookup"><span data-stu-id="da69c-214">None</span></span>

<span data-ttu-id="da69c-215">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="da69c-215">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="da69c-216">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="da69c-216">NOTES</span></span>

<span data-ttu-id="da69c-217">Командлет `Set-WmiInstance` , командлет инструментарий управления Windows (WMI) (WMI), аналогичен.</span><span class="sxs-lookup"><span data-stu-id="da69c-217">The `Set-WmiInstance` cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span>
<span data-ttu-id="da69c-218">`Set-WmiInstance` использует DCOM-соединение/транспортный уровень для создания или обновления экземпляров WMI.</span><span class="sxs-lookup"><span data-stu-id="da69c-218">`Set-WmiInstance` uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

## <span data-ttu-id="da69c-219">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="da69c-219">RELATED LINKS</span></span>

[<span data-ttu-id="da69c-220">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="da69c-220">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="da69c-221">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="da69c-221">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="da69c-222">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="da69c-222">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="da69c-223">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="da69c-223">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="da69c-224">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="da69c-224">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="da69c-225">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="da69c-225">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="da69c-226">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="da69c-226">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="da69c-227">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="da69c-227">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="da69c-228">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="da69c-228">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="da69c-229">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="da69c-229">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="da69c-230">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="da69c-230">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="da69c-231">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="da69c-231">Test-WSMan</span></span>](Test-WSMan.md)
