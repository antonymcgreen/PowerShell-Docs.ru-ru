---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 85b7f62686ed5f4aef267041ef624e3d7e388038
ms.sourcegitcommit: 9a53e53e7a3ef9ac0a212c61005efff9e9902452
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "93230469"
---
# <span data-ttu-id="4236c-103">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="4236c-103">New-CimSession</span></span>

## <span data-ttu-id="4236c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4236c-104">SYNOPSIS</span></span>

<span data-ttu-id="4236c-105">Создает сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="4236c-105">Creates a CIM session.</span></span>

## <span data-ttu-id="4236c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4236c-106">SYNTAX</span></span>

### <span data-ttu-id="4236c-107">Кредентиалпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4236c-107">CredentialParameterSet (Default)</span></span>

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### <span data-ttu-id="4236c-108">цертификатепараметерсет</span><span class="sxs-lookup"><span data-stu-id="4236c-108">CertificateParameterSet</span></span>

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## <span data-ttu-id="4236c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4236c-109">DESCRIPTION</span></span>

<span data-ttu-id="4236c-110">`New-CimSession`Командлет создает сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="4236c-110">The `New-CimSession` cmdlet creates a CIM session.</span></span> <span data-ttu-id="4236c-111">Сеанс CIM — это клиентский объект, представляющий подключение к локальному компьютеру или удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="4236c-111">A CIM session is a client-side object representing a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="4236c-112">Сеанс CIM содержит сведения о соединении, например **ComputerName** , используемый протокол или различные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="4236c-112">The CIM session contains information about the connection, such as **ComputerName** , the protocol used, or various identifiers.</span></span>

<span data-ttu-id="4236c-113">Этот командлет возвращает объект сеанса CIM, который может использоваться всеми другими командлетами CIM.</span><span class="sxs-lookup"><span data-stu-id="4236c-113">This cmdlet returns a CIM session object that can be used by all other CIM cmdlets.</span></span>

## <span data-ttu-id="4236c-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="4236c-114">EXAMPLES</span></span>

### <span data-ttu-id="4236c-115">Пример 1. Создание сеанса CIM с параметрами по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4236c-115">Example 1: Create a CIM session with default options</span></span>

<span data-ttu-id="4236c-116">В этом примере создается локальный сеанс CIM с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4236c-116">This example creates a local CIM session with default options.</span></span> <span data-ttu-id="4236c-117">Если параметр **ComputerName** не указан, `New-CimSession` создает сеанс DCOM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4236c-117">If **ComputerName** is not specified, `New-CimSession` creates a DCOM session to the local computer.</span></span>

```powershell
New-CimSession
```

### <span data-ttu-id="4236c-118">Пример 2. Создание сеанса CIM для определенного компьютера</span><span class="sxs-lookup"><span data-stu-id="4236c-118">Example 2: Create a CIM session to a specific computer</span></span>

<span data-ttu-id="4236c-119">В этом примере создается сеанс CIM для компьютера, указанного параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="4236c-119">This example creates a CIM session to the computer specified by **ComputerName** .</span></span>
<span data-ttu-id="4236c-120">По умолчанию `New-CimSession` создает сеанс WSMan при указании **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="4236c-120">By default, `New-CimSession` creates a WSMan session when **ComputerName** is specified.</span></span>

```powershell
New-CimSession -ComputerName Server01
```

### <span data-ttu-id="4236c-121">Пример 3. Создание сеанса CIM для нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="4236c-121">Example 3: Create a CIM session to multiple computers</span></span>

<span data-ttu-id="4236c-122">В этом примере создается сеанс CIM для каждого компьютера, указанного параметром **ComputerName** , в списке с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="4236c-122">This example creates a CIM session to each of the computers specified by **ComputerName** , in the comma separated list.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### <span data-ttu-id="4236c-123">Пример 4. Создание сеанса CIM с понятным именем</span><span class="sxs-lookup"><span data-stu-id="4236c-123">Example 4: Create a CIM session with a friendly name</span></span>

<span data-ttu-id="4236c-124">В этом примере создается удаленный сеанс CIM для каждого из компьютеров, указанных параметром **ComputerName** , в списке с разделителями-запятыми и назначается понятное имя новым сеансам путем указания **имени** .</span><span class="sxs-lookup"><span data-stu-id="4236c-124">This example creates a remote CIM session to each of the computers specified by **ComputerName** , in the comma separated list, and assigns a friendly name to the new sessions, by specifying **Name** .</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

<span data-ttu-id="4236c-125">Понятное имя сеанса CIM можно использовать для ссылки на сеанс в других командлетах CIM, например [Get-CimSession](Get-CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="4236c-125">You can use the friendly name of a CIM session to refer to the session in other CIM cmdlets, for example, [Get-CimSession](Get-CimSession.md).</span></span>

### <span data-ttu-id="4236c-126">Пример 5. Создание сеанса CIM для компьютера с помощью объекта PSCredential</span><span class="sxs-lookup"><span data-stu-id="4236c-126">Example 5: Create a CIM session to a computer using a PSCredential object</span></span>

<span data-ttu-id="4236c-127">В этом примере создается сеанс CIM с компьютером, указанным в параметре **ComputerName** , с использованием объекта **PSCredential** , указанного в параметре **Credential** , и типа проверки подлинности, заданного **проверкой подлинности** .</span><span class="sxs-lookup"><span data-stu-id="4236c-127">This example creates a CIM session to the computer specified by **ComputerName** , using the **PSCredential** object specified by **Credential** , and the authentication type specified by **Authentication** .</span></span>

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

<span data-ttu-id="4236c-128">Объект **PSCredential** можно создать с помощью [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) командлета.</span><span class="sxs-lookup"><span data-stu-id="4236c-128">You can create a **PSCredential** object using the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

### <span data-ttu-id="4236c-129">Пример 6. Создание сеанса CIM для компьютера с помощью определенного порта</span><span class="sxs-lookup"><span data-stu-id="4236c-129">Example 6: Create a CIM session to a computer using a specific port</span></span>

<span data-ttu-id="4236c-130">В этом примере создается сеанс CIM для компьютера, указанного параметром **ComputerName** , с использованием TCP-порта, заданного **портом** .</span><span class="sxs-lookup"><span data-stu-id="4236c-130">This example creates a CIM session to the computer specified by **ComputerName** using the TCP port specified by **Port** .</span></span>

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### <span data-ttu-id="4236c-131">Пример 7. Создание сеанса CIM с помощью DCOM</span><span class="sxs-lookup"><span data-stu-id="4236c-131">Example 7: Create a CIM session using DCOM</span></span>

<span data-ttu-id="4236c-132">В этом примере создается сеанс CIM с использованием протокола DCOM, а не WSMan.</span><span class="sxs-lookup"><span data-stu-id="4236c-132">This example creates a CIM session using the Distributed COM (DCOM) protocol instead of WSMan.</span></span>

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## <span data-ttu-id="4236c-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4236c-133">PARAMETERS</span></span>

### <span data-ttu-id="4236c-134">-Authentication</span><span class="sxs-lookup"><span data-stu-id="4236c-134">-Authentication</span></span>

<span data-ttu-id="4236c-135">Указывает тип проверки подлинности, используемый для учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="4236c-135">Specifies the authentication type used for the user's credentials.</span></span> <span data-ttu-id="4236c-136">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="4236c-136">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4236c-137">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="4236c-137">Default</span></span>
- <span data-ttu-id="4236c-138">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="4236c-138">Digest</span></span>
- <span data-ttu-id="4236c-139">Согласование</span><span class="sxs-lookup"><span data-stu-id="4236c-139">Negotiate</span></span>
- <span data-ttu-id="4236c-140">Базовый</span><span class="sxs-lookup"><span data-stu-id="4236c-140">Basic</span></span>
- <span data-ttu-id="4236c-141">Kerberos</span><span class="sxs-lookup"><span data-stu-id="4236c-141">Kerberos</span></span>
- <span data-ttu-id="4236c-142">нтлмдомаин</span><span class="sxs-lookup"><span data-stu-id="4236c-142">NtlmDomain</span></span>
- <span data-ttu-id="4236c-143">CredSsp</span><span class="sxs-lookup"><span data-stu-id="4236c-143">CredSsp</span></span>

<span data-ttu-id="4236c-144">Тип проверки подлинности **нтлмдомаин** нельзя использовать для подключения к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="4236c-144">You cannot use the **NtlmDomain** authentication type for connection to the local computer.</span></span> <span data-ttu-id="4236c-145">Проверка подлинности **CredSSP** доступна только в Windows Vista, windows Server 2008 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="4236c-145">**CredSSP** authentication is available only in Windows Vista, Windows Server 2008, and later versions of Windows.</span></span>

> [!CAUTION]
> <span data-ttu-id="4236c-146">Проверка подлинности поставщика службы безопасности учетных данных (CredSSP) предназначена для команд, требующих проверки подлинности в нескольких ресурсах, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="4236c-146">Credential Security Service Provider (CredSSP) authentication is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="4236c-147">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="4236c-147">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="4236c-148">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="4236c-148">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-149">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="4236c-149">-CertificateThumbprint</span></span>

<span data-ttu-id="4236c-150">Указывает сертификат цифрового открытого ключа (X. 509) учетной записи пользователя, имеющей разрешение на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="4236c-150">Specifies the digital public key certificate (X.509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="4236c-151">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="4236c-151">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="4236c-152">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="4236c-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="4236c-153">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="4236c-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="4236c-154">Чтобы получить отпечаток сертификата, используйте [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) командлеты или в поставщике сертификатов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4236c-154">To get a certificate thumbprint, use the [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) or [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets in the PowerShell Certificate Provider.</span></span>

<span data-ttu-id="4236c-155">Дополнительные сведения см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="4236c-155">For more information, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

```yaml
Type: System.String
Parameter Sets: CertificateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-156">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4236c-156">-ComputerName</span></span>

<span data-ttu-id="4236c-157">Указывает имя компьютера, на котором создается сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="4236c-157">Specifies the name of the computer to which to create the CIM session.</span></span> <span data-ttu-id="4236c-158">Укажите одно имя компьютера или несколько имен компьютеров, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="4236c-158">Specify either a single computer name, or multiple computer names separated by a comma.</span></span>

<span data-ttu-id="4236c-159">Если параметр **ComputerName** не указан, создается сеанс CIM для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="4236c-159">If **ComputerName** is not specified, a CIM session to the local computer is created.</span></span> <span data-ttu-id="4236c-160">Можно указать значение имени компьютера в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="4236c-160">You can specify the value for computer name in one of the following formats:</span></span>

- <span data-ttu-id="4236c-161">Одно или несколько имен NetBIOS</span><span class="sxs-lookup"><span data-stu-id="4236c-161">One or more NetBIOS names</span></span>
- <span data-ttu-id="4236c-162">Один или несколько IP-адресов</span><span class="sxs-lookup"><span data-stu-id="4236c-162">One or more IP addresses</span></span>
- <span data-ttu-id="4236c-163">Одно или несколько полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="4236c-163">One or more fully qualified domain names.</span></span>

<span data-ttu-id="4236c-164">Если компьютер находится в домене, отличном от домена пользователя, необходимо указать полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="4236c-164">If the computer is in a different domain than the user, you must specify the fully qualified domain name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="4236c-165">-Credential</span></span>

<span data-ttu-id="4236c-166">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="4236c-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="4236c-167">Если **учетные данные** не указаны, используется текущая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="4236c-167">If **Credential** is not specified, the current user account is used.</span></span>

<span data-ttu-id="4236c-168">Укажите значение **учетных данных** в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="4236c-168">Specify the value for **Credential** using one of the following formats:</span></span>

- <span data-ttu-id="4236c-169">Имя пользователя: "User01"</span><span class="sxs-lookup"><span data-stu-id="4236c-169">A user name: "User01"</span></span>
- <span data-ttu-id="4236c-170">Имя домена и имя пользователя: "Domain01\User01"</span><span class="sxs-lookup"><span data-stu-id="4236c-170">A domain name and a user name: "Domain01\User01"</span></span>
- <span data-ttu-id="4236c-171">Имя участника-пользователя: " User@Domain.com "</span><span class="sxs-lookup"><span data-stu-id="4236c-171">A user principal name: "User@Domain.com"</span></span>
- <span data-ttu-id="4236c-172">Объект PSCredential, например, возвращаемый [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) командлетом.</span><span class="sxs-lookup"><span data-stu-id="4236c-172">A PSCredential object, such as one returned by the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

<span data-ttu-id="4236c-173">При вводе имени пользователя запрашивается пароль.</span><span class="sxs-lookup"><span data-stu-id="4236c-173">When you type a user name, you are prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-174">-Name</span><span class="sxs-lookup"><span data-stu-id="4236c-174">-Name</span></span>

<span data-ttu-id="4236c-175">Указывает понятное имя для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="4236c-175">Specifies a friendly name for the CIM session.</span></span>

<span data-ttu-id="4236c-176">Имя можно использовать для ссылки на сеанс CIM при использовании других командлетов, например командлета [Get-CimSession](Get-CimSession.md) .</span><span class="sxs-lookup"><span data-stu-id="4236c-176">You can use the name to refer to the CIM session when using other cmdlets, such as the [Get-CimSession](Get-CimSession.md) cmdlet.</span></span>
<span data-ttu-id="4236c-177">Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="4236c-177">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-178">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="4236c-178">-OperationTimeoutSec</span></span>

<span data-ttu-id="4236c-179">Длительность, в течение которого командлет ожидает ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="4236c-179">Duration for which the cmdlet waits for a response from the server.</span></span>

<span data-ttu-id="4236c-180">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="4236c-180">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="4236c-181">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="4236c-181">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-182">-Port</span><span class="sxs-lookup"><span data-stu-id="4236c-182">-Port</span></span>

<span data-ttu-id="4236c-183">Задает сетевой порт на удаленном компьютере, используемый для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="4236c-183">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="4236c-184">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="4236c-184">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="4236c-185">Порты по умолчанию: 5985 (порт службы удаленного управления Windows для HTTP) и 5986 (порт службы удаленного управления Windows для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="4236c-185">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="4236c-186">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="4236c-186">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="4236c-187">Для настройки прослушивателя используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4236c-187">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

<span data-ttu-id="4236c-188">Не используйте параметр **Port** , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="4236c-188">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="4236c-189">Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="4236c-189">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="4236c-190">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4236c-190">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-191">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="4236c-191">-SessionOption</span></span>

<span data-ttu-id="4236c-192">Задает дополнительные параметры для нового сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="4236c-192">Sets advanced options for the new CIM session.</span></span> <span data-ttu-id="4236c-193">Введите имя объекта **Цимсессионоптион** , созданного с помощью [`New-CimSessionOption`](New-CimSessionOption.md) командлета.</span><span class="sxs-lookup"><span data-stu-id="4236c-193">Enter the name of a **CimSessionOption** object created using the [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-194">-Скиптестконнектион</span><span class="sxs-lookup"><span data-stu-id="4236c-194">-SkipTestConnection</span></span>

<span data-ttu-id="4236c-195">По умолчанию `New-CimSession` командлет устанавливает подключение к удаленной конечной точке WS-Management по двум причинам: чтобы убедиться, что удаленный сервер прослушивает номер порта, указанный с помощью параметра **Port** , и проверить указанные учетные данные учетной записи.</span><span class="sxs-lookup"><span data-stu-id="4236c-195">By default, the `New-CimSession` cmdlet establishes a connection with a remote WS-Management endpoint for two reasons: to verify that the remote server is listening on the port number that is specified using the **Port** parameter, and to verify the specified account credentials.</span></span> <span data-ttu-id="4236c-196">Проверка выполняется с помощью стандартной операции WS-Identity.</span><span class="sxs-lookup"><span data-stu-id="4236c-196">The verification is accomplished using a standard WS-Identity operation.</span></span> <span data-ttu-id="4236c-197">Можно добавить параметр **скиптестконнектион** , если конечная точка удаленного WS-Management не может использовать WS-Identify или сократить время передачи данных.</span><span class="sxs-lookup"><span data-stu-id="4236c-197">You can add the **SkipTestConnection** switch parameter if the remote WS-Management endpoint cannot use WS-Identify, or to reduce some data transmission time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4236c-198">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4236c-198">CommonParameters</span></span>

<span data-ttu-id="4236c-199">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4236c-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4236c-200">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4236c-200">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4236c-201">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4236c-201">INPUTS</span></span>

### <span data-ttu-id="4236c-202">Нет</span><span class="sxs-lookup"><span data-stu-id="4236c-202">None</span></span>

<span data-ttu-id="4236c-203">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="4236c-203">This cmdlet accepts no inputs.</span></span>

## <span data-ttu-id="4236c-204">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4236c-204">OUTPUTS</span></span>

### <span data-ttu-id="4236c-205">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="4236c-205">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="4236c-206">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4236c-206">NOTES</span></span>

## <span data-ttu-id="4236c-207">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4236c-207">RELATED LINKS</span></span>

[<span data-ttu-id="4236c-208">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="4236c-208">Get-ChildItem</span></span>](../Microsoft.Powershell.Management/Get-ChildItem.md)

[<span data-ttu-id="4236c-209">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="4236c-209">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="4236c-210">Get-Item</span><span class="sxs-lookup"><span data-stu-id="4236c-210">Get-Item</span></span>](../Microsoft.Powershell.Management/Get-Item.md)

[<span data-ttu-id="4236c-211">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="4236c-211">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="4236c-212">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="4236c-212">Remove-CimSession</span></span>](Remove-CimSession.md)

[<span data-ttu-id="4236c-213">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="4236c-213">New-CimSessionOption</span></span>](New-CimSessionOption.md)

[<span data-ttu-id="4236c-214">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="4236c-214">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)
