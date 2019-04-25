---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: b8940ded189d822a5a2cd40773ef5146353611cc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62059004"
---
# <a name="cryptographic-message-syntax-cms-cmdlets"></a><span data-ttu-id="59b85-102">Командлеты Cryptographic Message Syntax (CMS)</span><span class="sxs-lookup"><span data-stu-id="59b85-102">Cryptographic Message Syntax (CMS) cmdlets</span></span>

<span data-ttu-id="59b85-103">Командлеты Cryptographic Message Syntax поддерживают шифрование и расшифровку содержимого с помощью стандартного формата IETF для криптографической защиты сообщений, задокументированного в [RFC5652](https://tools.ietf.org/html/rfc5652).</span><span class="sxs-lookup"><span data-stu-id="59b85-103">The Cryptographic Message Syntax cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

```powershell
Get-CmsMessage [-Content] <string>
Get-CmsMessage [-Path] <string>
Get-CmsMessage [-LiteralPath] <string>
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <string> [[-OutFile] <string>]
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <string> [[-OutFile] <string>]
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <string> [[-OutFile] <string>]
Unprotect-CmsMessage [-EventLogRecord] <EventLogRecord> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
Unprotect-CmsMessage [-Content] <string> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
Unprotect-CmsMessage [-Path] <string> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
Unprotect-CmsMessage [-LiteralPath] <string> [[-To] <CmsMessageRecipient[]>] [-IncludeContext]
```

<span data-ttu-id="59b85-104">Стандарт шифрования CMS реализует шифрование с открытым ключом, при котором ключи, используемые для шифрования содержимого (*открытый ключ*) и для его расшифровки (*закрытый ключ*), существуют отдельно.</span><span class="sxs-lookup"><span data-stu-id="59b85-104">The CMS encryption standard implements public key cryptography, where the keys used to encrypt content (the *public key*) and the keys used to decrypt content (the *private key*) are separate.</span></span>

<span data-ttu-id="59b85-105">Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям.</span><span class="sxs-lookup"><span data-stu-id="59b85-105">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="59b85-106">Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="59b85-106">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="59b85-107">Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="59b85-107">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="59b85-108">Для распознавания в PowerShell сертификатам шифрования требуется уникальный идентификатор использования ключа (EKU), который определяет их в качестве сертификатов шифрования данных (например, идентификаторы для "Подписывание кода", "Зашифрованная почта").</span><span class="sxs-lookup"><span data-stu-id="59b85-108">To be recognized in PowerShell, encryption certificates require a unique key usage identifier (EKU) to identify them as data encryption certificates (like the identifiers for 'Code Signing', 'Encrypted Mail').</span></span>

<span data-ttu-id="59b85-109">Ниже приведен пример создания сертификата, который хорошо подходит для шифрования документов:</span><span class="sxs-lookup"><span data-stu-id="59b85-109">Here is an example of creating a certificate that is good for Document Encryption:</span></span>

```powershell
(Change the text in **Subject** to your name, email, or other identifier), and put in a file (i.e.: DocumentEncryption.inf):
[Version]
Signature = "$Windows NT$"
[Strings]
szOID\_ENHANCED\_KEY\_USAGE = "2.5.29.37"
szOID\_DOCUMENT\_ENCRYPTION = "1.3.6.1.4.1.311.80.1"
[NewRequest]
Subject = "<cn=me@somewhere.com>"
MachineKeySet = false
KeyLength = 2048
KeySpec = AT\_KEYEXCHANGE
HashAlgorithm = Sha1
Exportable = true
RequestType = Cert
KeyUsage = "CERT\_KEY\_ENCIPHERMENT\_KEY\_USAGE | CERT\_DATA\_ENCIPHERMENT\_KEY\_USAGE"
ValidityPeriod = "Years"
ValidityPeriodUnits = "1000"
[Extensions]
%szOID\_ENHANCED\_KEY\_USAGE% = "{text}%szOID\_DOCUMENT\_ENCRYPTION%"
```

<span data-ttu-id="59b85-110">Далее выполните:</span><span class="sxs-lookup"><span data-stu-id="59b85-110">Then run:</span></span>
```powershell
certreq -new DocumentEncryption.inf DocumentEncryption.cer
```

<span data-ttu-id="59b85-111">Теперь вы можете шифровать и расшифровывать содержимое:</span><span class="sxs-lookup"><span data-stu-id="59b85-111">And you can now encrypt and decrypt content:</span></span>

```powershell
$protected = "Hello World" | Protect-CmsMessage -To "\*me@somewhere.com\*[](mailto:*leeholm@microsoft.com*)"
$protected
-----BEGIN CMS-----
MIIBqAYJKoZIhvcNAQcDoIIBmTCCAZUCAQAxggFQMIIBTAIBADA0MCAxHjAcBgNVBAMMFWxlZWhv
bG1AbWljcm9zb2Z0LmNvbQIQQYHsbcXnjIJCtH+OhGmc1DANBgkqhkiG9w0BAQcwAASCAQAnkFHM
proJnFy4geFGfyNmxH3yeoPvwEYzdnsoVqqDPAd8D3wao77z7OhJEXwz9GeFLnxD6djKV/tF4PxR
E27aduKSLbnxfpf/sepZ4fUkuGibnwWFrxGE3B1G26MCenHWjYQiqv+Nq32Gc97qEAERrhLv6S4R
G+2dJEnesW8A+z9QPo+DwYU5FzD0Td0ExrkswVckpLNR6j17Yaags3ltNVmbdEXekhi6Psf2MLMP
TSO79lv2L0KeXFGuPOrdzPAwCkV0vNEqTEBeDnZGrjv/5766bM3GW34FXApod9u+VSFpBnqVOCBA
DVDraA6k+xwBt66cV84OHLkh0kT02SIHMDwGCSqGSIb3DQEHATAdBglghkgBZQMEASoEEJbJaiRl
KMnBoD1dkb/FzSWAEBaL8xkFwCu0e1ZtDj7nSJc=
-----END CMS-----

$protected | Unprotect-CmsMessage
Hello World
```

<span data-ttu-id="59b85-112">Любой параметр типа **CMSMessageRecipient** поддерживает идентификаторы в следующих форматах:</span><span class="sxs-lookup"><span data-stu-id="59b85-112">Any parameter of type **CMSMessageRecipient** supports identifiers in the following formats:</span></span>
- <span data-ttu-id="59b85-113">Фактический сертификат (в том виде, в котором он получен от поставщика сертификатов)</span><span class="sxs-lookup"><span data-stu-id="59b85-113">An actual certificate (as retrieved from the certificate provider)</span></span>
- <span data-ttu-id="59b85-114">Путь к файлу, содержащему сертификат</span><span class="sxs-lookup"><span data-stu-id="59b85-114">Path to the a file containing the certificate</span></span>
- <span data-ttu-id="59b85-115">Путь к каталогу, содержащему сертификат</span><span class="sxs-lookup"><span data-stu-id="59b85-115">Path to a directory containing the certificate</span></span>
- <span data-ttu-id="59b85-116">Отпечаток сертификата (используемый для поиска в хранилище сертификатов)</span><span class="sxs-lookup"><span data-stu-id="59b85-116">Thumbprint of the certificate (used to look in the certificate store)</span></span>
- <span data-ttu-id="59b85-117">Имя субъекта сертификата (используемое для поиска в хранилище сертификатов)</span><span class="sxs-lookup"><span data-stu-id="59b85-117">Subject name of the certificate (used to look in the certificate store)</span></span>

<span data-ttu-id="59b85-118">Чтобы просмотреть сертификаты шифрования документов в поставщике сертификатов, можно использовать динамический параметр **-DocumentEncryptionCert**:</span><span class="sxs-lookup"><span data-stu-id="59b85-118">To view document encryption certificates in the certificate provider, you can use the **-DocumentEncryptionCert** dynamic parameter:</span></span>

```powershell
dir -DocumentEncryptionCert
```
