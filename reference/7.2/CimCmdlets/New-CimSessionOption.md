---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 54a2ca8a28d54bfe1d9676acdaace4592f62620f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599983"
---
# <span data-ttu-id="27a8a-102">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="27a8a-102">New-CimSessionOption</span></span>

## <span data-ttu-id="27a8a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="27a8a-103">SYNOPSIS</span></span>
<span data-ttu-id="27a8a-104">Задает дополнительные параметры для командлета New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="27a8a-104">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="27a8a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27a8a-105">SYNTAX</span></span>

### <span data-ttu-id="27a8a-106">Протоколтипесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="27a8a-106">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="27a8a-107">всманпараметерсет</span><span class="sxs-lookup"><span data-stu-id="27a8a-107">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="27a8a-108">дкомпараметерсет</span><span class="sxs-lookup"><span data-stu-id="27a8a-108">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="27a8a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27a8a-109">DESCRIPTION</span></span>

<span data-ttu-id="27a8a-110">`New-CimSessionOption`Командлет создает экземпляр объекта параметров сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-110">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="27a8a-111">Используйте объект параметров сеанса CIM в качестве входных данных для `New-CimSession` командлета, чтобы указать параметры для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-111">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="27a8a-112">Этот командлет имеет два набора параметров: один для параметров WsMan и один для параметров распределенной модели объектов компонента (DCOM).</span><span class="sxs-lookup"><span data-stu-id="27a8a-112">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="27a8a-113">В зависимости от используемых параметров командлет возвращает либо экземпляр параметров сеанса DCOM, либо метод, который возвращает параметры сеанса WsMan.</span><span class="sxs-lookup"><span data-stu-id="27a8a-113">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="27a8a-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="27a8a-114">EXAMPLES</span></span>

### <span data-ttu-id="27a8a-115">Пример 1. Создание объекта параметров сеанса CIM для DCOM</span><span class="sxs-lookup"><span data-stu-id="27a8a-115">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="27a8a-116">В этом примере создается объект параметров сеанса CIM для протокола DCOM и сохраняется в переменной с именем `$so` .</span><span class="sxs-lookup"><span data-stu-id="27a8a-116">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="27a8a-117">После этого содержимое переменной передается в `New-CimSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="27a8a-117">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="27a8a-118">`New-CimSession` затем создает новый сеанс CIM с удаленным сервером с именем Server01, используя параметры, определенные в переменной.</span><span class="sxs-lookup"><span data-stu-id="27a8a-118">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="27a8a-119">Пример 2. Создание объекта параметров сеанса CIM для WsMan</span><span class="sxs-lookup"><span data-stu-id="27a8a-119">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="27a8a-120">В этом примере создается объект параметров сеанса CIM для протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="27a8a-120">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="27a8a-121">Объект содержит конфигурацию режима проверки подлинности **Kerberos** , заданного параметром **проксяусентикатион** , учетные данные, указанные параметром **ProxyCredential** , и указывает, что команда должна пропустить проверку ЦС, пропустить проверку CN и использовать SSL.</span><span class="sxs-lookup"><span data-stu-id="27a8a-121">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="27a8a-122">Пример 3. Создание объекта параметров сеанса CIM с заданной культурой</span><span class="sxs-lookup"><span data-stu-id="27a8a-122">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="27a8a-123">В этом примере указывается язык и региональные параметры, используемые для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-123">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="27a8a-124">По умолчанию при выполнении операций используется язык и региональные параметры клиента.</span><span class="sxs-lookup"><span data-stu-id="27a8a-124">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="27a8a-125">Однако язык и региональные параметры по умолчанию можно переопределить с помощью параметра **culture** .</span><span class="sxs-lookup"><span data-stu-id="27a8a-125">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="27a8a-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27a8a-126">PARAMETERS</span></span>

### <span data-ttu-id="27a8a-127">-Culture</span><span class="sxs-lookup"><span data-stu-id="27a8a-127">-Culture</span></span>

<span data-ttu-id="27a8a-128">Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-128">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="27a8a-129">Укажите значение этого параметра в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="27a8a-129">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="27a8a-130">Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например "en-US".</span><span class="sxs-lookup"><span data-stu-id="27a8a-130">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="27a8a-131">Переменная, содержащая объект **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="27a8a-131">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="27a8a-132">Команда, которая получает объект **CultureInfo** , например [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span><span class="sxs-lookup"><span data-stu-id="27a8a-132">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-133">-ЕнкодепортинсервицепринЦипалнаме</span><span class="sxs-lookup"><span data-stu-id="27a8a-133">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="27a8a-134">Указывает, что соединение Kerberos подключается к службе, имя участника-службы (SPN) которого содержит номер порта службы.</span><span class="sxs-lookup"><span data-stu-id="27a8a-134">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="27a8a-135">Этот тип соединения не является распространенным.</span><span class="sxs-lookup"><span data-stu-id="27a8a-135">This type of connection is not common.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-136">-Encoding</span><span class="sxs-lookup"><span data-stu-id="27a8a-136">-Encoding</span></span>

<span data-ttu-id="27a8a-137">Указывает кодировку, используемую для протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="27a8a-137">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="27a8a-138">Допустимые значения для этого параметра: **Default**, **Utf8** или **Utf16**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-138">The acceptable values for this parameter are: **Default**, **Utf8**, or **Utf16**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PacketEncoding
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Utf8, Utf16

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-139">-Хттппрефикс</span><span class="sxs-lookup"><span data-stu-id="27a8a-139">-HttpPrefix</span></span>

<span data-ttu-id="27a8a-140">Указывает часть URL-адреса HTTP после имени компьютера и номера порта.</span><span class="sxs-lookup"><span data-stu-id="27a8a-140">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="27a8a-141">Изменение этого не является распространенным.</span><span class="sxs-lookup"><span data-stu-id="27a8a-141">Changing this is not common.</span></span> <span data-ttu-id="27a8a-142">По умолчанию значение этого параметра равно **/всман**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-142">By default, the value of this parameter is **/wsman**.</span></span>

```yaml
Type: System.Uri
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-143">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="27a8a-143">-Impersonation</span></span>

<span data-ttu-id="27a8a-144">Создает сеанс DCOM для инструментарий управления Windows (WMI) (WMI) с использованием олицетворения.</span><span class="sxs-lookup"><span data-stu-id="27a8a-144">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="27a8a-145">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="27a8a-145">Valid values for this parameter are:</span></span>

- <span data-ttu-id="27a8a-146">По умолчанию. DCOM может выбрать уровень олицетворения с помощью обычного алгоритма согласования безопасности.</span><span class="sxs-lookup"><span data-stu-id="27a8a-146">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="27a8a-147">Нет: клиент является анонимным для сервера.</span><span class="sxs-lookup"><span data-stu-id="27a8a-147">None: The client is anonymous to the server.</span></span> <span data-ttu-id="27a8a-148">Серверный процесс может олицетворять клиента, но маркер олицетворения не содержит никаких сведений и не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="27a8a-148">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="27a8a-149">Identify: позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="27a8a-149">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="27a8a-150">Impersonate: позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="27a8a-150">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="27a8a-151">Delegate: позволяет объектам разрешить другим объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="27a8a-151">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="27a8a-152">Если **олицетворение** не указано, `New-CimSession` командлет использует значение **impersonate**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-152">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ImpersonationType
Parameter Sets: DcomParameterSet
Aliases:
Accepted values: Default, None, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-153">-Максенвелопесизекб</span><span class="sxs-lookup"><span data-stu-id="27a8a-153">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="27a8a-154">Задает предельный размер сообщений WsMan XML для любого направления.</span><span class="sxs-lookup"><span data-stu-id="27a8a-154">Specifies the size limit of WsMan XML messages for either direction.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-155">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="27a8a-155">-NoEncryption</span></span>

<span data-ttu-id="27a8a-156">Указывает, что шифрование данных отключено.</span><span class="sxs-lookup"><span data-stu-id="27a8a-156">Specifies that data encryption is turned off.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-157">-Паккетинтегрити</span><span class="sxs-lookup"><span data-stu-id="27a8a-157">-PacketIntegrity</span></span>

<span data-ttu-id="27a8a-158">Указывает, что сеанс DCOM, созданный для WMI, использует функциональные возможности _Паккетинтегрити_ модели COM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-158">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="27a8a-159">По умолчанию все сеансы CIM, созданные с помощью DCOM, имеют для параметра **паккетинтегрити** значение **true**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-159">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-160">-Паккетприваци</span><span class="sxs-lookup"><span data-stu-id="27a8a-160">-PacketPrivacy</span></span>

<span data-ttu-id="27a8a-161">Создает сеанс DCOM для WMI с помощью _ПАККЕТПРИВАЦИ_ com.</span><span class="sxs-lookup"><span data-stu-id="27a8a-161">Creates a DCOM session to WMI using the COM _PacketPrivacy_.</span></span> <span data-ttu-id="27a8a-162">По умолчанию все сеансы CIM, созданные с помощью DCOM, имеют для параметра **паккетприваци** значение **true**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-162">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-163">-Protocol</span><span class="sxs-lookup"><span data-stu-id="27a8a-163">-Protocol</span></span>

<span data-ttu-id="27a8a-164">Указывает протокол, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="27a8a-164">Specifies the protocol to use.</span></span> <span data-ttu-id="27a8a-165">Допустимые значения для этого параметра: **DCOM**, **Default** или **WSMan**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-165">The acceptable values for this parameter are: **DCOM**, **Default**, or **Wsman**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimCmdlets.ProtocolType
Parameter Sets: ProtocolTypeSet
Aliases:
Accepted values: Dcom, Default, Wsman

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-166">-Проксяусентикатион</span><span class="sxs-lookup"><span data-stu-id="27a8a-166">-ProxyAuthentication</span></span>

<span data-ttu-id="27a8a-167">Указывает метод проверки подлинности, используемый для разрешения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="27a8a-167">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="27a8a-168">Допустимые значения для этого параметра: **Default**, **дайджест**, **Negotiate**, **Basic**, **Kerberos**, **нтлмдомаин** или **CredSsp**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-168">The acceptable values for this parameter are: **Default**, **Digest**, **Negotiate**, **Basic**, **Kerberos**, **NtlmDomain**, or **CredSsp**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-169">-Проксицертификатесумбпринт</span><span class="sxs-lookup"><span data-stu-id="27a8a-169">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="27a8a-170">Указывает сертификат цифрового открытого ключа (x. 509) учетной записи пользователя для проверки подлинности прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="27a8a-170">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="27a8a-171">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="27a8a-171">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="27a8a-172">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="27a8a-172">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="27a8a-173">Они могут быть сопоставлены только с локальными учетными записями пользователей и не работают с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="27a8a-173">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="27a8a-174">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` командлеты или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="27a8a-174">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="27a8a-175">-ProxyCredential</span></span>

<span data-ttu-id="27a8a-176">Задает учетные данные, используемые для аутентификации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="27a8a-176">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="27a8a-177">Введите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="27a8a-177">Enter one of the following:</span></span>

- <span data-ttu-id="27a8a-178">Переменная, содержащая объект PSCredential.</span><span class="sxs-lookup"><span data-stu-id="27a8a-178">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="27a8a-179">Команда, которая получает объект PSCredential, например `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="27a8a-179">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="27a8a-180">Если этот параметр не задан, то нельзя указать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="27a8a-180">If this option is not set, then you cannot specify any credentials.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-181">-Прокситипе</span><span class="sxs-lookup"><span data-stu-id="27a8a-181">-ProxyType</span></span>

<span data-ttu-id="27a8a-182">Указывает используемый механизм разрешения имен узлов.</span><span class="sxs-lookup"><span data-stu-id="27a8a-182">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="27a8a-183">Допустимые значения для этого параметра: **None**, **WinHTTP**, **Auto** или **InternetExplorer**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-183">The acceptable values for this parameter are: **None**, **WinHttp**, **Auto**, or **InternetExplorer**.</span></span>

<span data-ttu-id="27a8a-184">Значение этого параметра по умолчанию — **InternetExplorer**.</span><span class="sxs-lookup"><span data-stu-id="27a8a-184">The default value of this parameter is **InternetExplorer**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ProxyType
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: None, WinHttp, Auto, InternetExplorer

Required: False
Position: Named
Default value: InternetExplorer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-185">-Скипкачекк</span><span class="sxs-lookup"><span data-stu-id="27a8a-185">-SkipCACheck</span></span>

<span data-ttu-id="27a8a-186">Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="27a8a-186">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="27a8a-187">Используйте этот параметр только в том случае, если удаленный компьютер является доверенным с помощью другого механизма, например, когда удаленный компьютер входит в сеть, которая физически защищена и изолирована, или если удаленный компьютер указан как доверенный узел в конфигурации WinRM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-187">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-188">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="27a8a-188">-SkipCNCheck</span></span>

<span data-ttu-id="27a8a-189">Указывает, что общее имя сертификата (CN) сервера не обязательно должно совпадать с именем узла сервера.</span><span class="sxs-lookup"><span data-stu-id="27a8a-189">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="27a8a-190">Используйте этот параметр для удаленных операций только с доверенными компьютерами, использующими протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="27a8a-190">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-191">-Скипревокатиончекк</span><span class="sxs-lookup"><span data-stu-id="27a8a-191">-SkipRevocationCheck</span></span>

<span data-ttu-id="27a8a-192">Указывает, что проверка отзыва сертификатов сервера пропускается.</span><span class="sxs-lookup"><span data-stu-id="27a8a-192">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="27a8a-193">Используйте этот параметр только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="27a8a-193">Use this parameter only for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-194">-UICulture</span><span class="sxs-lookup"><span data-stu-id="27a8a-194">-UICulture</span></span>

<span data-ttu-id="27a8a-195">Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-195">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="27a8a-196">Укажите значение этого параметра в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="27a8a-196">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="27a8a-197">Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например "en-US".</span><span class="sxs-lookup"><span data-stu-id="27a8a-197">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="27a8a-198">Переменная, содержащая объект CultureInfo.</span><span class="sxs-lookup"><span data-stu-id="27a8a-198">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="27a8a-199">Команда, которая получает объект CultureInfo, например `Get-Culture` .</span><span class="sxs-lookup"><span data-stu-id="27a8a-199">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-200">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="27a8a-200">-UseSsl</span></span>

<span data-ttu-id="27a8a-201">Указывает, что для установления соединения с удаленным компьютером следует использовать протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="27a8a-201">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="27a8a-202">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="27a8a-202">By default, SSL is not used.</span></span> <span data-ttu-id="27a8a-203">WsMan шифрует все содержимое, передаваемое по сети, даже при использовании протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="27a8a-203">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="27a8a-204">Этот параметр позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="27a8a-204">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="27a8a-205">Если протокол SSL недоступен для порта, используемого для соединения, и указан этот параметр, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="27a8a-205">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="27a8a-206">Рекомендуется использовать этот параметр только в том случае, если не указан параметр **паккетприваци** .</span><span class="sxs-lookup"><span data-stu-id="27a8a-206">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="27a8a-207">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="27a8a-207">CommonParameters</span></span>

<span data-ttu-id="27a8a-208">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27a8a-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27a8a-209">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="27a8a-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27a8a-210">Входные данные</span><span class="sxs-lookup"><span data-stu-id="27a8a-210">INPUTS</span></span>

### <span data-ttu-id="27a8a-211">None</span><span class="sxs-lookup"><span data-stu-id="27a8a-211">None</span></span>

<span data-ttu-id="27a8a-212">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="27a8a-212">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="27a8a-213">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="27a8a-213">OUTPUTS</span></span>

### <span data-ttu-id="27a8a-214">Цимсессионоптион</span><span class="sxs-lookup"><span data-stu-id="27a8a-214">CIMSessionOption</span></span>

<span data-ttu-id="27a8a-215">Этот командлет возвращает объект, содержащий сведения о параметрах сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="27a8a-215">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="27a8a-216">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="27a8a-216">NOTES</span></span>

## <span data-ttu-id="27a8a-217">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="27a8a-217">RELATED LINKS</span></span>

[<span data-ttu-id="27a8a-218">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="27a8a-218">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="27a8a-219">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="27a8a-219">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="27a8a-220">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="27a8a-220">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="27a8a-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="27a8a-221">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="27a8a-222">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="27a8a-222">New-CimSession</span></span>](New-CimSession.md)

