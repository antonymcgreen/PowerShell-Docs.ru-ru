---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/remove-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WSManInstance
ms.openlocfilehash: 6bd166942551671c581c04cb611c222378caeba1
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229818"
---
# <span data-ttu-id="3eac0-103">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3eac0-103">Remove-WSManInstance</span></span>

## <span data-ttu-id="3eac0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3eac0-104">SYNOPSIS</span></span>
<span data-ttu-id="3eac0-105">Удаляет экземпляр ресурса управления.</span><span class="sxs-lookup"><span data-stu-id="3eac0-105">Deletes a management resource instance.</span></span>

## <span data-ttu-id="3eac0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3eac0-106">SYNTAX</span></span>

### <span data-ttu-id="3eac0-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3eac0-107">ComputerName (Default)</span></span>

```
Remove-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-UseSSL]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="3eac0-108">URI</span><span class="sxs-lookup"><span data-stu-id="3eac0-108">URI</span></span>

```
Remove-WSManInstance [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="3eac0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3eac0-109">DESCRIPTION</span></span>

<span data-ttu-id="3eac0-110">Командлет **Remove-WSManInstance** удаляет экземпляр ресурса управления, указанный в параметрах *resourceUri* и *selector* .</span><span class="sxs-lookup"><span data-stu-id="3eac0-110">The **Remove-WSManInstance** cmdlet deletes an instance of a management resource that is specified in the *ResourceURI* and *SelectorSet* parameters.</span></span>

<span data-ttu-id="3eac0-111">Для удаления экземпляра ресурса управления этот командлет использует соединение/транспортный уровень службы удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="3eac0-111">This cmdlet uses the WinRM connection/transport layer to delete the management resource instance.</span></span>

## <span data-ttu-id="3eac0-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="3eac0-112">EXAMPLES</span></span>

### <span data-ttu-id="3eac0-113">Пример 1. Удаление прослушивателя</span><span class="sxs-lookup"><span data-stu-id="3eac0-113">Example 1: Delete a listener</span></span>

```
PS C:\> Remove-WSManInstance -ResourceUri winrm/config/Listener -SelectorSet Address=test.fabrikam.com;Transport=http
```

<span data-ttu-id="3eac0-114">Эта команда удаляет прослушиватель WS-Management HTTP на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3eac0-114">This command deletes the WS-Management HTTP listener on a computer.</span></span>

## <span data-ttu-id="3eac0-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3eac0-115">PARAMETERS</span></span>

### <span data-ttu-id="3eac0-116">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="3eac0-116">-ApplicationName</span></span>

<span data-ttu-id="3eac0-117">Указывает имя приложения в соединении.</span><span class="sxs-lookup"><span data-stu-id="3eac0-117">Specifies the application name in the connection.</span></span>
<span data-ttu-id="3eac0-118">Значением параметра *applicationName* по умолчанию является WSMan.</span><span class="sxs-lookup"><span data-stu-id="3eac0-118">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="3eac0-119">Полный идентификатор для удаленной конечной точки имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="3eac0-119">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="3eac0-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="3eac0-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="3eac0-121">Пример: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="3eac0-121">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="3eac0-122">Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.</span><span class="sxs-lookup"><span data-stu-id="3eac0-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="3eac0-123">Значение по умолчанию (WSMAN) подходит для большинства задач.</span><span class="sxs-lookup"><span data-stu-id="3eac0-123">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="3eac0-124">Этот параметр предназначен для использования, если многие компьютеры устанавливают удаленные подключения к одному компьютеру, на котором работает PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3eac0-124">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="3eac0-125">В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="3eac0-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="3eac0-126">-Authentication</span><span class="sxs-lookup"><span data-stu-id="3eac0-126">-Authentication</span></span>

<span data-ttu-id="3eac0-127">Задает способ проверки подлинности, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="3eac0-127">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="3eac0-128">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3eac0-128">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3eac0-129">Обычные.</span><span class="sxs-lookup"><span data-stu-id="3eac0-129">Basic.</span></span>
<span data-ttu-id="3eac0-130">схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="3eac0-130">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="3eac0-131">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3eac0-131">Default.</span></span>
<span data-ttu-id="3eac0-132">использование метода аутентификации, реализованного протоколом WS-Management.</span><span class="sxs-lookup"><span data-stu-id="3eac0-132">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="3eac0-133">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3eac0-133">This is the default.</span></span>
- <span data-ttu-id="3eac0-134">Дайджест.</span><span class="sxs-lookup"><span data-stu-id="3eac0-134">Digest.</span></span>
<span data-ttu-id="3eac0-135">это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="3eac0-135">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="3eac0-136">Kerberos —</span><span class="sxs-lookup"><span data-stu-id="3eac0-136">Kerberos.</span></span>
<span data-ttu-id="3eac0-137">клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3eac0-137">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="3eac0-138">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="3eac0-138">Negotiate.</span></span>
<span data-ttu-id="3eac0-139">это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="3eac0-139">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="3eac0-140">Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.</span><span class="sxs-lookup"><span data-stu-id="3eac0-140">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="3eac0-141">CredSSP —</span><span class="sxs-lookup"><span data-stu-id="3eac0-141">CredSSP.</span></span>
<span data-ttu-id="3eac0-142">использование проверки подлинности CredSSP, которая позволяет пользователю делегировать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="3eac0-142">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="3eac0-143">Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3eac0-143">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="3eac0-144">Внимание! CredSSP делегирует учетные данные пользователя с локального на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="3eac0-144">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="3eac0-145">Это повышает угрозу безопасности при работе в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="3eac0-145">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="3eac0-146">Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="3eac0-146">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="3eac0-147">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="3eac0-147">-CertificateThumbprint</span></span>

<span data-ttu-id="3eac0-148">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="3eac0-148">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="3eac0-149">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="3eac0-149">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="3eac0-150">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="3eac0-150">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="3eac0-151">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="3eac0-151">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="3eac0-152">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="3eac0-152">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="3eac0-153">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3eac0-153">-ComputerName</span></span>

<span data-ttu-id="3eac0-154">Задает имя компьютера, для которого требуется выполнить операцию управления.</span><span class="sxs-lookup"><span data-stu-id="3eac0-154">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="3eac0-155">Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="3eac0-155">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="3eac0-156">Для указания локального компьютера используйте его имя, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="3eac0-156">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="3eac0-157">Локальный компьютер используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3eac0-157">The local computer is the default.</span></span>
<span data-ttu-id="3eac0-158">Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="3eac0-158">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="3eac0-159">Можно передать значение этого параметра в командлет.</span><span class="sxs-lookup"><span data-stu-id="3eac0-159">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="3eac0-160">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="3eac0-160">-ConnectionURI</span></span>

<span data-ttu-id="3eac0-161">Указывает конечную точку соединения.</span><span class="sxs-lookup"><span data-stu-id="3eac0-161">Specifies the connection endpoint.</span></span>
<span data-ttu-id="3eac0-162">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="3eac0-162">The format of this string is as follows:</span></span>

<span data-ttu-id="3eac0-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="3eac0-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="3eac0-164">Следующая строка представляет собой правильно отформатированное значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3eac0-164">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="3eac0-165">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="3eac0-165">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="3eac0-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="3eac0-166">-Credential</span></span>

<span data-ttu-id="3eac0-167">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="3eac0-167">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="3eac0-168">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="3eac0-168">The default is the current user.</span></span>
<span data-ttu-id="3eac0-169">Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="3eac0-169">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="3eac0-170">Или введите объект **PSCredential** , например, возвращаемый командлетом Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="3eac0-170">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="3eac0-171">При вводе имени пользователя этот командлет запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="3eac0-171">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="3eac0-172">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="3eac0-172">-OptionSet</span></span>

<span data-ttu-id="3eac0-173">Указывает набор параметров в службе, чтобы изменить или уточнить характер запроса.</span><span class="sxs-lookup"><span data-stu-id="3eac0-173">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="3eac0-174">Это похоже на ключи, используемые в оболочках командной строки, так как они зависят от конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="3eac0-174">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="3eac0-175">Можно указать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="3eac0-175">Any number of options can be specified.</span></span>

<span data-ttu-id="3eac0-176">В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:</span><span class="sxs-lookup"><span data-stu-id="3eac0-176">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="3eac0-177">-Port</span><span class="sxs-lookup"><span data-stu-id="3eac0-177">-Port</span></span>

<span data-ttu-id="3eac0-178">Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="3eac0-178">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="3eac0-179">Если транспортом является HTTP, порт по умолчанию равен 80.</span><span class="sxs-lookup"><span data-stu-id="3eac0-179">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="3eac0-180">Если транспортом является HTTPS, порт по умолчанию равен 443.</span><span class="sxs-lookup"><span data-stu-id="3eac0-180">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="3eac0-181">При использовании протокола HTTPS в качестве транспорта значение параметра *ComputerName* должно совпадать с общим именем сертификата сервера (CN).</span><span class="sxs-lookup"><span data-stu-id="3eac0-181">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="3eac0-182">Но если параметр *SkipCNCheck* указан в составе параметра *SessionOption* , то общее имя сертификата сервера может отличаться от имени узла сервера.</span><span class="sxs-lookup"><span data-stu-id="3eac0-182">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="3eac0-183">Параметр *SkipCNCheck* следует использовать только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3eac0-183">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="3eac0-184">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="3eac0-184">-ResourceURI</span></span>

<span data-ttu-id="3eac0-185">Указывает URI класса или экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="3eac0-185">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="3eac0-186">URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3eac0-186">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="3eac0-187">URI состоит из префикса и пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="3eac0-187">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="3eac0-188">Пример:</span><span class="sxs-lookup"><span data-stu-id="3eac0-188">For example:</span></span>

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

### <span data-ttu-id="3eac0-189">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="3eac0-189">-SelectorSet</span></span>

<span data-ttu-id="3eac0-190">Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.</span><span class="sxs-lookup"><span data-stu-id="3eac0-190">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="3eac0-191">Параметр *selector* используется, если существует более одного экземпляра ресурса.</span><span class="sxs-lookup"><span data-stu-id="3eac0-191">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="3eac0-192">Значение *selector* должно быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="3eac0-192">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="3eac0-193">В следующем примере показано, как ввести значение для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="3eac0-193">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3eac0-194">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="3eac0-194">-SessionOption</span></span>

<span data-ttu-id="3eac0-195">Определяет расширенные параметры для сеанса WS-Management.</span><span class="sxs-lookup"><span data-stu-id="3eac0-195">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="3eac0-196">Введите объект **SessionOption** , созданный с помощью командлета New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="3eac0-196">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="3eac0-197">Чтобы получить дополнительные сведения о доступных параметрах, введите `Get-Help New-WSManSessionOption`.</span><span class="sxs-lookup"><span data-stu-id="3eac0-197">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="3eac0-198">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="3eac0-198">-UseSSL</span></span>

<span data-ttu-id="3eac0-199">Указывает, что для подключения к удаленному компьютеру используется протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="3eac0-199">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="3eac0-200">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="3eac0-200">By default, SSL is not used.</span></span>

<span data-ttu-id="3eac0-201">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="3eac0-201">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="3eac0-202">Параметр *UseSSL* позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="3eac0-202">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="3eac0-203">Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3eac0-203">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="3eac0-204">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3eac0-204">CommonParameters</span></span>

<span data-ttu-id="3eac0-205">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3eac0-205">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3eac0-206">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3eac0-206">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3eac0-207">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3eac0-207">INPUTS</span></span>

### <span data-ttu-id="3eac0-208">Нет</span><span class="sxs-lookup"><span data-stu-id="3eac0-208">None</span></span>

<span data-ttu-id="3eac0-209">Этот командлет не принимает никаких входных данных.</span><span class="sxs-lookup"><span data-stu-id="3eac0-209">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="3eac0-210">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3eac0-210">OUTPUTS</span></span>

### <span data-ttu-id="3eac0-211">Нет</span><span class="sxs-lookup"><span data-stu-id="3eac0-211">None</span></span>

<span data-ttu-id="3eac0-212">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3eac0-212">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3eac0-213">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3eac0-213">NOTES</span></span>

* <span data-ttu-id="3eac0-214">Командлет Remove-WmiObject инструментария управления Windows (WMI) имеет аналогичное назначение.</span><span class="sxs-lookup"><span data-stu-id="3eac0-214">The Remove-WmiObject cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span> <span data-ttu-id="3eac0-215">**Remove-WmiObject** использует DCOM-соединение/транспортный уровень для создания или обновления экземпляров WMI.</span><span class="sxs-lookup"><span data-stu-id="3eac0-215">**Remove-WmiObject** uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

*

## <span data-ttu-id="3eac0-216">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3eac0-216">RELATED LINKS</span></span>

[<span data-ttu-id="3eac0-217">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="3eac0-217">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="3eac0-218">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3eac0-218">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="3eac0-219">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="3eac0-219">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="3eac0-220">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3eac0-220">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="3eac0-221">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="3eac0-221">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="3eac0-222">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3eac0-222">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="3eac0-223">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="3eac0-223">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="3eac0-224">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3eac0-224">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="3eac0-225">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="3eac0-225">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="3eac0-226">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3eac0-226">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="3eac0-227">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="3eac0-227">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="3eac0-228">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="3eac0-228">Test-WSMan</span></span>](Test-WSMan.md)
