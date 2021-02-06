---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: ed1c80a70e8fc51c242be6f9369f0a0bd44cb9c8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603973"
---
# <span data-ttu-id="cb8bf-102">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="cb8bf-102">Unprotect-CmsMessage</span></span>

## <span data-ttu-id="cb8bf-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cb8bf-103">SYNOPSIS</span></span>
<span data-ttu-id="cb8bf-104">Расшифровывает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-104">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="cb8bf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb8bf-105">SYNTAX</span></span>

### <span data-ttu-id="cb8bf-106">Бивиневент (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cb8bf-106">ByWinEvent (Default)</span></span>

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="cb8bf-107">биконтент</span><span class="sxs-lookup"><span data-stu-id="cb8bf-107">ByContent</span></span>

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="cb8bf-108">бипас</span><span class="sxs-lookup"><span data-stu-id="cb8bf-108">ByPath</span></span>

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="cb8bf-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="cb8bf-109">ByLiteralPath</span></span>

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="cb8bf-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb8bf-110">DESCRIPTION</span></span>

<span data-ttu-id="cb8bf-111">`Unprotect-CmsMessage`Командлет расшифровывает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения (CMS).</span><span class="sxs-lookup"><span data-stu-id="cb8bf-111">The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="cb8bf-112">Командлеты CMS поддерживают шифрование и расшифровку содержимого, используя стандартный формат IETF для криптографической защиты сообщений, как описано в [RFC5652](https://tools.ietf.org/html/rfc5652).</span><span class="sxs-lookup"><span data-stu-id="cb8bf-112">The CMS cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="cb8bf-113">Стандарт шифрования CMS использует шифрование с открытым ключом, где ключи, используемые для шифрования содержимого (открытый ключ) и ключи, используемые для расшифровки содержимого (закрытый ключ), являются отдельными.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-113">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="cb8bf-114">Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-114">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="cb8bf-115">Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-115">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="cb8bf-116">Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="cb8bf-116">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="cb8bf-117">`Unprotect-CmsMessage` расшифровывает содержимое, зашифрованное в формате CMS.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-117">`Unprotect-CmsMessage` decrypts content that has been encrypted in CMS format.</span></span> <span data-ttu-id="cb8bf-118">Этот командлет можно использовать для расшифровки зашифрованного содержимого, выполнив `Protect-CmsMessage` командлет.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-118">You can run this cmdlet to decrypt content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="cb8bf-119">Можно указать содержимое, которое нужно расшифровать как строку, с помощью идентификатора записи журнала событий шифрования или путем к зашифрованному содержимому.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-119">You can specify content that you want to decrypt as a string, by the encryption event log record ID number, or by path to the encrypted content.</span></span> <span data-ttu-id="cb8bf-120">`Unprotect-CmsMessage`Командлет возвращает расшифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-120">The `Unprotect-CmsMessage` cmdlet returns the decrypted content.</span></span>

<span data-ttu-id="cb8bf-121">В PowerShell 7,1 добавлена поддержка Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-121">Support for Linux and macOS was added in PowerShell 7.1.</span></span>

## <span data-ttu-id="cb8bf-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="cb8bf-122">EXAMPLES</span></span>

### <span data-ttu-id="cb8bf-123">Пример 1. Расшифровка сообщения</span><span class="sxs-lookup"><span data-stu-id="cb8bf-123">Example 1: Decrypt a message</span></span>

<span data-ttu-id="cb8bf-124">В следующем примере выполняется расшифровка содержимого, расположенного по литеральному пути `C:\Users\Test\Documents\PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="cb8bf-124">In the following example, you decrypt content that is located at the literal path `C:\Users\Test\Documents\PowerShell`.</span></span> <span data-ttu-id="cb8bf-125">В этом примере для значения параметра Required **to** используется отпечаток сертификата, который использовался для шифрования.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-125">For the value of the required **To** parameter, this example uses the thumbprint of the certificate that was used to perform the encryption.</span></span> <span data-ttu-id="cb8bf-126">Расшифрованное сообщение "попробовать новую команду" прервать все "— результат.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-126">The decrypted message, "Try the new Break All command," is the result.</span></span>

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

## <span data-ttu-id="cb8bf-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb8bf-127">PARAMETERS</span></span>

### <span data-ttu-id="cb8bf-128">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="cb8bf-128">-Content</span></span>

<span data-ttu-id="cb8bf-129">Задает зашифрованную строку или переменную, содержащую зашифрованную строку.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-129">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

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

### <span data-ttu-id="cb8bf-130">-EventLogRecord</span><span class="sxs-lookup"><span data-stu-id="cb8bf-130">-EventLogRecord</span></span>

<span data-ttu-id="cb8bf-131">Указывает идентификатор записи в журнале событий, представляющий операцию шифрования CMS.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-131">Specifies an event log record ID that represents a CMS encryption operation.</span></span>

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

### <span data-ttu-id="cb8bf-132">-Инклудеконтекст</span><span class="sxs-lookup"><span data-stu-id="cb8bf-132">-IncludeContext</span></span>

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

### <span data-ttu-id="cb8bf-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cb8bf-133">-LiteralPath</span></span>

<span data-ttu-id="cb8bf-134">Указывает путь к зашифрованному содержимому, которое необходимо расшифровать.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-134">Specifies the path to encrypted content that you want to decrypt.</span></span> <span data-ttu-id="cb8bf-135">В отличие от параметра **Path**, значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-135">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="cb8bf-136">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-136">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="cb8bf-137">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-137">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="cb8bf-138">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-138">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="cb8bf-139">-Path</span><span class="sxs-lookup"><span data-stu-id="cb8bf-139">-Path</span></span>

<span data-ttu-id="cb8bf-140">Указывает путь к зашифрованному содержимому, которое необходимо расшифровать.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-140">Specifies the path to encrypted content that you want to decrypt.</span></span>

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

### <span data-ttu-id="cb8bf-141">— Для</span><span class="sxs-lookup"><span data-stu-id="cb8bf-141">-To</span></span>

<span data-ttu-id="cb8bf-142">Указывает одного или нескольких получателей сообщений CMS, определенных в любом из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="cb8bf-142">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="cb8bf-143">Фактический сертификат (полученный от поставщика сертификата).</span><span class="sxs-lookup"><span data-stu-id="cb8bf-143">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="cb8bf-144">Путь к файлу, содержащему сертификат.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-144">Path to the a file containing the certificate.</span></span>
- <span data-ttu-id="cb8bf-145">Путь к каталогу, содержащему сертификат.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-145">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="cb8bf-146">Отпечаток сертификата (используется для поиска в хранилище сертификатов).</span><span class="sxs-lookup"><span data-stu-id="cb8bf-146">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="cb8bf-147">Имя субъекта сертификата (используется для поиска в хранилище сертификатов).</span><span class="sxs-lookup"><span data-stu-id="cb8bf-147">Subject name of the certificate (used to look in the certificate store).</span></span>

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

### <span data-ttu-id="cb8bf-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cb8bf-148">CommonParameters</span></span>

<span data-ttu-id="cb8bf-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb8bf-150">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cb8bf-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cb8bf-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cb8bf-151">INPUTS</span></span>

### <span data-ttu-id="cb8bf-152">System. Diagnostics. Eventing. Reader. EventLogRecord или System. String</span><span class="sxs-lookup"><span data-stu-id="cb8bf-152">System.Diagnostics.Eventing.Reader.EventLogRecord or System.String</span></span>

<span data-ttu-id="cb8bf-153">Объект, содержащий зашифрованное содержимое, можно передать в `Unprotect-CmsMessage` .</span><span class="sxs-lookup"><span data-stu-id="cb8bf-153">You can pipe an object containing encrypted content to `Unprotect-CmsMessage`.</span></span>

## <span data-ttu-id="cb8bf-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cb8bf-154">OUTPUTS</span></span>

### <span data-ttu-id="cb8bf-155">System.String</span><span class="sxs-lookup"><span data-stu-id="cb8bf-155">System.String</span></span>

<span data-ttu-id="cb8bf-156">Незашифрованное сообщение.</span><span class="sxs-lookup"><span data-stu-id="cb8bf-156">The unencrypted message.</span></span>

## <span data-ttu-id="cb8bf-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cb8bf-157">NOTES</span></span>

## <span data-ttu-id="cb8bf-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cb8bf-158">RELATED LINKS</span></span>

[<span data-ttu-id="cb8bf-159">about_Providers</span><span class="sxs-lookup"><span data-stu-id="cb8bf-159">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="cb8bf-160">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="cb8bf-160">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="cb8bf-161">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="cb8bf-161">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)
