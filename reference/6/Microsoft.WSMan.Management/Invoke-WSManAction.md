---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: b969449d3e2e888138f783c17e16fa696fe40efe
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229965"
---
# <span data-ttu-id="fa81d-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="fa81d-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="fa81d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fa81d-104">SYNOPSIS</span></span>
<span data-ttu-id="fa81d-105">Вызывает действие для объекта, указанного в URI ресурса и селекторах.</span><span class="sxs-lookup"><span data-stu-id="fa81d-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="fa81d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa81d-106">SYNTAX</span></span>

### <span data-ttu-id="fa81d-107">URI (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fa81d-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="fa81d-108">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="fa81d-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="fa81d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fa81d-109">DESCRIPTION</span></span>
<span data-ttu-id="fa81d-110">**Командлет Invoke-WSManAction** выполняет действие с объектом, указанным в RESOURCE_URI, где параметры задаются парами "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="fa81d-110">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="fa81d-111">Для выполнения действия этот командлет использует соединение/транспортный уровень WS-Management.</span><span class="sxs-lookup"><span data-stu-id="fa81d-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="fa81d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="fa81d-112">EXAMPLES</span></span>

### <span data-ttu-id="fa81d-113">Пример 1. вызов метода</span><span class="sxs-lookup"><span data-stu-id="fa81d-113">Example 1: Invoke a method</span></span>

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

<span data-ttu-id="fa81d-114">Эта команда вызывает метод **StartService** экземпляра класса WMI Win32_Service, который соответствует службе диспетчера очереди печати.</span><span class="sxs-lookup"><span data-stu-id="fa81d-114">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="fa81d-115">Возвращаемое значение указывает, было ли действие успешным.</span><span class="sxs-lookup"><span data-stu-id="fa81d-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="fa81d-116">В данном случае возвращаемое значение 0 указывает на успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="fa81d-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="fa81d-117">Возвращаемое значение 5 указывает на то, что служба уже запущена.</span><span class="sxs-lookup"><span data-stu-id="fa81d-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="fa81d-118">Пример 2. вызов метода</span><span class="sxs-lookup"><span data-stu-id="fa81d-118">Example 2: Invoke a method</span></span>

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

<span data-ttu-id="fa81d-119">Эта команда вызывает метод **«не используется» в** службе диспетчера очереди, используя входные данные из файла.</span><span class="sxs-lookup"><span data-stu-id="fa81d-119">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="fa81d-120">Файл Input.xml содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="fa81d-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="fa81d-121">Пример 3. вызов метода с указанными значениями параметров</span><span class="sxs-lookup"><span data-stu-id="fa81d-121">Example 3: Invoke a method with specified parameter values</span></span>

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

<span data-ttu-id="fa81d-122">Эта команда вызывает метод **CREATE** класса Win32_Process.</span><span class="sxs-lookup"><span data-stu-id="fa81d-122">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="fa81d-123">Он передает методу два значения параметров: Notepad.exe и C:\..</span><span class="sxs-lookup"><span data-stu-id="fa81d-123">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="fa81d-124">В результате создается новый процесс для запуска Блокнота, а текущим каталогом нового процесса присваивается значение C:\.</span><span class="sxs-lookup"><span data-stu-id="fa81d-124">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="fa81d-125">Пример 4. вызов метода на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="fa81d-125">Example 4: Invoke a method on a remote computer</span></span>

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

<span data-ttu-id="fa81d-126">Эта команда вызывает метод **StartService** экземпляра класса WMI Win32_Service, который соответствует службе диспетчера очереди печати.</span><span class="sxs-lookup"><span data-stu-id="fa81d-126">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="fa81d-127">Так как указан параметр *ComputerName* , команда выполняется на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="fa81d-127">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="fa81d-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa81d-128">PARAMETERS</span></span>

### <span data-ttu-id="fa81d-129">-Action</span><span class="sxs-lookup"><span data-stu-id="fa81d-129">-Action</span></span>
<span data-ttu-id="fa81d-130">Задает метод для выполнения в объекте управления, указанном ResourceURI и селекторами.</span><span class="sxs-lookup"><span data-stu-id="fa81d-130">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="fa81d-131">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="fa81d-131">-ApplicationName</span></span>
<span data-ttu-id="fa81d-132">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="fa81d-132">Specifies the application name in the connection.</span></span>
<span data-ttu-id="fa81d-133">Значением параметра *applicationName* по умолчанию является WSMan.</span><span class="sxs-lookup"><span data-stu-id="fa81d-133">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="fa81d-134">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="fa81d-134">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="fa81d-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="fa81d-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="fa81d-136">Пример: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="fa81d-136">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="fa81d-137">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="fa81d-137">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="fa81d-138">Значение по умолчанию (WSMAN) подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="fa81d-138">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="fa81d-139">Этот параметр предназначен для использования, если многие компьютеры устанавливают удаленные подключения к одному компьютеру, на котором работает PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa81d-139">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="fa81d-140">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="fa81d-140">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="fa81d-141">-Authentication</span><span class="sxs-lookup"><span data-stu-id="fa81d-141">-Authentication</span></span>
<span data-ttu-id="fa81d-142">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="fa81d-142">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="fa81d-143">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="fa81d-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fa81d-144">Обычные.</span><span class="sxs-lookup"><span data-stu-id="fa81d-144">Basic.</span></span>
<span data-ttu-id="fa81d-145">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="fa81d-145">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="fa81d-146">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fa81d-146">Default.</span></span>
<span data-ttu-id="fa81d-147">использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="fa81d-147">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="fa81d-148">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fa81d-148">This is the default.</span></span>
- <span data-ttu-id="fa81d-149">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="fa81d-149">Digest.</span></span>
<span data-ttu-id="fa81d-150">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="fa81d-150">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="fa81d-151">Kerberos —</span><span class="sxs-lookup"><span data-stu-id="fa81d-151">Kerberos.</span></span>
<span data-ttu-id="fa81d-152">клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="fa81d-152">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="fa81d-153">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="fa81d-153">Negotiate.</span></span>
<span data-ttu-id="fa81d-154">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="fa81d-154">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="fa81d-155">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="fa81d-155">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="fa81d-156">CredSSP —</span><span class="sxs-lookup"><span data-stu-id="fa81d-156">CredSSP.</span></span>
<span data-ttu-id="fa81d-157">использование проверки подлинности CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fa81d-157">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="fa81d-158">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="fa81d-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="fa81d-159">Внимание! CredSSP делегирует учетные данные пользователя с локального на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="fa81d-159">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="fa81d-160">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="fa81d-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="fa81d-161">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="fa81d-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="fa81d-162">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="fa81d-162">-CertificateThumbprint</span></span>
<span data-ttu-id="fa81d-163">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="fa81d-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="fa81d-164">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="fa81d-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="fa81d-165">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="fa81d-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="fa81d-166">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="fa81d-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="fa81d-167">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="fa81d-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="fa81d-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="fa81d-168">-ComputerName</span></span>
<span data-ttu-id="fa81d-169">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="fa81d-169">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="fa81d-170">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="fa81d-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="fa81d-171">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="fa81d-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="fa81d-172">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fa81d-172">The local computer is the default.</span></span>
<span data-ttu-id="fa81d-173">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="fa81d-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="fa81d-174">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="fa81d-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="fa81d-175">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="fa81d-175">-ConnectionURI</span></span>
<span data-ttu-id="fa81d-176">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="fa81d-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="fa81d-177">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="fa81d-177">The format of this string is as follows:</span></span>

<span data-ttu-id="fa81d-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="fa81d-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="fa81d-179">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="fa81d-179">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="fa81d-180">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="fa81d-180">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="fa81d-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="fa81d-181">-Credential</span></span>
<span data-ttu-id="fa81d-182">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="fa81d-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="fa81d-183">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="fa81d-183">The default is the current user.</span></span>
<span data-ttu-id="fa81d-184">Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="fa81d-184">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="fa81d-185">Или введите объект **PSCredential** , например, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="fa81d-185">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="fa81d-186">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="fa81d-186">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="fa81d-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="fa81d-187">-FilePath</span></span>
<span data-ttu-id="fa81d-188">Указывает путь к файлу, который используется для обновления ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="fa81d-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="fa81d-189">Ресурс управления указывается с помощью параметра *resourceUri* и параметра *selector* .</span><span class="sxs-lookup"><span data-stu-id="fa81d-189">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="fa81d-190">Например, следующая команда использует параметр *FilePath* :</span><span class="sxs-lookup"><span data-stu-id="fa81d-190">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="fa81d-191">Эта команда вызывает метод **«не используется» в** службе **диспетчера очереди** , используя входные данные из файла.</span><span class="sxs-lookup"><span data-stu-id="fa81d-191">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="fa81d-192">Файл Input.xml содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="fa81d-192">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="fa81d-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="fa81d-193">-OptionSet</span></span>
<span data-ttu-id="fa81d-194">Указывает набор параметров в службе, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="fa81d-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="fa81d-195">Это похоже на ключи, используемые в оболочках командной строки, так как они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="fa81d-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="fa81d-196">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="fa81d-196">Any number of options can be specified.</span></span>

<span data-ttu-id="fa81d-197">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="fa81d-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="fa81d-198">-Port</span><span class="sxs-lookup"><span data-stu-id="fa81d-198">-Port</span></span>
<span data-ttu-id="fa81d-199">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="fa81d-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="fa81d-200">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="fa81d-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="fa81d-201">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="fa81d-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="fa81d-202">При использовании протокола HTTPS в качестве транспорта значение параметра *ComputerName* должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="fa81d-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="fa81d-203">Но если параметр *SkipCNCheck* указан в составе параметра *SessionOption* , то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="fa81d-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="fa81d-204">Параметр *SkipCNCheck* следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="fa81d-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="fa81d-205">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="fa81d-205">-ResourceURI</span></span>
<span data-ttu-id="fa81d-206">Указывает URI класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="fa81d-206">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="fa81d-207">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fa81d-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="fa81d-208">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="fa81d-208">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="fa81d-209">Пример:</span><span class="sxs-lookup"><span data-stu-id="fa81d-209">For example:</span></span>

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

### <span data-ttu-id="fa81d-210">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="fa81d-210">-SelectorSet</span></span>
<span data-ttu-id="fa81d-211">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="fa81d-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="fa81d-212">Набор *selector* используется, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="fa81d-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="fa81d-213">Значение *selector* должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="fa81d-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="fa81d-214">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="fa81d-214">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="fa81d-215">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="fa81d-215">-SessionOption</span></span>
<span data-ttu-id="fa81d-216">Определяет расширенные параметры для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="fa81d-216">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="fa81d-217">Введите объект **SessionOption** , созданный с помощью командлета New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="fa81d-217">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="fa81d-218">Чтобы получить дополнительные сведения о доступных параметрах, введите `Get-Help New-WSManSessionOption`.</span><span class="sxs-lookup"><span data-stu-id="fa81d-218">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="fa81d-219">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="fa81d-219">-UseSSL</span></span>
<span data-ttu-id="fa81d-220">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="fa81d-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="fa81d-221">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="fa81d-221">By default, SSL is not used.</span></span>

<span data-ttu-id="fa81d-222">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="fa81d-222">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="fa81d-223">Параметр *UseSSL* позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa81d-223">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="fa81d-224">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fa81d-224">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="fa81d-225">-Value</span><span class="sxs-lookup"><span data-stu-id="fa81d-225">-ValueSet</span></span>
<span data-ttu-id="fa81d-226">Указывает хэш-таблицу, помогающую изменить ресурс управления.</span><span class="sxs-lookup"><span data-stu-id="fa81d-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="fa81d-227">Ресурс управления указывается с помощью *resourceUri* и *selector* .</span><span class="sxs-lookup"><span data-stu-id="fa81d-227">You specify the management resource by using *ResourceURI* and *SelectorSet* .</span></span>
<span data-ttu-id="fa81d-228">Значение параметра набора *значений* должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="fa81d-228">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="fa81d-229">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fa81d-229">CommonParameters</span></span>
<span data-ttu-id="fa81d-230">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fa81d-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa81d-231">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fa81d-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa81d-232">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fa81d-232">INPUTS</span></span>

### <span data-ttu-id="fa81d-233">Нет</span><span class="sxs-lookup"><span data-stu-id="fa81d-233">None</span></span>
<span data-ttu-id="fa81d-234">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="fa81d-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="fa81d-235">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fa81d-235">OUTPUTS</span></span>

### <span data-ttu-id="fa81d-236">Нет</span><span class="sxs-lookup"><span data-stu-id="fa81d-236">None</span></span>
<span data-ttu-id="fa81d-237">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fa81d-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fa81d-238">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fa81d-238">NOTES</span></span>

## <span data-ttu-id="fa81d-239">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fa81d-239">RELATED LINKS</span></span>

[<span data-ttu-id="fa81d-240">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fa81d-240">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="fa81d-241">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fa81d-241">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="fa81d-242">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fa81d-242">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="fa81d-243">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fa81d-243">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="fa81d-244">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fa81d-244">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="fa81d-245">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fa81d-245">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="fa81d-246">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fa81d-246">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="fa81d-247">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="fa81d-247">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="fa81d-248">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fa81d-248">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="fa81d-249">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fa81d-249">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="fa81d-250">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="fa81d-250">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="fa81d-251">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="fa81d-251">Test-WSMan</span></span>](Test-WSMan.md)
