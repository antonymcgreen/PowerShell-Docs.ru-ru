---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: f43e84dfc5b3255d17df266bf04a05778362847b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228226"
---
# <span data-ttu-id="be284-103">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="be284-103">New-CimSessionOption</span></span>

## <span data-ttu-id="be284-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="be284-104">SYNOPSIS</span></span>
<span data-ttu-id="be284-105">Задает дополнительные параметры для командлета New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="be284-105">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="be284-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="be284-106">SYNTAX</span></span>

### <span data-ttu-id="be284-107">Протоколтипесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="be284-107">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="be284-108">всманпараметерсет</span><span class="sxs-lookup"><span data-stu-id="be284-108">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="be284-109">дкомпараметерсет</span><span class="sxs-lookup"><span data-stu-id="be284-109">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="be284-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="be284-110">DESCRIPTION</span></span>

<span data-ttu-id="be284-111">`New-CimSessionOption`Командлет создает экземпляр объекта параметров сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="be284-111">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="be284-112">Используйте объект параметров сеанса CIM в качестве входных данных для `New-CimSession` командлета, чтобы указать параметры для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="be284-112">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="be284-113">Этот командлет имеет два набора параметров: один для параметров WsMan и один для параметров распределенной модели объектов компонента (DCOM).</span><span class="sxs-lookup"><span data-stu-id="be284-113">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="be284-114">В зависимости от используемых параметров командлет возвращает либо экземпляр параметров сеанса DCOM, либо метод, который возвращает параметры сеанса WsMan.</span><span class="sxs-lookup"><span data-stu-id="be284-114">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="be284-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="be284-115">EXAMPLES</span></span>

### <span data-ttu-id="be284-116">Пример 1. Создание объекта параметров сеанса CIM для DCOM</span><span class="sxs-lookup"><span data-stu-id="be284-116">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="be284-117">В этом примере создается объект параметров сеанса CIM для протокола DCOM и сохраняется в переменной с именем `$so` .</span><span class="sxs-lookup"><span data-stu-id="be284-117">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="be284-118">После этого содержимое переменной передается в `New-CimSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="be284-118">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="be284-119">`New-CimSession` затем создает новый сеанс CIM с удаленным сервером с именем Server01, используя параметры, определенные в переменной.</span><span class="sxs-lookup"><span data-stu-id="be284-119">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="be284-120">Пример 2. Создание объекта параметров сеанса CIM для WsMan</span><span class="sxs-lookup"><span data-stu-id="be284-120">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="be284-121">В этом примере создается объект параметров сеанса CIM для протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="be284-121">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="be284-122">Объект содержит конфигурацию режима проверки подлинности **Kerberos** , заданного параметром **проксяусентикатион** , учетные данные, указанные параметром **ProxyCredential** , и указывает, что команда должна пропустить проверку ЦС, пропустить проверку CN и использовать SSL.</span><span class="sxs-lookup"><span data-stu-id="be284-122">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="be284-123">Пример 3. Создание объекта параметров сеанса CIM с заданной культурой</span><span class="sxs-lookup"><span data-stu-id="be284-123">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="be284-124">В этом примере указывается язык и региональные параметры, используемые для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="be284-124">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="be284-125">По умолчанию при выполнении операций используется язык и региональные параметры клиента.</span><span class="sxs-lookup"><span data-stu-id="be284-125">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="be284-126">Однако язык и региональные параметры по умолчанию можно переопределить с помощью параметра **culture** .</span><span class="sxs-lookup"><span data-stu-id="be284-126">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="be284-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="be284-127">PARAMETERS</span></span>

### <span data-ttu-id="be284-128">-Culture</span><span class="sxs-lookup"><span data-stu-id="be284-128">-Culture</span></span>

<span data-ttu-id="be284-129">Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="be284-129">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="be284-130">Укажите значение этого параметра в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="be284-130">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="be284-131">Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например "en-US".</span><span class="sxs-lookup"><span data-stu-id="be284-131">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="be284-132">Переменная, содержащая объект **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="be284-132">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="be284-133">Команда, которая получает объект **CultureInfo** , например [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span><span class="sxs-lookup"><span data-stu-id="be284-133">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

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

### <span data-ttu-id="be284-134">-ЕнкодепортинсервицепринЦипалнаме</span><span class="sxs-lookup"><span data-stu-id="be284-134">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="be284-135">Указывает, что соединение Kerberos подключается к службе, имя участника-службы (SPN) которого содержит номер порта службы.</span><span class="sxs-lookup"><span data-stu-id="be284-135">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="be284-136">Этот тип соединения не является распространенным.</span><span class="sxs-lookup"><span data-stu-id="be284-136">This type of connection is not common.</span></span>

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

### <span data-ttu-id="be284-137">-Encoding</span><span class="sxs-lookup"><span data-stu-id="be284-137">-Encoding</span></span>

<span data-ttu-id="be284-138">Указывает кодировку, используемую для протокола WsMan.</span><span class="sxs-lookup"><span data-stu-id="be284-138">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="be284-139">Допустимые значения для этого параметра: **Default** , **Utf8** или **Utf16** .</span><span class="sxs-lookup"><span data-stu-id="be284-139">The acceptable values for this parameter are: **Default** , **Utf8** , or **Utf16** .</span></span>

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

### <span data-ttu-id="be284-140">-Хттппрефикс</span><span class="sxs-lookup"><span data-stu-id="be284-140">-HttpPrefix</span></span>

<span data-ttu-id="be284-141">Указывает часть URL-адреса HTTP после имени компьютера и номера порта.</span><span class="sxs-lookup"><span data-stu-id="be284-141">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="be284-142">Изменение этого не является распространенным.</span><span class="sxs-lookup"><span data-stu-id="be284-142">Changing this is not common.</span></span> <span data-ttu-id="be284-143">По умолчанию значение этого параметра равно **/всман** .</span><span class="sxs-lookup"><span data-stu-id="be284-143">By default, the value of this parameter is **/wsman** .</span></span>

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

### <span data-ttu-id="be284-144">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="be284-144">-Impersonation</span></span>

<span data-ttu-id="be284-145">Создает сеанс DCOM для инструментарий управления Windows (WMI) (WMI) с использованием олицетворения.</span><span class="sxs-lookup"><span data-stu-id="be284-145">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="be284-146">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="be284-146">Valid values for this parameter are:</span></span>

- <span data-ttu-id="be284-147">По умолчанию. DCOM может выбрать уровень олицетворения с помощью обычного алгоритма согласования безопасности.</span><span class="sxs-lookup"><span data-stu-id="be284-147">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="be284-148">Нет: клиент является анонимным для сервера.</span><span class="sxs-lookup"><span data-stu-id="be284-148">None: The client is anonymous to the server.</span></span> <span data-ttu-id="be284-149">Серверный процесс может олицетворять клиента, но маркер олицетворения не содержит никаких сведений и не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="be284-149">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="be284-150">Identify: позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="be284-150">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="be284-151">Impersonate: позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="be284-151">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="be284-152">Delegate: позволяет объектам разрешить другим объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="be284-152">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="be284-153">Если **олицетворение** не указано, `New-CimSession` командлет использует значение **impersonate** .</span><span class="sxs-lookup"><span data-stu-id="be284-153">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate** .</span></span>

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

### <span data-ttu-id="be284-154">-Максенвелопесизекб</span><span class="sxs-lookup"><span data-stu-id="be284-154">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="be284-155">Задает предельный размер сообщений WsMan XML для любого направления.</span><span class="sxs-lookup"><span data-stu-id="be284-155">Specifies the size limit of WsMan XML messages for either direction.</span></span>

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

### <span data-ttu-id="be284-156">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="be284-156">-NoEncryption</span></span>

<span data-ttu-id="be284-157">Указывает, что шифрование данных отключено.</span><span class="sxs-lookup"><span data-stu-id="be284-157">Specifies that data encryption is turned off.</span></span>

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

### <span data-ttu-id="be284-158">-Паккетинтегрити</span><span class="sxs-lookup"><span data-stu-id="be284-158">-PacketIntegrity</span></span>

<span data-ttu-id="be284-159">Указывает, что сеанс DCOM, созданный для WMI, использует функциональные возможности _Паккетинтегрити_ модели COM.</span><span class="sxs-lookup"><span data-stu-id="be284-159">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="be284-160">По умолчанию все сеансы CIM, созданные с помощью DCOM, имеют для параметра **паккетинтегрити** значение **true** .</span><span class="sxs-lookup"><span data-stu-id="be284-160">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True** .</span></span>

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

### <span data-ttu-id="be284-161">-Паккетприваци</span><span class="sxs-lookup"><span data-stu-id="be284-161">-PacketPrivacy</span></span>

<span data-ttu-id="be284-162">Создает сеанс DCOM для WMI с помощью _ПАККЕТПРИВАЦИ_ com.</span><span class="sxs-lookup"><span data-stu-id="be284-162">Creates a DCOM session to WMI using the COM _PacketPrivacy_ .</span></span> <span data-ttu-id="be284-163">По умолчанию все сеансы CIM, созданные с помощью DCOM, имеют для параметра **паккетприваци** значение **true** .</span><span class="sxs-lookup"><span data-stu-id="be284-163">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true** .</span></span>

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

### <span data-ttu-id="be284-164">-Protocol</span><span class="sxs-lookup"><span data-stu-id="be284-164">-Protocol</span></span>

<span data-ttu-id="be284-165">Указывает протокол, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="be284-165">Specifies the protocol to use.</span></span> <span data-ttu-id="be284-166">Допустимые значения для этого параметра: **DCOM** , **Default** или **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="be284-166">The acceptable values for this parameter are: **DCOM** , **Default** , or **Wsman** .</span></span>

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

### <span data-ttu-id="be284-167">-Проксяусентикатион</span><span class="sxs-lookup"><span data-stu-id="be284-167">-ProxyAuthentication</span></span>

<span data-ttu-id="be284-168">Указывает метод проверки подлинности, используемый для разрешения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="be284-168">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="be284-169">Допустимые значения для этого параметра: **Default** , **дайджест** , **Negotiate** , **Basic** , **Kerberos** , **нтлмдомаин** или **CredSsp** .</span><span class="sxs-lookup"><span data-stu-id="be284-169">The acceptable values for this parameter are: **Default** , **Digest** , **Negotiate** , **Basic** , **Kerberos** , **NtlmDomain** , or **CredSsp** .</span></span>

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

### <span data-ttu-id="be284-170">-Проксицертификатесумбпринт</span><span class="sxs-lookup"><span data-stu-id="be284-170">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="be284-171">Указывает сертификат цифрового открытого ключа (x. 509) учетной записи пользователя для проверки подлинности прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="be284-171">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="be284-172">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="be284-172">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="be284-173">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="be284-173">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="be284-174">Они могут быть сопоставлены только с локальными учетными записями пользователей и не работают с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="be284-174">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="be284-175">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` командлеты или на диске PowerShell CERT:.</span><span class="sxs-lookup"><span data-stu-id="be284-175">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="be284-176">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="be284-176">-ProxyCredential</span></span>

<span data-ttu-id="be284-177">Задает учетные данные, используемые для аутентификации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="be284-177">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="be284-178">Введите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="be284-178">Enter one of the following:</span></span>

- <span data-ttu-id="be284-179">Переменная, содержащая объект PSCredential.</span><span class="sxs-lookup"><span data-stu-id="be284-179">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="be284-180">Команда, которая получает объект PSCredential, например `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="be284-180">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="be284-181">Если этот параметр не задан, то нельзя указать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="be284-181">If this option is not set, then you cannot specify any credentials.</span></span>

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

### <span data-ttu-id="be284-182">-Прокситипе</span><span class="sxs-lookup"><span data-stu-id="be284-182">-ProxyType</span></span>

<span data-ttu-id="be284-183">Указывает используемый механизм разрешения имен узлов.</span><span class="sxs-lookup"><span data-stu-id="be284-183">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="be284-184">Допустимые значения для этого параметра: **None** , **WinHTTP** , **Auto** или **InternetExplorer** .</span><span class="sxs-lookup"><span data-stu-id="be284-184">The acceptable values for this parameter are: **None** , **WinHttp** , **Auto** , or **InternetExplorer** .</span></span>

<span data-ttu-id="be284-185">Значение этого параметра по умолчанию — **InternetExplorer** .</span><span class="sxs-lookup"><span data-stu-id="be284-185">The default value of this parameter is **InternetExplorer** .</span></span>

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

### <span data-ttu-id="be284-186">-Скипкачекк</span><span class="sxs-lookup"><span data-stu-id="be284-186">-SkipCACheck</span></span>

<span data-ttu-id="be284-187">Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="be284-187">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="be284-188">Используйте этот параметр только в том случае, если удаленный компьютер является доверенным с помощью другого механизма, например, когда удаленный компьютер входит в сеть, которая физически защищена и изолирована, или если удаленный компьютер указан как доверенный узел в конфигурации WinRM.</span><span class="sxs-lookup"><span data-stu-id="be284-188">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="be284-189">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="be284-189">-SkipCNCheck</span></span>

<span data-ttu-id="be284-190">Указывает, что общее имя сертификата (CN) сервера не обязательно должно совпадать с именем узла сервера.</span><span class="sxs-lookup"><span data-stu-id="be284-190">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="be284-191">Используйте этот параметр для удаленных операций только с доверенными компьютерами, использующими протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="be284-191">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

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

### <span data-ttu-id="be284-192">-Скипревокатиончекк</span><span class="sxs-lookup"><span data-stu-id="be284-192">-SkipRevocationCheck</span></span>

<span data-ttu-id="be284-193">Указывает, что проверка отзыва сертификатов сервера пропускается.</span><span class="sxs-lookup"><span data-stu-id="be284-193">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="be284-194">Используйте этот параметр только для доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="be284-194">Use this parameter only for trusted computers.</span></span>

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

### <span data-ttu-id="be284-195">-UICulture</span><span class="sxs-lookup"><span data-stu-id="be284-195">-UICulture</span></span>

<span data-ttu-id="be284-196">Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="be284-196">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="be284-197">Укажите значение этого параметра в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="be284-197">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="be284-198">Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например "en-US".</span><span class="sxs-lookup"><span data-stu-id="be284-198">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="be284-199">Переменная, содержащая объект CultureInfo.</span><span class="sxs-lookup"><span data-stu-id="be284-199">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="be284-200">Команда, которая получает объект CultureInfo, например `Get-Culture` .</span><span class="sxs-lookup"><span data-stu-id="be284-200">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

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

### <span data-ttu-id="be284-201">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="be284-201">-UseSsl</span></span>

<span data-ttu-id="be284-202">Указывает, что для установления соединения с удаленным компьютером следует использовать протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="be284-202">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="be284-203">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="be284-203">By default, SSL is not used.</span></span> <span data-ttu-id="be284-204">WsMan шифрует все содержимое, передаваемое по сети, даже при использовании протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="be284-204">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="be284-205">Этот параметр позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="be284-205">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="be284-206">Если протокол SSL недоступен для порта, используемого для соединения, и указан этот параметр, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="be284-206">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="be284-207">Рекомендуется использовать этот параметр только в том случае, если не указан параметр **паккетприваци** .</span><span class="sxs-lookup"><span data-stu-id="be284-207">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

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

### <span data-ttu-id="be284-208">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="be284-208">CommonParameters</span></span>

<span data-ttu-id="be284-209">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="be284-209">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="be284-210">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="be284-210">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="be284-211">Входные данные</span><span class="sxs-lookup"><span data-stu-id="be284-211">INPUTS</span></span>

### <span data-ttu-id="be284-212">Нет</span><span class="sxs-lookup"><span data-stu-id="be284-212">None</span></span>

<span data-ttu-id="be284-213">Этот командлет не принимает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="be284-213">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="be284-214">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="be284-214">OUTPUTS</span></span>

### <span data-ttu-id="be284-215">Цимсессионоптион</span><span class="sxs-lookup"><span data-stu-id="be284-215">CIMSessionOption</span></span>

<span data-ttu-id="be284-216">Этот командлет возвращает объект, содержащий сведения о параметрах сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="be284-216">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="be284-217">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="be284-217">NOTES</span></span>

## <span data-ttu-id="be284-218">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="be284-218">RELATED LINKS</span></span>

[<span data-ttu-id="be284-219">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="be284-219">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="be284-220">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="be284-220">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="be284-221">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="be284-221">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="be284-222">Get-Item</span><span class="sxs-lookup"><span data-stu-id="be284-222">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="be284-223">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="be284-223">New-CimSession</span></span>](New-CimSession.md)
