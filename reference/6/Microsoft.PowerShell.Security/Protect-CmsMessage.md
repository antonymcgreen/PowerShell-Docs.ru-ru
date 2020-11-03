---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: d148a9d1013de20885cd9914f283b85a2a7acd3f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229110"
---
# <span data-ttu-id="9c60f-103">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9c60f-103">Protect-CmsMessage</span></span>

## <span data-ttu-id="9c60f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9c60f-104">SYNOPSIS</span></span>
<span data-ttu-id="9c60f-105">Шифрует содержимое с помощью формата синтаксиса криптографического сообщения.</span><span class="sxs-lookup"><span data-stu-id="9c60f-105">Encrypts content by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="9c60f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c60f-106">SYNTAX</span></span>

### <span data-ttu-id="9c60f-107">Биконтент (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9c60f-107">ByContent (Default)</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="9c60f-108">бипас</span><span class="sxs-lookup"><span data-stu-id="9c60f-108">ByPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### <span data-ttu-id="9c60f-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="9c60f-109">ByLiteralPath</span></span>

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="9c60f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c60f-110">DESCRIPTION</span></span>

<span data-ttu-id="9c60f-111">`Protect-CmsMessage`Командлет шифрует содержимое с помощью формата синтаксиса криптографического сообщения (CMS).</span><span class="sxs-lookup"><span data-stu-id="9c60f-111">The `Protect-CmsMessage` cmdlet encrypts content by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="9c60f-112">Командлеты CMS поддерживают шифрование и расшифровку содержимого с помощью формата IETF, как описано в [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span><span class="sxs-lookup"><span data-stu-id="9c60f-112">The CMS cmdlets support encryption and decryption of content using the IETF format as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="9c60f-113">Стандарт шифрования CMS использует шифрование с открытым ключом, где ключи, используемые для шифрования содержимого (открытый ключ) и ключи, используемые для расшифровки содержимого (закрытый ключ), являются отдельными.</span><span class="sxs-lookup"><span data-stu-id="9c60f-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="9c60f-114">Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям.</span><span class="sxs-lookup"><span data-stu-id="9c60f-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="9c60f-115">Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="9c60f-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="9c60f-116">Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="9c60f-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="9c60f-117">Перед запуском `Protect-CmsMessage` командлета необходимо настроить сертификат шифрования.</span><span class="sxs-lookup"><span data-stu-id="9c60f-117">Before you can run the `Protect-CmsMessage` cmdlet, you must have an encryption certificate set up.</span></span>
<span data-ttu-id="9c60f-118">Для распознавания в PowerShell сертификатам шифрования требуется уникальный идентификатор расширенного использования ключа ([EKU](/windows/desktop/SecCrypto/eku)), чтобы идентифицировать их в качестве сертификатов шифрования данных (например, идентификаторы для подписывания кода и зашифрованной почты).</span><span class="sxs-lookup"><span data-stu-id="9c60f-118">To be recognized in PowerShell, encryption certificates require a unique extended key usage ([EKU](/windows/desktop/SecCrypto/eku)) ID to identify them as data encryption certificates (such as the IDs for Code Signing and Encrypted Mail).</span></span> <span data-ttu-id="9c60f-119">Пример сертификата, который будет работать при шифровании документов, см. в примере 1 в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9c60f-119">For an example of a certificate that would work for document encryption, see Example 1 in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="9c60f-120">Этот командлет доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="9c60f-120">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="9c60f-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="9c60f-121">EXAMPLES</span></span>

### <span data-ttu-id="9c60f-122">Пример 1. Создание сертификата для шифрования содержимого</span><span class="sxs-lookup"><span data-stu-id="9c60f-122">Example 1: Create a certificate for encrypting content</span></span>

<span data-ttu-id="9c60f-123">Перед запуском `Protect-CmsMessage` командлета необходимо создать сертификат шифрования.</span><span class="sxs-lookup"><span data-stu-id="9c60f-123">Before you can run the `Protect-CmsMessage` cmdlet, you must create an encryption certificate.</span></span> <span data-ttu-id="9c60f-124">Используя следующий текст, измените имя в строке темы на имя, адрес электронной почты или другой идентификатор и сохраните сертификат в файле (например `DocumentEncryption.inf` , как показано в этом примере).</span><span class="sxs-lookup"><span data-stu-id="9c60f-124">Using the following text, change the name in the Subject line to your name, email, or other identifier, and save the certificate in a file (such as `DocumentEncryption.inf`, as shown in this example).</span></span>

```powershell
# Create .INF file for certreq
{[Version]
Signature = "$Windows NT$"

[Strings]
szOID_ENHANCED_KEY_USAGE = "2.5.29.37"
szOID_DOCUMENT_ENCRYPTION = "1.3.6.1.4.1.311.80.1"

[NewRequest]
Subject = "cn=youralias@emailaddress.com"
MachineKeySet = false
KeyLength = 2048
KeySpec = AT_KEYEXCHANGE
HashAlgorithm = Sha1
Exportable = true
RequestType = Cert
KeyUsage = "CERT_KEY_ENCIPHERMENT_KEY_USAGE | CERT_DATA_ENCIPHERMENT_KEY_USAGE"
ValidityPeriod = "Years"
ValidityPeriodUnits = "1000"

[Extensions]
%szOID_ENHANCED_KEY_USAGE% = "{text}%szOID_DOCUMENT_ENCRYPTION%"
} | Out-File -FilePath DocumentEncryption.inf

# After you have created your certificate file, run the following command to add
# the certificate file to the certificate store. Now you are ready to encrypt and
# decrypt content with the next two examples.
certreq.exe -new DocumentEncryption.inf DocumentEncryption.cer
```

### <span data-ttu-id="9c60f-125">Пример 2. шифрование сообщения, отправленного по электронной почте</span><span class="sxs-lookup"><span data-stu-id="9c60f-125">Example 2: Encrypt a message sent by email</span></span>

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

<span data-ttu-id="9c60f-126">В следующем примере выполняется шифрование сообщения "Hello World" путем передачи его в `Protect-CmsMessage` командлет, а затем сохраняется зашифрованное сообщение в переменной.</span><span class="sxs-lookup"><span data-stu-id="9c60f-126">In the following example, you encrypt a message, "Hello World", by piping it to the `Protect-CmsMessage` cmdlet, and then save the encrypted message in a variable.</span></span> <span data-ttu-id="9c60f-127">Параметр **to** использует значение строки темы в сертификате.</span><span class="sxs-lookup"><span data-stu-id="9c60f-127">The **To** parameter uses the value of the Subject line in the certificate.</span></span>

### <span data-ttu-id="9c60f-128">Пример 3. Просмотр сертификатов шифрования документов</span><span class="sxs-lookup"><span data-stu-id="9c60f-128">Example 3: View document encryption certificates</span></span>

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

<span data-ttu-id="9c60f-129">Чтобы просмотреть сертификаты шифрования документов в поставщике сертификатов, можно добавить динамический параметр **документенкриптионцерт** командлета [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), доступный только при загрузке поставщика сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9c60f-129">To view document encryption certificates in the certificate provider, you can add the **DocumentEncryptionCert** dynamic parameter of [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), available only when the certificate provider is loaded.</span></span>

## <span data-ttu-id="9c60f-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c60f-130">PARAMETERS</span></span>

### <span data-ttu-id="9c60f-131">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="9c60f-131">-Content</span></span>

<span data-ttu-id="9c60f-132">Задает **PSObject** , содержащий содержимое, которое необходимо зашифровать.</span><span class="sxs-lookup"><span data-stu-id="9c60f-132">Specifies a **PSObject** that contains content that you want to encrypt.</span></span> <span data-ttu-id="9c60f-133">Например, можно зашифровать содержимое сообщения о событии, а затем использовать переменную, содержащую сообщение ( `$Event` в данном примере), в качестве значения параметра **Content** : `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` .</span><span class="sxs-lookup"><span data-stu-id="9c60f-133">For example, you can encrypt the content of an event message, and then use the variable containing the message (`$Event`, in this example) as the value of the **Content** parameter: `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1`.</span></span> <span data-ttu-id="9c60f-134">Можно также использовать командлет, `Get-Content` чтобы получить содержимое файла, например документ Microsoft Word, и сохранить содержимое в переменной, используемой в качестве значения параметра **Content** .</span><span class="sxs-lookup"><span data-stu-id="9c60f-134">You can also use the `Get-Content` cmdlet to get the contents of a file, such as a Microsoft Word document, and save the content in a variable that you use as the value of the **Content** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByContent
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9c60f-135">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9c60f-135">-LiteralPath</span></span>

<span data-ttu-id="9c60f-136">Указывает путь к содержимому, которое необходимо зашифровать.</span><span class="sxs-lookup"><span data-stu-id="9c60f-136">Specifies the path to content that you want to encrypt.</span></span> <span data-ttu-id="9c60f-137">В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="9c60f-137">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9c60f-138">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="9c60f-138">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9c60f-139">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9c60f-139">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9c60f-140">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="9c60f-140">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c60f-141">-Файл</span><span class="sxs-lookup"><span data-stu-id="9c60f-141">-OutFile</span></span>

<span data-ttu-id="9c60f-142">Указывает путь и имя файла, в который будет отправлено зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="9c60f-142">Specifies the path and file name of a file to which you want to send the encrypted content.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c60f-143">-Path</span><span class="sxs-lookup"><span data-stu-id="9c60f-143">-Path</span></span>

<span data-ttu-id="9c60f-144">Указывает путь к содержимому, которое необходимо зашифровать.</span><span class="sxs-lookup"><span data-stu-id="9c60f-144">Specifies the path to content that you want to encrypt.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c60f-145">— Для</span><span class="sxs-lookup"><span data-stu-id="9c60f-145">-To</span></span>

<span data-ttu-id="9c60f-146">Указывает одного или нескольких получателей сообщений CMS, определенных в любом из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="9c60f-146">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="9c60f-147">Фактический сертификат (полученный от поставщика сертификата).</span><span class="sxs-lookup"><span data-stu-id="9c60f-147">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="9c60f-148">Путь к файлу, содержащему сертификат.</span><span class="sxs-lookup"><span data-stu-id="9c60f-148">Path to the file containing the certificate.</span></span>
- <span data-ttu-id="9c60f-149">Путь к каталогу, содержащему сертификат.</span><span class="sxs-lookup"><span data-stu-id="9c60f-149">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="9c60f-150">Отпечаток сертификата (используется для поиска в хранилище сертификатов).</span><span class="sxs-lookup"><span data-stu-id="9c60f-150">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="9c60f-151">Имя субъекта сертификата (используется для поиска в хранилище сертификатов).</span><span class="sxs-lookup"><span data-stu-id="9c60f-151">Subject name of the certificate (used to look in the certificate store).</span></span>

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c60f-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9c60f-152">CommonParameters</span></span>

<span data-ttu-id="9c60f-153">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="9c60f-153">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9c60f-154">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9c60f-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9c60f-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9c60f-155">INPUTS</span></span>

## <span data-ttu-id="9c60f-156">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9c60f-156">OUTPUTS</span></span>

## <span data-ttu-id="9c60f-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9c60f-157">NOTES</span></span>

## <span data-ttu-id="9c60f-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9c60f-158">RELATED LINKS</span></span>

[<span data-ttu-id="9c60f-159">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9c60f-159">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="9c60f-160">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9c60f-160">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="9c60f-161">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9c60f-161">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
