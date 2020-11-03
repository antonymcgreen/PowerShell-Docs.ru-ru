---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-authenticodesignature?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AuthenticodeSignature
ms.openlocfilehash: d4d0b6cf71ac1f856d66639bccd1fce8ab91ccc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229106"
---
# <span data-ttu-id="9d46c-103">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="9d46c-103">Set-AuthenticodeSignature</span></span>

## <span data-ttu-id="9d46c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9d46c-104">SYNOPSIS</span></span>
<span data-ttu-id="9d46c-105">Добавляет подпись [Authenticode](/windows-hardware/drivers/install/authenticode) в скрипт PowerShell или другой файл.</span><span class="sxs-lookup"><span data-stu-id="9d46c-105">Adds an [Authenticode](/windows-hardware/drivers/install/authenticode) signature to a PowerShell script or other file.</span></span>

## <span data-ttu-id="9d46c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9d46c-106">SYNTAX</span></span>

### <span data-ttu-id="9d46c-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9d46c-107">ByPath (Default)</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] [-FilePath] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9d46c-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d46c-108">ByLiteralPath</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -LiteralPath <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9d46c-109">биконтент</span><span class="sxs-lookup"><span data-stu-id="9d46c-109">ByContent</span></span>

```
Set-AuthenticodeSignature [-Certificate] <X509Certificate2> [-IncludeChain <String>]
 [-TimestampServer <String>] [-HashAlgorithm <String>] [-Force] -SourcePathOrExtension <String[]>
 -Content <Byte[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9d46c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d46c-110">DESCRIPTION</span></span>

<span data-ttu-id="9d46c-111">`Set-AuthenticodeSignature`Командлет добавляет подпись Authenticode в любой файл, поддерживающий пакет интерфейса субъекта (SIP).</span><span class="sxs-lookup"><span data-stu-id="9d46c-111">The `Set-AuthenticodeSignature` cmdlet adds an Authenticode signature to any file that supports Subject Interface Package (SIP).</span></span>

<span data-ttu-id="9d46c-112">В файле сценария PowerShell сигнатура принимает форму блока текста, который указывает на конец инструкций, выполняемых в скрипте.</span><span class="sxs-lookup"><span data-stu-id="9d46c-112">In a PowerShell script file, the signature takes the form of a block of text that indicates the end of the instructions that are executed in the script.</span></span> <span data-ttu-id="9d46c-113">Если при запуске командлета подпись в файле уже есть, эта подпись удаляется.</span><span class="sxs-lookup"><span data-stu-id="9d46c-113">If there is a signature in the file when this cmdlet runs, that signature is removed.</span></span>

## <span data-ttu-id="9d46c-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="9d46c-114">EXAMPLES</span></span>

### <span data-ttu-id="9d46c-115">Пример 1. Подписание скрипта с помощью сертификата из локального хранилища сертификатов</span><span class="sxs-lookup"><span data-stu-id="9d46c-115">Example 1 - Sign a script using a certificate from the local certificate store</span></span>

<span data-ttu-id="9d46c-116">Эти команды извлекают сертификат подписи кода из поставщика сертификата PowerShell и используют его для подписания скрипта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d46c-116">These commands retrieve a code-signing certificate from the PowerShell certificate provider and use it to sign a PowerShell script.</span></span>

```powershell
$cert=Get-ChildItem -Path Cert:\CurrentUser\My -CodeSigningCert
Set-AuthenticodeSignature -FilePath PsTestInternet2.ps1 -Certificate $cert
```

<span data-ttu-id="9d46c-117">Первая команда использует `Get-ChildItem` командлет и поставщик сертификата PowerShell для получения сертификатов в `Cert:\CurrentUser\My` подкаталоге хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d46c-117">The first command uses the `Get-ChildItem` cmdlet and the PowerShell certificate provider to get the certificates in the `Cert:\CurrentUser\My` subdirectory of the certificate store.</span></span> <span data-ttu-id="9d46c-118">`Cert:`Диск — это диск, предоставляемый поставщиком сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d46c-118">The `Cert:` drive is the drive exposed by the certificate provider.</span></span> <span data-ttu-id="9d46c-119">Параметр **CodeSigningCert** , который поддерживается только поставщиком сертификатов, ограничивает доступ к сертификатам, получаемым с помощью центра подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="9d46c-119">The **CodeSigningCert** parameter, which is supported only by the certificate provider, limits the certificates retrieved to those with code-signing authority.</span></span> <span data-ttu-id="9d46c-120">Команда сохраняет результат в `$cert` переменной.</span><span class="sxs-lookup"><span data-stu-id="9d46c-120">The command stores the result in the `$cert` variable.</span></span>

<span data-ttu-id="9d46c-121">Вторая команда использует `Set-AuthenticodeSignature` командлет для подписи `PSTestInternet2.ps1` скрипта.</span><span class="sxs-lookup"><span data-stu-id="9d46c-121">The second command uses the `Set-AuthenticodeSignature` cmdlet to sign the `PSTestInternet2.ps1` script.</span></span> <span data-ttu-id="9d46c-122">Он использует параметр **FilePath** , чтобы указать имя скрипта и параметр **сертификата** , чтобы указать, что сертификат хранится в `$cert` переменной.</span><span class="sxs-lookup"><span data-stu-id="9d46c-122">It uses the **FilePath** parameter to specify the name of the script and the **Certificate** parameter to specify that the certificate is stored in the `$cert` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="9d46c-123">Использование параметра **CodeSigningCert** с параметрами `Get-ChildItem` возвращает только сертификаты, которые имеют центр подписи кода и содержат закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="9d46c-123">Using the **CodeSigningCert** parameter with `Get-ChildItem` only returns certificates that have code-signing authority and contain a private key.</span></span> <span data-ttu-id="9d46c-124">Если закрытый ключ отсутствует, сертификаты не могут использоваться для подписывания.</span><span class="sxs-lookup"><span data-stu-id="9d46c-124">If there is no private key, the certificates cannot be used for signing.</span></span>

### <span data-ttu-id="9d46c-125">Пример 2. Подписание сценария с помощью сертификата из PFX-файла</span><span class="sxs-lookup"><span data-stu-id="9d46c-125">Example 2 - Sign a script using a certificate from a PFX file</span></span>

<span data-ttu-id="9d46c-126">Эти команды используют `Get-PfxCertificate` командлет для загрузки сертификата подписи кода.</span><span class="sxs-lookup"><span data-stu-id="9d46c-126">These commands use the `Get-PfxCertificate` cmdlet to load a code signing certificate.</span></span> <span data-ttu-id="9d46c-127">Затем используйте его для подписания скрипта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d46c-127">Then, use it to sign a PowerShell script.</span></span>

```powershell
$cert = Get-PfxCertificate -FilePath C:\Test\Mysign.pfx
Set-AuthenticodeSignature -FilePath ServerProps.ps1 -Certificate $cert
```

<span data-ttu-id="9d46c-128">Первая команда использует `Get-PfxCertificate` командлет для загрузки сертификата к:\тест\мисигн.пфкс в `$cert` переменную.</span><span class="sxs-lookup"><span data-stu-id="9d46c-128">The first command uses the `Get-PfxCertificate` cmdlet to load the C:\Test\MySign.pfx certificate into the `$cert` variable.</span></span>

<span data-ttu-id="9d46c-129">Вторая команда использует `Set-AuthenticodeSignature` для подписания скрипта.</span><span class="sxs-lookup"><span data-stu-id="9d46c-129">The second command uses `Set-AuthenticodeSignature` to sign the script.</span></span> <span data-ttu-id="9d46c-130">Параметр **FilePath** параметра `Set-AuthenticodeSignature` указывает путь к подписанному файлу скрипта, а параметр **CERT** передает `$cert` переменную, содержащую сертификат `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="9d46c-130">The **FilePath** parameter of `Set-AuthenticodeSignature` specifies the path to the script file being signed and the **Cert** parameter passes the `$cert` variable containing the certificate to `Set-AuthenticodeSignature`.</span></span>

<span data-ttu-id="9d46c-131">Если файл сертификата защищен паролем, PowerShell запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="9d46c-131">If the certificate file is password protected, PowerShell prompts you for the password.</span></span>

### <span data-ttu-id="9d46c-132">Пример 3. Добавление подписи, включающей корневой центр</span><span class="sxs-lookup"><span data-stu-id="9d46c-132">Example 3 - Add a signature that includes the root authority</span></span>

<span data-ttu-id="9d46c-133">Эта команда добавляет цифровую подпись, включающую корневой центр в цепочке доверия, и подпись стороннего сервера отметок времени.</span><span class="sxs-lookup"><span data-stu-id="9d46c-133">This command adds a digital signature that includes the root authority in the trust chain, and it is signed by a third-party timestamp server.</span></span>

```powershell
Set-AuthenticodeSignature -FilePath c:\scripts\Remodel.ps1 -Certificate $cert -IncludeChain All -TimestampServer "http://timestamp.fabrikam.com/scripts/timstamper.dll"
```

<span data-ttu-id="9d46c-134">Команда использует параметр **FilePath** для указания подписанного скрипта, а параметр **сертификата** — для указания сертификата, сохраненного в `$cert` переменной.</span><span class="sxs-lookup"><span data-stu-id="9d46c-134">The command uses the **FilePath** parameter to specify the script being signed and the **Certificate** parameter to specify the certificate that is saved in the `$cert` variable.</span></span> <span data-ttu-id="9d46c-135">Он использует параметр **инклудечаин** для включения всех подписей в цепочку доверия, включая корневой центр.</span><span class="sxs-lookup"><span data-stu-id="9d46c-135">It uses the **IncludeChain** parameter to include all of the signatures in the trust chain, including the root authority.</span></span> <span data-ttu-id="9d46c-136">Он также использует параметр **тиместампсервер** для добавления метки времени к сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="9d46c-136">It also uses the **TimeStampServer** parameter to add a timestamp to the signature.</span></span>
<span data-ttu-id="9d46c-137">Это защищает скрипт от сбоя, если срок действия сертификата истек.</span><span class="sxs-lookup"><span data-stu-id="9d46c-137">This prevents the script from failing when the certificate expires.</span></span>

## <span data-ttu-id="9d46c-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9d46c-138">PARAMETERS</span></span>

### <span data-ttu-id="9d46c-139">— Сертификат</span><span class="sxs-lookup"><span data-stu-id="9d46c-139">-Certificate</span></span>

<span data-ttu-id="9d46c-140">Задает сертификат, который будет использоваться для подписания скрипта или файла.</span><span class="sxs-lookup"><span data-stu-id="9d46c-140">Specifies the certificate that will be used to sign the script or file.</span></span> <span data-ttu-id="9d46c-141">Введите переменную, в которой хранится объект, представляющий сертификат, или выражение, которое получает сертификат.</span><span class="sxs-lookup"><span data-stu-id="9d46c-141">Enter a variable that stores an object representing the certificate or an expression that gets the certificate.</span></span>

<span data-ttu-id="9d46c-142">Чтобы найти сертификат, используйте `Get-PfxCertificate` или используйте `Get-ChildItem` командлет на диске с сертификатом `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="9d46c-142">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate `Cert:` drive.</span></span> <span data-ttu-id="9d46c-143">Если сертификат недействителен или не имеет `code-signing` полномочий, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9d46c-143">If the certificate is not valid or does not have `code-signing` authority, the command fails.</span></span>

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

### <span data-ttu-id="9d46c-144">-FilePath</span><span class="sxs-lookup"><span data-stu-id="9d46c-144">-FilePath</span></span>

<span data-ttu-id="9d46c-145">Указывает путь к подписываемому файлу.</span><span class="sxs-lookup"><span data-stu-id="9d46c-145">Specifies the path to a file that is being signed.</span></span>

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

### <span data-ttu-id="9d46c-146">-Force</span><span class="sxs-lookup"><span data-stu-id="9d46c-146">-Force</span></span>

<span data-ttu-id="9d46c-147">Позволяет командлету добавлять подпись в файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9d46c-147">Allows the cmdlet to append a signature to a read-only file.</span></span> <span data-ttu-id="9d46c-148">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="9d46c-148">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="9d46c-149">-HashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="9d46c-149">-HashAlgorithm</span></span>

<span data-ttu-id="9d46c-150">Задает алгоритм хэширования, который использует Windows для расчета цифровой подписи для файла.</span><span class="sxs-lookup"><span data-stu-id="9d46c-150">Specifies the hashing algorithm that Windows uses to compute the digital signature for the file.</span></span>

<span data-ttu-id="9d46c-151">Для PowerShell 3,0 значение по умолчанию — SHA256, то есть алгоритм хэширования Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d46c-151">For PowerShell 3.0, the default is SHA256, which is the Windows default hashing algorithm.</span></span> <span data-ttu-id="9d46c-152">Для PowerShell 2,0 значение по умолчанию — SHA1.</span><span class="sxs-lookup"><span data-stu-id="9d46c-152">For PowerShell 2.0, the default is SHA1.</span></span> <span data-ttu-id="9d46c-153">Файлы, подписанные с использованием другого алгоритма хэширования, могут не распознаваться в других системах.</span><span class="sxs-lookup"><span data-stu-id="9d46c-153">Files that are signed with a different hashing algorithm might not be recognized on other systems.</span></span> <span data-ttu-id="9d46c-154">Поддерживаемые алгоритмы зависят от версии операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9d46c-154">Which algorithms are supported depends on the version of the operating system.</span></span>

<span data-ttu-id="9d46c-155">Список возможных значений см. в разделе [Структура хашалгорисмнаме](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span><span class="sxs-lookup"><span data-stu-id="9d46c-155">For a list of possible values, see [HashAlgorithmName Struct](/dotnet/api/system.security.cryptography.hashalgorithmname?view=netframework-4.7.2#properties).</span></span>

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

### <span data-ttu-id="9d46c-156">-Инклудечаин</span><span class="sxs-lookup"><span data-stu-id="9d46c-156">-IncludeChain</span></span>

<span data-ttu-id="9d46c-157">Определяет, какие сертификаты в цепочке доверия сертификатов включаются в цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="9d46c-157">Determines which certificates in the certificate trust chain are included in the digital signature.</span></span>
<span data-ttu-id="9d46c-158">По умолчанию используется **нотрут** .</span><span class="sxs-lookup"><span data-stu-id="9d46c-158">**NotRoot** is the default.</span></span>

<span data-ttu-id="9d46c-159">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="9d46c-159">Valid values are:</span></span>

- <span data-ttu-id="9d46c-160">Подписавший: включает только сертификат подписывания.</span><span class="sxs-lookup"><span data-stu-id="9d46c-160">Signer: Includes only the signer's certificate.</span></span>
- <span data-ttu-id="9d46c-161">Нотрут: включает все сертификаты в цепочке сертификатов, за исключением корневого центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="9d46c-161">NotRoot: Includes all of the certificates in the certificate chain, except for the root authority.</span></span>
- <span data-ttu-id="9d46c-162">Все: включает все сертификаты в цепочке сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d46c-162">All: Includes all the certificates in the certificate chain.</span></span>

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

### <span data-ttu-id="9d46c-163">-Тиместампсервер</span><span class="sxs-lookup"><span data-stu-id="9d46c-163">-TimestampServer</span></span>

<span data-ttu-id="9d46c-164">Добавляет к подписи отметку времени, использует заданный сервер отметок времени.</span><span class="sxs-lookup"><span data-stu-id="9d46c-164">Uses the specified time stamp server to add a time stamp to the signature.</span></span> <span data-ttu-id="9d46c-165">Введите URL-адрес сервера отметок времени в виде строки.</span><span class="sxs-lookup"><span data-stu-id="9d46c-165">Type the URL of the time stamp server as a string.</span></span>

<span data-ttu-id="9d46c-166">Отметка времени представляет собой значение точного времени, когда сертификат был добавлен в файл.</span><span class="sxs-lookup"><span data-stu-id="9d46c-166">The time stamp represents the exact time that the certificate was added to the file.</span></span> <span data-ttu-id="9d46c-167">Отметка времени защищает скрипт от сбоев в случае истечения срока действия сертификата, поскольку пользователи и программы могут проверить, что сертификат действовал в момент подписания.</span><span class="sxs-lookup"><span data-stu-id="9d46c-167">A time stamp prevents the script from failing if the certificate expires because users and programs can verify that the certificate was valid at the time of signing.</span></span>

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

### <span data-ttu-id="9d46c-168">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d46c-168">-LiteralPath</span></span>

<span data-ttu-id="9d46c-169">Указывает путь к подписываемому файлу.</span><span class="sxs-lookup"><span data-stu-id="9d46c-169">Specifies the path to a file that is being signed.</span></span> <span data-ttu-id="9d46c-170">В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="9d46c-170">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="9d46c-171">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="9d46c-171">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9d46c-172">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9d46c-172">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9d46c-173">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="9d46c-173">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="9d46c-174">-Саурцепасорекстенсион</span><span class="sxs-lookup"><span data-stu-id="9d46c-174">-SourcePathOrExtension</span></span>

<span data-ttu-id="9d46c-175">Путь к файлу или типу файла содержимого, для которого добавляется цифровая подпись.</span><span class="sxs-lookup"><span data-stu-id="9d46c-175">Path to the file or file type of the content for which the digital signature is added.</span></span> <span data-ttu-id="9d46c-176">Этот параметр используется с **содержимым** , где содержимое файла передается как массив байтов.</span><span class="sxs-lookup"><span data-stu-id="9d46c-176">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

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

### <span data-ttu-id="9d46c-177">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="9d46c-177">-Content</span></span>

<span data-ttu-id="9d46c-178">Содержимое файла в виде массива байтов, для которого добавляется цифровая подпись.</span><span class="sxs-lookup"><span data-stu-id="9d46c-178">Contents of a file as a byte array for which the digital signature is added.</span></span> <span data-ttu-id="9d46c-179">Этот параметр должен использоваться с параметром **саурцепасорекстенсион** .</span><span class="sxs-lookup"><span data-stu-id="9d46c-179">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="9d46c-180">Содержимое файла должно быть в формате Unicode (UTF-16LE).</span><span class="sxs-lookup"><span data-stu-id="9d46c-180">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

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

### <span data-ttu-id="9d46c-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9d46c-181">-Confirm</span></span>

<span data-ttu-id="9d46c-182">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9d46c-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9d46c-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9d46c-183">-WhatIf</span></span>

<span data-ttu-id="9d46c-184">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9d46c-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9d46c-185">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9d46c-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9d46c-186">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9d46c-186">CommonParameters</span></span>

<span data-ttu-id="9d46c-187">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9d46c-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9d46c-188">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9d46c-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9d46c-189">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9d46c-189">INPUTS</span></span>

### <span data-ttu-id="9d46c-190">System.String</span><span class="sxs-lookup"><span data-stu-id="9d46c-190">System.String</span></span>

<span data-ttu-id="9d46c-191">Строку, содержащую путь к файлу, можно передать по конвейеру `Set-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="9d46c-191">You can pipe a string that contains the file path to `Set-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="9d46c-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9d46c-192">OUTPUTS</span></span>

### <span data-ttu-id="9d46c-193">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="9d46c-193">System.Management.Automation.Signature</span></span>

## <span data-ttu-id="9d46c-194">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9d46c-194">NOTES</span></span>

## <span data-ttu-id="9d46c-195">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9d46c-195">RELATED LINKS</span></span>

[<span data-ttu-id="9d46c-196">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="9d46c-196">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="9d46c-197">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="9d46c-197">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="9d46c-198">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="9d46c-198">Get-PfxCertificate</span></span>](Get-PfxCertificate.md)

[<span data-ttu-id="9d46c-199">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="9d46c-199">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="9d46c-200">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="9d46c-200">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="9d46c-201">about_Signing</span><span class="sxs-lookup"><span data-stu-id="9d46c-201">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
