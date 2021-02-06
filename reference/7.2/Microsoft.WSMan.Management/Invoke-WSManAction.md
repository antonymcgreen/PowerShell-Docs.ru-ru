---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: e2456e1da866929d60c36cc0e09990399b41614b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602079"
---
# <span data-ttu-id="90f45-102">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="90f45-102">Invoke-WSManAction</span></span>

## <span data-ttu-id="90f45-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="90f45-103">SYNOPSIS</span></span>
<span data-ttu-id="90f45-104">Вызывает действие для объекта, указанного в URI ресурса и селекторах.</span><span class="sxs-lookup"><span data-stu-id="90f45-104">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="90f45-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90f45-105">SYNTAX</span></span>

### <span data-ttu-id="90f45-106">URI (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="90f45-106">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="90f45-107">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="90f45-107">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="90f45-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="90f45-108">DESCRIPTION</span></span>
<span data-ttu-id="90f45-109">**Командлет Invoke-WSManAction** выполняет действие с объектом, указанным в RESOURCE_URI, где параметры задаются парами "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="90f45-109">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="90f45-110">Для выполнения действия этот командлет использует соединение/транспортный уровень WS-Management.</span><span class="sxs-lookup"><span data-stu-id="90f45-110">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="90f45-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="90f45-111">EXAMPLES</span></span>

### <span data-ttu-id="90f45-112">Пример 1. вызов метода</span><span class="sxs-lookup"><span data-stu-id="90f45-112">Example 1: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="90f45-113">Эта команда вызывает метод **StartService** экземпляра класса WMI Win32_Service, который соответствует службе диспетчера очереди печати.</span><span class="sxs-lookup"><span data-stu-id="90f45-113">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="90f45-114">Возвращаемое значение указывает, было ли действие успешным.</span><span class="sxs-lookup"><span data-stu-id="90f45-114">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="90f45-115">В данном случае возвращаемое значение 0 указывает на успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="90f45-115">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="90f45-116">Возвращаемое значение 5 указывает на то, что служба уже запущена.</span><span class="sxs-lookup"><span data-stu-id="90f45-116">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="90f45-117">Пример 2. вызов метода</span><span class="sxs-lookup"><span data-stu-id="90f45-117">Example 2: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action stopservice -ResourceURI wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:input.xml -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="90f45-118">Эта команда вызывает метод **«не используется» в** службе диспетчера очереди, используя входные данные из файла.</span><span class="sxs-lookup"><span data-stu-id="90f45-118">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="90f45-119">Файл Input.xml содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="90f45-119">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="90f45-120">Пример 3. вызов метода с указанными значениями параметров</span><span class="sxs-lookup"><span data-stu-id="90f45-120">Example 3: Invoke a method with specified parameter values</span></span>

```powershell
Invoke-WSManAction -Action create -ResourceURI wmicimv2/win32_process -ValueSet @{commandline="notepad.exe";currentdirectory="C:\"}
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Process
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ProcessId   : 6356
ReturnValue : 0
```

<span data-ttu-id="90f45-121">Эта команда вызывает метод **CREATE** класса Win32_Process.</span><span class="sxs-lookup"><span data-stu-id="90f45-121">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="90f45-122">Он передает методу два значения параметров: Notepad.exe и C:\..</span><span class="sxs-lookup"><span data-stu-id="90f45-122">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="90f45-123">В результате создается новый процесс для запуска Блокнота, а текущим каталогом нового процесса присваивается значение C:\.</span><span class="sxs-lookup"><span data-stu-id="90f45-123">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="90f45-124">Пример 4. вызов метода на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="90f45-124">Example 4: Invoke a method on a remote computer</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -ComputerName server01 -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="90f45-125">Эта команда вызывает метод **StartService** экземпляра класса WMI Win32_Service, который соответствует службе диспетчера очереди печати.</span><span class="sxs-lookup"><span data-stu-id="90f45-125">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="90f45-126">Так как указан параметр *ComputerName* , команда выполняется на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="90f45-126">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="90f45-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90f45-127">PARAMETERS</span></span>

### <span data-ttu-id="90f45-128">-Action</span><span class="sxs-lookup"><span data-stu-id="90f45-128">-Action</span></span>
<span data-ttu-id="90f45-129">Задает метод для выполнения в объекте управления, указанном ResourceURI и селекторами.</span><span class="sxs-lookup"><span data-stu-id="90f45-129">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="90f45-130">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="90f45-130">-ApplicationName</span></span>
<span data-ttu-id="90f45-131">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="90f45-131">Specifies the application name in the connection.</span></span>
<span data-ttu-id="90f45-132">Значением параметра *applicationName* по умолчанию является WSMan.</span><span class="sxs-lookup"><span data-stu-id="90f45-132">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="90f45-133">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="90f45-133">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="90f45-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="90f45-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="90f45-135">Пример: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="90f45-135">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="90f45-136">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="90f45-136">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="90f45-137">Значение по умолчанию (WSMAN) подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="90f45-137">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="90f45-138">Этот параметр предназначен для использования, если многие компьютеры устанавливают удаленные подключения к одному компьютеру, на котором работает PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90f45-138">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="90f45-139">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="90f45-139">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="90f45-140">-Authentication</span><span class="sxs-lookup"><span data-stu-id="90f45-140">-Authentication</span></span>
<span data-ttu-id="90f45-141">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="90f45-141">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="90f45-142">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="90f45-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="90f45-143">Обычные.</span><span class="sxs-lookup"><span data-stu-id="90f45-143">Basic.</span></span>
<span data-ttu-id="90f45-144">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="90f45-144">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="90f45-145">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90f45-145">Default.</span></span>
<span data-ttu-id="90f45-146">использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="90f45-146">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="90f45-147">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90f45-147">This is the default.</span></span>
- <span data-ttu-id="90f45-148">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="90f45-148">Digest.</span></span>
<span data-ttu-id="90f45-149">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="90f45-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="90f45-150">Kerberos —</span><span class="sxs-lookup"><span data-stu-id="90f45-150">Kerberos.</span></span>
<span data-ttu-id="90f45-151">клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="90f45-151">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="90f45-152">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="90f45-152">Negotiate.</span></span>
<span data-ttu-id="90f45-153">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="90f45-153">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="90f45-154">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="90f45-154">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="90f45-155">CredSSP —</span><span class="sxs-lookup"><span data-stu-id="90f45-155">CredSSP.</span></span>
<span data-ttu-id="90f45-156">использование проверки подлинности CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="90f45-156">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="90f45-157">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="90f45-157">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="90f45-158">Внимание! CredSSP делегирует учетные данные пользователя с локального на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="90f45-158">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="90f45-159">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="90f45-159">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="90f45-160">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="90f45-160">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="90f45-161">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="90f45-161">-CertificateThumbprint</span></span>
<span data-ttu-id="90f45-162">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="90f45-162">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="90f45-163">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="90f45-163">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="90f45-164">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="90f45-164">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="90f45-165">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="90f45-165">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="90f45-166">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="90f45-166">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="90f45-167">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="90f45-167">-ComputerName</span></span>
<span data-ttu-id="90f45-168">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="90f45-168">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="90f45-169">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="90f45-169">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="90f45-170">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="90f45-170">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="90f45-171">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90f45-171">The local computer is the default.</span></span>
<span data-ttu-id="90f45-172">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="90f45-172">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="90f45-173">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="90f45-173">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90f45-174">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="90f45-174">-ConnectionURI</span></span>
<span data-ttu-id="90f45-175">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="90f45-175">Specifies the connection endpoint.</span></span>
<span data-ttu-id="90f45-176">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="90f45-176">The format of this string is as follows:</span></span>

<span data-ttu-id="90f45-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="90f45-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="90f45-178">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="90f45-178">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="90f45-179">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="90f45-179">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="90f45-180">-Credential</span><span class="sxs-lookup"><span data-stu-id="90f45-180">-Credential</span></span>
<span data-ttu-id="90f45-181">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="90f45-181">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="90f45-182">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="90f45-182">The default is the current user.</span></span>
<span data-ttu-id="90f45-183">Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="90f45-183">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="90f45-184">Или введите объект **PSCredential** , например, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="90f45-184">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="90f45-185">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="90f45-185">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="90f45-186">-FilePath</span><span class="sxs-lookup"><span data-stu-id="90f45-186">-FilePath</span></span>
<span data-ttu-id="90f45-187">Указывает путь к файлу, который используется для обновления ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="90f45-187">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="90f45-188">Ресурс управления указывается с помощью параметра *resourceUri* и параметра *selector* .</span><span class="sxs-lookup"><span data-stu-id="90f45-188">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="90f45-189">Например, следующая команда использует параметр *FilePath* :</span><span class="sxs-lookup"><span data-stu-id="90f45-189">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="90f45-190">Эта команда вызывает метод **«не используется» в** службе **диспетчера очереди** , используя входные данные из файла.</span><span class="sxs-lookup"><span data-stu-id="90f45-190">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="90f45-191">Файл Input.xml содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="90f45-191">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="90f45-192">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="90f45-192">-OptionSet</span></span>
<span data-ttu-id="90f45-193">Указывает набор параметров в службе, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="90f45-193">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="90f45-194">Это похоже на ключи, используемые в оболочках командной строки, так как они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="90f45-194">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="90f45-195">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="90f45-195">Any number of options can be specified.</span></span>

<span data-ttu-id="90f45-196">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="90f45-196">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="90f45-197">-Port</span><span class="sxs-lookup"><span data-stu-id="90f45-197">-Port</span></span>
<span data-ttu-id="90f45-198">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="90f45-198">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="90f45-199">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="90f45-199">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="90f45-200">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="90f45-200">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="90f45-201">При использовании протокола HTTPS в качестве транспорта значение параметра *ComputerName* должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="90f45-201">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="90f45-202">Но если параметр *SkipCNCheck* указан в составе параметра *SessionOption*, то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="90f45-202">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="90f45-203">Параметр *SkipCNCheck* следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="90f45-203">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="90f45-204">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="90f45-204">-ResourceURI</span></span>
<span data-ttu-id="90f45-205">Указывает URI класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="90f45-205">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="90f45-206">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="90f45-206">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="90f45-207">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="90f45-207">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="90f45-208">Пример:</span><span class="sxs-lookup"><span data-stu-id="90f45-208">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="90f45-209">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="90f45-209">-SelectorSet</span></span>
<span data-ttu-id="90f45-210">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="90f45-210">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="90f45-211">Набор *selector* используется, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="90f45-211">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="90f45-212">Значение *selector* должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="90f45-212">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="90f45-213">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="90f45-213">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="90f45-214">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="90f45-214">-SessionOption</span></span>
<span data-ttu-id="90f45-215">Определяет расширенные параметры для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="90f45-215">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="90f45-216">Введите объект **SessionOption** , созданный с помощью командлета New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="90f45-216">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="90f45-217">Чтобы получить дополнительные сведения о доступных параметрах, введите `Get-Help New-WSManSessionOption`.</span><span class="sxs-lookup"><span data-stu-id="90f45-217">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="90f45-218">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="90f45-218">-UseSSL</span></span>
<span data-ttu-id="90f45-219">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="90f45-219">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="90f45-220">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="90f45-220">By default, SSL is not used.</span></span>

<span data-ttu-id="90f45-221">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="90f45-221">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="90f45-222">Параметр *UseSSL* позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="90f45-222">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="90f45-223">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="90f45-223">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="90f45-224">-Value</span><span class="sxs-lookup"><span data-stu-id="90f45-224">-ValueSet</span></span>
<span data-ttu-id="90f45-225">Указывает хэш-таблицу, помогающую изменить ресурс управления.</span><span class="sxs-lookup"><span data-stu-id="90f45-225">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="90f45-226">Ресурс управления указывается с помощью *resourceUri* и *selector*.</span><span class="sxs-lookup"><span data-stu-id="90f45-226">You specify the management resource by using *ResourceURI* and *SelectorSet*.</span></span>
<span data-ttu-id="90f45-227">Значение параметра набора *значений* должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="90f45-227">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="90f45-228">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="90f45-228">CommonParameters</span></span>
<span data-ttu-id="90f45-229">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="90f45-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="90f45-230">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="90f45-230">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="90f45-231">Входные данные</span><span class="sxs-lookup"><span data-stu-id="90f45-231">INPUTS</span></span>

### <span data-ttu-id="90f45-232">None</span><span class="sxs-lookup"><span data-stu-id="90f45-232">None</span></span>
<span data-ttu-id="90f45-233">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="90f45-233">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="90f45-234">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="90f45-234">OUTPUTS</span></span>

### <span data-ttu-id="90f45-235">None</span><span class="sxs-lookup"><span data-stu-id="90f45-235">None</span></span>
<span data-ttu-id="90f45-236">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="90f45-236">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="90f45-237">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="90f45-237">NOTES</span></span>

## <span data-ttu-id="90f45-238">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="90f45-238">RELATED LINKS</span></span>

[<span data-ttu-id="90f45-239">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="90f45-239">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="90f45-240">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="90f45-240">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="90f45-241">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="90f45-241">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="90f45-242">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="90f45-242">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="90f45-243">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="90f45-243">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="90f45-244">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="90f45-244">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="90f45-245">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="90f45-245">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="90f45-246">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="90f45-246">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="90f45-247">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="90f45-247">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="90f45-248">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="90f45-248">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="90f45-249">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="90f45-249">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="90f45-250">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="90f45-250">Test-WSMan</span></span>](Test-WSMan.md)

