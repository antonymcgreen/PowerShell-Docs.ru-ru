---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 3f4ee9edf6e8dfce21a51ff9c055fe56a0cbef3c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229938"
---
# <span data-ttu-id="4ea65-103">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="4ea65-103">Set-WSManInstance</span></span>

## <span data-ttu-id="4ea65-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4ea65-104">SYNOPSIS</span></span>
<span data-ttu-id="4ea65-105">Изменяет данные управления, связанные с ресурсом.</span><span class="sxs-lookup"><span data-stu-id="4ea65-105">Modifies the management information that is related to a resource.</span></span>

## <span data-ttu-id="4ea65-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4ea65-106">SYNTAX</span></span>

### <span data-ttu-id="4ea65-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4ea65-107">ComputerName (Default)</span></span>

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="4ea65-108">URI</span><span class="sxs-lookup"><span data-stu-id="4ea65-108">URI</span></span>

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="4ea65-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4ea65-109">DESCRIPTION</span></span>

<span data-ttu-id="4ea65-110">Командлет Set-WSManInstance изменяет данные управления, связанные с ресурсом.</span><span class="sxs-lookup"><span data-stu-id="4ea65-110">The Set-WSManInstance cmdlet modifies the management information that is related to a resource.</span></span>

<span data-ttu-id="4ea65-111">Для изменения информации он использует соединение/транспортный уровень службы удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea65-111">This cmdlet uses the WinRM connection/transport layer to modify the information.</span></span>

## <span data-ttu-id="4ea65-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="4ea65-112">EXAMPLES</span></span>

### <span data-ttu-id="4ea65-113">Пример 1. Отключение прослушивателя на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="4ea65-113">Example 1: Disable a listener on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.171, ::1, 2001:4898:0:fff:0:5efe:172.30.168.171...}
```

<span data-ttu-id="4ea65-114">Эта команда отключает прослушиватель HTTPS на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4ea65-114">This command disables the https listener on the local computer.</span></span>

<span data-ttu-id="4ea65-115">Важно! в *параметре* Parameter учитывается регистр, если он совпадает с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="4ea65-115">Important: The *ValueSet* parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="4ea65-116">Например, в этой команде</span><span class="sxs-lookup"><span data-stu-id="4ea65-116">For example, in this command,</span></span>

<span data-ttu-id="4ea65-117">Этот сбой: `-ValueSet @{enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="4ea65-117">This fails: `-ValueSet @{enabled="False"}`</span></span>

<span data-ttu-id="4ea65-118">Это будет выполнен следующим образом: `-ValueSet @{Enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="4ea65-118">This succeeds: `-ValueSet @{Enabled="False"}`</span></span>

### <span data-ttu-id="4ea65-119">Пример 2. Установка максимального размера конверта на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="4ea65-119">Example 2: Set the maximum envelope size on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config -ValueSet @{MaxEnvelopeSizekb = "200"}
```

```Output
cfg                 : http://schemas.microsoft.com/wbem/wsman/1/config
lang                : en-US
MaxEnvelopeSizekb   : 200
MaxTimeoutms        : 60000
MaxBatchItems       : 32000
MaxProviderRequests : 4294967295
Client              : Client
Service             : Service
Winrs               : Winrs
```

<span data-ttu-id="4ea65-120">Эта команда задает для MaxEnvelopeSizekb значение 200 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4ea65-120">This command sets the MaxEnvelopeSizekb value to 200 on the local computer.</span></span>

<span data-ttu-id="4ea65-121">Важно! в параметре Parameter учитывается регистр, если он совпадает с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="4ea65-121">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="4ea65-122">Например, воспользуемся указанной выше командой.</span><span class="sxs-lookup"><span data-stu-id="4ea65-122">For example, using the above command.</span></span>

<span data-ttu-id="4ea65-123">Этот сбой:-value @ {Максенвелопесизекб = "200"}</span><span class="sxs-lookup"><span data-stu-id="4ea65-123">This fails:     -ValueSet @{MaxEnvelopeSizeKB ="200"}</span></span>

<span data-ttu-id="4ea65-124">Это будет выполнен следующим образом:-value @ {Максенвелопесизекб = "200"}</span><span class="sxs-lookup"><span data-stu-id="4ea65-124">This succeeds:  -ValueSet @{MaxEnvelopeSizekb ="200"}</span></span>

### <span data-ttu-id="4ea65-125">Пример 3. Отключение прослушивателя на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="4ea65-125">Example 3: Disable a listener on a remote computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -ComputerName SERVER02 -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.172, ::1, 2001:4898:0:fff:0:5efe:172.30.168.172...}
```

<span data-ttu-id="4ea65-126">Эта команда отключает прослушиватель HTTPS на удаленном компьютере SERVER02.</span><span class="sxs-lookup"><span data-stu-id="4ea65-126">This command disables the https listener on the remote computer SERVER02.</span></span>

<span data-ttu-id="4ea65-127">Важно! в параметре Parameter учитывается регистр, если он совпадает с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="4ea65-127">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="4ea65-128">Например, воспользуемся указанной выше командой.</span><span class="sxs-lookup"><span data-stu-id="4ea65-128">For example, using the above command.</span></span>

<span data-ttu-id="4ea65-129">Этот сбой: параметр-value @ {Enabled = "false"}</span><span class="sxs-lookup"><span data-stu-id="4ea65-129">This fails:     -ValueSet @{enabled="False"}</span></span>

<span data-ttu-id="4ea65-130">Это происходит следующим образом:-valued @ {Enabled = "false"}</span><span class="sxs-lookup"><span data-stu-id="4ea65-130">This succeeds:  -ValueSet @{Enabled="False"}</span></span>

## <span data-ttu-id="4ea65-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4ea65-131">PARAMETERS</span></span>

### <span data-ttu-id="4ea65-132">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="4ea65-132">-ApplicationName</span></span>

<span data-ttu-id="4ea65-133">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="4ea65-133">Specifies the application name in the connection.</span></span>
<span data-ttu-id="4ea65-134">Значение по умолчанию для параметра ApplicationName — WSMAN.</span><span class="sxs-lookup"><span data-stu-id="4ea65-134">The default value of the ApplicationName parameter is "WSMAN".</span></span>
<span data-ttu-id="4ea65-135">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="4ea65-135">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="4ea65-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="4ea65-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="4ea65-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="4ea65-137">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="4ea65-138">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="4ea65-138">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="4ea65-139">Этот параметр по умолчанию WSMAN подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="4ea65-139">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="4ea65-140">Он предназначен для использования в ситуации, когда много компьютеров устанавливают удаленное подключение к одному компьютеру, на котором выполняется Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ea65-140">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="4ea65-141">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="4ea65-141">In this case, IIS hosts Web Services for Management (WS-Management ) for efficiency.</span></span>

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

### <span data-ttu-id="4ea65-142">-Authentication</span><span class="sxs-lookup"><span data-stu-id="4ea65-142">-Authentication</span></span>

<span data-ttu-id="4ea65-143">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="4ea65-143">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="4ea65-144">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4ea65-144">Possible values are:</span></span>

- <span data-ttu-id="4ea65-145">Basic — схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="4ea65-145">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="4ea65-146">Default — использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="4ea65-146">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="4ea65-147">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ea65-147">This is the default.</span></span>
- <span data-ttu-id="4ea65-148">Digest — это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="4ea65-148">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="4ea65-149">Kerberos — клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4ea65-149">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="4ea65-150">Negotiate — это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="4ea65-150">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="4ea65-151">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="4ea65-151">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="4ea65-152">CredSSP — использование аутентификации CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="4ea65-152">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="4ea65-153">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4ea65-153">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="4ea65-154">Внимание! CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="4ea65-154">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="4ea65-155">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="4ea65-155">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="4ea65-156">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="4ea65-156">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4ea65-157">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="4ea65-157">-CertificateThumbprint</span></span>

<span data-ttu-id="4ea65-158">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="4ea65-158">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="4ea65-159">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="4ea65-159">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="4ea65-160">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="4ea65-160">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="4ea65-161">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="4ea65-161">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="4ea65-162">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="4ea65-162">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="4ea65-163">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4ea65-163">-ComputerName</span></span>

<span data-ttu-id="4ea65-164">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="4ea65-164">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="4ea65-165">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="4ea65-165">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="4ea65-166">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="4ea65-166">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="4ea65-167">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ea65-167">The local computer is the default.</span></span>
<span data-ttu-id="4ea65-168">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="4ea65-168">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="4ea65-169">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="4ea65-169">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="4ea65-170">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="4ea65-170">-ConnectionURI</span></span>

<span data-ttu-id="4ea65-171">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="4ea65-171">Specifies the connection endpoint.</span></span>
<span data-ttu-id="4ea65-172">Строки имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="4ea65-172">The format of this string is:</span></span>

<span data-ttu-id="4ea65-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="4ea65-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="4ea65-174">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="4ea65-174">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="4ea65-175">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="4ea65-175">The URI must be fully qualified .</span></span>

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

### <span data-ttu-id="4ea65-176">-Credential</span><span class="sxs-lookup"><span data-stu-id="4ea65-176">-Credential</span></span>

<span data-ttu-id="4ea65-177">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="4ea65-177">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="4ea65-178">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="4ea65-178">The default is the current user.</span></span>
<span data-ttu-id="4ea65-179">Введите имя пользователя, например "User01", "Domain01\User01" или " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="4ea65-179">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span>
<span data-ttu-id="4ea65-180">либо введите объект PSCredential, например такой, который возвращает командлет Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="4ea65-180">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="4ea65-181">При вводе имени пользователя появится приглашение ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="4ea65-181">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="4ea65-182">-Dialect</span><span class="sxs-lookup"><span data-stu-id="4ea65-182">-Dialect</span></span>

<span data-ttu-id="4ea65-183">Определяет диалект, используемый в предикате фильтра.</span><span class="sxs-lookup"><span data-stu-id="4ea65-183">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="4ea65-184">Это может быть любой диалект, поддерживаемый удаленной службой.</span><span class="sxs-lookup"><span data-stu-id="4ea65-184">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="4ea65-185">Для URI диалекта можно использовать следующие псевдонимы:</span><span class="sxs-lookup"><span data-stu-id="4ea65-185">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="4ea65-186">ВОДИТ `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="4ea65-186">WQL: `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="4ea65-187">Выбора `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="4ea65-187">Selector: `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="4ea65-188">Связке `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="4ea65-188">Association: `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: http://schemas.microsoft.com/wbem/wsman/1/WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4ea65-189">-FilePath</span><span class="sxs-lookup"><span data-stu-id="4ea65-189">-FilePath</span></span>

<span data-ttu-id="4ea65-190">Указывает путь к файлу, который используется для обновления ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="4ea65-190">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="4ea65-191">Для указания ресурса управления используется параметр ResourceURI и параметр SelectorSet.</span><span class="sxs-lookup"><span data-stu-id="4ea65-191">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter .</span></span>
<span data-ttu-id="4ea65-192">Например, следующая команда использует параметр FilePath:</span><span class="sxs-lookup"><span data-stu-id="4ea65-192">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

<span data-ttu-id="4ea65-193">Эта команда вызывает метод StopService для службы очереди печати с использованием входных данных из файла.</span><span class="sxs-lookup"><span data-stu-id="4ea65-193">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="4ea65-194">Файл Input.xml содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="4ea65-194">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4ea65-195">-Fragment</span><span class="sxs-lookup"><span data-stu-id="4ea65-195">-Fragment</span></span>

<span data-ttu-id="4ea65-196">Задает раздел внутри экземпляра, который должен быть обновлен или возвращен для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="4ea65-196">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="4ea65-197">Например, чтобы получить состояние службы очереди печати, укажите "-Fragment Status".</span><span class="sxs-lookup"><span data-stu-id="4ea65-197">For example, to get the status of a spooler service, specify "-Fragment Status".</span></span>

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

### <span data-ttu-id="4ea65-198">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="4ea65-198">-OptionSet</span></span>

<span data-ttu-id="4ea65-199">Передает набор параметров в службу, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="4ea65-199">Passes a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="4ea65-200">Это похоже на ключи, используемые в оболочках командной строки, поскольку они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="4ea65-200">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="4ea65-201">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="4ea65-201">Any number of options can be specified.</span></span>

<span data-ttu-id="4ea65-202">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="4ea65-202">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

<span data-ttu-id="4ea65-203">-OptionSet @{a=1;b=2;c=3}</span><span class="sxs-lookup"><span data-stu-id="4ea65-203">-OptionSet @{a=1;b=2;c=3}</span></span>

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

### <span data-ttu-id="4ea65-204">-Port</span><span class="sxs-lookup"><span data-stu-id="4ea65-204">-Port</span></span>

<span data-ttu-id="4ea65-205">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea65-205">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="4ea65-206">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="4ea65-206">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="4ea65-207">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="4ea65-207">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="4ea65-208">При использовании HTTPS в качестве транспорта значение параметра ComputerName должно соответствовать общему имени (CN) сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="4ea65-208">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="4ea65-209">Однако если параметр SkipCNCheck указан в составе параметра SessionOption, то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="4ea65-209">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="4ea65-210">Параметр SkipCNCheck следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="4ea65-210">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="4ea65-211">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="4ea65-211">-ResourceURI</span></span>

<span data-ttu-id="4ea65-212">Содержит универсальный код ресурса (URI) для класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="4ea65-212">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="4ea65-213">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4ea65-213">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="4ea65-214">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="4ea65-214">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="4ea65-215">Пример:</span><span class="sxs-lookup"><span data-stu-id="4ea65-215">For example:</span></span>

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

### <span data-ttu-id="4ea65-216">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="4ea65-216">-SelectorSet</span></span>

<span data-ttu-id="4ea65-217">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="4ea65-217">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="4ea65-218">Параметр SelectorSet используется в том случае, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="4ea65-218">The SelectorSet parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="4ea65-219">Значение параметра SelectorSet должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="4ea65-219">The value of the SelectorSet parameter must be a hash table.</span></span>
<span data-ttu-id="4ea65-220">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="4ea65-220">The following example shows how to enter a value for this parameter:</span></span>

<span data-ttu-id="4ea65-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span><span class="sxs-lookup"><span data-stu-id="4ea65-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4ea65-222">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="4ea65-222">-SessionOption</span></span>

<span data-ttu-id="4ea65-223">Определяет набор расширенных параметров для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="4ea65-223">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="4ea65-224">Введите объект SessionOption, созданный с помощью командлета New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="4ea65-224">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="4ea65-225">Дополнительные сведения о доступных параметрах см. в описании New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="4ea65-225">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="4ea65-226">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="4ea65-226">-UseSSL</span></span>

<span data-ttu-id="4ea65-227">Указывает, что для подключения к удаленному компьютеру следует использовать протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="4ea65-227">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="4ea65-228">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="4ea65-228">By default, SSL is not used.</span></span>

<span data-ttu-id="4ea65-229">WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="4ea65-229">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="4ea65-230">Параметр UseSSL позволяет задать дополнительную защиту HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="4ea65-230">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="4ea65-231">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4ea65-231">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases: ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4ea65-232">-Value</span><span class="sxs-lookup"><span data-stu-id="4ea65-232">-ValueSet</span></span>

<span data-ttu-id="4ea65-233">Указывает хэш-таблицу, помогающую изменить ресурс управления.</span><span class="sxs-lookup"><span data-stu-id="4ea65-233">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="4ea65-234">Для указания ресурса управления используется параметр ResourceURI и параметр SelectorSet.</span><span class="sxs-lookup"><span data-stu-id="4ea65-234">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="4ea65-235">Значение параметра ValueSet должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="4ea65-235">The value of the ValueSet parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4ea65-236">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4ea65-236">CommonParameters</span></span>

<span data-ttu-id="4ea65-237">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4ea65-237">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4ea65-238">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4ea65-238">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4ea65-239">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4ea65-239">INPUTS</span></span>

### <span data-ttu-id="4ea65-240">Нет</span><span class="sxs-lookup"><span data-stu-id="4ea65-240">None</span></span>

<span data-ttu-id="4ea65-241">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="4ea65-241">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="4ea65-242">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4ea65-242">OUTPUTS</span></span>

### <span data-ttu-id="4ea65-243">Нет</span><span class="sxs-lookup"><span data-stu-id="4ea65-243">None</span></span>

<span data-ttu-id="4ea65-244">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4ea65-244">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4ea65-245">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4ea65-245">NOTES</span></span>

## <span data-ttu-id="4ea65-246">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4ea65-246">RELATED LINKS</span></span>

[<span data-ttu-id="4ea65-247">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="4ea65-247">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="4ea65-248">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="4ea65-248">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="4ea65-249">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="4ea65-249">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="4ea65-250">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="4ea65-250">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="4ea65-251">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="4ea65-251">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="4ea65-252">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="4ea65-252">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="4ea65-253">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="4ea65-253">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="4ea65-254">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="4ea65-254">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="4ea65-255">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="4ea65-255">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="4ea65-256">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="4ea65-256">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="4ea65-257">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="4ea65-257">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="4ea65-258">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="4ea65-258">Test-WSMan</span></span>](Test-WSMan.md)
