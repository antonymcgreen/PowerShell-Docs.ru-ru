---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: 696bce9c1a578b054e5f9a7877f2195273ab8e8b
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230025"
---
# <span data-ttu-id="b14fc-103">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b14fc-103">New-WSManInstance</span></span>

## <span data-ttu-id="b14fc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b14fc-104">SYNOPSIS</span></span>
<span data-ttu-id="b14fc-105">Создает новый экземпляр ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="b14fc-105">Creates a new instance of a management resource.</span></span>

## <span data-ttu-id="b14fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b14fc-106">SYNTAX</span></span>

### <span data-ttu-id="b14fc-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b14fc-107">ComputerName (Default)</span></span>

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="b14fc-108">URI</span><span class="sxs-lookup"><span data-stu-id="b14fc-108">URI</span></span>

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="b14fc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b14fc-109">DESCRIPTION</span></span>

<span data-ttu-id="b14fc-110">`New-WSManInstance`Командлет создает новый экземпляр ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="b14fc-110">The `New-WSManInstance` cmdlet creates a new instance of a management resource.</span></span> <span data-ttu-id="b14fc-111">Для создания нового экземпляра ресурса управления он использует URI ресурса и заданное значение или входной файл.</span><span class="sxs-lookup"><span data-stu-id="b14fc-111">It uses a resource URI and a value set or input file to create the new instance of the management resource.</span></span>

<span data-ttu-id="b14fc-112">Для создания экземпляра ресурса управления этот командлет использует соединение/транспортный уровень службы удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="b14fc-112">This cmdlet uses the WinRM connection/transport layer to create the management resource instance.</span></span>

## <span data-ttu-id="b14fc-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b14fc-113">EXAMPLES</span></span>

### <span data-ttu-id="b14fc-114">Пример 1. Создание прослушивателя HTTPS</span><span class="sxs-lookup"><span data-stu-id="b14fc-114">Example 1: Create a HTTPS listener</span></span>

<span data-ttu-id="b14fc-115">Эта команда создает экземпляр прослушивателя HTTPS WS-Management для всех IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="b14fc-115">This command creates an instance of a WS-Management HTTPS listener on all IP addresses.</span></span>

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## <span data-ttu-id="b14fc-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b14fc-116">PARAMETERS</span></span>

### <span data-ttu-id="b14fc-117">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="b14fc-117">-ApplicationName</span></span>

<span data-ttu-id="b14fc-118">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="b14fc-118">Specifies the application name in the connection.</span></span> <span data-ttu-id="b14fc-119">Значением параметра **applicationName** по умолчанию является **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="b14fc-119">The default value of the **ApplicationName** parameter is **WSMAN** .</span></span> <span data-ttu-id="b14fc-120">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="b14fc-120">The complete identifier for the remote endpoint is in the following format:</span></span>

`<transport>://<server>:<port>/<ApplicationName>`

<span data-ttu-id="b14fc-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="b14fc-121">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="b14fc-122">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="b14fc-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span> <span data-ttu-id="b14fc-123">Этот параметр по умолчанию **WSMan** подходит для большинства применений.</span><span class="sxs-lookup"><span data-stu-id="b14fc-123">This default setting of **WSMAN** is appropriate for most uses.</span></span> <span data-ttu-id="b14fc-124">Он предназначен для использования в ситуации, когда много компьютеров устанавливают удаленное подключение к одному компьютеру, на котором выполняется Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b14fc-124">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span> <span data-ttu-id="b14fc-125">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="b14fc-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="b14fc-126">-Authentication</span><span class="sxs-lookup"><span data-stu-id="b14fc-126">-Authentication</span></span>

<span data-ttu-id="b14fc-127">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="b14fc-127">Specifies the authentication mechanism to be used at the server.</span></span> <span data-ttu-id="b14fc-128">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b14fc-128">Possible values are:</span></span>

- <span data-ttu-id="b14fc-129">Базовый: базовый — это схема, в которой имя пользователя и пароль отправляются открытым текстом на сервер или на прокси.</span><span class="sxs-lookup"><span data-stu-id="b14fc-129">Basic: Basic is a scheme in which the username and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="b14fc-130">По умолчанию: используйте метод проверки подлинности, реализованный протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="b14fc-130">Default: Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="b14fc-131">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b14fc-131">This is the default.</span></span>
- <span data-ttu-id="b14fc-132">Digest — это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="b14fc-132">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="b14fc-133">Kerberos: клиентский компьютер и сервер выполняют взаимную проверку подлинности с помощью сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b14fc-133">Kerberos: The client computer and the server mutually authenticate using Kerberos certificates.</span></span>
- <span data-ttu-id="b14fc-134">Negotiate — это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="b14fc-134">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="b14fc-135">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="b14fc-135">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="b14fc-136">CredSSP — использование аутентификации CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="b14fc-136">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="b14fc-137">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="b14fc-137">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

> [!CAUTION]
> <span data-ttu-id="b14fc-138">CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b14fc-138">CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="b14fc-139">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="b14fc-139">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="b14fc-140">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="b14fc-140">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="b14fc-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="b14fc-141">-CertificateThumbprint</span></span>

<span data-ttu-id="b14fc-142">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="b14fc-142">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="b14fc-143">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="b14fc-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="b14fc-144">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="b14fc-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="b14fc-145">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="b14fc-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="b14fc-146">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="b14fc-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="b14fc-147">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b14fc-147">-ComputerName</span></span>

<span data-ttu-id="b14fc-148">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="b14fc-148">Specifies the computer against which you want to run the management operation.</span></span> <span data-ttu-id="b14fc-149">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="b14fc-149">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="b14fc-150">Используйте имя локального компьютера, localhost или точку ( `.` ), чтобы указать локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b14fc-150">Use the local computer name, use localhost, or use a dot (`.`) to specify the local computer.</span></span> <span data-ttu-id="b14fc-151">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b14fc-151">The local computer is the default.</span></span> <span data-ttu-id="b14fc-152">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="b14fc-152">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span> <span data-ttu-id="b14fc-153">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="b14fc-153">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="b14fc-154">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="b14fc-154">-ConnectionURI</span></span>

<span data-ttu-id="b14fc-155">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="b14fc-155">Specifies the connection endpoint.</span></span>
<span data-ttu-id="b14fc-156">Строки имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="b14fc-156">The format of this string is:</span></span>

`<Transport>://<Server>:<Port>/<ApplicationName>`

<span data-ttu-id="b14fc-157">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b14fc-157">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="b14fc-158">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="b14fc-158">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="b14fc-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="b14fc-159">-Credential</span></span>

<span data-ttu-id="b14fc-160">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="b14fc-160">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="b14fc-161">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="b14fc-161">The default is the current user.</span></span> <span data-ttu-id="b14fc-162">Введите имя пользователя, например "User01", "Domain01\User01" или " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="b14fc-162">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span> <span data-ttu-id="b14fc-163">Или введите объект PSCredential, например, возвращаемый `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="b14fc-163">Or, enter a PSCredential object, such as one returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b14fc-164">При вводе имени пользователя появится приглашение ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="b14fc-164">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="b14fc-165">-FilePath</span><span class="sxs-lookup"><span data-stu-id="b14fc-165">-FilePath</span></span>

<span data-ttu-id="b14fc-166">Указывает путь к файлу, который используется для создания ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="b14fc-166">Specifies the path of a file that is used to create a management resource.</span></span> <span data-ttu-id="b14fc-167">Ресурс управления указывается с помощью параметра **resourceUri** и параметра **selector** .</span><span class="sxs-lookup"><span data-stu-id="b14fc-167">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter .</span></span> <span data-ttu-id="b14fc-168">Например, следующая команда использует параметр **File** :</span><span class="sxs-lookup"><span data-stu-id="b14fc-168">For example, the following command uses the **File** parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

<span data-ttu-id="b14fc-169">Эта команда вызывает метод **«не используется» в** службе диспетчера очереди, используя входные данные из файла.</span><span class="sxs-lookup"><span data-stu-id="b14fc-169">This command calls the **StopService** method on the Spooler service using input from a file.</span></span> <span data-ttu-id="b14fc-170">Файл `Input.xml` содержит следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="b14fc-170">The file, `Input.xml`, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b14fc-171">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="b14fc-171">-OptionSet</span></span>

<span data-ttu-id="b14fc-172">Передает набор параметров в службу, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="b14fc-172">Passes a set of switches to a service to modify or refine the nature of the request.</span></span> <span data-ttu-id="b14fc-173">Это похоже на ключи, используемые в оболочках командной строки, поскольку они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="b14fc-173">These are similar to switches used in command-line shells because they are service specific.</span></span> <span data-ttu-id="b14fc-174">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="b14fc-174">Any number of options can be specified.</span></span>

<span data-ttu-id="b14fc-175">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="b14fc-175">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="b14fc-176">-Port</span><span class="sxs-lookup"><span data-stu-id="b14fc-176">-Port</span></span>

<span data-ttu-id="b14fc-177">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="b14fc-177">Specifies the port to use when the client connects to the WinRM service.</span></span> <span data-ttu-id="b14fc-178">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="b14fc-178">When the transport is HTTP, the default port is 80.</span></span> <span data-ttu-id="b14fc-179">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="b14fc-179">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="b14fc-180">При использовании протокола HTTPS в качестве транспорта значение параметра **ComputerName** должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="b14fc-180">When you use HTTPS as the transport, the value of the **ComputerName** parameter must match the server's certificate common name (CN).</span></span> <span data-ttu-id="b14fc-181">Но если параметр **SkipCNCheck** указан в составе параметра **SessionOption** , то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="b14fc-181">However, if the **SkipCNCheck** parameter is specified as part of the **SessionOption** parameter, the certificate common name of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="b14fc-182">Параметр **SkipCNCheck** следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="b14fc-182">The **SkipCNCheck** parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="b14fc-183">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="b14fc-183">-ResourceURI</span></span>

<span data-ttu-id="b14fc-184">Содержит универсальный код ресурса (URI) для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="b14fc-184">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="b14fc-185">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b14fc-185">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="b14fc-186">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b14fc-186">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="b14fc-187">Пример:</span><span class="sxs-lookup"><span data-stu-id="b14fc-187">For example:</span></span>

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

### <span data-ttu-id="b14fc-188">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="b14fc-188">-SelectorSet</span></span>

<span data-ttu-id="b14fc-189">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="b14fc-189">Specifies a set of value pairs that are used to select particular management resource instances.</span></span> <span data-ttu-id="b14fc-190">Параметр **selector** используется, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="b14fc-190">The **SelectorSet** parameter is used when more than one instance of the resource exists.</span></span> <span data-ttu-id="b14fc-191">Значение параметра набора **selector** должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="b14fc-191">The value of the **SelectorSet** parameter must be a hash table.</span></span>

<span data-ttu-id="b14fc-192">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b14fc-192">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="b14fc-193">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="b14fc-193">-SessionOption</span></span>

<span data-ttu-id="b14fc-194">Определяет набор расширенных параметров для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="b14fc-194">Defines a set of extended options for the WS-Management session.</span></span> <span data-ttu-id="b14fc-195">Введите объект **SessionOption** , созданный с помощью `New-WSManSessionOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="b14fc-195">Enter a **SessionOption** object that you create using the `New-WSManSessionOption` cmdlet.</span></span> <span data-ttu-id="b14fc-196">Дополнительные сведения о доступных параметрах см. в разделе `New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="b14fc-196">For more information about the options that are available, see `New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="b14fc-197">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="b14fc-197">-UseSSL</span></span>

<span data-ttu-id="b14fc-198">Указывает, что для подключения к удаленному компьютеру следует использовать протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="b14fc-198">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="b14fc-199">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="b14fc-199">By default, SSL is not used.</span></span>

<span data-ttu-id="b14fc-200">WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="b14fc-200">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="b14fc-201">Параметр **UseSSL** позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="b14fc-201">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="b14fc-202">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b14fc-202">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="b14fc-203">-Value</span><span class="sxs-lookup"><span data-stu-id="b14fc-203">-ValueSet</span></span>

<span data-ttu-id="b14fc-204">Указывает хэш-таблицу, помогающую изменить ресурс управления.</span><span class="sxs-lookup"><span data-stu-id="b14fc-204">Specifies a hash table that helps modify a management resource.</span></span> <span data-ttu-id="b14fc-205">Ресурс управления указывается с помощью параметра **resourceUri** и параметра **selector** .</span><span class="sxs-lookup"><span data-stu-id="b14fc-205">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter.</span></span> <span data-ttu-id="b14fc-206">Значение параметра набора **значений** должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="b14fc-206">The value of the **ValueSet** parameter must be a hash table.</span></span>

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

### <span data-ttu-id="b14fc-207">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b14fc-207">CommonParameters</span></span>

<span data-ttu-id="b14fc-208">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b14fc-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b14fc-209">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b14fc-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b14fc-210">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b14fc-210">INPUTS</span></span>

### <span data-ttu-id="b14fc-211">Нет</span><span class="sxs-lookup"><span data-stu-id="b14fc-211">None</span></span>

<span data-ttu-id="b14fc-212">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="b14fc-212">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="b14fc-213">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b14fc-213">OUTPUTS</span></span>

### <span data-ttu-id="b14fc-214">Нет</span><span class="sxs-lookup"><span data-stu-id="b14fc-214">None</span></span>

<span data-ttu-id="b14fc-215">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b14fc-215">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b14fc-216">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b14fc-216">NOTES</span></span>

<span data-ttu-id="b14fc-217">Командлет `Set-WmiInstance` , командлет инструментарий управления Windows (WMI) (WMI), аналогичен.</span><span class="sxs-lookup"><span data-stu-id="b14fc-217">The `Set-WmiInstance` cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span>
<span data-ttu-id="b14fc-218">`Set-WmiInstance` использует DCOM-соединение/транспортный уровень для создания или обновления экземпляров WMI.</span><span class="sxs-lookup"><span data-stu-id="b14fc-218">`Set-WmiInstance` uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

## <span data-ttu-id="b14fc-219">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b14fc-219">RELATED LINKS</span></span>

[<span data-ttu-id="b14fc-220">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b14fc-220">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="b14fc-221">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b14fc-221">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="b14fc-222">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b14fc-222">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="b14fc-223">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b14fc-223">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="b14fc-224">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b14fc-224">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="b14fc-225">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b14fc-225">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="b14fc-226">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b14fc-226">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="b14fc-227">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="b14fc-227">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="b14fc-228">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b14fc-228">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="b14fc-229">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b14fc-229">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="b14fc-230">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="b14fc-230">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="b14fc-231">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="b14fc-231">Test-WSMan</span></span>](Test-WSMan.md)
