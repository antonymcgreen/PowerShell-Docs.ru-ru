---
description: Сертификат
keywords: powershell,командлет
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Поставщик Certificate
ms.openlocfilehash: d1280d34429600e8c06e96a36921df3d04f9eda6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232485"
---
# <a name="certificate-provider"></a><span data-ttu-id="13013-104">Поставщик Certificate</span><span class="sxs-lookup"><span data-stu-id="13013-104">Certificate Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="13013-105">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="13013-105">Provider name</span></span>

<span data-ttu-id="13013-106">Сертификат</span><span class="sxs-lookup"><span data-stu-id="13013-106">Certificate</span></span>

## <a name="drives"></a><span data-ttu-id="13013-107">Диски</span><span class="sxs-lookup"><span data-stu-id="13013-107">Drives</span></span>

`Cert:`

## <a name="capabilities"></a><span data-ttu-id="13013-108">Характеристики</span><span class="sxs-lookup"><span data-stu-id="13013-108">Capabilities</span></span>

<span data-ttu-id="13013-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="13013-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="13013-110">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="13013-110">Short description</span></span>

<span data-ttu-id="13013-111">Предоставляет доступ к хранилищам сертификатов X. 509 и сертификатам в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13013-111">Provides access to X.509 certificate stores and certificates in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="13013-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="13013-112">Detailed description</span></span>

<span data-ttu-id="13013-113">Поставщик **сертификатов** PowerShell позволяет получать, добавлять, изменять, очищать и удалять сертификаты и хранилища сертификатов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13013-113">The PowerShell **Certificate** provider lets you get, add, change, clear, and delete certificates and certificate stores in PowerShell.</span></span>

<span data-ttu-id="13013-114">Диск **сертификата** — это иерархическое пространство имен, содержащее хранилища сертификатов и сертификаты на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13013-114">The **Certificate** drive is a hierarchical namespace containing the certificate stores and certificates on your computer.</span></span>

<span data-ttu-id="13013-115">Поставщик **сертификатов** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="13013-115">The **Certificate** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="13013-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="13013-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="13013-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="13013-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="13013-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="13013-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="13013-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="13013-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="13013-120">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="13013-120">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="13013-121">Move-Item</span><span class="sxs-lookup"><span data-stu-id="13013-121">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="13013-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="13013-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="13013-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="13013-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="13013-124">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13013-124">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="13013-125">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13013-125">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="13013-126">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="13013-126">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="13013-127">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="13013-127">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="13013-128">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="13013-128">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="13013-129">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="13013-129">Types exposed by this provider</span></span>

<span data-ttu-id="13013-130">Диск сертификата предоставляет следующие типы.</span><span class="sxs-lookup"><span data-stu-id="13013-130">The Certificate drive exposes the following types.</span></span>

- <span data-ttu-id="13013-131">Расположения магазинов (Microsoft. PowerShell. Commands. X509StoreLocation) — это контейнеры высокого уровня, которые группируют сертификаты для текущего пользователя и для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="13013-131">Store locations (Microsoft.PowerShell.Commands.X509StoreLocation), which are high-level containers that group the certificates for the current user and for all users.</span></span> <span data-ttu-id="13013-132">В каждой системе существует расположение хранилищ CurrentUser и LocalMachine (все пользователи).</span><span class="sxs-lookup"><span data-stu-id="13013-132">Each system has a CurrentUser and LocalMachine (all users) store location.</span></span>

- <span data-ttu-id="13013-133">Хранилища сертификатов (System. Security. Cryptography. X509Certificates. X509Store), которые являются физическими хранилищами, в которых сохраняются и управляются сертификаты.</span><span class="sxs-lookup"><span data-stu-id="13013-133">Certificates stores (System.Security.Cryptography.X509Certificates.X509Store), which are physical stores in which certificates are saved and managed.</span></span>

- <span data-ttu-id="13013-134">Сертификат x. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** , каждый из которых представляет сертификат X. 509 на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13013-134">X.509 **System.Security.Cryptography.X509Certificates.X509Certificate2** certificates, each of which represent an X.509 certificate on the computer.</span></span>
  <span data-ttu-id="13013-135">Сертификаты идентифицируются по их отпечаткам.</span><span class="sxs-lookup"><span data-stu-id="13013-135">Certificates are identified by their thumbprints.</span></span>

## <a name="navigating-the-certificate-drive"></a><span data-ttu-id="13013-136">Навигация по диску сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-136">Navigating the Certificate drive</span></span>

<span data-ttu-id="13013-137">Поставщик **сертификата** предоставляет пространство имен сертификата `Cert:` в качестве диска в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13013-137">The **Certificate** provider exposes the certificate namespace as the `Cert:` drive in PowerShell.</span></span> <span data-ttu-id="13013-138">Эта команда использует `Set-Location` команду, чтобы изменить текущее расположение на корневое хранилище сертификатов в расположении хранилища LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="13013-138">This command uses the `Set-Location` command to change the current location to the Root certificate store in the LocalMachine store location.</span></span> <span data-ttu-id="13013-139">Используйте обратную косую черту ( \\ ) или косую черту (/), чтобы указать уровень `Cert:` диска.</span><span class="sxs-lookup"><span data-stu-id="13013-139">Use a backslash (\\) or a forward slash (/) to indicate a level of the `Cert:` drive.</span></span>

```powershell
Set-Location Cert:
```

<span data-ttu-id="13013-140">Вы также можете работать с поставщиком сертификата с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13013-140">You can also work with the certificate provider from any other PowerShell drive.</span></span> <span data-ttu-id="13013-141">Чтобы сослаться на псевдоним из другого расположения, используйте `Cert:` имя диска в пути.</span><span class="sxs-lookup"><span data-stu-id="13013-141">To reference an alias from another location, use the `Cert:` drive name in the path.</span></span>

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

<span data-ttu-id="13013-142">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="13013-142">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="13013-143">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="13013-143">For example, type:</span></span>

```powershell
Set-Location C:
```

> [!NOTE]
> <span data-ttu-id="13013-144">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="13013-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="13013-145">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="13013-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span>
> <span data-ttu-id="13013-146">и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="13013-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-contents-of-the-cert-drive"></a><span data-ttu-id="13013-147">Отображение содержимого диска Cert:</span><span class="sxs-lookup"><span data-stu-id="13013-147">Displaying the Contents of the Cert: drive</span></span>

<span data-ttu-id="13013-148">Эта команда использует `Get-ChildItem` командлет для вывода хранилищ сертификатов в расположении хранилища сертификатов CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="13013-148">This command uses the `Get-ChildItem` cmdlet to display the certificate stores in the CurrentUser certificate store location.</span></span>

<span data-ttu-id="13013-149">Если вы не используете `Cert:` диск, используйте абсолютный путь.</span><span class="sxs-lookup"><span data-stu-id="13013-149">If you are not in the `Cert:` drive, use an absolute path.</span></span>

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a><span data-ttu-id="13013-150">Отображение свойств сертификата на диске CERT:</span><span class="sxs-lookup"><span data-stu-id="13013-150">Displaying certificate properties within the Cert: drive</span></span>

<span data-ttu-id="13013-151">Этот пример получает сертификат с `Get-Item` и сохраняет его в переменной.</span><span class="sxs-lookup"><span data-stu-id="13013-151">This example gets a certificate with `Get-Item` and stores it in a variable.</span></span>
<span data-ttu-id="13013-152">В примере показаны новые свойства сценария сертификата ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) с помощью `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="13013-152">The example shows the new certificate script properties ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) using `Select-Object`.</span></span>

```powershell
$c = Get-Item cert:\LocalMachine\My\52A149D0393CE8A8D4AF0B172ED667A9E3A1F44E
$c | Format-List DnsNameList, EnhancedKeyUsageList, SendAsTrustedIssuer
```

```output
DnsNameList          : {SERVER01.contoso.com}
EnhancedKeyUsageList : {WiFi-Machine (1.3.6.1.4.1.311.42.2.6),
                       Client Authentication (1.3.6.1.5.5.7.3.2)}
SendAsTrustedIssuer  : False
```

### <a name="find-all-codesigning-certificates"></a><span data-ttu-id="13013-153">Найти все сертификаты соразработки</span><span class="sxs-lookup"><span data-stu-id="13013-153">Find all CodeSigning certificates</span></span>

<span data-ttu-id="13013-154">Эта команда использует **CodeSigningCert** и **Рекурсивные** параметры `Get-ChildItem` командлета, чтобы получить все сертификаты на компьютере с центром подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="13013-154">This command uses the **CodeSigningCert** and **Recurse** parameters of the `Get-ChildItem` cmdlet to get all of the certificates on the computer that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a><span data-ttu-id="13013-155">Поиск сертификатов с истекшим сроком действия</span><span class="sxs-lookup"><span data-stu-id="13013-155">Find expired certificates</span></span>

<span data-ttu-id="13013-156">Эта команда использует параметр **ExpiringInDays** `Get-ChildItem` командлета для получения сертификатов, срок действия которых истекает в течение следующих 30 дней.</span><span class="sxs-lookup"><span data-stu-id="13013-156">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet to get certificates that will expire within the next 30 days.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a><span data-ttu-id="13013-157">Поиск SSL-сертификатов сервера</span><span class="sxs-lookup"><span data-stu-id="13013-157">Find Server SSL Certificates</span></span>

<span data-ttu-id="13013-158">Эта команда использует параметр **SSLServerAuthentication** `Get-ChildItem` командлета для получения всех SSL-сертификатов сервера в хранилищах My и WebHost.</span><span class="sxs-lookup"><span data-stu-id="13013-158">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get all Server SSL Certificates in the My and WebHosting stores.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a><span data-ttu-id="13013-159">Поиск сертификатов с истекшим сроком действия на удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="13013-159">Find expired certificates on remote computers</span></span>

<span data-ttu-id="13013-160">Эта команда использует `Invoke-Command` командлет для выполнения `Get-ChildItem` команды на компьютерах SRV01 и Srv02.</span><span class="sxs-lookup"><span data-stu-id="13013-160">This command uses the `Invoke-Command` cmdlet to run a `Get-ChildItem` command on the Srv01 and Srv02 computers.</span></span> <span data-ttu-id="13013-161">Нулевое значение (0) в параметре **ExpiringInDays** возвращает сертификаты на компьютерах SRV01 и Srv02, срок действия которых истек.</span><span class="sxs-lookup"><span data-stu-id="13013-161">A value of zero (0) in the **ExpiringInDays** parameter gets certificates on the Srv01 and Srv02 computers that have expired.</span></span>

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a><span data-ttu-id="13013-162">Объединение фильтров для поиска определенного набора сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-162">Combining filters to find a specific set of certificates</span></span>

<span data-ttu-id="13013-163">Эта команда возвращает все сертификаты в расположении хранилища LocalMachine, которые имеют следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="13013-163">This command gets all certificates in the LocalMachine store location that have the following attributes:</span></span>

- <span data-ttu-id="13013-164">"Fabrikam" в своем DNS-имени</span><span class="sxs-lookup"><span data-stu-id="13013-164">"fabrikam" in their DNS name</span></span>
- <span data-ttu-id="13013-165">"Проверка подлинности клиента" в EKU</span><span class="sxs-lookup"><span data-stu-id="13013-165">"Client Authentication" in their EKU</span></span>
- <span data-ttu-id="13013-166">значение `$true` для свойства **SendAsTrustedIssuer**</span><span class="sxs-lookup"><span data-stu-id="13013-166">a value of `$true` for the **SendAsTrustedIssuer** property</span></span>
- <span data-ttu-id="13013-167">срок действия не истекает в течение следующих 30 дней.</span><span class="sxs-lookup"><span data-stu-id="13013-167">do not expire within the next 30 days.</span></span>

<span data-ttu-id="13013-168">Свойство **NotAfter** хранит дату окончания срока действия сертификата.</span><span class="sxs-lookup"><span data-stu-id="13013-168">The **NotAfter** property stores the certificate expiration date.</span></span>

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a><span data-ttu-id="13013-169">Открытие оснастки "Сертификаты" консоли MMC</span><span class="sxs-lookup"><span data-stu-id="13013-169">Opening the Certificates MMC Snap-in</span></span>

<span data-ttu-id="13013-170">`Invoke-Item`Командлет будет использовать приложение по умолчанию, чтобы открыть указанный путь.</span><span class="sxs-lookup"><span data-stu-id="13013-170">The `Invoke-Item` cmdlet will use the default application to open a path you specify.</span></span> <span data-ttu-id="13013-171">Для сертификатов приложение по умолчанию — оснастка MMC "сертификаты".</span><span class="sxs-lookup"><span data-stu-id="13013-171">For certificates, the default application is the Certificates MMC snap-in.</span></span>

<span data-ttu-id="13013-172">Эта команда открывает оснастку "Сертификаты" MMC для управления указанным сертификатом.</span><span class="sxs-lookup"><span data-stu-id="13013-172">This command opens the Certificates MMC snap-in to manage the specified certificate.</span></span>

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a><span data-ttu-id="13013-173">Копирование сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-173">Copying Certificates</span></span>

<span data-ttu-id="13013-174">Копирование сертификатов не поддерживается поставщиком **сертификатов** .</span><span class="sxs-lookup"><span data-stu-id="13013-174">Copying certificates is not supported by the **Certificate** provider.</span></span> <span data-ttu-id="13013-175">При попытке скопировать сертификат появляется сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="13013-175">When you attempt to copy a certificate, you see this error.</span></span>

```
$path = "Cert:\LocalMachine\Root\E2C0F6662D3C569705B4B31FE2CBF3434094B254"
PS Cert:\LocalMachine\> Copy-Item -Path $path -Destination .\CA\
Copy-Item : Provider operation stopped because the provider does not support
this operation.
At line:1 char:1
+ Copy-Item -Path $path -Destination .\CA\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotImplemented: (:) [Copy-Item],
                              PSNotSupportedException
    + FullyQualifiedErrorId : NotSupported,
                              Microsoft.PowerShell.Commands.CopyItemCommand
```

## <a name="moving-certificates"></a><span data-ttu-id="13013-176">Перемещение сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-176">Moving Certificates</span></span>

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a><span data-ttu-id="13013-177">Перемещение всех сертификатов проверки подлинности сервера SSL в хранилище веб-узлов</span><span class="sxs-lookup"><span data-stu-id="13013-177">Move all SSL Server authentication certs to the WebHosting store</span></span>

<span data-ttu-id="13013-178">Эта команда использует `Move-Item` командлет для перемещения сертификата из хранилища My в хранилище веб-узлов.</span><span class="sxs-lookup"><span data-stu-id="13013-178">This command uses the `Move-Item` cmdlet to move a certificate from the My store to the WebHosting store.</span></span>

<span data-ttu-id="13013-179">`Move-Item` не будет перемещать хранилища сертификатов и не будет переносить сертификаты в другое расположение, например переместить сертификат из хранилища LocalMachine в CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="13013-179">`Move-Item` will not move certificate stores and it will not move certificates to a different store location, such as moving a certificate from LocalMachine to CurrentUser.</span></span> <span data-ttu-id="13013-180">`Move-Item`Командлет перемещает сертификаты, но не перемещает закрытые ключи.</span><span class="sxs-lookup"><span data-stu-id="13013-180">The `Move-Item` cmdlet moves certificates, but it does not move private keys.</span></span>

<span data-ttu-id="13013-181">Эта команда использует параметр **SSLServerAuthentication** `Get-ChildItem` командлета для получения сертификатов проверки подлинности сервера SSL в хранилище сертификатов My.</span><span class="sxs-lookup"><span data-stu-id="13013-181">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get SSL server authentication certificates in the MY certificate store.</span></span>

<span data-ttu-id="13013-182">Возвращенные сертификаты передаются в `Move-Item` командлет, который перемещает сертификаты в хранилище WebHost.</span><span class="sxs-lookup"><span data-stu-id="13013-182">The returned certificates are piped to the `Move-Item` cmdlet, which moves the certificates to the WebHosting store.</span></span>

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a><span data-ttu-id="13013-183">Удаление сертификатов и закрытых ключей</span><span class="sxs-lookup"><span data-stu-id="13013-183">Deleting Certificates and Private Keys</span></span>

<span data-ttu-id="13013-184">`Remove-Item`Командлет удалит указанные сертификаты.</span><span class="sxs-lookup"><span data-stu-id="13013-184">The `Remove-Item` cmdlet will remove certificates that you specify.</span></span> <span data-ttu-id="13013-185">`-DeleteKey`Динамический параметр удаляет закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="13013-185">The `-DeleteKey` dynamic parameter deletes the private key.</span></span>

### <a name="delete-a-certificate-from-the-ca-store"></a><span data-ttu-id="13013-186">Удаление сертификата из хранилища ЦС</span><span class="sxs-lookup"><span data-stu-id="13013-186">Delete a Certificate from the CA store</span></span>

<span data-ttu-id="13013-187">Эта команда удаляет сертификат из хранилища сертификатов центра сертификации, но не затрагивает связанный закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="13013-187">This command deletes a certificate from the CA certificate store, but leaves the associated private key intact.</span></span>

<span data-ttu-id="13013-188">На `Cert:` диске `Remove-Item` командлет поддерживает только параметры **DeleteKey** , **path** , **WhatIf** и **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="13013-188">In the `Cert:` drive, the `Remove-Item` cmdlet supports only the **DeleteKey** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="13013-189">Все остальные параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="13013-189">All other parameters are ignored.</span></span>

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a><span data-ttu-id="13013-190">Удаление сертификата с помощью подстановочных знаков в DNS-имени</span><span class="sxs-lookup"><span data-stu-id="13013-190">Delete a Certificate using a wildcards in the DNS name</span></span>

<span data-ttu-id="13013-191">Эта команда удаляет все сертификаты с именем DNS, содержащим "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="13013-191">This command deletes all certificates that have a DNS name that contains "Fabrikam".</span></span> <span data-ttu-id="13013-192">**DNSName** `Get-ChildItem` Для получения сертификатов и `Remove-Item` командлета для их удаления используется параметр dnsName командлета.</span><span class="sxs-lookup"><span data-stu-id="13013-192">It uses the **DNSName** parameter of the `Get-ChildItem` cmdlet to get the certificates and the `Remove-Item` cmdlet to delete them.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a><span data-ttu-id="13013-193">Удаление закрытых ключей с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="13013-193">Delete private keys from a remote computer</span></span>

<span data-ttu-id="13013-194">Эта серия команд включает делегирование, а затем удаляет сертификат и связанный закрытый ключ на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="13013-194">This series of commands enables delegation and then deletes the certificate and associated private key on a remote computer.</span></span> <span data-ttu-id="13013-195">Чтобы удалить закрытый ключ на удаленном компьютере, необходимо использовать делегированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="13013-195">To delete a private key on a remote computer, you must use delegated credentials.</span></span>

<span data-ttu-id="13013-196">Используйте `Enable-WSManCredSSP` командлет, чтобы включить проверку подлинности на стороне поставщика службы безопасности учетных данных на клиенте на удаленном компьютере S1.</span><span class="sxs-lookup"><span data-stu-id="13013-196">Use the `Enable-WSManCredSSP` cmdlet to enable Credential Security Service Provider (CredSSP) authentication on a client on the S1 remote computer.</span></span>
<span data-ttu-id="13013-197">CredSSP разрешает делегирование проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="13013-197">CredSSP permits delegated authentication.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

<span data-ttu-id="13013-198">С помощью `Connect-WSMan` командлета Подключите компьютер S1 к службе WinRM на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="13013-198">Use the `Connect-WSMan` cmdlet to connect the S1 computer to the WinRM service on the local computer.</span></span> <span data-ttu-id="13013-199">После выполнения этой команды компьютер S1 отображается на локальном `WSMan:` диске в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13013-199">When this command completes, the S1 computer appears in the local `WSMan:` drive in PowerShell.</span></span>

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

<span data-ttu-id="13013-200">Теперь можно использовать командлет Set-Item на диске WSMan:, чтобы включить атрибут CredSSP для службы WinRM.</span><span class="sxs-lookup"><span data-stu-id="13013-200">Now, you can use the Set-Item cmdlet in the WSMan: drive to enable the CredSSP attribute for the WinRM service.</span></span>

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

<span data-ttu-id="13013-201">Запустите удаленный сеанс на компьютере S1 с помощью `New-PSSession` командлета и укажите проверку подлинности CredSSP.</span><span class="sxs-lookup"><span data-stu-id="13013-201">Start a remote session on the s1 computer using the `New-PSSession` cmdlet, and specify CredSSP authentication.</span></span> <span data-ttu-id="13013-202">Сохраняет сеанс в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="13013-202">Saves the session in the `$s` variable.</span></span>

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

<span data-ttu-id="13013-203">Наконец, используйте `Invoke-Command` командлет для выполнения `Remove-Item` команды в сеансе в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="13013-203">Finally, use the `Invoke-Command` cmdlet to run a `Remove-Item` command in the session in the `$s` variable.</span></span> <span data-ttu-id="13013-204">`Remove-Item`Команда использует параметр **DeleteKey** для удаления закрытого ключа вместе с указанным сертификатом.</span><span class="sxs-lookup"><span data-stu-id="13013-204">The `Remove-Item` command uses the **DeleteKey** parameter to remove the private key along with the specified certificate.</span></span>

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a><span data-ttu-id="13013-205">Удаление просроченных сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-205">Delete expired Certificates</span></span>

<span data-ttu-id="13013-206">Эта команда использует параметр **ExpiringInDays** `Get-ChildItem` командлета со значением 0 для получения сертификатов в хранилище веб-размещения с истекшим сроком действия.</span><span class="sxs-lookup"><span data-stu-id="13013-206">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet with a value of 0 to get certificates in the WebHosting store that have expired.</span></span>

<span data-ttu-id="13013-207">Переменная, содержащая возвращенные сертификаты, передается в `Remove-Item` командлет, который удаляет их.</span><span class="sxs-lookup"><span data-stu-id="13013-207">The variable containing the returned certificates is piped to the `Remove-Item` cmdlet, which deletes them.</span></span> <span data-ttu-id="13013-208">Команда использует параметр **DeleteKey** для удаления закрытого ключа вместе с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="13013-208">The command uses the **DeleteKey** parameter to delete the private key along with the certificate.</span></span>

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a><span data-ttu-id="13013-209">Создание сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-209">Creating Certificates</span></span>

<span data-ttu-id="13013-210">`New-Item`Командлет не создает новые сертификаты в поставщике **сертификатов** .</span><span class="sxs-lookup"><span data-stu-id="13013-210">The `New-Item` cmdlet does not create new certificates in the **Certificate** provider.</span></span> <span data-ttu-id="13013-211">Используйте командлет [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) , чтобы создать сертификат для целей тестирования.</span><span class="sxs-lookup"><span data-stu-id="13013-211">Use the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet to create a certificate for testing purposes.</span></span>

## <a name="creating-certificate-stores"></a><span data-ttu-id="13013-212">Создание хранилищ сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-212">Creating Certificate Stores</span></span>

<span data-ttu-id="13013-213">На диске CERT: `New-Item` командлет создает хранилища сертификатов в расположении хранилища LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="13013-213">In the Cert: drive, the `New-Item` cmdlet creates certificate stores in the LocalMachine store location.</span></span> <span data-ttu-id="13013-214">Он поддерживает параметры **Name** , **path** , **WhatIf** и **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="13013-214">It supports the **Name** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="13013-215">Все остальные параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="13013-215">All other parameters are ignored.</span></span> <span data-ttu-id="13013-216">Команда возвращает **System. Security. Cryptography. X509Certificates. X509Store** , представляющий новое хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="13013-216">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

<span data-ttu-id="13013-217">Эта команда создает новое хранилище сертификатов с именем "CustomStore" в расположении хранилищ LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="13013-217">This command creates a new certificate store named "CustomStore" in the LocalMachine store location.</span></span>

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a><span data-ttu-id="13013-218">Создание нового хранилища сертификатов на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="13013-218">Create a new certificate store on a remote computer</span></span>

<span data-ttu-id="13013-219">Эта команда создает новое хранилище сертификатов с именем "HostingStore" в расположении хранилищ LocalMachine на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="13013-219">This command creates a new certificate store named "HostingStore" in the LocalMachine store location on the Server01 computer.</span></span>

<span data-ttu-id="13013-220">Команда использует `Invoke-Command` командлет для выполнения `New-Item` команды на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="13013-220">The command uses the `Invoke-Command` cmdlet to run a `New-Item` command on the Server01 computer.</span></span> <span data-ttu-id="13013-221">Команда возвращает **System. Security. Cryptography. X509Certificates. X509Store** , представляющий новое хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="13013-221">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a><span data-ttu-id="13013-222">Создание сертификатов клиента для WS-Man</span><span class="sxs-lookup"><span data-stu-id="13013-222">Creating Client Certificates for WS-Man</span></span>

<span data-ttu-id="13013-223">Эта команда создает запись **clientcertificate** , которая может использоваться клиентом **WS-Management** .</span><span class="sxs-lookup"><span data-stu-id="13013-223">This command creates **ClientCertificate** entry that can be used by the **WS-Management** client.</span></span> <span data-ttu-id="13013-224">Новый **clientcertificate** будет отображаться в каталоге **ClientCertificate** как "ClientCertificate_1234567890".</span><span class="sxs-lookup"><span data-stu-id="13013-224">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="13013-225">Все параметры являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="13013-225">All of the parameters are mandatory.</span></span> <span data-ttu-id="13013-226">**Издатель** должен быть отпечаткой сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="13013-226">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a><span data-ttu-id="13013-227">Удаление хранилищ сертификатов</span><span class="sxs-lookup"><span data-stu-id="13013-227">Deleting Certificate Stores</span></span>

### <a name="delete-a-certificate-store-from-a-remote-computer"></a><span data-ttu-id="13013-228">Удаление хранилища сертификатов с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="13013-228">Delete a certificate store from a remote computer</span></span>

<span data-ttu-id="13013-229">Эта команда использует `Invoke-Command` командлет для выполнения `Remove-Item` команды на компьютерах S1 и S2.</span><span class="sxs-lookup"><span data-stu-id="13013-229">This command uses the `Invoke-Command` cmdlet to run a `Remove-Item` command on the S1 and S2 computers.</span></span> <span data-ttu-id="13013-230">`Remove-Item`Команда включает параметр **рекурсии** , который удаляет сертификаты из хранилища перед удалением хранилища.</span><span class="sxs-lookup"><span data-stu-id="13013-230">The `Remove-Item` command includes the **Recurse** parameter, which deletes the certificates in the store before it deletes the store.</span></span>

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a><span data-ttu-id="13013-231">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="13013-231">Dynamic parameters</span></span>

<span data-ttu-id="13013-232">Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="13013-232">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span> <span data-ttu-id="13013-233">Эти параметры действительны во всех подкаталогах поставщика сертификатов, но действуют только для сертификатов.</span><span class="sxs-lookup"><span data-stu-id="13013-233">These parameters are valid in all subdirectories of the Certificate provider, but are effective only on certificates.</span></span>

> [!NOTE]
> <span data-ttu-id="13013-234">Параметры, выполняющие фильтрацию по `EnhancedKeyUsageList` свойству, также возвращают элементы с пустым `EnhancedKeyUsageList` значением свойства.</span><span class="sxs-lookup"><span data-stu-id="13013-234">Parameters that perform filtering against the `EnhancedKeyUsageList` property also return items with an empty `EnhancedKeyUsageList` property value.</span></span>
> <span data-ttu-id="13013-235">Сертификаты с пустым **EnhancedKeyUsageList** можно использовать для всех целей.</span><span class="sxs-lookup"><span data-stu-id="13013-235">Certificates that have an empty **EnhancedKeyUsageList** can be used for all purposes.</span></span>

<span data-ttu-id="13013-236">В PowerShell 6,0 были удалены следующие параметры поставщика сертификата.</span><span class="sxs-lookup"><span data-stu-id="13013-236">The following Certificate provider parameters were removed in PowerShell 6.0.</span></span>

- <span data-ttu-id="13013-237">DNSName</span><span class="sxs-lookup"><span data-stu-id="13013-237">DNSName</span></span>
- <span data-ttu-id="13013-238">документенкриптионцерт</span><span class="sxs-lookup"><span data-stu-id="13013-238">DocumentEncryptionCert</span></span>
- <span data-ttu-id="13013-239">EKU</span><span class="sxs-lookup"><span data-stu-id="13013-239">EKU</span></span>
- <span data-ttu-id="13013-240">ExpiringInDays</span><span class="sxs-lookup"><span data-stu-id="13013-240">ExpiringInDays</span></span>
- <span data-ttu-id="13013-241">SSLServerAuthentication</span><span class="sxs-lookup"><span data-stu-id="13013-241">SSLServerAuthentication</span></span>

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="13013-242">CodeSigningCert <System.Management.Automation.SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="13013-242">CodeSigningCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="13013-243">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="13013-243">Cmdlets supported</span></span>

- [<span data-ttu-id="13013-244">Get-Item</span><span class="sxs-lookup"><span data-stu-id="13013-244">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="13013-245">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="13013-245">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="13013-246">Этот параметр возвращает сертификаты с подписыванием кода в значении свойства **EnhancedKeyUsageList** .</span><span class="sxs-lookup"><span data-stu-id="13013-246">This parameter gets certificates that have "Code Signing" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="deletekey-systemmanagementautomationswitchparameter"></a><span data-ttu-id="13013-247">DeleteKey <System.Management.Automation.SwitchParameter></span><span class="sxs-lookup"><span data-stu-id="13013-247">DeleteKey <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="13013-248">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="13013-248">Cmdlets supported</span></span>

- [<span data-ttu-id="13013-249">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="13013-249">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

<span data-ttu-id="13013-250">Этот параметр удаляет связанный закрытый ключ при удалении сертификата.</span><span class="sxs-lookup"><span data-stu-id="13013-250">This parameter deletes the associated private key when it deletes the certificate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13013-251">Чтобы удалить закрытый ключ, связанный с сертификатом пользователя в `Cert:\CurrentUser` хранилище на удаленном компьютере, необходимо использовать делегированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="13013-251">To delete a private key that is associated with a user certificate in the `Cert:\CurrentUser` store on a remote computer, you must use delegated credentials.</span></span> <span data-ttu-id="13013-252">`Invoke-Command`Командлет поддерживает делегирование учетных данных с помощью параметра **CredSSP** .</span><span class="sxs-lookup"><span data-stu-id="13013-252">The `Invoke-Command` cmdlet supports credential delegation using the **CredSSP** parameter.</span></span> <span data-ttu-id="13013-253">Перед использованием `Remove-Item` с `Invoke-Command` делегированием учетных данных следует учитывать все риски безопасности.</span><span class="sxs-lookup"><span data-stu-id="13013-253">You should consider any security risks before using `Remove-Item` with `Invoke-Command` and credential delegation.</span></span>

<span data-ttu-id="13013-254">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="13013-254">This parameter was introduced in Windows PowerShell 3.0.</span></span>

### <a name="itemtype-string"></a><span data-ttu-id="13013-255">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="13013-255">ItemType \<String\></span></span>

<span data-ttu-id="13013-256">Этот параметр позволяет указать тип элемента, созданного `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="13013-256">This parameter allows you to specify the type of item created by `New-Item`.</span></span>

<span data-ttu-id="13013-257">В `Certificate` диске допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="13013-257">In a `Certificate` drive, the following values are allowed:</span></span>

- <span data-ttu-id="13013-258">Поставщик Certificate</span><span class="sxs-lookup"><span data-stu-id="13013-258">Certificate Provider</span></span>
- <span data-ttu-id="13013-259">Сертификат</span><span class="sxs-lookup"><span data-stu-id="13013-259">Certificate</span></span>
- <span data-ttu-id="13013-260">Магазин</span><span class="sxs-lookup"><span data-stu-id="13013-260">Store</span></span>
- <span data-ttu-id="13013-261">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="13013-261">StoreLocation</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="13013-262">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="13013-262">Cmdlets Supported</span></span>

- [<span data-ttu-id="13013-263">New-Item</span><span class="sxs-lookup"><span data-stu-id="13013-263">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="script-properties"></a><span data-ttu-id="13013-264">Свойства скрипта</span><span class="sxs-lookup"><span data-stu-id="13013-264">Script properties</span></span>

<span data-ttu-id="13013-265">В объект **x509Certificate2** , представляющий сертификаты, были добавлены новые свойства скрипта, которые упрощают поиск сертификатов и управление ими.</span><span class="sxs-lookup"><span data-stu-id="13013-265">New script properties have been added to the **x509Certificate2** object that represents the certificates to make it easy to search and manage the certificates.</span></span>

- <span data-ttu-id="13013-266">`DnsNameList`: Для заполнения `DnsNameList` свойства поставщик сертификата копирует содержимое из записи dnsName в расширении субжекталтернативенаме (SAN).</span><span class="sxs-lookup"><span data-stu-id="13013-266">`DnsNameList`: To populate the `DnsNameList` property, the Certificate provider copies the content from the DNSName entry in the SubjectAlternativeName (SAN) extension.</span></span> <span data-ttu-id="13013-267">Если расширение SAN пусто, свойство заполняется содержимым из поля Subject сертификата.</span><span class="sxs-lookup"><span data-stu-id="13013-267">If the SAN extension is empty, the property is populated with content from the Subject field of the certificate.</span></span>

- <span data-ttu-id="13013-268">`EnhancedKeyUsageList`. Чтобы заполнить `EnhancedKeyUsageList` свойство, поставщик сертификата копирует свойства Oid поля енханцедкэйусаже (EKU) в сертификате и создает для него понятное имя.</span><span class="sxs-lookup"><span data-stu-id="13013-268">`EnhancedKeyUsageList`: To populate the `EnhancedKeyUsageList` property, the Certificate provider copies the OID properties of the EnhancedKeyUsage (EKU) field in the certificate and creates a friendly name for it.</span></span>

- <span data-ttu-id="13013-269">`SendAsTrustedIssuer`: Для заполнения `SendAsTrustedIssuer` свойства поставщик сертификата копирует `SendAsTrustedIssuer` свойство из сертификата.</span><span class="sxs-lookup"><span data-stu-id="13013-269">`SendAsTrustedIssuer`: To populate the `SendAsTrustedIssuer` property, the Certificate provider copies the `SendAsTrustedIssuer` property from the certificate.</span></span>  <span data-ttu-id="13013-270">Дополнительные сведения см. в разделе [Управление доверенными издателями для проверки подлинности клиента](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span><span class="sxs-lookup"><span data-stu-id="13013-270">For more information see [Management of trusted issuers for client authentication](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span></span>

<span data-ttu-id="13013-271">Эти новые функции позволяют выполнять поиск сертификатов на основе их DNS-имен и дат истечения срока действия сертификатов и различать сертификаты проверки подлинности клиента и сервера по значению свойств расширенного использования ключа (EKU).</span><span class="sxs-lookup"><span data-stu-id="13013-271">These new features let you search for certificates based on their DNS names and expiration dates, and distinguish client and server authentication certificates by the value of their Enhanced Key Usage (EKU) properties.</span></span>

## <a name="using-the-pipeline"></a><span data-ttu-id="13013-272">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="13013-272">Using the pipeline</span></span>

<span data-ttu-id="13013-273">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="13013-273">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="13013-274">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="13013-274">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="13013-275">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="13013-275">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="13013-276">Получение справки</span><span class="sxs-lookup"><span data-stu-id="13013-276">Getting help</span></span>

<span data-ttu-id="13013-277">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="13013-277">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="13013-278">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте `-Path` параметр параметра, `Get-Help` чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="13013-278">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of `Get-Help` to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a><span data-ttu-id="13013-279">См. также статью</span><span class="sxs-lookup"><span data-stu-id="13013-279">See also</span></span>

[<span data-ttu-id="13013-280">about_Providers</span><span class="sxs-lookup"><span data-stu-id="13013-280">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="13013-281">about_Signing</span><span class="sxs-lookup"><span data-stu-id="13013-281">about_Signing</span></span>](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[<span data-ttu-id="13013-282">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="13013-282">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[<span data-ttu-id="13013-283">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="13013-283">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[<span data-ttu-id="13013-284">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="13013-284">Get-PfxCertificate</span></span>](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
