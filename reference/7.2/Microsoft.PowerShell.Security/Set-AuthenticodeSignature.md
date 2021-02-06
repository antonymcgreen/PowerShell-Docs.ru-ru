---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: 831f40e9bd24cee20eeae54a41e0b022dc6300da
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603953"
---
# <span data-ttu-id="ea0db-102">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ea0db-102">Set-AuthenticodeSignature</span></span>

## <span data-ttu-id="ea0db-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ea0db-103">SYNOPSIS</span></span>
<span data-ttu-id="ea0db-104">Добавляет подпись [Authenticode](/windows-hardware/drivers/install/authenticode) в скрипт PowerShell или другой файл.</span><span class="sxs-lookup"><span data-stu-id="ea0db-104">Adds an [Authenticode](/windows-hardware/drivers/install/authenticode) signature to a PowerShell script or other file.</span></span>

## <span data-ttu-id="ea0db-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea0db-105">SYNTAX</span></span>

### <span data-ttu-id="ea0db-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ea0db-106">ByPath (Default)</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ea0db-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="ea0db-107">ByLiteralPath</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ea0db-108">биконтент</span><span class="sxs-lookup"><span data-stu-id="ea0db-108">ByContent</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ea0db-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea0db-109">DESCRIPTION</span></span>

<span data-ttu-id="ea0db-110">`Set-AuthenticodeSignature`Командлет добавляет подпись Authenticode в любой файл, поддерживающий пакет интерфейса субъекта (SIP).</span><span class="sxs-lookup"><span data-stu-id="ea0db-110">The `Set-AuthenticodeSignature` cmdlet adds an Authenticode signature to any file that supports Subject Interface Package (SIP).</span></span>

<span data-ttu-id="ea0db-111">В файле сценария PowerShell сигнатура принимает форму блока текста, который указывает на конец инструкций, выполняемых в скрипте.</span><span class="sxs-lookup"><span data-stu-id="ea0db-111">In a PowerShell script file, the signature takes the form of a block of text that indicates the end of the instructions that are executed in the script.</span></span> <span data-ttu-id="ea0db-112">Если при запуске командлета подпись в файле уже есть, эта подпись удаляется.</span><span class="sxs-lookup"><span data-stu-id="ea0db-112">If there is a signature in the file when this cmdlet runs, that signature is removed.</span></span>

## <span data-ttu-id="ea0db-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="ea0db-113">EXAMPLES</span></span>

### <span data-ttu-id="ea0db-114">Пример 1. Подписание скрипта с помощью сертификата из локального хранилища сертификатов</span><span class="sxs-lookup"><span data-stu-id="ea0db-114">Example 1 - Sign a script using a certificate from the local certificate store</span></span>

<span data-ttu-id="ea0db-115">Эти команды извлекают сертификат подписи кода из поставщика сертификата PowerShell и используют его для подписания скрипта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea0db-115">These commands retrieve a code-signing certificate from the PowerShell certificate provider and use it to sign a PowerShell script.</span></span>

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

<span data-ttu-id="ea0db-116">Первая команда использует `Get-ChildItem` командлет и поставщик сертификата PowerShell для получения сертификатов в `Cert:\CurrentUser\My` подкаталоге хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ea0db-116">The first command uses the `Get-ChildItem` cmdlet and the PowerShell certificate provider to get the certificates in the `Cert:\CurrentUser\My` subdirectory of the certificate store.</span></span> <span data-ttu-id="ea0db-117">`Cert:`Диск — это диск, предоставляемый поставщиком сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ea0db-117">The `Cert:` drive is the drive exposed by the certificate provider.</span></span> <span data-ttu-id="ea0db-118">Параметр **CodeSigningCert** , который поддерживается только поставщиком сертификатов, ограничивает доступ к сертификатам, получаемым с помощью центра подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="ea0db-118">The **CodeSigningCert** parameter, which is supported only by the certificate provider, limits the certificates retrieved to those with code-signing authority.</span></span> <span data-ttu-id="ea0db-119">Команда сохраняет результат в `$cert` переменной.</span><span class="sxs-lookup"><span data-stu-id="ea0db-119">The command stores the result in the `$cert` variable.</span></span>

<span data-ttu-id="ea0db-120">Вторая команда использует `Set-AuthenticodeSignature` командлет для подписи `PSTestInternet2.ps1` скрипта.</span><span class="sxs-lookup"><span data-stu-id="ea0db-120">The second command uses the `Set-AuthenticodeSignature` cmdlet to sign the `PSTestInternet2.ps1` script.</span></span> <span data-ttu-id="ea0db-121">Он использует параметр **FilePath** , чтобы указать имя скрипта и параметр **сертификата** , чтобы указать, что сертификат хранится в `$cert` переменной.</span><span class="sxs-lookup"><span data-stu-id="ea0db-121">It uses the **FilePath** parameter to specify the name of the script and the **Certificate** parameter to specify that the certificate is stored in the `$cert` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="ea0db-122">Использование параметра **CodeSigningCert** с параметрами `Get-ChildItem` возвращает только сертификаты, которые имеют центр подписи кода и содержат закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ea0db-122">Using the **CodeSigningCert** parameter with `Get-ChildItem` only returns certificates that have code-signing authority and contain a private key.</span></span> <span data-ttu-id="ea0db-123">Если закрытый ключ отсутствует, сертификаты не могут использоваться для подписывания.</span><span class="sxs-lookup"><span data-stu-id="ea0db-123">If there is no private key, the certificates cannot be used for signing.</span></span>

### <span data-ttu-id="ea0db-124">Пример 2. Подписание сценария с помощью сертификата из PFX-файла</span><span class="sxs-lookup"><span data-stu-id="ea0db-124">Example 2 - Sign a script using a certificate from a PFX file</span></span>

<span data-ttu-id="ea0db-125">Эти команды используют `Get-PfxCertificate` командлет для загрузки сертификата подписи кода.</span><span class="sxs-lookup"><span data-stu-id="ea0db-125">These commands use the `Get-PfxCertificate` cmdlet to load a code signing certificate.</span></span> <span data-ttu-id="ea0db-126">Затем используйте его для подписания скрипта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea0db-126">Then, use it to sign a PowerShell script.</span></span>

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

<span data-ttu-id="ea0db-127">Первая команда использует `Get-PfxCertificate` командлет для загрузки сертификата к:\тест\мисигн.пфкс в `$cert` переменную.</span><span class="sxs-lookup"><span data-stu-id="ea0db-127">The first command uses the `Get-PfxCertificate` cmdlet to load the C:\Test\MySign.pfx certificate into the `$cert` variable.</span></span>

<span data-ttu-id="ea0db-128">Вторая команда использует `Set-AuthenticodeSignature` для подписания скрипта.</span><span class="sxs-lookup"><span data-stu-id="ea0db-128">The second command uses `Set-AuthenticodeSignature` to sign the script.</span></span> <span data-ttu-id="ea0db-129">Параметр **FilePath** параметра `Set-AuthenticodeSignature` указывает путь к подписанному файлу скрипта, а параметр **CERT** передает `$cert` переменную, содержащую сертификат `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="ea0db-129">The **FilePath** parameter of `Set-AuthenticodeSignature` specifies the path to the script file being signed and the **Cert** parameter passes the `$cert` variable containing the certificate to `Set-AuthenticodeSignature`.</span></span>

<span data-ttu-id="ea0db-130">Если файл сертификата защищен паролем, PowerShell запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="ea0db-130">If the certificate file is password protected, PowerShell prompts you for the password.</span></span>

### <span data-ttu-id="ea0db-131">Пример 3. Добавление подписи, включающей корневой центр</span><span class="sxs-lookup"><span data-stu-id="ea0db-131">Example 3 - Add a signature that includes the root authority</span></span>

<span data-ttu-id="ea0db-132">Эта команда добавляет цифровую подпись, включающую корневой центр в цепочке доверия, и подпись стороннего сервера отметок времени.</span><span class="sxs-lookup"><span data-stu-id="ea0db-132">This command adds a digital signature that includes the root authority in the trust chain, and it is signed by a third-party timestamp server.</span></span>

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

<span data-ttu-id="ea0db-133">Команда использует параметр **FilePath** для указания подписанного скрипта, а параметр **сертификата** — для указания сертификата, сохраненного в `$cert` переменной.</span><span class="sxs-lookup"><span data-stu-id="ea0db-133">The command uses the **FilePath** parameter to specify the script being signed and the **Certificate** parameter to specify the certificate that is saved in the `$cert` variable.</span></span> <span data-ttu-id="ea0db-134">Он использует параметр **инклудечаин** для включения всех подписей в цепочку доверия, включая корневой центр.</span><span class="sxs-lookup"><span data-stu-id="ea0db-134">It uses the **IncludeChain** parameter to include all of the signatures in the trust chain, including the root authority.</span></span> <span data-ttu-id="ea0db-135">Он также использует параметр **тиместампсервер** для добавления метки времени к сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="ea0db-135">It also uses the **TimeStampServer** parameter to add a timestamp to the signature.</span></span>
<span data-ttu-id="ea0db-136">Это защищает скрипт от сбоя, если срок действия сертификата истек.</span><span class="sxs-lookup"><span data-stu-id="ea0db-136">This prevents the script from failing when the certificate expires.</span></span>

## <span data-ttu-id="ea0db-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea0db-137">PARAMETERS</span></span>

### <span data-ttu-id="ea0db-138">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="ea0db-138">-Certificate</span></span>

<span data-ttu-id="ea0db-139">Задает сертификат, который будет использоваться для подписания скрипта или файла.</span><span class="sxs-lookup"><span data-stu-id="ea0db-139">Specifies the certificate that will be used to sign the script or file.</span></span> <span data-ttu-id="ea0db-140">Введите переменную, в которой хранится объект, представляющий сертификат, или выражение, которое получает сертификат.</span><span class="sxs-lookup"><span data-stu-id="ea0db-140">Enter a variable that stores an object representing the certificate or an expression that gets the certificate.</span></span>

<span data-ttu-id="ea0db-141">Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске с сертификатом `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="ea0db-141">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate `Cert:` drive.</span></span> <span data-ttu-id="ea0db-142">Если сертификат недействителен или не имеет `code-signing` полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ea0db-142">If the certificate is not valid or does not have `code-signing` authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ea0db-143">-FilePath</span></span>

<span data-ttu-id="ea0db-144">Указывает путь к подписываемому файлу.</span><span class="sxs-lookup"><span data-stu-id="ea0db-144">Specifies the path to a file that is being signed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-145">-Force</span><span class="sxs-lookup"><span data-stu-id="ea0db-145">-Force</span></span>

<span data-ttu-id="ea0db-146">Позволяет командлету добавлять подпись в файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ea0db-146">Allows the cmdlet to append a signature to a read-only file.</span></span> <span data-ttu-id="ea0db-147">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="ea0db-147">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-148">-HashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="ea0db-148">-HashAlgorithm</span></span>

<span data-ttu-id="ea0db-149">Задает алгоритм хэширования, который использует Windows для расчета цифровой подписи для файла.</span><span class="sxs-lookup"><span data-stu-id="ea0db-149">Specifies the hashing algorithm that Windows uses to compute the digital signature for the file.</span></span>

<span data-ttu-id="ea0db-150">Для PowerShell 3,0 значение по умолчанию — SHA256, то есть алгоритм хэширования Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea0db-150">For PowerShell 3.0, the default is SHA256, which is the Windows default hashing algorithm.</span></span> <span data-ttu-id="ea0db-151">Для PowerShell 2,0 значение по умолчанию — SHA1.</span><span class="sxs-lookup"><span data-stu-id="ea0db-151">For PowerShell 2.0, the default is SHA1.</span></span> <span data-ttu-id="ea0db-152">Файлы, подписанные с использованием другого алгоритма хэширования, могут не распознаваться в других системах.</span><span class="sxs-lookup"><span data-stu-id="ea0db-152">Files that are signed with a different hashing algorithm might not be recognized on other systems.</span></span> <span data-ttu-id="ea0db-153">Поддерживаемые алгоритмы зависят от версии операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ea0db-153">Which algorithms are supported depends on the version of the operating system.</span></span>

<span data-ttu-id="ea0db-154">Список возможных значений см. в разделе [Структура хашалгорисмнаме](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span><span class="sxs-lookup"><span data-stu-id="ea0db-154">For a list of possible values, see [HashAlgorithmName Struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SHA256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-155">-Инклудечаин</span><span class="sxs-lookup"><span data-stu-id="ea0db-155">-IncludeChain</span></span>

<span data-ttu-id="ea0db-156">Определяет, какие сертификаты в цепочке доверия сертификатов включаются в цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="ea0db-156">Determines which certificates in the certificate trust chain are included in the digital signature.</span></span>
<span data-ttu-id="ea0db-157">По умолчанию используется **нотрут** .</span><span class="sxs-lookup"><span data-stu-id="ea0db-157">**NotRoot** is the default.</span></span>

<span data-ttu-id="ea0db-158">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ea0db-158">Valid values are:</span></span>

- <span data-ttu-id="ea0db-159">Подписавший: включает только сертификат подписывания.</span><span class="sxs-lookup"><span data-stu-id="ea0db-159">Signer: Includes only the signer's certificate.</span></span>
- <span data-ttu-id="ea0db-160">Нотрут: включает все сертификаты в цепочке сертификатов, за исключением корневого центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="ea0db-160">NotRoot: Includes all of the certificates in the certificate chain, except for the root authority.</span></span>
- <span data-ttu-id="ea0db-161">Все: включает все сертификаты в цепочке сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ea0db-161">All: Includes all the certificates in the certificate chain.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NotRoot
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-162">-Тиместампсервер</span><span class="sxs-lookup"><span data-stu-id="ea0db-162">-TimestampServer</span></span>

<span data-ttu-id="ea0db-163">Добавляет к подписи отметку времени, использует заданный сервер отметок времени.</span><span class="sxs-lookup"><span data-stu-id="ea0db-163">Uses the specified time stamp server to add a time stamp to the signature.</span></span> <span data-ttu-id="ea0db-164">Введите URL-адрес сервера отметок времени в виде строки.</span><span class="sxs-lookup"><span data-stu-id="ea0db-164">Type the URL of the time stamp server as a string.</span></span>

<span data-ttu-id="ea0db-165">Отметка времени представляет собой значение точного времени, когда сертификат был добавлен в файл.</span><span class="sxs-lookup"><span data-stu-id="ea0db-165">The time stamp represents the exact time that the certificate was added to the file.</span></span> <span data-ttu-id="ea0db-166">Отметка времени защищает скрипт от сбоев в случае истечения срока действия сертификата, поскольку пользователи и программы могут проверить, что сертификат действовал в момент подписания.</span><span class="sxs-lookup"><span data-stu-id="ea0db-166">A time stamp prevents the script from failing if the certificate expires because users and programs can verify that the certificate was valid at the time of signing.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-167">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ea0db-167">-LiteralPath</span></span>

<span data-ttu-id="ea0db-168">Указывает путь к подписываемому файлу.</span><span class="sxs-lookup"><span data-stu-id="ea0db-168">Specifies the path to a file that is being signed.</span></span> <span data-ttu-id="ea0db-169">В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="ea0db-169">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="ea0db-170">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="ea0db-170">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ea0db-171">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ea0db-171">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ea0db-172">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="ea0db-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="ea0db-173">-Саурцепасорекстенсион</span><span class="sxs-lookup"><span data-stu-id="ea0db-173">-SourcePathOrExtension</span></span>

<span data-ttu-id="ea0db-174">Путь к файлу или типу файла содержимого, для которого добавляется цифровая подпись.</span><span class="sxs-lookup"><span data-stu-id="ea0db-174">Path to the file or file type of the content for which the digital signature is added.</span></span> <span data-ttu-id="ea0db-175">Этот параметр используется с **содержимым** , где содержимое файла передается как массив байтов.</span><span class="sxs-lookup"><span data-stu-id="ea0db-175">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-176">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="ea0db-176">-Content</span></span>

<span data-ttu-id="ea0db-177">Содержимое файла в виде массива байтов, для которого добавляется цифровая подпись.</span><span class="sxs-lookup"><span data-stu-id="ea0db-177">Contents of a file as a byte array for which the digital signature is added.</span></span> <span data-ttu-id="ea0db-178">Этот параметр должен использоваться с параметром **саурцепасорекстенсион** .</span><span class="sxs-lookup"><span data-stu-id="ea0db-178">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="ea0db-179">Содержимое файла должно быть в формате Unicode (UTF-16LE).</span><span class="sxs-lookup"><span data-stu-id="ea0db-179">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ea0db-180">-Confirm</span></span>

<span data-ttu-id="ea0db-181">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="ea0db-181">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ea0db-182">-WhatIf</span></span>

<span data-ttu-id="ea0db-183">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="ea0db-183">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ea0db-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ea0db-184">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea0db-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ea0db-185">CommonParameters</span></span>

<span data-ttu-id="ea0db-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ea0db-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea0db-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ea0db-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea0db-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ea0db-188">INPUTS</span></span>

### <span data-ttu-id="ea0db-189">System.String</span><span class="sxs-lookup"><span data-stu-id="ea0db-189">System.String</span></span>

<span data-ttu-id="ea0db-190">Строку, содержащую путь к файлу, можно передать по конвейеру `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="ea0db-190">You can pipe a string that contains the file path to `Set-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="ea0db-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ea0db-191">OUTPUTS</span></span>

### <span data-ttu-id="ea0db-192">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="ea0db-192">System.Management.Automation.Signature</span></span>

## <span data-ttu-id="ea0db-193">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ea0db-193">NOTES</span></span>

<span data-ttu-id="ea0db-194">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="ea0db-194">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="ea0db-195">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ea0db-195">RELATED LINKS</span></span>

[<span data-ttu-id="ea0db-196">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ea0db-196">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="ea0db-197">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ea0db-197">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="ea0db-198">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="ea0db-198">Get-PfxCertificate</span></span>](Get-PfxCertificate.md)

[<span data-ttu-id="ea0db-199">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ea0db-199">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="ea0db-200">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="ea0db-200">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="ea0db-201">about_Signing</span><span class="sxs-lookup"><span data-stu-id="ea0db-201">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
