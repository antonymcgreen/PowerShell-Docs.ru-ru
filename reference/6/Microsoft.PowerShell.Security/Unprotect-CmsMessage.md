---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: 7d33d6b5ffe9a2a4807d864c6acb2021fff88e01
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "93229645"
---
# <span data-ttu-id="9a4be-103">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9a4be-103">Unprotect-CmsMessage</span></span>

## <span data-ttu-id="9a4be-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9a4be-104">SYNOPSIS</span></span>
<span data-ttu-id="9a4be-105">Расшифровывает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения.</span><span class="sxs-lookup"><span data-stu-id="9a4be-105">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="9a4be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a4be-106">SYNTAX</span></span>

### <span data-ttu-id="9a4be-107">Бивиневент (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9a4be-107">ByWinEvent (Default)</span></span>

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="9a4be-108">биконтент</span><span class="sxs-lookup"><span data-stu-id="9a4be-108">ByContent</span></span>

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="9a4be-109">бипас</span><span class="sxs-lookup"><span data-stu-id="9a4be-109">ByPath</span></span>

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="9a4be-110">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="9a4be-110">ByLiteralPath</span></span>

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="9a4be-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9a4be-111">DESCRIPTION</span></span>

<span data-ttu-id="9a4be-112">`Unprotect-CmsMessage`Командлет расшифровывает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения (CMS).</span><span class="sxs-lookup"><span data-stu-id="9a4be-112">The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="9a4be-113">Командлеты CMS поддерживают шифрование и расшифровку содержимого, используя стандартный формат IETF для криптографической защиты сообщений, как описано в [RFC5652](https://tools.ietf.org/html/rfc5652).</span><span class="sxs-lookup"><span data-stu-id="9a4be-113">The CMS cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="9a4be-114">Стандарт шифрования CMS использует шифрование с открытым ключом, где ключи, используемые для шифрования содержимого (открытый ключ) и ключи, используемые для расшифровки содержимого (закрытый ключ), являются отдельными.</span><span class="sxs-lookup"><span data-stu-id="9a4be-114">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="9a4be-115">Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям.</span><span class="sxs-lookup"><span data-stu-id="9a4be-115">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="9a4be-116">Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="9a4be-116">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="9a4be-117">Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="9a4be-117">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="9a4be-118">`Unprotect-CmsMessage` расшифровывает содержимое, зашифрованное в формате CMS.</span><span class="sxs-lookup"><span data-stu-id="9a4be-118">`Unprotect-CmsMessage` decrypts content that has been encrypted in CMS format.</span></span> <span data-ttu-id="9a4be-119">Этот командлет можно использовать для расшифровки зашифрованного содержимого, выполнив `Protect-CmsMessage` командлет.</span><span class="sxs-lookup"><span data-stu-id="9a4be-119">You can run this cmdlet to decrypt content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="9a4be-120">Можно указать содержимое, которое нужно расшифровать как строку, с помощью идентификатора записи журнала событий шифрования или путем к зашифрованному содержимому.</span><span class="sxs-lookup"><span data-stu-id="9a4be-120">You can specify content that you want to decrypt as a string, by the encryption event log record ID number, or by path to the encrypted content.</span></span> <span data-ttu-id="9a4be-121">`Unprotect-CmsMessage`Командлет возвращает расшифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="9a4be-121">The `Unprotect-CmsMessage` cmdlet returns the decrypted content.</span></span>

> [!NOTE]
> <span data-ttu-id="9a4be-122">Этот командлет доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="9a4be-122">This cmdlet is only available on Windows.</span></span>

## <span data-ttu-id="9a4be-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="9a4be-123">EXAMPLES</span></span>

### <span data-ttu-id="9a4be-124">Пример 1. Расшифровка сообщения</span><span class="sxs-lookup"><span data-stu-id="9a4be-124">Example 1: Decrypt a message</span></span>

<span data-ttu-id="9a4be-125">В следующем примере выполняется расшифровка содержимого, расположенного по литеральному пути `C:\Users\Test\Documents\PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="9a4be-125">In the following example, you decrypt content that is located at the literal path `C:\Users\Test\Documents\PowerShell`.</span></span> <span data-ttu-id="9a4be-126">В этом примере для значения параметра Required **to** используется отпечаток сертификата, который использовался для шифрования.</span><span class="sxs-lookup"><span data-stu-id="9a4be-126">For the value of the required **To** parameter, this example uses the thumbprint of the certificate that was used to perform the encryption.</span></span> <span data-ttu-id="9a4be-127">Расшифрованное сообщение "попробовать новую команду" прервать все "— результат.</span><span class="sxs-lookup"><span data-stu-id="9a4be-127">The decrypted message, "Try the new Break All command," is the result.</span></span>

```powershell
$parameters = @{
  LiteralPath = "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
  To = '0f 8j b1 ab e0 ce 35 1d 67 d2 f2 6f a2 d2 00 cl 22 z9 m9 85'
}
Unprotect-CmsMessage -LiteralPath @parameters
```

```Output
Try the new Break All command
```

## <span data-ttu-id="9a4be-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9a4be-128">PARAMETERS</span></span>

### <span data-ttu-id="9a4be-129">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="9a4be-129">-Content</span></span>

<span data-ttu-id="9a4be-130">Задает зашифрованную строку или переменную, содержащую зашифрованную строку.</span><span class="sxs-lookup"><span data-stu-id="9a4be-130">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9a4be-131">-EventLogRecord</span><span class="sxs-lookup"><span data-stu-id="9a4be-131">-EventLogRecord</span></span>

<span data-ttu-id="9a4be-132">Указывает идентификатор записи в журнале событий, представляющий операцию шифрования CMS.</span><span class="sxs-lookup"><span data-stu-id="9a4be-132">Specifies an event log record ID that represents a CMS encryption operation.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByWinEvent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9a4be-133">-Инклудеконтекст</span><span class="sxs-lookup"><span data-stu-id="9a4be-133">-IncludeContext</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a4be-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9a4be-134">-LiteralPath</span></span>

<span data-ttu-id="9a4be-135">Указывает путь к зашифрованному содержимому, которое необходимо расшифровать.</span><span class="sxs-lookup"><span data-stu-id="9a4be-135">Specifies the path to encrypted content that you want to decrypt.</span></span> <span data-ttu-id="9a4be-136">В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="9a4be-136">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9a4be-137">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9a4be-137">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="9a4be-138">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9a4be-138">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9a4be-139">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="9a4be-139">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a4be-140">-Path</span><span class="sxs-lookup"><span data-stu-id="9a4be-140">-Path</span></span>

<span data-ttu-id="9a4be-141">Указывает путь к зашифрованному содержимому, которое необходимо расшифровать.</span><span class="sxs-lookup"><span data-stu-id="9a4be-141">Specifies the path to encrypted content that you want to decrypt.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a4be-142">— Для</span><span class="sxs-lookup"><span data-stu-id="9a4be-142">-To</span></span>

<span data-ttu-id="9a4be-143">Указывает одного или нескольких получателей сообщений CMS, определенных в любом из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="9a4be-143">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="9a4be-144">Фактический сертификат (полученный от поставщика сертификата).</span><span class="sxs-lookup"><span data-stu-id="9a4be-144">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="9a4be-145">Путь к файлу, содержащему сертификат.</span><span class="sxs-lookup"><span data-stu-id="9a4be-145">Path to the a file containing the certificate.</span></span>
- <span data-ttu-id="9a4be-146">Путь к каталогу, содержащему сертификат.</span><span class="sxs-lookup"><span data-stu-id="9a4be-146">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="9a4be-147">Отпечаток сертификата (используется для поиска в хранилище сертификатов).</span><span class="sxs-lookup"><span data-stu-id="9a4be-147">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="9a4be-148">Имя субъекта сертификата (используется для поиска в хранилище сертификатов).</span><span class="sxs-lookup"><span data-stu-id="9a4be-148">Subject name of the certificate (used to look in the certificate store).</span></span>

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a4be-149">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9a4be-149">CommonParameters</span></span>

<span data-ttu-id="9a4be-150">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9a4be-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9a4be-151">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9a4be-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9a4be-152">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9a4be-152">INPUTS</span></span>

### <span data-ttu-id="9a4be-153">System. Diagnostics. Eventing. Reader. EventLogRecord или System. String</span><span class="sxs-lookup"><span data-stu-id="9a4be-153">System.Diagnostics.Eventing.Reader.EventLogRecord or System.String</span></span>

<span data-ttu-id="9a4be-154">Объект, содержащий зашифрованное содержимое, можно передать в `Unprotect-CmsMessage` .</span><span class="sxs-lookup"><span data-stu-id="9a4be-154">You can pipe an object containing encrypted content to `Unprotect-CmsMessage`.</span></span>

## <span data-ttu-id="9a4be-155">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9a4be-155">OUTPUTS</span></span>

### <span data-ttu-id="9a4be-156">System.String</span><span class="sxs-lookup"><span data-stu-id="9a4be-156">System.String</span></span>

<span data-ttu-id="9a4be-157">Незашифрованное сообщение.</span><span class="sxs-lookup"><span data-stu-id="9a4be-157">The unencrypted message.</span></span>

## <span data-ttu-id="9a4be-158">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9a4be-158">NOTES</span></span>

## <span data-ttu-id="9a4be-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9a4be-159">RELATED LINKS</span></span>

[<span data-ttu-id="9a4be-160">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9a4be-160">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="9a4be-161">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9a4be-161">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="9a4be-162">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="9a4be-162">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)
