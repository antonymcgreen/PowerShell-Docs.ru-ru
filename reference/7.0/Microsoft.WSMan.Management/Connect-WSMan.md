---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: e22aeef7dbc7ef799127def2606a15fdccbfffe3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226178"
---
# <span data-ttu-id="c818f-103">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="c818f-103">Connect-WSMan</span></span>

## <span data-ttu-id="c818f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c818f-104">SYNOPSIS</span></span>
<span data-ttu-id="c818f-105">Подключается к службе удаленного управления Windows на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c818f-105">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="c818f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c818f-106">SYNTAX</span></span>

### <span data-ttu-id="c818f-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c818f-107">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="c818f-108">URI</span><span class="sxs-lookup"><span data-stu-id="c818f-108">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="c818f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c818f-109">DESCRIPTION</span></span>
<span data-ttu-id="c818f-110">Командлет **Connect-WSMan** подключается к службе WinRM на удаленном компьютере и устанавливает постоянное подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="c818f-110">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="c818f-111">Этот командлет можно использовать в контексте поставщика WSMan для подключения к службе WinRM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c818f-111">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="c818f-112">Однако его также можно использовать для подключения к службе удаленного управления Windows на удаленном компьютере перед изменением поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="c818f-112">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="c818f-113">Удаленный компьютер появится в корневом каталоге поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="c818f-113">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="c818f-114">Если клиентский и серверный компьютеры находятся в разных доменах или рабочих группах, необходимы явные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c818f-114">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="c818f-115">Сведения о том, как отключиться от службы WinRM на удаленном компьютере, см. в описании командлета Disconnect-WSMan.</span><span class="sxs-lookup"><span data-stu-id="c818f-115">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="c818f-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="c818f-116">EXAMPLES</span></span>

### <span data-ttu-id="c818f-117">Пример 1. подключение к удаленному компьютеру</span><span class="sxs-lookup"><span data-stu-id="c818f-117">Example 1: Connect to a remote computer</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01"
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c818f-118">Эта команда создает подключение к удаленному компьютеру server01.</span><span class="sxs-lookup"><span data-stu-id="c818f-118">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="c818f-119">Командлет **Connect-WSMan** обычно используется в контексте поставщика WSMan для подключения к удаленному компьютеру (в данном случае это компьютер Server01).</span><span class="sxs-lookup"><span data-stu-id="c818f-119">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="c818f-120">Однако этот командлет можно использовать для установки соединения с удаленными компьютерами перед изменением поставщика WSMan.</span><span class="sxs-lookup"><span data-stu-id="c818f-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="c818f-121">Эти подключения отображаются в списке **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="c818f-121">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="c818f-122">Пример 2. подключение к удаленному компьютеру с помощью учетных данных администратора</span><span class="sxs-lookup"><span data-stu-id="c818f-122">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

```
PS C:\> $cred = Get-Credential Administrator
PS C:\> Connect-WSMan -ComputerName "server01" -Credential $cred
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c818f-123">Эта команда создает подключение к удаленной системе server01 с использованием учетных данных учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="c818f-123">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="c818f-124">Первая команда использует командлет Get-Credential, чтобы получить учетные данные администратора, и сохраняет их в переменной $cred.</span><span class="sxs-lookup"><span data-stu-id="c818f-124">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="c818f-125">**Get-Credential** запрашивает пароль пользователя и пароль в диалоговом окне или в командной строке в зависимости от параметров системного реестра.</span><span class="sxs-lookup"><span data-stu-id="c818f-125">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="c818f-126">Вторая команда использует параметр *Credential* для передачи учетных данных, хранящихся в $CRED, в **Connect-WSMan**.</span><span class="sxs-lookup"><span data-stu-id="c818f-126">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan**.</span></span>
<span data-ttu-id="c818f-127">**Connect-WSMan** подключается к удаленной системе Server01 с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="c818f-127">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="c818f-128">Пример 3. подключение к удаленному компьютеру через указанный порт</span><span class="sxs-lookup"><span data-stu-id="c818f-128">Example 3: Connect to a remote computer over a specified port</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01" -Port 80
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c818f-129">Эта команда создает подключение к удаленному компьютеру server01 через порт 80.</span><span class="sxs-lookup"><span data-stu-id="c818f-129">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="c818f-130">Пример 4. подключение к удаленному компьютеру с помощью параметров подключения</span><span class="sxs-lookup"><span data-stu-id="c818f-130">Example 4: Connect to a remote computer by using connection options</span></span>

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c818f-131">В этом примере создается подключение к удаленному компьютеру Server01 с помощью параметров соединения, определенных в команде **New-WSManSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="c818f-131">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="c818f-132">Первая команда использует **New-WSManSessionOption** для хранения набора параметров подключения в переменной $a.</span><span class="sxs-lookup"><span data-stu-id="c818f-132">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="c818f-133">В этом случае для параметров сеанса задано время ожидания подключения в размере 30 секунд (30 000 миллисекунд).</span><span class="sxs-lookup"><span data-stu-id="c818f-133">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="c818f-134">Вторая команда использует параметр *SessionOption* для передачи учетных данных, хранящихся в переменной $a, в **Connect-WSMan**.</span><span class="sxs-lookup"><span data-stu-id="c818f-134">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="c818f-135">Затем **Connect-WSMan** подключается к удаленному компьютеру Server01, используя указанные параметры сеанса.</span><span class="sxs-lookup"><span data-stu-id="c818f-135">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="c818f-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c818f-136">PARAMETERS</span></span>

### <span data-ttu-id="c818f-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="c818f-137">-ApplicationName</span></span>
<span data-ttu-id="c818f-138">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="c818f-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="c818f-139">Значением параметра *applicationName* по умолчанию является WSMan.</span><span class="sxs-lookup"><span data-stu-id="c818f-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="c818f-140">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="c818f-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="c818f-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="c818f-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="c818f-142">Пример: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="c818f-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="c818f-143">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="c818f-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="c818f-144">Значение по умолчанию (WSMAN) подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="c818f-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="c818f-145">Этот параметр предназначен для использования, если многие компьютеры устанавливают удаленные подключения к одному компьютеру, на котором работает PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c818f-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="c818f-146">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="c818f-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c818f-147">-Authentication</span><span class="sxs-lookup"><span data-stu-id="c818f-147">-Authentication</span></span>
<span data-ttu-id="c818f-148">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="c818f-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="c818f-149">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="c818f-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c818f-150">Обычные.</span><span class="sxs-lookup"><span data-stu-id="c818f-150">Basic.</span></span>
<span data-ttu-id="c818f-151">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="c818f-151">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="c818f-152">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c818f-152">Default.</span></span>
<span data-ttu-id="c818f-153">использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c818f-153">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="c818f-154">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c818f-154">This is the default.</span></span>
- <span data-ttu-id="c818f-155">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="c818f-155">Digest.</span></span>
<span data-ttu-id="c818f-156">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="c818f-156">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="c818f-157">Kerberos —</span><span class="sxs-lookup"><span data-stu-id="c818f-157">Kerberos.</span></span>
<span data-ttu-id="c818f-158">клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c818f-158">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="c818f-159">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="c818f-159">Negotiate.</span></span>
<span data-ttu-id="c818f-160">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="c818f-160">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="c818f-161">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="c818f-161">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="c818f-162">CredSSP —</span><span class="sxs-lookup"><span data-stu-id="c818f-162">CredSSP.</span></span>
<span data-ttu-id="c818f-163">использование проверки подлинности CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c818f-163">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="c818f-164">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="c818f-164">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="c818f-165">Внимание! CredSSP делегирует учетные данные пользователя с локального на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="c818f-165">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="c818f-166">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="c818f-166">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="c818f-167">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="c818f-167">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="c818f-168">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="c818f-168">-CertificateThumbprint</span></span>
<span data-ttu-id="c818f-169">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="c818f-169">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="c818f-170">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="c818f-170">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="c818f-171">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="c818f-171">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="c818f-172">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="c818f-172">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="c818f-173">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="c818f-173">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="c818f-174">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c818f-174">-ComputerName</span></span>
<span data-ttu-id="c818f-175">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="c818f-175">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="c818f-176">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="c818f-176">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="c818f-177">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="c818f-177">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="c818f-178">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c818f-178">The local computer is the default.</span></span>
<span data-ttu-id="c818f-179">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="c818f-179">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="c818f-180">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="c818f-180">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c818f-181">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="c818f-181">-ConnectionURI</span></span>
<span data-ttu-id="c818f-182">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="c818f-182">Specifies the connection endpoint.</span></span>
<span data-ttu-id="c818f-183">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="c818f-183">The format of this string is as follows:</span></span>

<span data-ttu-id="c818f-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="c818f-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="c818f-185">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="c818f-185">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="c818f-186">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="c818f-186">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c818f-187">-Credential</span><span class="sxs-lookup"><span data-stu-id="c818f-187">-Credential</span></span>
<span data-ttu-id="c818f-188">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="c818f-188">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="c818f-189">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="c818f-189">The default is the current user.</span></span>
<span data-ttu-id="c818f-190">Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="c818f-190">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="c818f-191">Или введите объект **PSCredential** , например, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="c818f-191">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="c818f-192">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="c818f-192">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="c818f-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="c818f-193">-OptionSet</span></span>
<span data-ttu-id="c818f-194">Указывает набор параметров в службе, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="c818f-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="c818f-195">Это похоже на ключи, используемые в оболочках командной строки, так как они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="c818f-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="c818f-196">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="c818f-196">Any number of options can be specified.</span></span>

<span data-ttu-id="c818f-197">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="c818f-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="c818f-198">-Port</span><span class="sxs-lookup"><span data-stu-id="c818f-198">-Port</span></span>
<span data-ttu-id="c818f-199">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="c818f-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="c818f-200">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="c818f-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="c818f-201">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="c818f-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="c818f-202">При использовании протокола HTTPS в качестве транспорта значение параметра *ComputerName* должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="c818f-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="c818f-203">Но если параметр *SkipCNCheck* указан в составе параметра *SessionOption* , то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="c818f-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="c818f-204">Параметр *SkipCNCheck* следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="c818f-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="c818f-205">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="c818f-205">-SessionOption</span></span>
<span data-ttu-id="c818f-206">Определяет расширенные параметры для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c818f-206">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="c818f-207">Введите объект **SessionOption** , созданный с помощью командлета New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="c818f-207">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="c818f-208">Чтобы получить дополнительные сведения о доступных параметрах, введите `Get-Help New-WSManSessionOption`.</span><span class="sxs-lookup"><span data-stu-id="c818f-208">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="c818f-209">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="c818f-209">-UseSSL</span></span>
<span data-ttu-id="c818f-210">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="c818f-210">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="c818f-211">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="c818f-211">By default, SSL is not used.</span></span>

<span data-ttu-id="c818f-212">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="c818f-212">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="c818f-213">Параметр *UseSSL* позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="c818f-213">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="c818f-214">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c818f-214">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="c818f-215">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c818f-215">CommonParameters</span></span>
<span data-ttu-id="c818f-216">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c818f-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c818f-217">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c818f-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c818f-218">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c818f-218">INPUTS</span></span>

### <span data-ttu-id="c818f-219">Нет</span><span class="sxs-lookup"><span data-stu-id="c818f-219">None</span></span>
<span data-ttu-id="c818f-220">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="c818f-220">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="c818f-221">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c818f-221">OUTPUTS</span></span>

### <span data-ttu-id="c818f-222">Нет</span><span class="sxs-lookup"><span data-stu-id="c818f-222">None</span></span>
<span data-ttu-id="c818f-223">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c818f-223">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c818f-224">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c818f-224">NOTES</span></span>

* <span data-ttu-id="c818f-225">Вы можете выполнять команды управления или запрашивать данные управления на удаленном компьютере без создания сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c818f-225">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="c818f-226">Это можно сделать с помощью параметров *ComputerName* в Invoke-WSManAction и Get-WSManInstance.</span><span class="sxs-lookup"><span data-stu-id="c818f-226">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="c818f-227">При использовании параметра *ComputerName* PowerShell создает временное подключение, используемое для одной команды.</span><span class="sxs-lookup"><span data-stu-id="c818f-227">When you use the *ComputerName* parameter, PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="c818f-228">После выполнения команды соединение закрывается.</span><span class="sxs-lookup"><span data-stu-id="c818f-228">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="c818f-229">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c818f-229">RELATED LINKS</span></span>

[<span data-ttu-id="c818f-230">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c818f-230">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="c818f-231">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="c818f-231">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="c818f-232">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c818f-232">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="c818f-233">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c818f-233">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="c818f-234">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c818f-234">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="c818f-235">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="c818f-235">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="c818f-236">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c818f-236">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="c818f-237">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="c818f-237">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="c818f-238">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c818f-238">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="c818f-239">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c818f-239">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="c818f-240">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="c818f-240">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="c818f-241">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="c818f-241">Test-WSMan</span></span>](Test-WSMan.md)
