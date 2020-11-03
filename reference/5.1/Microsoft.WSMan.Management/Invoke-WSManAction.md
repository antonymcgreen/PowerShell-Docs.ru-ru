---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: 1eeeb912ab32ec5334959daba1e352f20fec15b1
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233065"
---
# <span data-ttu-id="06826-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="06826-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="06826-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="06826-104">SYNOPSIS</span></span>
<span data-ttu-id="06826-105">Вызывает действие для объекта, указанного в URI ресурса и селекторах.</span><span class="sxs-lookup"><span data-stu-id="06826-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="06826-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06826-106">SYNTAX</span></span>

### <span data-ttu-id="06826-107">URI (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06826-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="06826-108">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="06826-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="06826-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06826-109">DESCRIPTION</span></span>

<span data-ttu-id="06826-110">Invoke-WSManAction выполняет действие с объектом, заданным RESOURCE_URI, где параметры указываются парами "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="06826-110">The Invoke-WSManAction runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="06826-111">Для выполнения действия этот командлет использует соединение/транспортный уровень WS-Management.</span><span class="sxs-lookup"><span data-stu-id="06826-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="06826-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="06826-112">EXAMPLES</span></span>

### <span data-ttu-id="06826-113">Пример 1</span><span class="sxs-lookup"><span data-stu-id="06826-113">Example 1</span></span>

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

<span data-ttu-id="06826-114">Эта команда вызывает метод StartService экземпляра класса WMI Win32_Service, соответствующий службе очереди печати.</span><span class="sxs-lookup"><span data-stu-id="06826-114">This command calls the StartService method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="06826-115">Возвращаемое значение указывает, было ли действие успешным.</span><span class="sxs-lookup"><span data-stu-id="06826-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="06826-116">В данном случае возвращаемое значение 0 указывает на успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="06826-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="06826-117">Возвращаемое значение 5 указывает на то, что служба уже запущена.</span><span class="sxs-lookup"><span data-stu-id="06826-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="06826-118">Пример 2</span><span class="sxs-lookup"><span data-stu-id="06826-118">Example 2</span></span>

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

<span data-ttu-id="06826-119">Эта команда вызывает метод StopService для службы очереди печати с использованием входных данных из файла.</span><span class="sxs-lookup"><span data-stu-id="06826-119">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="06826-120">Файл Input.xml содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="06826-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

<span data-ttu-id="06826-121">Возвращаемое значение указывает, было ли действие успешным.</span><span class="sxs-lookup"><span data-stu-id="06826-121">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="06826-122">В данном случае возвращаемое значение 0 указывает на успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="06826-122">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="06826-123">Возвращаемое значение 5 указывает на то, что служба уже запущена.</span><span class="sxs-lookup"><span data-stu-id="06826-123">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="06826-124">Пример 3</span><span class="sxs-lookup"><span data-stu-id="06826-124">Example 3</span></span>

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

<span data-ttu-id="06826-125">Эта команда вызывает метод Create класса Win32_Process.</span><span class="sxs-lookup"><span data-stu-id="06826-125">This command calls the Create method of the Win32_Process class.</span></span>
<span data-ttu-id="06826-126">Он передает два значения параметра, Notepad.exe и "C: \" .</span><span class="sxs-lookup"><span data-stu-id="06826-126">It passes the method two parameter values, Notepad.exe and "C:\".</span></span>
<span data-ttu-id="06826-127">В результате создается новый процесс для запуска Блокнота, а текущим каталогом нового процесса присваивается значение "C:" \" .</span><span class="sxs-lookup"><span data-stu-id="06826-127">As a result, a new process is created to run Notepad, and the current directory of the new process is set to "C:\".</span></span>

### <span data-ttu-id="06826-128">Пример 4</span><span class="sxs-lookup"><span data-stu-id="06826-128">Example 4</span></span>

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

<span data-ttu-id="06826-129">Эта команда вызывает метод StartService экземпляра класса WMI Win32_Service, соответствующий службе очереди печати.</span><span class="sxs-lookup"><span data-stu-id="06826-129">This command calls the StartService method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="06826-130">Поскольку указан параметр ComputerName, команда выполняется для удаленного компьютера server01.</span><span class="sxs-lookup"><span data-stu-id="06826-130">Because the ComputerName parameter is specified, the command runs against the remote server01 computer.</span></span>

<span data-ttu-id="06826-131">Возвращаемое значение указывает, было ли действие успешным.</span><span class="sxs-lookup"><span data-stu-id="06826-131">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="06826-132">В данном случае возвращаемое значение 0 указывает на успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="06826-132">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="06826-133">Возвращаемое значение 5 указывает на то, что служба уже запущена.</span><span class="sxs-lookup"><span data-stu-id="06826-133">A return value of 5 indicates that the service is already started.</span></span>

## <span data-ttu-id="06826-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06826-134">PARAMETERS</span></span>

### <span data-ttu-id="06826-135">-Action</span><span class="sxs-lookup"><span data-stu-id="06826-135">-Action</span></span>

<span data-ttu-id="06826-136">Задает метод для выполнения в объекте управления, указанном ResourceURI и селекторами.</span><span class="sxs-lookup"><span data-stu-id="06826-136">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="06826-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="06826-137">-ApplicationName</span></span>

<span data-ttu-id="06826-138">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="06826-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="06826-139">Значение по умолчанию для параметра ApplicationName — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="06826-139">The default value of the ApplicationName parameter is WSMAN.</span></span>
<span data-ttu-id="06826-140">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="06826-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="06826-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="06826-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="06826-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="06826-142">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="06826-143">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="06826-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="06826-144">Этот параметр по умолчанию WSMAN подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="06826-144">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="06826-145">Он предназначен для использования в ситуации, когда много компьютеров устанавливают удаленное подключение к одному компьютеру, на котором выполняется Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06826-145">This parameter is designed to be used when numerous computers establish remote connections to one computer running Windows PowerShell.</span></span>
<span data-ttu-id="06826-146">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="06826-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="06826-147">-Authentication</span><span class="sxs-lookup"><span data-stu-id="06826-147">-Authentication</span></span>

<span data-ttu-id="06826-148">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="06826-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="06826-149">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="06826-149">Possible values are:</span></span>

- <span data-ttu-id="06826-150">Basic — схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="06826-150">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="06826-151">Default — использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="06826-151">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="06826-152">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="06826-152">This is the default.</span></span>
- <span data-ttu-id="06826-153">Digest — это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="06826-153">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="06826-154">Kerberos — клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="06826-154">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="06826-155">Negotiate — это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="06826-155">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="06826-156">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="06826-156">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="06826-157">CredSSP — использование аутентификации CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="06826-157">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="06826-158">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="06826-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="06826-159">Внимание! CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="06826-159">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="06826-160">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="06826-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="06826-161">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="06826-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="06826-162">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="06826-162">-CertificateThumbprint</span></span>

<span data-ttu-id="06826-163">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="06826-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="06826-164">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="06826-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="06826-165">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="06826-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="06826-166">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="06826-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="06826-167">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске сертификатов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06826-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="06826-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="06826-168">-ComputerName</span></span>

<span data-ttu-id="06826-169">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="06826-169">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="06826-170">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="06826-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="06826-171">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="06826-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="06826-172">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="06826-172">The local computer is the default.</span></span>
<span data-ttu-id="06826-173">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="06826-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="06826-174">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="06826-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="06826-175">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="06826-175">-ConnectionURI</span></span>

<span data-ttu-id="06826-176">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="06826-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="06826-177">Строки имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="06826-177">The format of this string is:</span></span>

<span data-ttu-id="06826-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="06826-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="06826-179">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="06826-179">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="06826-180">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="06826-180">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="06826-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="06826-181">-Credential</span></span>

<span data-ttu-id="06826-182">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="06826-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="06826-183">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="06826-183">The default is the current user.</span></span>
<span data-ttu-id="06826-184">Введите имя пользователя, например "User01", "Domain01\User01", или User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="06826-184">Type a user name, such as "User01", "Domain01\User01", or User@Domain.com.</span></span>
<span data-ttu-id="06826-185">либо введите объект PSCredential, например такой, который возвращает командлет Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="06826-185">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="06826-186">При вводе имени пользователя появится приглашение ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="06826-186">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="06826-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="06826-187">-FilePath</span></span>

<span data-ttu-id="06826-188">Указывает путь к файлу, который используется для обновления ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="06826-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="06826-189">Для указания ресурса управления используется параметр ResourceURI и параметр SelectorSet.</span><span class="sxs-lookup"><span data-stu-id="06826-189">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="06826-190">Например, следующая команда использует параметр FilePath:</span><span class="sxs-lookup"><span data-stu-id="06826-190">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="06826-191">Эта команда вызывает метод StopService для службы очереди печати с использованием входных данных из файла.</span><span class="sxs-lookup"><span data-stu-id="06826-191">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="06826-192">Файл Input.xml содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="06826-192">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="06826-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="06826-193">-OptionSet</span></span>

<span data-ttu-id="06826-194">Передает набор параметров в службу для изменения или уточнения природы запроса.</span><span class="sxs-lookup"><span data-stu-id="06826-194">Passes a set of switches  to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="06826-195">Это похоже на ключи, используемые в оболочках командной строки, поскольку они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="06826-195">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="06826-196">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="06826-196">Any number of options  can be specified.</span></span>

<span data-ttu-id="06826-197">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="06826-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="06826-198">-Port</span><span class="sxs-lookup"><span data-stu-id="06826-198">-Port</span></span>

<span data-ttu-id="06826-199">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="06826-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="06826-200">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="06826-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="06826-201">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="06826-201">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="06826-202">При использовании HTTPS в качестве транспорта значение параметра ComputerName должно соответствовать общему имени (CN) сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="06826-202">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="06826-203">Однако если параметр SkipCNCheck указан в составе параметра SessionOption, то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="06826-203">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="06826-204">Параметр SkipCNCheck следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="06826-204">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="06826-205">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="06826-205">-ResourceURI</span></span>

<span data-ttu-id="06826-206">Содержит универсальный код ресурса (URI) для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="06826-206">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="06826-207">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="06826-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="06826-208">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="06826-208">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="06826-209">Пример:</span><span class="sxs-lookup"><span data-stu-id="06826-209">For example:</span></span>

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

### <span data-ttu-id="06826-210">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="06826-210">-SelectorSet</span></span>

<span data-ttu-id="06826-211">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="06826-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="06826-212">Набор *selector* используется, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="06826-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="06826-213">Значение *selector* должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="06826-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="06826-214">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="06826-214">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="06826-215">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="06826-215">-SessionOption</span></span>

<span data-ttu-id="06826-216">Определяет набор расширенных параметров для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="06826-216">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="06826-217">Введите объект SessionOption, созданный с помощью командлета New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="06826-217">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="06826-218">Дополнительные сведения о доступных параметрах см. в описании New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="06826-218">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="06826-219">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="06826-219">-UseSSL</span></span>

<span data-ttu-id="06826-220">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="06826-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="06826-221">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="06826-221">By default, SSL is not used.</span></span>

<span data-ttu-id="06826-222">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="06826-222">WS-Management encrypts all the PowerShell content  that is transmitted over the network.</span></span>
<span data-ttu-id="06826-223">Параметр UseSSL позволяет задать дополнительную защиту HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="06826-223">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="06826-224">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="06826-224">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="06826-225">-Value</span><span class="sxs-lookup"><span data-stu-id="06826-225">-ValueSet</span></span>

<span data-ttu-id="06826-226">Указывает хэш-таблицу, помогающую изменить ресурс управления.</span><span class="sxs-lookup"><span data-stu-id="06826-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="06826-227">Ресурс управления указывается с помощью параметров ResourceURI и Selector.</span><span class="sxs-lookup"><span data-stu-id="06826-227">You specify the management resource using the ResourceURI and SelectorSet parameters.</span></span>
<span data-ttu-id="06826-228">Значение параметра ValueSet должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="06826-228">The value of the ValueSet parameter must be a hash table.</span></span>

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

### <span data-ttu-id="06826-229">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="06826-229">CommonParameters</span></span>

<span data-ttu-id="06826-230">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="06826-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06826-231">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="06826-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="06826-232">Входные данные</span><span class="sxs-lookup"><span data-stu-id="06826-232">INPUTS</span></span>

### <span data-ttu-id="06826-233">Нет</span><span class="sxs-lookup"><span data-stu-id="06826-233">None</span></span>

<span data-ttu-id="06826-234">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="06826-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="06826-235">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="06826-235">OUTPUTS</span></span>

### <span data-ttu-id="06826-236">Нет</span><span class="sxs-lookup"><span data-stu-id="06826-236">None</span></span>

<span data-ttu-id="06826-237">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="06826-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="06826-238">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="06826-238">NOTES</span></span>

## <span data-ttu-id="06826-239">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="06826-239">RELATED LINKS</span></span>

[<span data-ttu-id="06826-240">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="06826-240">Invoke-WmiMethod</span></span>](../Microsoft.PowerShell.Management/Invoke-WmiMethod.md)

[<span data-ttu-id="06826-241">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="06826-241">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="06826-242">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="06826-242">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="06826-243">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="06826-243">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="06826-244">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="06826-244">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="06826-245">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="06826-245">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="06826-246">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="06826-246">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="06826-247">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="06826-247">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="06826-248">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="06826-248">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="06826-249">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="06826-249">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="06826-250">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="06826-250">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="06826-251">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="06826-251">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="06826-252">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="06826-252">Test-WSMan</span></span>](Test-WSMan.md)
