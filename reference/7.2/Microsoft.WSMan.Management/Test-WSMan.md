---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/test-wsman?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WSMan
ms.openlocfilehash: a29a9ef1e35f0c0f802952b99d853c617614a97b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602838"
---
# <span data-ttu-id="62286-102">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="62286-102">Test-WSMan</span></span>

## <span data-ttu-id="62286-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="62286-103">SYNOPSIS</span></span>
<span data-ttu-id="62286-104">Проверяет, запущена ли служба удаленного управления Windows на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="62286-104">Tests whether the WinRM service is running on a local or remote computer.</span></span>

## <span data-ttu-id="62286-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="62286-105">SYNTAX</span></span>

```
Test-WSMan [[-ComputerName] <String>] [-Authentication <AuthenticationMechanism>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-Credential <PSCredential>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="62286-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="62286-106">DESCRIPTION</span></span>

<span data-ttu-id="62286-107">Командлет **Test-WSMan** отправляет запрос на идентификацию, который определяет, запущена ли служба WinRM на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="62286-107">The **Test-WSMan** cmdlet submits an identification request that determines whether the WinRM service is running on a local or remote computer.</span></span>
<span data-ttu-id="62286-108">Если на проверенном компьютере эта служба выполняется, командлет отображает схему удостоверений WS-Management, версию протокола, поставщика продукта и версию продукта протестированной службы.</span><span class="sxs-lookup"><span data-stu-id="62286-108">If the tested computer is running the service, the cmdlet displays the WS-Management identity schema, the protocol version, the product vendor, and the product version of the tested service.</span></span>

## <span data-ttu-id="62286-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="62286-109">EXAMPLES</span></span>

### <span data-ttu-id="62286-110">Пример 1. Определение состояния службы WinRM</span><span class="sxs-lookup"><span data-stu-id="62286-110">Example 1: Determine the status of the WinRM service</span></span>

```
PS C:\> Test-WSMan
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="62286-111">Эта команда определяет, выполняется ли служба удаленного управления Windows на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="62286-111">This command determines whether the WinRM service is running on the local computer or on a remote computer.</span></span>

### <span data-ttu-id="62286-112">Пример 2. Определение состояния службы WinRM на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="62286-112">Example 2: Determine the status of the WinRM service on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01"
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="62286-113">Эта команда определяет, запущена ли служба WinRM на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="62286-113">This command determines whether the WinRM service is running on the server01 computer.</span></span>

### <span data-ttu-id="62286-114">Пример 3. Определение состояния службы WinRM и версии операционной системы</span><span class="sxs-lookup"><span data-stu-id="62286-114">Example 3: Determine the status of the WinRM service and the operating system version</span></span>

```
PS C:\> Test-WSMan -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.0.6001 SP: 1.0 Stack: 2.0
```

<span data-ttu-id="62286-115">Эта команда проверяет, запущена ли служба WS-Management (WinRM) на локальном компьютере с помощью параметра Authentication.</span><span class="sxs-lookup"><span data-stu-id="62286-115">This command tests to see whether the WS-Management (WinRM) service is running on the local computer by using the authentication parameter.</span></span>

<span data-ttu-id="62286-116">Использование параметра Authentication позволяет **Test-WSMan** вернуть версию операционной системы.</span><span class="sxs-lookup"><span data-stu-id="62286-116">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

### <span data-ttu-id="62286-117">Пример 4. Определение состояния службы WinRM и версии операционной системы на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="62286-117">Example 4: Determine the status of the WinRM service and the operating system version on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01" -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.1.7021 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="62286-118">Эта команда проверяет, запущена ли служба WS-Management (WinRM) на компьютере с именем Server01, используя параметр Authentication.</span><span class="sxs-lookup"><span data-stu-id="62286-118">This command tests to see whether the WS-Management (WinRM) service is running on the computer named server01 using the authentication parameter.</span></span>

<span data-ttu-id="62286-119">Использование параметра Authentication позволяет **Test-WSMan** вернуть версию операционной системы.</span><span class="sxs-lookup"><span data-stu-id="62286-119">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

## <span data-ttu-id="62286-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="62286-120">PARAMETERS</span></span>

### <span data-ttu-id="62286-121">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="62286-121">-ApplicationName</span></span>

<span data-ttu-id="62286-122">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="62286-122">Specifies the application name in the connection.</span></span>
<span data-ttu-id="62286-123">Значением параметра *applicationName* по умолчанию является WSMan.</span><span class="sxs-lookup"><span data-stu-id="62286-123">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="62286-124">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="62286-124">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="62286-125">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="62286-125">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="62286-126">Пример: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="62286-126">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="62286-127">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="62286-127">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="62286-128">Значение по умолчанию (WSMAN) подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="62286-128">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="62286-129">Этот параметр предназначен для использования, если многие компьютеры устанавливают удаленные подключения к одному компьютеру, на котором работает PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62286-129">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="62286-130">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="62286-130">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="62286-131">-Authentication</span><span class="sxs-lookup"><span data-stu-id="62286-131">-Authentication</span></span>

<span data-ttu-id="62286-132">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="62286-132">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="62286-133">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="62286-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="62286-134">Обычные.</span><span class="sxs-lookup"><span data-stu-id="62286-134">Basic.</span></span>
<span data-ttu-id="62286-135">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="62286-135">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="62286-136">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="62286-136">Default.</span></span>
<span data-ttu-id="62286-137">использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="62286-137">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="62286-138">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="62286-138">This is the default.</span></span>
- <span data-ttu-id="62286-139">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="62286-139">Digest.</span></span>
<span data-ttu-id="62286-140">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="62286-140">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="62286-141">Kerberos —</span><span class="sxs-lookup"><span data-stu-id="62286-141">Kerberos.</span></span>
<span data-ttu-id="62286-142">клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="62286-142">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="62286-143">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="62286-143">Negotiate.</span></span>
<span data-ttu-id="62286-144">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="62286-144">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="62286-145">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="62286-145">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="62286-146">CredSSP —</span><span class="sxs-lookup"><span data-stu-id="62286-146">CredSSP.</span></span>
<span data-ttu-id="62286-147">использование проверки подлинности CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="62286-147">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="62286-148">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="62286-148">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="62286-149">Внимание! CredSSP делегирует учетные данные пользователя с локального на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="62286-149">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="62286-150">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="62286-150">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="62286-151">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="62286-151">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

<span data-ttu-id="62286-152">Важно. Если параметр *проверки подлинности* не указан, запрос на **проверку WSMan** отправляется на удаленный компьютер анонимно без использования проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="62286-152">Important: If you do not specify the *Authentication* parameter,, the **Test-WSMan** request is sent to the remote computer anonymously, without using authentication.</span></span>
<span data-ttu-id="62286-153">Если запрос сделан анонимно, он не возвращает никаких сведений, относящихся к версии операционной системы.</span><span class="sxs-lookup"><span data-stu-id="62286-153">If the request is made anonymously, it returns no information that is specific to the operating-system version.</span></span>
<span data-ttu-id="62286-154">Вместо этого командлет отображает значения NULL для версии операционной системы и уровня пакета обновления (ОС: 0.0.0 SP: 0,0).</span><span class="sxs-lookup"><span data-stu-id="62286-154">Instead, this cmdlet displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

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

### <span data-ttu-id="62286-155">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="62286-155">-CertificateThumbprint</span></span>

<span data-ttu-id="62286-156">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="62286-156">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="62286-157">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="62286-157">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="62286-158">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="62286-158">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="62286-159">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="62286-159">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="62286-160">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="62286-160">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="62286-161">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="62286-161">-ComputerName</span></span>

<span data-ttu-id="62286-162">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="62286-162">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="62286-163">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="62286-163">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="62286-164">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="62286-164">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="62286-165">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="62286-165">The local computer is the default.</span></span>
<span data-ttu-id="62286-166">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="62286-166">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="62286-167">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="62286-167">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="62286-168">-Credential</span><span class="sxs-lookup"><span data-stu-id="62286-168">-Credential</span></span>

<span data-ttu-id="62286-169">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="62286-169">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="62286-170">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="62286-170">The default is the current user.</span></span>
<span data-ttu-id="62286-171">Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="62286-171">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="62286-172">Или введите объект **PSCredential** , например, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="62286-172">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="62286-173">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="62286-173">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="62286-174">-Port</span><span class="sxs-lookup"><span data-stu-id="62286-174">-Port</span></span>

<span data-ttu-id="62286-175">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="62286-175">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="62286-176">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="62286-176">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="62286-177">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="62286-177">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="62286-178">При использовании протокола HTTPS в качестве транспорта значение параметра *ComputerName* должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="62286-178">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>

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

### <span data-ttu-id="62286-179">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="62286-179">-UseSSL</span></span>

<span data-ttu-id="62286-180">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="62286-180">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="62286-181">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="62286-181">By default, SSL is not used.</span></span>

<span data-ttu-id="62286-182">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="62286-182">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="62286-183">Параметр *UseSSL* позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="62286-183">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="62286-184">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="62286-184">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="62286-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="62286-185">CommonParameters</span></span>

<span data-ttu-id="62286-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="62286-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="62286-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="62286-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="62286-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="62286-188">INPUTS</span></span>

### <span data-ttu-id="62286-189">None</span><span class="sxs-lookup"><span data-stu-id="62286-189">None</span></span>

<span data-ttu-id="62286-190">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="62286-190">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="62286-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="62286-191">OUTPUTS</span></span>

### <span data-ttu-id="62286-192">None</span><span class="sxs-lookup"><span data-stu-id="62286-192">None</span></span>

<span data-ttu-id="62286-193">Этот командлет не формирует никакого выходного объекта.</span><span class="sxs-lookup"><span data-stu-id="62286-193">This cmdlet does not generate any output object.</span></span>

## <span data-ttu-id="62286-194">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="62286-194">NOTES</span></span>

* <span data-ttu-id="62286-195">По умолчанию командлет **Test-WSMan** запрашивает службу WinRM без использования проверки подлинности и не возвращает сведений, относящихся к версии операционной системы.</span><span class="sxs-lookup"><span data-stu-id="62286-195">By default, the **Test-WSMan** cmdlet queries the WinRM service without using authentication, and it returns no information that is specific to the operating-system version.</span></span> <span data-ttu-id="62286-196">Вместо этого в нем отображаются значения NULL для версии операционной системы и уровня пакета обновления (ОС: 0.0.0 SP: 0,0).</span><span class="sxs-lookup"><span data-stu-id="62286-196">Instead, it displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

*

## <span data-ttu-id="62286-197">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="62286-197">RELATED LINKS</span></span>

[<span data-ttu-id="62286-198">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="62286-198">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="62286-199">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="62286-199">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="62286-200">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="62286-200">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="62286-201">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="62286-201">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="62286-202">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="62286-202">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="62286-203">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="62286-203">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="62286-204">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="62286-204">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="62286-205">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="62286-205">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="62286-206">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="62286-206">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="62286-207">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="62286-207">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="62286-208">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="62286-208">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="62286-209">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="62286-209">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

