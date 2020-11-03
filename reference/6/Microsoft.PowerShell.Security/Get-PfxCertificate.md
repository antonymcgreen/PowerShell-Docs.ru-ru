---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 67bb56a50f452475ba12abb2fccaeeaf5785c8b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229114"
---
# <span data-ttu-id="67047-103">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="67047-103">Get-PfxCertificate</span></span>

## <span data-ttu-id="67047-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="67047-104">SYNOPSIS</span></span>
<span data-ttu-id="67047-105">Возвращает сведения о файлах сертификатов PFX на компьютере.</span><span class="sxs-lookup"><span data-stu-id="67047-105">Gets information about PFX certificate files on the computer.</span></span>

## <span data-ttu-id="67047-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="67047-106">SYNTAX</span></span>

### <span data-ttu-id="67047-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="67047-107">ByPath (Default)</span></span>

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### <span data-ttu-id="67047-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="67047-108">ByLiteralPath</span></span>

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## <span data-ttu-id="67047-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="67047-109">DESCRIPTION</span></span>

<span data-ttu-id="67047-110">`Get-PfxCertificate`Командлет возвращает объект, представляющий каждый указанный PFX-файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="67047-110">The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file.</span></span>
<span data-ttu-id="67047-111">PFX-файл включает сертификат и закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="67047-111">A PFX file includes both the certificate and a private key.</span></span>

## <span data-ttu-id="67047-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="67047-112">EXAMPLES</span></span>

### <span data-ttu-id="67047-113">Пример 1. получение сертификата PFX</span><span class="sxs-lookup"><span data-stu-id="67047-113">Example 1: Get a PFX certificate</span></span>

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

<span data-ttu-id="67047-114">Эта команда возвращает сведения о файле сертификата Test. pfx в системе.</span><span class="sxs-lookup"><span data-stu-id="67047-114">This command gets information about the Test.pfx certificate file on the system.</span></span>

### <span data-ttu-id="67047-115">Пример 2. получение сертификата PFX с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="67047-115">Example 2: Get a PFX certificate from a remote computer</span></span>

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

<span data-ttu-id="67047-116">Эта команда получает PFX-файл сертификата с удаленного компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="67047-116">This command gets a PFX certificate file from the Server01 remote computer.</span></span> <span data-ttu-id="67047-117">Он использует `Invoke-Command` для удаленного выполнения `Get-PfxCertificate` команды.</span><span class="sxs-lookup"><span data-stu-id="67047-117">It uses `Invoke-Command` to run a `Get-PfxCertificate` command remotely.</span></span>

<span data-ttu-id="67047-118">Если файл сертификата PFX не защищен паролем, параметр **проверки подлинности** `Invoke-Command` должен иметь значение CredSSP.</span><span class="sxs-lookup"><span data-stu-id="67047-118">When the PFX certificate file is not password-protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="67047-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="67047-119">PARAMETERS</span></span>

### <span data-ttu-id="67047-120">-FilePath</span><span class="sxs-lookup"><span data-stu-id="67047-120">-FilePath</span></span>

<span data-ttu-id="67047-121">Указывает полный путь к PFX-файлу защищенного файла.</span><span class="sxs-lookup"><span data-stu-id="67047-121">Specifies the full path to the PFX file of the secured file.</span></span> <span data-ttu-id="67047-122">Если указать значение для этого параметра, то вводить `-FilePath` в командной строке не нужно.</span><span class="sxs-lookup"><span data-stu-id="67047-122">If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line.</span></span>

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

### <span data-ttu-id="67047-123">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="67047-123">-LiteralPath</span></span>

<span data-ttu-id="67047-124">Полный путь к PFX-файлу защищенного файла.</span><span class="sxs-lookup"><span data-stu-id="67047-124">The full path to the PFX file of the secured file.</span></span> <span data-ttu-id="67047-125">В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="67047-125">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="67047-126">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="67047-126">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="67047-127">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="67047-127">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="67047-128">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="67047-128">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="67047-129">-Нопромптфорпассворд</span><span class="sxs-lookup"><span data-stu-id="67047-129">-NoPromptForPassword</span></span>

<span data-ttu-id="67047-130">Подавляет запрос пароля.</span><span class="sxs-lookup"><span data-stu-id="67047-130">Suppresses prompting for a password.</span></span>

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

### <span data-ttu-id="67047-131">-Password</span><span class="sxs-lookup"><span data-stu-id="67047-131">-Password</span></span>

<span data-ttu-id="67047-132">Указывает пароль, необходимый для доступа к `.pfx` файлу сертификата.</span><span class="sxs-lookup"><span data-stu-id="67047-132">Specifies a password required to access a `.pfx` certificate file.</span></span>

<span data-ttu-id="67047-133">Этот параметр появился в PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="67047-133">This parameter was introduced in PowerShell 6.1.</span></span>

> [!NOTE]
> <span data-ttu-id="67047-134">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="67047-134">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="67047-135">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="67047-135">CommonParameters</span></span>

<span data-ttu-id="67047-136">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="67047-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="67047-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="67047-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="67047-138">Входные данные</span><span class="sxs-lookup"><span data-stu-id="67047-138">INPUTS</span></span>

### <span data-ttu-id="67047-139">System.String</span><span class="sxs-lookup"><span data-stu-id="67047-139">System.String</span></span>

<span data-ttu-id="67047-140">Строку, содержащую путь к файлу, можно передать по конвейеру `Get-PfxCertificate` .</span><span class="sxs-lookup"><span data-stu-id="67047-140">You can pipe a string that contains a file path to `Get-PfxCertificate`.</span></span>

## <span data-ttu-id="67047-141">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="67047-141">OUTPUTS</span></span>

### <span data-ttu-id="67047-142">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="67047-142">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>

<span data-ttu-id="67047-143">`Get-PfxCertificate` Возвращает объект для каждого сертификата, который он получает.</span><span class="sxs-lookup"><span data-stu-id="67047-143">`Get-PfxCertificate` returns an object for each certificate that it gets.</span></span>

## <span data-ttu-id="67047-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="67047-144">NOTES</span></span>

<span data-ttu-id="67047-145">При использовании `Invoke-Command` командлета для удаленного выполнения `Get-PfxCertificate` команды, если файл сертификата pfx не защищен паролем, параметр **проверки подлинности** `Invoke-Command` должен иметь значение CredSSP.</span><span class="sxs-lookup"><span data-stu-id="67047-145">When using the `Invoke-Command` cmdlet to run a `Get-PfxCertificate` command remotely, and the PFX certificate file is not password protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="67047-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="67047-146">RELATED LINKS</span></span>

[<span data-ttu-id="67047-147">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="67047-147">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="67047-148">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="67047-148">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)
