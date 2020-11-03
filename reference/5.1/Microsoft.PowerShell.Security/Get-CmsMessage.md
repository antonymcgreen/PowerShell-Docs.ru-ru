---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-cmsmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CmsMessage
ms.openlocfilehash: bafe666c5cb24accfc931c58cb1805e85455ab30
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227801"
---
# <span data-ttu-id="9b9ff-103">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9b9ff-103">Get-CmsMessage</span></span>

## <span data-ttu-id="9b9ff-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9b9ff-104">SYNOPSIS</span></span>
<span data-ttu-id="9b9ff-105">Возвращает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-105">Gets content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="9b9ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9b9ff-106">SYNTAX</span></span>

### <span data-ttu-id="9b9ff-107">биконтент</span><span class="sxs-lookup"><span data-stu-id="9b9ff-107">ByContent</span></span>

```
Get-CmsMessage [-Content] <String> [<CommonParameters>]
```

### <span data-ttu-id="9b9ff-108">бипас</span><span class="sxs-lookup"><span data-stu-id="9b9ff-108">ByPath</span></span>

```
Get-CmsMessage [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="9b9ff-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="9b9ff-109">ByLiteralPath</span></span>

```
Get-CmsMessage [-LiteralPath] <String> [<CommonParameters>]
```

## <span data-ttu-id="9b9ff-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b9ff-110">DESCRIPTION</span></span>

<span data-ttu-id="9b9ff-111">`Get-CmsMessage`Командлет получает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения (CMS).</span><span class="sxs-lookup"><span data-stu-id="9b9ff-111">The `Get-CmsMessage` cmdlet gets content that has been encrypted using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="9b9ff-112">Командлеты CMS поддерживают шифрование и расшифровку содержимого, используя формат IETF для криптографической защиты сообщений, как описано в [RFC5652](https://tools.ietf.org/html/rfc5652).</span><span class="sxs-lookup"><span data-stu-id="9b9ff-112">The CMS cmdlets support encryption and decryption of content using the IETF format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="9b9ff-113">Стандарт шифрования CMS использует шифрование с открытым ключом, где ключи, используемые для шифрования содержимого (открытый ключ) и ключи, используемые для расшифровки содержимого (закрытый ключ), являются отдельными.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="9b9ff-114">Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="9b9ff-115">Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="9b9ff-116">Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="9b9ff-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="9b9ff-117">`Get-CmsMessage` Возвращает содержимое, зашифрованное в формате CMS.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-117">`Get-CmsMessage` gets content that has been encrypted in CMS format.</span></span> <span data-ttu-id="9b9ff-118">Он не расшифровывает и не снимает защиту с содержимого.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-118">It does not decrypt or unprotect content.</span></span> <span data-ttu-id="9b9ff-119">Этот командлет можно использовать для получения зашифрованного содержимого, выполнив `Protect-CmsMessage` командлет.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-119">You can run this cmdlet to get content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="9b9ff-120">Можно указать содержимое, которое нужно расшифровать как строку, или путем к зашифрованному содержимому.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-120">You can specify content that you want to decrypt as a string, or by path to the encrypted content.</span></span> <span data-ttu-id="9b9ff-121">Вы можете передать результаты в для `Get-CmsMessage` `Unprotect-CmsMessage` расшифровки содержимого при условии, что у вас есть сведения о сертификате шифрования документов, который использовался для шифрования содержимого.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-121">You can pipe the results of `Get-CmsMessage` to `Unprotect-CmsMessage` to decrypt the content, provided that you have information about the document encryption certificate that was used to encrypt the content.</span></span>

## <span data-ttu-id="9b9ff-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="9b9ff-122">EXAMPLES</span></span>

### <span data-ttu-id="9b9ff-123">Пример 1. Получение зашифрованного содержимого</span><span class="sxs-lookup"><span data-stu-id="9b9ff-123">Example 1: Get encrypted content</span></span>

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg.Content
```

```Output
-----BEGIN CMS-----
MIIBqAYJKoZIhvcNAQcDoIIBmTCCAZUCAQAxggFQMIIBTAIBADA0MCAxHjAcBgNVBAMBFWxlZWhv
bG1AbGljcm9zb2Z0LmNvbQIQQYHsbcXnjIJCtH+OhGmc1DANBgkqhkiG9w0BAQcwAASCAQAnkFHM
proJnFy4geFGfyNmxH3yeoPvwEYzdnsoVqqDPAd8D3wao77z7OhJEXwz9GeFLnxD6djKV/tF4PxR
E27aduKSLbnxfpf/sepZ4fUkuGibnwWFrxGE3B1G26MCenHWjYQiqv+Nq32Gc97qEAERrhLv6S4R
G+2dJEnesW8A+z9QPo+DwYP5FzD0Td0ExrkswVckpLNR6j17Yaags3ltNXmbdEXekhi6Psf2MLMP
TSO79lv2L0KeXFGuPOrdzPRwCkV0vNEqTEBeDnZGrjv/5766bM3GW34FXApod9u+VSFpBnqVOCBA
DVDraA6k+xwBt66cV84AHLkh0kT02SIHMDwGCSqGSIb3DQEHATAdBglghkgBZQMEASoEEJbJaiRl
KMnBoD1dkb/FzSWAEBaL8xkFwCu0e1AtDj7nSJc=
-----END CMS-----
```

<span data-ttu-id="9b9ff-124">Эта команда получает зашифрованное содержимое, расположенное по адресу C:\Users\Test\Documents\PowerShell\Future_Plans.txt.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-124">This command gets encrypted content located at C:\Users\Test\Documents\PowerShell\Future_Plans.txt.</span></span>

### <span data-ttu-id="9b9ff-125">Пример 2. переканалировать зашифрованное содержимое в Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9b9ff-125">Example 2: Pipe encrypted content to Unprotect-CmsMessage</span></span>

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg | Unprotect-CmsMessage -To "cn=youralias@emailaddress.com"
```

```Output
Try the new Break All command
```

<span data-ttu-id="9b9ff-126">Эта команда передает результаты `Get-CmsMessage` командлета из примера 1 в `Unprotect-CmsMessage` , чтобы расшифровать сообщение и прочитать его в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-126">This command pipes the results of the `Get-CmsMessage` cmdlet from Example 1 to `Unprotect-CmsMessage`, to decrypt the message and read it in plain text.</span></span> <span data-ttu-id="9b9ff-127">В этом случае значением параметра **to** является значение строки темы сертификата шифрования.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-127">In this case, the value of the **To** parameter is the value of the encrypting certificate's Subject line.</span></span> <span data-ttu-id="9b9ff-128">Расшифрованное сообщение "попробовать новую команду" прервать все "— результат.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-128">The decrypted message, "Try the new Break All command," is the result.</span></span>

## <span data-ttu-id="9b9ff-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9b9ff-129">PARAMETERS</span></span>

### <span data-ttu-id="9b9ff-130">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="9b9ff-130">-Content</span></span>

<span data-ttu-id="9b9ff-131">Задает зашифрованную строку или переменную, содержащую зашифрованную строку.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-131">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9b9ff-132">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9b9ff-132">-LiteralPath</span></span>

<span data-ttu-id="9b9ff-133">Указывает путь к зашифрованному содержимому, которое требуется получить.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-133">Specifies the path to encrypted content that you want to get.</span></span> <span data-ttu-id="9b9ff-134">В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-134">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9b9ff-135">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-135">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="9b9ff-136">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-136">If the path includes escape characters, enclose each one in single quotation marks.</span></span>
<span data-ttu-id="9b9ff-137">Одинарные кавычки указывают, что PowerShell не интерпретирует символы, заключенные в escape-символы.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-137">Single quotation marks tell PowerShell not to interpret enclosed characters as escape characters.</span></span>

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

### <span data-ttu-id="9b9ff-138">-Path</span><span class="sxs-lookup"><span data-stu-id="9b9ff-138">-Path</span></span>

<span data-ttu-id="9b9ff-139">Указывает путь к зашифрованному содержимому, которое необходимо расшифровать.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-139">Specifies the path to encrypted content that you want to decrypt.</span></span>

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

### <span data-ttu-id="9b9ff-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9b9ff-140">CommonParameters</span></span>

<span data-ttu-id="9b9ff-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9b9ff-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9b9ff-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9b9ff-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9b9ff-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9b9ff-143">INPUTS</span></span>

## <span data-ttu-id="9b9ff-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9b9ff-144">OUTPUTS</span></span>

## <span data-ttu-id="9b9ff-145">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9b9ff-145">NOTES</span></span>

## <span data-ttu-id="9b9ff-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9b9ff-146">RELATED LINKS</span></span>

[<span data-ttu-id="9b9ff-147">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9b9ff-147">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="9b9ff-148">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9b9ff-148">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)

[<span data-ttu-id="9b9ff-149">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9b9ff-149">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
