---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 59e70f75ac9d822db00419d84055d92a3882c11d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602845"
---
# <span data-ttu-id="5eba1-102">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="5eba1-102">New-CimSession</span></span>

## <span data-ttu-id="5eba1-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5eba1-103">SYNOPSIS</span></span>

<span data-ttu-id="5eba1-104">Создает сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="5eba1-104">Creates a CIM session.</span></span>

## <span data-ttu-id="5eba1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5eba1-105">SYNTAX</span></span>

### <span data-ttu-id="5eba1-106">Кредентиалпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5eba1-106">CredentialParameterSet (Default)</span></span>

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### <span data-ttu-id="5eba1-107">цертификатепараметерсет</span><span class="sxs-lookup"><span data-stu-id="5eba1-107">CertificateParameterSet</span></span>

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## <span data-ttu-id="5eba1-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5eba1-108">DESCRIPTION</span></span>

<span data-ttu-id="5eba1-109">`New-CimSession`Командлет создает сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="5eba1-109">The `New-CimSession` cmdlet creates a CIM session.</span></span> <span data-ttu-id="5eba1-110">Сеанс CIM — это клиентский объект, представляющий подключение к локальному компьютеру или удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5eba1-110">A CIM session is a client-side object representing a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="5eba1-111">Сеанс CIM содержит сведения о соединении, например **ComputerName**, используемый протокол или различные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="5eba1-111">The CIM session contains information about the connection, such as **ComputerName**, the protocol used, or various identifiers.</span></span>

<span data-ttu-id="5eba1-112">Этот командлет возвращает объект сеанса CIM, который может использоваться всеми другими командлетами CIM.</span><span class="sxs-lookup"><span data-stu-id="5eba1-112">This cmdlet returns a CIM session object that can be used by all other CIM cmdlets.</span></span>

## <span data-ttu-id="5eba1-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="5eba1-113">EXAMPLES</span></span>

### <span data-ttu-id="5eba1-114">Пример 1. Создание сеанса CIM с параметрами по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5eba1-114">Example 1: Create a CIM session with default options</span></span>

<span data-ttu-id="5eba1-115">В этом примере создается локальный сеанс CIM с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5eba1-115">This example creates a local CIM session with default options.</span></span> <span data-ttu-id="5eba1-116">Если параметр **ComputerName** не указан, `New-CimSession` создает сеанс DCOM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5eba1-116">If **ComputerName** is not specified, `New-CimSession` creates a DCOM session to the local computer.</span></span>

```powershell
New-CimSession
```

### <span data-ttu-id="5eba1-117">Пример 2. Создание сеанса CIM для определенного компьютера</span><span class="sxs-lookup"><span data-stu-id="5eba1-117">Example 2: Create a CIM session to a specific computer</span></span>

<span data-ttu-id="5eba1-118">В этом примере создается сеанс CIM для компьютера, указанного параметром **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="5eba1-118">This example creates a CIM session to the computer specified by **ComputerName**.</span></span>
<span data-ttu-id="5eba1-119">По умолчанию `New-CimSession` создает сеанс WSMan при указании **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="5eba1-119">By default, `New-CimSession` creates a WSMan session when **ComputerName** is specified.</span></span>

```powershell
New-CimSession -ComputerName Server01
```

### <span data-ttu-id="5eba1-120">Пример 3. Создание сеанса CIM для нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="5eba1-120">Example 3: Create a CIM session to multiple computers</span></span>

<span data-ttu-id="5eba1-121">В этом примере создается сеанс CIM для каждого компьютера, указанного параметром **ComputerName**, в списке с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="5eba1-121">This example creates a CIM session to each of the computers specified by **ComputerName**, in the comma separated list.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### <span data-ttu-id="5eba1-122">Пример 4. Создание сеанса CIM с понятным именем</span><span class="sxs-lookup"><span data-stu-id="5eba1-122">Example 4: Create a CIM session with a friendly name</span></span>

<span data-ttu-id="5eba1-123">В этом примере создается удаленный сеанс CIM для каждого из компьютеров, указанных параметром **ComputerName**, в списке с разделителями-запятыми и назначается понятное имя новым сеансам путем указания **имени**.</span><span class="sxs-lookup"><span data-stu-id="5eba1-123">This example creates a remote CIM session to each of the computers specified by **ComputerName**, in the comma separated list, and assigns a friendly name to the new sessions, by specifying **Name**.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

<span data-ttu-id="5eba1-124">Понятное имя сеанса CIM можно использовать для ссылки на сеанс в других командлетах CIM, например [Get-CimSession](Get-CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="5eba1-124">You can use the friendly name of a CIM session to refer to the session in other CIM cmdlets, for example, [Get-CimSession](Get-CimSession.md).</span></span>

### <span data-ttu-id="5eba1-125">Пример 5. Создание сеанса CIM для компьютера с помощью объекта PSCredential</span><span class="sxs-lookup"><span data-stu-id="5eba1-125">Example 5: Create a CIM session to a computer using a PSCredential object</span></span>

<span data-ttu-id="5eba1-126">В этом примере создается сеанс CIM с компьютером, указанным в параметре **ComputerName**, с использованием объекта **PSCredential** , указанного в параметре **Credential**, и типа проверки подлинности, заданного **проверкой подлинности**.</span><span class="sxs-lookup"><span data-stu-id="5eba1-126">This example creates a CIM session to the computer specified by **ComputerName**, using the **PSCredential** object specified by **Credential**, and the authentication type specified by **Authentication**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

<span data-ttu-id="5eba1-127">Объект **PSCredential** можно создать с помощью [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) командлета.</span><span class="sxs-lookup"><span data-stu-id="5eba1-127">You can create a **PSCredential** object using the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

### <span data-ttu-id="5eba1-128">Пример 6. Создание сеанса CIM для компьютера с помощью определенного порта</span><span class="sxs-lookup"><span data-stu-id="5eba1-128">Example 6: Create a CIM session to a computer using a specific port</span></span>

<span data-ttu-id="5eba1-129">В этом примере создается сеанс CIM для компьютера, указанного параметром **ComputerName** , с использованием TCP-порта, заданного **портом**.</span><span class="sxs-lookup"><span data-stu-id="5eba1-129">This example creates a CIM session to the computer specified by **ComputerName** using the TCP port specified by **Port**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### <span data-ttu-id="5eba1-130">Пример 7. Создание сеанса CIM с помощью DCOM</span><span class="sxs-lookup"><span data-stu-id="5eba1-130">Example 7: Create a CIM session using DCOM</span></span>

<span data-ttu-id="5eba1-131">В этом примере создается сеанс CIM с использованием протокола DCOM, а не WSMan.</span><span class="sxs-lookup"><span data-stu-id="5eba1-131">This example creates a CIM session using the Distributed COM (DCOM) protocol instead of WSMan.</span></span>

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## <span data-ttu-id="5eba1-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5eba1-132">PARAMETERS</span></span>

### <span data-ttu-id="5eba1-133">-Authentication</span><span class="sxs-lookup"><span data-stu-id="5eba1-133">-Authentication</span></span>

<span data-ttu-id="5eba1-134">Указывает тип проверки подлинности, используемый для учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="5eba1-134">Specifies the authentication type used for the user's credentials.</span></span> <span data-ttu-id="5eba1-135">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5eba1-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5eba1-136">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="5eba1-136">Default</span></span>
- <span data-ttu-id="5eba1-137">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="5eba1-137">Digest</span></span>
- <span data-ttu-id="5eba1-138">Согласование</span><span class="sxs-lookup"><span data-stu-id="5eba1-138">Negotiate</span></span>
- <span data-ttu-id="5eba1-139">Basic</span><span class="sxs-lookup"><span data-stu-id="5eba1-139">Basic</span></span>
- <span data-ttu-id="5eba1-140">Kerberos</span><span class="sxs-lookup"><span data-stu-id="5eba1-140">Kerberos</span></span>
- <span data-ttu-id="5eba1-141">нтлмдомаин</span><span class="sxs-lookup"><span data-stu-id="5eba1-141">NtlmDomain</span></span>
- <span data-ttu-id="5eba1-142">CredSsp</span><span class="sxs-lookup"><span data-stu-id="5eba1-142">CredSsp</span></span>

<span data-ttu-id="5eba1-143">Тип проверки подлинности **нтлмдомаин** нельзя использовать для подключения к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5eba1-143">You cannot use the **NtlmDomain** authentication type for connection to the local computer.</span></span> <span data-ttu-id="5eba1-144">Проверка подлинности **CredSSP** доступна только в Windows Vista, windows Server 2008 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="5eba1-144">**CredSSP** authentication is available only in Windows Vista, Windows Server 2008, and later versions of Windows.</span></span>

> [!CAUTION]
> <span data-ttu-id="5eba1-145">Проверка подлинности поставщика службы безопасности учетных данных (CredSSP) предназначена для команд, требующих проверки подлинности в нескольких ресурсах, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="5eba1-145">Credential Security Service Provider (CredSSP) authentication is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="5eba1-146">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="5eba1-146">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="5eba1-147">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="5eba1-147">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="5eba1-148">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="5eba1-148">-CertificateThumbprint</span></span>

<span data-ttu-id="5eba1-149">Указывает сертификат цифрового открытого ключа (X. 509) учетной записи пользователя, имеющей разрешение на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="5eba1-149">Specifies the digital public key certificate (X.509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="5eba1-150">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="5eba1-150">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="5eba1-151">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="5eba1-151">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="5eba1-152">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="5eba1-152">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="5eba1-153">Чтобы получить отпечаток сертификата, используйте [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) командлеты или в поставщике сертификатов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5eba1-153">To get a certificate thumbprint, use the [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) or [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets in the PowerShell Certificate Provider.</span></span>

<span data-ttu-id="5eba1-154">Дополнительные сведения см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="5eba1-154">For more information, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

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

### <span data-ttu-id="5eba1-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="5eba1-155">-ComputerName</span></span>

<span data-ttu-id="5eba1-156">Указывает имя компьютера, на котором создается сеанс CIM.</span><span class="sxs-lookup"><span data-stu-id="5eba1-156">Specifies the name of the computer to which to create the CIM session.</span></span> <span data-ttu-id="5eba1-157">Укажите одно имя компьютера или несколько имен компьютеров, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="5eba1-157">Specify either a single computer name, or multiple computer names separated by a comma.</span></span>

<span data-ttu-id="5eba1-158">Если параметр **ComputerName** не указан, создается сеанс CIM для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="5eba1-158">If **ComputerName** is not specified, a CIM session to the local computer is created.</span></span> <span data-ttu-id="5eba1-159">Можно указать значение имени компьютера в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="5eba1-159">You can specify the value for computer name in one of the following formats:</span></span>

- <span data-ttu-id="5eba1-160">Одно или несколько имен NetBIOS</span><span class="sxs-lookup"><span data-stu-id="5eba1-160">One or more NetBIOS names</span></span>
- <span data-ttu-id="5eba1-161">Один или несколько IP-адресов</span><span class="sxs-lookup"><span data-stu-id="5eba1-161">One or more IP addresses</span></span>
- <span data-ttu-id="5eba1-162">Одно или несколько полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="5eba1-162">One or more fully qualified domain names.</span></span>

<span data-ttu-id="5eba1-163">Если компьютер находится в домене, отличном от домена пользователя, необходимо указать полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="5eba1-163">If the computer is in a different domain than the user, you must specify the fully qualified domain name.</span></span>

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

### <span data-ttu-id="5eba1-164">-Credential</span><span class="sxs-lookup"><span data-stu-id="5eba1-164">-Credential</span></span>

<span data-ttu-id="5eba1-165">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="5eba1-165">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="5eba1-166">Если **учетные данные** не указаны, используется текущая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="5eba1-166">If **Credential** is not specified, the current user account is used.</span></span>

<span data-ttu-id="5eba1-167">Укажите значение **учетных данных** в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="5eba1-167">Specify the value for **Credential** using one of the following formats:</span></span>

- <span data-ttu-id="5eba1-168">Имя пользователя: "User01"</span><span class="sxs-lookup"><span data-stu-id="5eba1-168">A user name: "User01"</span></span>
- <span data-ttu-id="5eba1-169">Имя домена и имя пользователя: "Domain01\User01"</span><span class="sxs-lookup"><span data-stu-id="5eba1-169">A domain name and a user name: "Domain01\User01"</span></span>
- <span data-ttu-id="5eba1-170">Имя участника-пользователя: " User@Domain.com "</span><span class="sxs-lookup"><span data-stu-id="5eba1-170">A user principal name: "User@Domain.com"</span></span>
- <span data-ttu-id="5eba1-171">Объект PSCredential, например, возвращаемый [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) командлетом.</span><span class="sxs-lookup"><span data-stu-id="5eba1-171">A PSCredential object, such as one returned by the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

<span data-ttu-id="5eba1-172">При вводе имени пользователя запрашивается пароль.</span><span class="sxs-lookup"><span data-stu-id="5eba1-172">When you type a user name, you are prompted for a password.</span></span>

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

### <span data-ttu-id="5eba1-173">-Name</span><span class="sxs-lookup"><span data-stu-id="5eba1-173">-Name</span></span>

<span data-ttu-id="5eba1-174">Указывает понятное имя для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="5eba1-174">Specifies a friendly name for the CIM session.</span></span>

<span data-ttu-id="5eba1-175">Имя можно использовать для ссылки на сеанс CIM при использовании других командлетов, например командлета [Get-CimSession](Get-CimSession.md) .</span><span class="sxs-lookup"><span data-stu-id="5eba1-175">You can use the name to refer to the CIM session when using other cmdlets, such as the [Get-CimSession](Get-CimSession.md) cmdlet.</span></span>
<span data-ttu-id="5eba1-176">Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5eba1-176">The name is not required to be unique to the computer or the current session.</span></span>

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

### <span data-ttu-id="5eba1-177">-Оператионтимеаутсек</span><span class="sxs-lookup"><span data-stu-id="5eba1-177">-OperationTimeoutSec</span></span>

<span data-ttu-id="5eba1-178">Длительность, в течение которого командлет ожидает ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="5eba1-178">Duration for which the cmdlet waits for a response from the server.</span></span>

<span data-ttu-id="5eba1-179">По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="5eba1-179">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="5eba1-180">Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.</span><span class="sxs-lookup"><span data-stu-id="5eba1-180">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="5eba1-181">-Port</span><span class="sxs-lookup"><span data-stu-id="5eba1-181">-Port</span></span>

<span data-ttu-id="5eba1-182">Задает сетевой порт на удаленном компьютере, используемый для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="5eba1-182">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="5eba1-183">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="5eba1-183">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="5eba1-184">Порты по умолчанию: 5985 (порт службы удаленного управления Windows для HTTP) и 5986 (порт службы удаленного управления Windows для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="5eba1-184">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="5eba1-185">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="5eba1-185">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="5eba1-186">Для настройки прослушивателя используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5eba1-186">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

<span data-ttu-id="5eba1-187">Не используйте параметр **Port**, если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="5eba1-187">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="5eba1-188">Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="5eba1-188">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="5eba1-189">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5eba1-189">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="5eba1-190">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="5eba1-190">-SessionOption</span></span>

<span data-ttu-id="5eba1-191">Задает дополнительные параметры для нового сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="5eba1-191">Sets advanced options for the new CIM session.</span></span> <span data-ttu-id="5eba1-192">Введите имя объекта **Цимсессионоптион** , созданного с помощью [`New-CimSessionOption`](New-CimSessionOption.md) командлета.</span><span class="sxs-lookup"><span data-stu-id="5eba1-192">Enter the name of a **CimSessionOption** object created using the [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span></span>

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

### <span data-ttu-id="5eba1-193">-Скиптестконнектион</span><span class="sxs-lookup"><span data-stu-id="5eba1-193">-SkipTestConnection</span></span>

<span data-ttu-id="5eba1-194">По умолчанию `New-CimSession` командлет устанавливает подключение к удаленной конечной точке WS-Management по двум причинам: чтобы убедиться, что удаленный сервер прослушивает номер порта, указанный с помощью параметра **Port** , и проверить указанные учетные данные учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5eba1-194">By default, the `New-CimSession` cmdlet establishes a connection with a remote WS-Management endpoint for two reasons: to verify that the remote server is listening on the port number that is specified using the **Port** parameter, and to verify the specified account credentials.</span></span> <span data-ttu-id="5eba1-195">Проверка выполняется с помощью стандартной операции WS-Identity.</span><span class="sxs-lookup"><span data-stu-id="5eba1-195">The verification is accomplished using a standard WS-Identity operation.</span></span> <span data-ttu-id="5eba1-196">Можно добавить параметр **скиптестконнектион** , если конечная точка удаленного WS-Management не может использовать WS-Identify или сократить время передачи данных.</span><span class="sxs-lookup"><span data-stu-id="5eba1-196">You can add the **SkipTestConnection** switch parameter if the remote WS-Management endpoint cannot use WS-Identify, or to reduce some data transmission time.</span></span>

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

### <span data-ttu-id="5eba1-197">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5eba1-197">CommonParameters</span></span>

<span data-ttu-id="5eba1-198">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5eba1-198">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5eba1-199">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5eba1-199">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5eba1-200">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5eba1-200">INPUTS</span></span>

### <span data-ttu-id="5eba1-201">None</span><span class="sxs-lookup"><span data-stu-id="5eba1-201">None</span></span>

<span data-ttu-id="5eba1-202">Этот командлет не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="5eba1-202">This cmdlet accepts no inputs.</span></span>

## <span data-ttu-id="5eba1-203">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5eba1-203">OUTPUTS</span></span>

### <span data-ttu-id="5eba1-204">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="5eba1-204">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="5eba1-205">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5eba1-205">NOTES</span></span>

## <span data-ttu-id="5eba1-206">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5eba1-206">RELATED LINKS</span></span>

[<span data-ttu-id="5eba1-207">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="5eba1-207">Get-ChildItem</span></span>](../Microsoft.Powershell.Management/Get-ChildItem.md)

[<span data-ttu-id="5eba1-208">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="5eba1-208">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="5eba1-209">Get-Item</span><span class="sxs-lookup"><span data-stu-id="5eba1-209">Get-Item</span></span>](../Microsoft.Powershell.Management/Get-Item.md)

[<span data-ttu-id="5eba1-210">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="5eba1-210">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="5eba1-211">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="5eba1-211">Remove-CimSession</span></span>](Remove-CimSession.md)

[<span data-ttu-id="5eba1-212">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="5eba1-212">New-CimSessionOption</span></span>](New-CimSessionOption.md)

[<span data-ttu-id="5eba1-213">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="5eba1-213">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

