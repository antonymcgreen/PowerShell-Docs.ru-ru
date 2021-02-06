---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: baf06c34511217f23d876843007525b9ce17f35b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605282"
---
# <span data-ttu-id="98522-102">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="98522-102">Get-PfxCertificate</span></span>

## <span data-ttu-id="98522-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="98522-103">SYNOPSIS</span></span>
<span data-ttu-id="98522-104">Возвращает сведения о файлах сертификатов PFX на компьютере.</span><span class="sxs-lookup"><span data-stu-id="98522-104">Gets information about PFX certificate files on the computer.</span></span>

## <span data-ttu-id="98522-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="98522-105">SYNTAX</span></span>

### <span data-ttu-id="98522-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="98522-106">ByPath (Default)</span></span>

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### <span data-ttu-id="98522-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="98522-107">ByLiteralPath</span></span>

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## <span data-ttu-id="98522-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="98522-108">DESCRIPTION</span></span>

<span data-ttu-id="98522-109">`Get-PfxCertificate`Командлет возвращает объект, представляющий каждый указанный PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="98522-109">The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file.</span></span>
<span data-ttu-id="98522-110">PFX-файл включает сертификат и закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="98522-110">A PFX file includes both the certificate and a private key.</span></span>

## <span data-ttu-id="98522-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="98522-111">EXAMPLES</span></span>

### <span data-ttu-id="98522-112">Пример 1. получение сертификата PFX</span><span class="sxs-lookup"><span data-stu-id="98522-112">Example 1: Get a PFX certificate</span></span>

```powershell
Get-PfxCertificate -FilePath "C:\windows\system32\Test.pfx"
```

```output
Password: ******
Signer Certificate:      David Chew (Self Certificate)
Time Certificate:
Time Stamp:
Path:                    C:\windows\system32\zap.pfx
```

<span data-ttu-id="98522-113">Эта команда возвращает сведения о файле сертификата Test. pfx в системе.</span><span class="sxs-lookup"><span data-stu-id="98522-113">This command gets information about the Test.pfx certificate file on the system.</span></span>

### <span data-ttu-id="98522-114">Пример 2. получение сертификата PFX с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="98522-114">Example 2: Get a PFX certificate from a remote computer</span></span>

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

<span data-ttu-id="98522-115">Эта команда получает PFX-файл сертификата с удаленного компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="98522-115">This command gets a PFX certificate file from the Server01 remote computer.</span></span> <span data-ttu-id="98522-116">Он использует `Invoke-Command` для удаленного выполнения `Get-PfxCertificate` команды.</span><span class="sxs-lookup"><span data-stu-id="98522-116">It uses `Invoke-Command` to run a `Get-PfxCertificate` command remotely.</span></span>

<span data-ttu-id="98522-117">Если файл сертификата PFX не защищен паролем, параметр **проверки подлинности** `Invoke-Command` должен иметь значение CredSSP.</span><span class="sxs-lookup"><span data-stu-id="98522-117">When the PFX certificate file is not password-protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="98522-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="98522-118">PARAMETERS</span></span>

### <span data-ttu-id="98522-119">-FilePath</span><span class="sxs-lookup"><span data-stu-id="98522-119">-FilePath</span></span>

<span data-ttu-id="98522-120">Указывает полный путь к PFX-файлу защищенного файла.</span><span class="sxs-lookup"><span data-stu-id="98522-120">Specifies the full path to the PFX file of the secured file.</span></span> <span data-ttu-id="98522-121">Если указать значение для этого параметра, то вводить `-FilePath` в командной строке не нужно.</span><span class="sxs-lookup"><span data-stu-id="98522-121">If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="98522-122">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="98522-122">-LiteralPath</span></span>

<span data-ttu-id="98522-123">Полный путь к PFX-файлу защищенного файла.</span><span class="sxs-lookup"><span data-stu-id="98522-123">The full path to the PFX file of the secured file.</span></span> <span data-ttu-id="98522-124">В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="98522-124">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="98522-125">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="98522-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="98522-126">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="98522-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="98522-127">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="98522-127">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="98522-128">-Нопромптфорпассворд</span><span class="sxs-lookup"><span data-stu-id="98522-128">-NoPromptForPassword</span></span>

<span data-ttu-id="98522-129">Подавляет запрос пароля.</span><span class="sxs-lookup"><span data-stu-id="98522-129">Suppresses prompting for a password.</span></span>

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

### <span data-ttu-id="98522-130">-Password</span><span class="sxs-lookup"><span data-stu-id="98522-130">-Password</span></span>

<span data-ttu-id="98522-131">Указывает пароль, необходимый для доступа к `.pfx` файлу сертификата.</span><span class="sxs-lookup"><span data-stu-id="98522-131">Specifies a password required to access a `.pfx` certificate file.</span></span>

<span data-ttu-id="98522-132">Этот параметр появился в PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="98522-132">This parameter was introduced in PowerShell 6.1.</span></span>

> [!NOTE]
> <span data-ttu-id="98522-133">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="98522-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98522-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="98522-134">CommonParameters</span></span>

<span data-ttu-id="98522-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="98522-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="98522-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="98522-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="98522-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="98522-137">INPUTS</span></span>

### <span data-ttu-id="98522-138">System.String</span><span class="sxs-lookup"><span data-stu-id="98522-138">System.String</span></span>

<span data-ttu-id="98522-139">Строку, содержащую путь к файлу, можно передать по конвейеру `Get-PfxCertificate` .</span><span class="sxs-lookup"><span data-stu-id="98522-139">You can pipe a string that contains a file path to `Get-PfxCertificate`.</span></span>

## <span data-ttu-id="98522-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="98522-140">OUTPUTS</span></span>

### <span data-ttu-id="98522-141">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="98522-141">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>

<span data-ttu-id="98522-142">`Get-PfxCertificate` Возвращает объект для каждого сертификата, который он получает.</span><span class="sxs-lookup"><span data-stu-id="98522-142">`Get-PfxCertificate` returns an object for each certificate that it gets.</span></span>

## <span data-ttu-id="98522-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="98522-143">NOTES</span></span>

<span data-ttu-id="98522-144">При использовании `Invoke-Command` командлета для удаленного выполнения `Get-PfxCertificate` команды, если файл сертификата pfx не защищен паролем, параметр **проверки подлинности** `Invoke-Command` должен иметь значение CredSSP.</span><span class="sxs-lookup"><span data-stu-id="98522-144">When using the `Invoke-Command` cmdlet to run a `Get-PfxCertificate` command remotely, and the PFX certificate file is not password protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="98522-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="98522-145">RELATED LINKS</span></span>

[<span data-ttu-id="98522-146">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="98522-146">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="98522-147">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="98522-147">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

