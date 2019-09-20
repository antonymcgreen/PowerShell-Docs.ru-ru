---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Новые и обновленные командлеты
ms.openlocfilehash: ffd5db2d4fc9bf8f67ef5e352633ad3209f72c87
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147594"
---
# <a name="new-and-updated-cmdlets"></a><span data-ttu-id="a9f83-103">Новые и обновленные командлеты</span><span class="sxs-lookup"><span data-stu-id="a9f83-103">New and updated cmdlets</span></span>

<span data-ttu-id="a9f83-104">В ответ на отзывы участников сообщества мы добавили новые и обновили имеющиеся командлеты.</span><span class="sxs-lookup"><span data-stu-id="a9f83-104">We have added new and updated existing cmdlets based on feedback from the community.</span></span>

## <a name="archive-cmdlets"></a><span data-ttu-id="a9f83-105">Командлеты Archive</span><span class="sxs-lookup"><span data-stu-id="a9f83-105">Archive cmdlets</span></span>

<span data-ttu-id="a9f83-106">Два новых командлета, `Compress-Archive` и `Expand-Archive`, позволяют сжимать и распаковывать ZIP-файлы.</span><span class="sxs-lookup"><span data-stu-id="a9f83-106">Two new cmdlets, `Compress-Archive` and `Expand-Archive`, let you compress and expand ZIP files.</span></span>

<span data-ttu-id="a9f83-107">Дополнительные сведения см. в разделе документации по модулю [Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/).</span><span class="sxs-lookup"><span data-stu-id="a9f83-107">For more information, see the [Microsoft.Powershell.Archive](/powershell/module/microsoft.powershell.archive/) module documentation.</span></span>

## <a name="catalog-cmdlets"></a><span data-ttu-id="a9f83-108">Командлеты для работы с каталогами</span><span class="sxs-lookup"><span data-stu-id="a9f83-108">Catalog Cmdlets</span></span>

<span data-ttu-id="a9f83-109">В модуле Microsoft.PowerShell.Security добавлены два новых командлета.</span><span class="sxs-lookup"><span data-stu-id="a9f83-109">Two new cmdlets have been added in the Microsoft.PowerShell.Security module.</span></span>

- [<span data-ttu-id="a9f83-110">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="a9f83-110">New-FileCatalog</span></span>](/powershell/module/microsoft.powershell.security/New-FileCatalog)
- [<span data-ttu-id="a9f83-111">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="a9f83-111">Test-FileCatalog</span></span>](/powershell/module/microsoft.powershell.security/Test-FileCatalog)

<span data-ttu-id="a9f83-112">Они создают и проверяют файлы каталога Windows.</span><span class="sxs-lookup"><span data-stu-id="a9f83-112">These generate and validate Windows catalog files.</span></span>

## <a name="clipboard-cmdlets"></a><span data-ttu-id="a9f83-113">Командлеты Clipboard</span><span class="sxs-lookup"><span data-stu-id="a9f83-113">Clipboard cmdlets</span></span>

<span data-ttu-id="a9f83-114">Командлеты `Get-Clipboard` и `Set-Clipboard` упрощают передачу содержимого в сеанс Windows PowerShell и из него.</span><span class="sxs-lookup"><span data-stu-id="a9f83-114">`Get-Clipboard` and `Set-Clipboard` make it easier for you to transfer content to and from a Windows PowerShell session.</span></span> <span data-ttu-id="a9f83-115">Командлеты Clipboard поддерживают изображения, звуковые файлы, списки файлов и текст.</span><span class="sxs-lookup"><span data-stu-id="a9f83-115">The Clipboard cmdlets support images, audio files, file lists, and text.</span></span>

<span data-ttu-id="a9f83-116">Дополнительная информация:</span><span class="sxs-lookup"><span data-stu-id="a9f83-116">For more information, see:</span></span>

- [<span data-ttu-id="a9f83-117">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="a9f83-117">Get-Clipboard</span></span>](/powershell/module/Microsoft.PowerShell.Management/Get-Clipboard)
- [<span data-ttu-id="a9f83-118">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="a9f83-118">Set-Clipboard</span></span>](/powershell/module/Microsoft.PowerShell.Management/Set-Clipboard)

## <a name="cryptographic-message-syntax-cms-cmdlets"></a><span data-ttu-id="a9f83-119">Командлеты Cryptographic Message Syntax (CMS)</span><span class="sxs-lookup"><span data-stu-id="a9f83-119">Cryptographic Message Syntax (CMS) cmdlets</span></span>

<span data-ttu-id="a9f83-120">Командлеты Cryptographic Message Syntax поддерживают шифрование и расшифровку содержимого с помощью стандартного формата IETF для криптографической защиты сообщений, задокументированного в [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span><span class="sxs-lookup"><span data-stu-id="a9f83-120">The Cryptographic Message Syntax cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages as documented by [RFC5652](https://tools.ietf.org/html/rfc5652.html).</span></span>

<span data-ttu-id="a9f83-121">Стандарт шифрования CMS реализует шифрование с открытым ключом, при котором ключи, используемые для шифрования содержимого (*открытый ключ*) и для его расшифровки (*закрытый ключ*), существуют отдельно.</span><span class="sxs-lookup"><span data-stu-id="a9f83-121">The CMS encryption standard implements public key cryptography, where the key used to encrypt content (the *public key*) and the key used to decrypt content (the *private key*) are separate.</span></span>

<span data-ttu-id="a9f83-122">Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям.</span><span class="sxs-lookup"><span data-stu-id="a9f83-122">Your public key can be shared widely and is not sensitive data.</span></span> <span data-ttu-id="a9f83-123">Любое содержимое, зашифрованное с помощью открытого ключа, можно расшифровать только с помощью закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="a9f83-123">Any content encrypted with the public key can only be decrypted using the private key.</span></span> <span data-ttu-id="a9f83-124">Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).</span><span class="sxs-lookup"><span data-stu-id="a9f83-124">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="a9f83-125">Дополнительная информация:</span><span class="sxs-lookup"><span data-stu-id="a9f83-125">For more information see:</span></span>

- [<span data-ttu-id="a9f83-126">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="a9f83-126">Get-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/Get-CmsMessage)
- [<span data-ttu-id="a9f83-127">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="a9f83-127">Protect-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage)
- [<span data-ttu-id="a9f83-128">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="a9f83-128">Unprotect-CmsMessage</span></span>](/powershell/module/Microsoft.PowerShell.Security/unprotect-CmsMessage)

<span data-ttu-id="a9f83-129">Для определения в качестве сертификатов шифрования данных в PowerShell сертификатам требуется уникальный идентификатор использования ключа (EKU), например "Подписывание кода" или "Зашифрованная почта".</span><span class="sxs-lookup"><span data-stu-id="a9f83-129">Certificates require a unique key usage identifier (EKU), such as 'Code Signing' or 'Encrypted Mail', to identify them as data encryption certificates in PowerShell.</span></span> <span data-ttu-id="a9f83-130">Чтобы просмотреть сертификаты шифрования документов в поставщике сертификатов, можно использовать динамический параметр **DocumentEncryptionCert** метода `Get-ChildItem`:</span><span class="sxs-lookup"><span data-stu-id="a9f83-130">To view document encryption certificates in the certificate provider, you can use the **DocumentEncryptionCert** dynamic parameter of `Get-ChildItem`:</span></span>

```powershell
Get-ChildItem Cert:\CurrentUser -DocumentEncryptionCert -Recurse
```

## <a name="extract-and-parse-structured-objects-from-string-content"></a><span data-ttu-id="a9f83-131">Извлечение и анализ структурированных объектов вне строки</span><span class="sxs-lookup"><span data-stu-id="a9f83-131">Extract and parse structured objects from string content</span></span>

### <a name="convertfrom-string"></a><span data-ttu-id="a9f83-132">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="a9f83-132">ConvertFrom-String</span></span>

<span data-ttu-id="a9f83-133">Новый командлет `ConvertFrom-String` поддерживает два режима:</span><span class="sxs-lookup"><span data-stu-id="a9f83-133">The new `ConvertFrom-String` cmdlet supports two modes:</span></span>

- <span data-ttu-id="a9f83-134">базовый анализ с разделением;</span><span class="sxs-lookup"><span data-stu-id="a9f83-134">Basic delimited parsing</span></span>
- <span data-ttu-id="a9f83-135">анализ с управлением автоматически создаваемым примером.</span><span class="sxs-lookup"><span data-stu-id="a9f83-135">Auto generated example-driven parsing</span></span>

<span data-ttu-id="a9f83-136">Анализ с разделением, используемый по умолчанию, разбивает входные данные с помощью пробелов и присваивает имена свойств получаемым группам.</span><span class="sxs-lookup"><span data-stu-id="a9f83-136">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="a9f83-137">Параметр **UpdateTemplate** для сохранения результатов алгоритма обучения в комментарий внутри файла шаблона.</span><span class="sxs-lookup"><span data-stu-id="a9f83-137">The **UpdateTemplate** parameter saves the results of the learning algorithm into a comment in the template file.</span></span> <span data-ttu-id="a9f83-138">Это делает затраты на процесс обучения (являющийся самым медленным этапом) единовременными.</span><span class="sxs-lookup"><span data-stu-id="a9f83-138">This makes the learning process (the slowest stage) a one-time cost.</span></span> <span data-ttu-id="a9f83-139">Выполнение `ConvertFrom-String` с шаблоном, содержащим закодированный обучающий алгоритм, теперь осуществляется практически мгновенно.</span><span class="sxs-lookup"><span data-stu-id="a9f83-139">Running `ConvertFrom-String` with a template that contains the encoded learning algorithm is now nearly instantaneous.</span></span>

<span data-ttu-id="a9f83-140">Дополнительные сведения см. в статье [ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String).</span><span class="sxs-lookup"><span data-stu-id="a9f83-140">For more information, see [ConvertFrom-String](/powershell/module/Microsoft.PowerShell.Utility/ConvertFrom-String).</span></span>

### <a name="convert-string"></a><span data-ttu-id="a9f83-141">Convert-String</span><span class="sxs-lookup"><span data-stu-id="a9f83-141">Convert-String</span></span>

<span data-ttu-id="a9f83-142">`Convert-String` позволяет указать примеры того, как должен выглядеть текст в исходном и итоговом виде.</span><span class="sxs-lookup"><span data-stu-id="a9f83-142">`Convert-String` allows you to provide before and after examples of how you want text to look.</span></span> <span data-ttu-id="a9f83-143">Командлет автоматически форматирует текст.</span><span class="sxs-lookup"><span data-stu-id="a9f83-143">The cmdlet formats your text automatically.</span></span>

<span data-ttu-id="a9f83-144">Дополнительные сведения см. в статье [Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String).</span><span class="sxs-lookup"><span data-stu-id="a9f83-144">For more information, see [Convert-String](/powershell/module/Microsoft.PowerShell.Utility/Convert-String).</span></span>

## <a name="updates-to-fileinfo-object"></a><span data-ttu-id="a9f83-145">Изменения объекта FileInfo</span><span class="sxs-lookup"><span data-stu-id="a9f83-145">Updates to FileInfo object</span></span>

<span data-ttu-id="a9f83-146">Сведения о версии файла могут вводить пользователя в заблуждение, особенно в случаях, когда файл был исправлен.</span><span class="sxs-lookup"><span data-stu-id="a9f83-146">File version information can be misleading, especially in cases where the file was patched.</span></span> <span data-ttu-id="a9f83-147">В выпуске WMF 5.0 добавлены новые свойства **FileVersionRaw** и **ProductVersionRaw** сценария для объектов **FileInfo**.</span><span class="sxs-lookup"><span data-stu-id="a9f83-147">WMF 5.0 adds new **FileVersionRaw** and **ProductVersionRaw** script properties to **FileInfo** objects.</span></span>
<span data-ttu-id="a9f83-148">Ниже приведены свойства, отображаемые для powershell.exe (при условии, что $pid является идентификатором процесса PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a9f83-148">Here are the properties as displayed for powershell.exe (assuming $pid is the ID of the PowerShell process):</span></span>

```powershell
Get-Process -Id $pid -FileVersionInfo | Format-List *version*
```

```Output
FileVersionRaw    : 10.0.17763.1
ProductVersionRaw : 10.0.17763.1
FileVersion       : 10.0.17763.1 (WinBuild.160101.0800)
ProductVersion    : 10.0.17763.1
```

## <a name="format-hex"></a><span data-ttu-id="a9f83-149">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="a9f83-149">Format-Hex</span></span>

<span data-ttu-id="a9f83-150">`Format-Hex` позволяет просматривать текст или двоичные данные в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="a9f83-150">`Format-Hex` lets you view text or binary data in hexadecimal format.</span></span>

<span data-ttu-id="a9f83-151">Дополнительные сведения см. в статье [Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex).</span><span class="sxs-lookup"><span data-stu-id="a9f83-151">For more information, see [Format-Hex](/powershell/module/microsoft.powershell.utility/format-hex).</span></span>

## <a name="get-childitem-has--depth-parameter"></a><span data-ttu-id="a9f83-152">Get-ChildItem получает параметр -Depth</span><span class="sxs-lookup"><span data-stu-id="a9f83-152">Get-ChildItem has -Depth parameter</span></span>

<span data-ttu-id="a9f83-153">Теперь `Get-ChildItem` имеет параметр **Depth**, используемый вместе с **Recurse** для ограничения рекурсии:</span><span class="sxs-lookup"><span data-stu-id="a9f83-153">`Get-ChildItem` now has a **Depth** parameter for use with **Recurse** to limit the recursion:</span></span>

## <a name="modules-support-for-declaring-version-ranges-1-etc"></a><span data-ttu-id="a9f83-154">Поддержка модулей для объявления диапазонов версий (1.\* и т. д.)</span><span class="sxs-lookup"><span data-stu-id="a9f83-154">Modules support for declaring version ranges (1.\*, etc)</span></span>

<span data-ttu-id="a9f83-155">Теперь вы можете сочетать **MinimumVersion** и **MaximumVersion**, чтобы импортировать модуль из определенного диапазона.</span><span class="sxs-lookup"><span data-stu-id="a9f83-155">You can now combine **MinimumVersion** and **MaximumVersion** to import module within specific range.</span></span> <span data-ttu-id="a9f83-156">Параметры также поддерживают подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a9f83-156">The parameters also support wildcards.</span></span>

```powershell
Import-Module psreadline -Verbose -MinimumVersion 1.0 -MaximumVersion 1.2.*
```

```Output
VERBOSE: Loading module from path 'C:\Program Files\WindowsPowerShell\Modules\psreadline\1.1\psreadline.psd1'.
VERBOSE: Importing cmdlet 'Get-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Get-PSReadlineOption'.
VERBOSE: Importing cmdlet 'Remove-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineOption'.
VERBOSE: Importing function 'PSConsoleHostReadline'.
```

## <a name="new-guid"></a><span data-ttu-id="a9f83-157">New-Guid</span><span class="sxs-lookup"><span data-stu-id="a9f83-157">New-Guid</span></span>

<span data-ttu-id="a9f83-158">Во многих сценариях требуется уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="a9f83-158">There are many scenarios where youneed for unique identifier.</span></span> <span data-ttu-id="a9f83-159">Командлет `New-GUID` предоставляет простой способ создания идентификатора GUID.</span><span class="sxs-lookup"><span data-stu-id="a9f83-159">The `New-GUID` cmdlet provides a simple way to create a new GUID.</span></span>

```powershell
New-Guid
```

```Output
Guid
----
e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
```

## <a name="nonewline-parameter"></a><span data-ttu-id="a9f83-160">Параметр NoNewLine</span><span class="sxs-lookup"><span data-stu-id="a9f83-160">NoNewLine parameter</span></span>

<span data-ttu-id="a9f83-161">Теперь для `Out-File`, `Add-Content` и `Set-Content` есть новый параметр **NoNewline**, который пропускает новую строку после выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a9f83-161">`Out-File`, `Add-Content`, and `Set-Content` now have a new **NoNewline** switch which omits a new line after the output.</span></span> <span data-ttu-id="a9f83-162">Например:</span><span class="sxs-lookup"><span data-stu-id="a9f83-162">For example:</span></span>

```powershell
"This is " | Out-File -FilePath Example.txt -NoNewline
"a single " | Add-Content -Path Example.txt -NoNewline
"sentence." | Add-Content -Path Example.txt -NoNewline
Get-Content .\Example.txt
```

```Output
This is a single sentence.
```

<span data-ttu-id="a9f83-163">Без параметра **NoNewline** каждый фрагмент будет находиться на отдельной строке:</span><span class="sxs-lookup"><span data-stu-id="a9f83-163">Without **NoNewline** specified, each fragment would be on a separate line:</span></span>

```powershell
"This is " | Out-File -FilePath Example.txt
"a single " | Add-Content -Path Example.txt
"sentence." | Add-Content -Path Example.txt
Get-Content .\Example.txt
```

```Output
This is
a single
sentence.
```

## <a name="interact-with-symbolic-links-using-improved-item-cmdlets"></a><span data-ttu-id="a9f83-164">Взаимодействие с символьными ссылками с помощью улучшенных командлетов Item</span><span class="sxs-lookup"><span data-stu-id="a9f83-164">Interact with Symbolic links using improved Item cmdlets</span></span>

<span data-ttu-id="a9f83-165">Для поддержки символьных ссылок расширена функциональность командлета Item и нескольких связанных с ним командлетов.</span><span class="sxs-lookup"><span data-stu-id="a9f83-165">The Item cmdlet and a few related cmdlets have been extended to support symbolic links.</span></span>

### <a name="symbolic-link-files"></a><span data-ttu-id="a9f83-166">Файлы с символьными ссылками</span><span class="sxs-lookup"><span data-stu-id="a9f83-166">Symbolic link files</span></span>

<span data-ttu-id="a9f83-167">В этом примере мы создадим файл символьной ссылки MySymLinkFile.txt в C:\Temp со ссылкой на файл $pshome\profile.ps1.</span><span class="sxs-lookup"><span data-stu-id="a9f83-167">In this example, we create a new symbolic link file named MySymLinkFile.txt in C:\Temp which links to $pshome\profile.ps1.</span></span> <span data-ttu-id="a9f83-168">Все три примера дают одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="a9f83-168">All three examples produce the same result.</span></span>

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="symbolic-link-directories"></a><span data-ttu-id="a9f83-169">Каталоги с символьными ссылками</span><span class="sxs-lookup"><span data-stu-id="a9f83-169">Symbolic link directories</span></span>

<span data-ttu-id="a9f83-170">В этом примере мы создадим каталог символьной ссылки MySymLinkDir в папке C:\Temp, который позволяет перейти к папке $pshome.</span><span class="sxs-lookup"><span data-stu-id="a9f83-170">In this example, we create a new symbolic link directory named MySymLinkDir in C:\Temp which links to the $pshome folder.</span></span> <span data-ttu-id="a9f83-171">Все три примера дают одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="a9f83-171">All three examples produce the same result.</span></span>

```powershell
New-Item -ItemType SymbolicLink -Path C:\Temp -Name MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Path C:\Temp\MySymLinkDir -Value $pshome
New-Item -ItemType SymbolicLink -Name C:\Temp\MySymLinkDir -Value $pshome
```

### <a name="hard-links"></a><span data-ttu-id="a9f83-172">жесткие ссылки;</span><span class="sxs-lookup"><span data-stu-id="a9f83-172">Hard links</span></span>

<span data-ttu-id="a9f83-173">Одинаковые комбинации **пути** и **имени** разрешены, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="a9f83-173">The same combinations of **Path** and **Name** allowed as described above.</span></span>

```powershell
New-Item -ItemType HardLink -Path C:\Temp -Name MyHardLinkFile.txt -Value $pshome\profile.ps1
```

### <a name="directory-junctions"></a><span data-ttu-id="a9f83-174">Соединения каталогов</span><span class="sxs-lookup"><span data-stu-id="a9f83-174">Directory junctions</span></span>

<span data-ttu-id="a9f83-175">Одинаковые комбинации **пути** и **имени** разрешены, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="a9f83-175">The same combinations of **Path** and **Name** allowed as described above.</span></span>

```powershell
New-Item -ItemType Junction -Path C:\Temp\MyJunctionDir -Value $pshome
```

### <a name="get-childitem"></a><span data-ttu-id="a9f83-176">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="a9f83-176">Get-ChildItem</span></span>

<span data-ttu-id="a9f83-177">`Get-ChildItem` теперь отображает "l" в свойстве **Mode**, указывающем на файл или каталог символьной ссылки.</span><span class="sxs-lookup"><span data-stu-id="a9f83-177">`Get-ChildItem` now displays an 'l' in the **Mode** property to indicate a symbolic link file or directory.</span></span>

```powershell
Get-ChildItem C:\Temp | sort LastWriteTime -Descending

Directory: C:\Temp

Mode       LastWriteTime Length Name
----       ------------- ------ ----
-a---- 6/13/2014 3:00 PM     16 File.txt
d----- 6/13/2014 3:00 PM        Directory
-a---l 6/13/2014 3:21 PM      0 MySymLinkFile.txt
d----l 6/13/2014 3:22 PM        MySymLinkDir
-a---l 6/13/2014 3:23 PM  23304 MyHardLinkFile.txt
d----l 6/13/2014 3:24 PM        MyJunctionDir
```

### <a name="remove-item"></a><span data-ttu-id="a9f83-178">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="a9f83-178">Remove-Item</span></span>

<span data-ttu-id="a9f83-179">Удаление символьной ссылки подобно удалению любого другого типа элемента.</span><span class="sxs-lookup"><span data-stu-id="a9f83-179">Removing symbolic links works like removing any other item type.</span></span>

```powershell
Remove-Item C:\Temp\MySymLinkFile.txt
Remove-Item C:\Temp\MySymLinkDir
```

<span data-ttu-id="a9f83-180">Используйте параметр **Force**, чтобы удалить файлы в целевом каталоге и символьную ссылку.</span><span class="sxs-lookup"><span data-stu-id="a9f83-180">Use the **Force** parameter to remove the files in the target directory and the symbolic link.</span></span>

```powershell
Remove-Item C:\Temp\MySymLinkDir -Force
```

## <a name="new-temporaryfile"></a><span data-ttu-id="a9f83-181">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="a9f83-181">New-TemporaryFile</span></span>

<span data-ttu-id="a9f83-182">Иногда в сценариях необходимо создать временный файл.</span><span class="sxs-lookup"><span data-stu-id="a9f83-182">Sometimes in your scripts, you must create a temporary file.</span></span> <span data-ttu-id="a9f83-183">Теперь это можно сделать с помощью командлета `New-TemporaryFile`:</span><span class="sxs-lookup"><span data-stu-id="a9f83-183">You can now do this with the `New-TemporaryFile` cmdlet:</span></span>

```powershell
$tempFile = New-TemporaryFile
$tempFile.FullName
```

```Output
C:\Users\user1\AppData\Local\Temp\tmp375.tmp
```

## <a name="network-switch-management-with-powershell"></a><span data-ttu-id="a9f83-184">Управление сетевыми коммутаторами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9f83-184">Network Switch Management with PowerShell</span></span>

<span data-ttu-id="a9f83-185">Командлеты сетевых коммутаторов, представленные в WMF 5.0, позволяют применять конфигурацию коммутатора, виртуальной локальной сети и портов базового сетевого коммутатора уровня 2 к сетевым коммутаторам, прошедшим сертификацию для Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="a9f83-185">The Network Switch cmdlets, introduced in WMF 5.0, enable you to apply switch, virtual LAN (VLAN), and basic Layer 2 network switch port configuration to Windows Server 2012 R2 logo-certified network switches.</span></span> <span data-ttu-id="a9f83-186">Эти командлеты позволяют осуществлять следующее.</span><span class="sxs-lookup"><span data-stu-id="a9f83-186">Using these cmdlets you can perform:</span></span>

- <span data-ttu-id="a9f83-187">Глобальная конфигурация коммутаторов, например следующее.</span><span class="sxs-lookup"><span data-stu-id="a9f83-187">Global switch configuration, such as:</span></span>
  - <span data-ttu-id="a9f83-188">Задание имени узла</span><span class="sxs-lookup"><span data-stu-id="a9f83-188">Set host name</span></span>
  - <span data-ttu-id="a9f83-189">Задание баннера параметров</span><span class="sxs-lookup"><span data-stu-id="a9f83-189">Set switch banner</span></span>
  - <span data-ttu-id="a9f83-190">Сохранение конфигурации</span><span class="sxs-lookup"><span data-stu-id="a9f83-190">Persist configuration</span></span>
  - <span data-ttu-id="a9f83-191">Включение и отключение функции</span><span class="sxs-lookup"><span data-stu-id="a9f83-191">Enable or disable feature</span></span>

- <span data-ttu-id="a9f83-192">Конфигурация виртуальной локальной сети:</span><span class="sxs-lookup"><span data-stu-id="a9f83-192">VLAN configuration:</span></span>
  - <span data-ttu-id="a9f83-193">Создание или удаление виртуальной ЛС</span><span class="sxs-lookup"><span data-stu-id="a9f83-193">Create or remove VLAN</span></span>
  - <span data-ttu-id="a9f83-194">Включение или отключение виртуальной ЛС</span><span class="sxs-lookup"><span data-stu-id="a9f83-194">Enable or disable VLAN</span></span>
  - <span data-ttu-id="a9f83-195">Перечисление виртуальной ЛС</span><span class="sxs-lookup"><span data-stu-id="a9f83-195">Enumerate VLAN</span></span>
  - <span data-ttu-id="a9f83-196">Указание понятного имени для виртуальной ЛС</span><span class="sxs-lookup"><span data-stu-id="a9f83-196">Set friendly name to a VLAN</span></span>

- <span data-ttu-id="a9f83-197">Конфигурация портов уровня 2:</span><span class="sxs-lookup"><span data-stu-id="a9f83-197">Layer 2 port configuration:</span></span>
  - <span data-ttu-id="a9f83-198">Перечисление портов</span><span class="sxs-lookup"><span data-stu-id="a9f83-198">Enumerate ports</span></span>
  - <span data-ttu-id="a9f83-199">Включение или отключение портов</span><span class="sxs-lookup"><span data-stu-id="a9f83-199">Enable or disable ports</span></span>
  - <span data-ttu-id="a9f83-200">Задание свойств и режимов портов</span><span class="sxs-lookup"><span data-stu-id="a9f83-200">Set port modes and properties</span></span>
  - <span data-ttu-id="a9f83-201">Добавление или сопоставление виртуальной ЛС с режимом магистрали или доступа для порта</span><span class="sxs-lookup"><span data-stu-id="a9f83-201">Add or associate VLAN to Trunk or Access on the port</span></span>

<span data-ttu-id="a9f83-202">Дополнительные сведения см. в статье документации [NetworkSwitchManager](/powershell/module/networkswitchmanager/).</span><span class="sxs-lookup"><span data-stu-id="a9f83-202">For more information, see the [NetworkSwitchManager](/powershell/module/networkswitchmanager/) documentation.</span></span>

## <a name="generate-powershell-cmdlets-based-on-an-odata-endpoint-with-odatautils"></a><span data-ttu-id="a9f83-203">Создание командлетов PowerShell на основе конечной точки OData с помощью ODataUtils</span><span class="sxs-lookup"><span data-stu-id="a9f83-203">Generate PowerShell cmdlets based on an OData endpoint with ODataUtils</span></span>

<span data-ttu-id="a9f83-204">Модуль ODataUtils позволяет создавать командлеты PowerShell на базе конечных точек REST, которые поддерживают OData.</span><span class="sxs-lookup"><span data-stu-id="a9f83-204">The ODataUtils module allows generation of PowerShell cmdlets from REST endpoints that support OData.</span></span> <span data-ttu-id="a9f83-205">Модуль Microsoft.PowerShell.ODataUtils включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="a9f83-205">The Microsoft.PowerShell.ODataUtils module includes the following features:</span></span>

- <span data-ttu-id="a9f83-206">Передача дополнительных сведений с серверной конечной точки на сторону клиента</span><span class="sxs-lookup"><span data-stu-id="a9f83-206">Channel additional information from server-side endpoint to client side.</span></span>
- <span data-ttu-id="a9f83-207">Поддержки разбивки на страницы на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="a9f83-207">Client-side paging support</span></span>
- <span data-ttu-id="a9f83-208">Фильтрация на стороне сервера с помощью параметра Select</span><span class="sxs-lookup"><span data-stu-id="a9f83-208">Server-side filtering by using the -Select parameter</span></span>
- <span data-ttu-id="a9f83-209">Поддержка заголовков веб-запросов</span><span class="sxs-lookup"><span data-stu-id="a9f83-209">Support for web request headers</span></span>

<span data-ttu-id="a9f83-210">Командлеты прокси-сервера, созданные командлетом `Export-ODataEndPointProxy`, предоставляют дополнительные сведения из конечной точки OData на стороне сервера в потоке **Information**.</span><span class="sxs-lookup"><span data-stu-id="a9f83-210">The proxy cmdlets generated by the `Export-ODataEndPointProxy` cmdlet provide additional information from the server-side OData endpoint on the **Information** stream.</span></span>

```powershell
Import-Module Microsoft.PowerShell.ODataUtils -Force
$generatedProxyModuleDir = Join-Path -Path $env:SystemDrive -ChildPath 'ODataDemoProxy'
$uri = "http://services.odata.org/V3/(S(fhleiief23wrm5a5nhf542q5))/OData/OData.svc/"
Export-ODataEndpointProxy -Uri $uri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -AllowClobber
```

<span data-ttu-id="a9f83-211">В следующем примере мы получаем данные о самом популярном продукте и записываем выходные данные в переменную `$infoStream`.</span><span class="sxs-lookup"><span data-stu-id="a9f83-211">In the following example, we are retrieving top product and capturing the output in the `$infoStream` variable.</span></span>

<span data-ttu-id="a9f83-212">Указав параметр **IncludeTotalResponseCount**, мы получаем общее число всех записей **Product**, доступных на сервере.</span><span class="sxs-lookup"><span data-stu-id="a9f83-212">By specifying **IncludeTotalResponseCount** parameter, we get the total count of all the **Product** records available on the server.</span></span>

```powershell
Import-Module $generatedProxyModuleDir -Force
$product = Get-Product -Top 1 -AllowUnsecureConnection -AllowAdditionalData -IncludeTotalResponseCount -InformationVariable infoStream
$additionalInfo = $infoStream.GetEnumerator() | % MessageData
$additionalInfo['odata.count']
```

<span data-ttu-id="a9f83-213">Записи с сервера можно получить в пакетах, используя поддержку разбивки на страницы на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="a9f83-213">You can get the records from the server in batches using client-side paging support.</span></span> <span data-ttu-id="a9f83-214">Это удобно, когда требуется получить большой объем данных с сервера по сети.</span><span class="sxs-lookup"><span data-stu-id="a9f83-214">This is useful when you must get a large amount of data from the server over the network.</span></span>

```powershell
$skipCount = 0
$batchSize = 3
while($skipCount -le $additionalInfo['odata.count'])
{
  Get-Product -AllowUnsecureConnection -AllowAdditionalData -Top $batchSize -Skip $skipCount
  $skipCount += $batchSize
}
```

<span data-ttu-id="a9f83-215">Созданные командлеты прокси-сервера поддерживают параметр **Select**, используемый в качестве фильтра, чтобы получить только свойства записей, необходимые клиенту.</span><span class="sxs-lookup"><span data-stu-id="a9f83-215">The generated proxy cmdlets support the **Select** parameter that is used as a filter to receive only the record properties that the client needs.</span></span> <span data-ttu-id="a9f83-216">Это уменьшает объем передаваемых по сети данных, так как фильтрация выполняется на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="a9f83-216">The filtering occurs on the server, which reduces the amount of data that is transferred over the network.</span></span>

```powershell
Get-Product -Top 2 -AllowUnsecureConnection -AllowAdditionalData -Select Name
```

<span data-ttu-id="a9f83-217">Командлет `Export-ODataEndpointProxy` и созданные на его основе командлеты прокси-сервера теперь поддерживают параметр **Headers**.</span><span class="sxs-lookup"><span data-stu-id="a9f83-217">The `Export-ODataEndpointProxy` cmdlet, and the proxy cmdlets generated by it, now support the **Headers** parameter.</span></span> <span data-ttu-id="a9f83-218">Заголовок может использоваться для передачи дополнительных сведений, ожидаемых конечной точкой OData.</span><span class="sxs-lookup"><span data-stu-id="a9f83-218">The header can be used to channel additional information expected by the OData endpoint.</span></span>

<span data-ttu-id="a9f83-219">В следующем примере в параметр **Headers** передается хэш-таблица, содержащая ключ подписки.</span><span class="sxs-lookup"><span data-stu-id="a9f83-219">In the following example, a hash table containing a Subscription key is provided to the **Headers** parameter.</span></span> <span data-ttu-id="a9f83-220">Это типичный пример для служб, которые ожидают ключ подписки для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a9f83-220">This is a typical example for services that are expecting a Subscription key for authentication.</span></span>

```powershell
Export-ODataEndpointProxy -Uri $endPointUri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -Headers @{'subscription-key'='XXXX'}
```
