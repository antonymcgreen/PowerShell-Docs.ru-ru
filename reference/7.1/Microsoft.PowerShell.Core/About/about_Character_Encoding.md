---
title: about_Character_Encoding
description: Описывает, как PowerShell использует кодировку символов для ввода и вывода строковых данных.
ms.date: 10/21/2020
Locale: en-US
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_character_encoding?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
ms.openlocfilehash: 6e2f515f774d7bc333baf6346cd6c8bd517cb6fa
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "93233241"
---
# <a name="about_character_encoding"></a><span data-ttu-id="f389b-103">about_Character_Encoding</span><span class="sxs-lookup"><span data-stu-id="f389b-103">about_Character_Encoding</span></span>

## <a name="short-description"></a><span data-ttu-id="f389b-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="f389b-104">Short description</span></span>
<span data-ttu-id="f389b-105">Описывает, как PowerShell использует кодировку символов для ввода и вывода строковых данных.</span><span class="sxs-lookup"><span data-stu-id="f389b-105">Describes how PowerShell uses character encoding for input and output of string data.</span></span>

## <a name="long-description"></a><span data-ttu-id="f389b-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f389b-106">Long description</span></span>

<span data-ttu-id="f389b-107">Юникод — это мировой стандарт кодировки символов.</span><span class="sxs-lookup"><span data-stu-id="f389b-107">Unicode is a worldwide character-encoding standard.</span></span> <span data-ttu-id="f389b-108">Система использует Юникод исключительно для обработки символов и строк.</span><span class="sxs-lookup"><span data-stu-id="f389b-108">The system uses Unicode exclusively for character and string manipulation.</span></span> <span data-ttu-id="f389b-109">Подробное описание всех аспектов Юникода см. в [стандарте Юникода](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="f389b-109">For a detailed description of all aspects of Unicode, refer to [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>

<span data-ttu-id="f389b-110">Windows поддерживает Юникод и традиционные наборы символов.</span><span class="sxs-lookup"><span data-stu-id="f389b-110">Windows supports Unicode and traditional character sets.</span></span> <span data-ttu-id="f389b-111">Традиционные кодировки, например кодовые страницы Windows, используют 8-разрядные значения или сочетания 8-разрядных значений для представления символов, используемых в определенном языке или географических регионах.</span><span class="sxs-lookup"><span data-stu-id="f389b-111">Traditional character sets, such as Windows code pages, use 8-bit values or combinations of 8-bit values to represent the characters used in a specific language or geographical region settings.</span></span>

<span data-ttu-id="f389b-112">По умолчанию PowerShell использует набор символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="f389b-112">PowerShell uses a Unicode character set by default.</span></span> <span data-ttu-id="f389b-113">Однако несколько командлетов имеют параметр **кодирования** , который может указывать кодировку для другой кодировки.</span><span class="sxs-lookup"><span data-stu-id="f389b-113">However, several cmdlets have an **Encoding** parameter that can specify encoding for a different character set.</span></span> <span data-ttu-id="f389b-114">Этот параметр позволяет выбрать конкретную кодировку символов, необходимую для взаимодействия с другими системами и приложениями.</span><span class="sxs-lookup"><span data-stu-id="f389b-114">This parameter allows you to choose the specific the character encoding you need for interoperability with other systems and applications.</span></span>

<span data-ttu-id="f389b-115">Следующие командлеты имеют параметр **Encoding** :</span><span class="sxs-lookup"><span data-stu-id="f389b-115">The following cmdlets have the **Encoding** parameter:</span></span>

- <span data-ttu-id="f389b-116">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="f389b-116">Microsoft.PowerShell.Management</span></span>
  - <span data-ttu-id="f389b-117">Add-Content</span><span class="sxs-lookup"><span data-stu-id="f389b-117">Add-Content</span></span>
  - <span data-ttu-id="f389b-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="f389b-118">Get-Content</span></span>
  - <span data-ttu-id="f389b-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="f389b-119">Set-Content</span></span>
- <span data-ttu-id="f389b-120">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="f389b-120">Microsoft.PowerShell.Utility</span></span>
  - <span data-ttu-id="f389b-121">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="f389b-121">Export-Clixml</span></span>
  - <span data-ttu-id="f389b-122">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="f389b-122">Export-Csv</span></span>
  - <span data-ttu-id="f389b-123">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="f389b-123">Export-PSSession</span></span>
  - <span data-ttu-id="f389b-124">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="f389b-124">Format-Hex</span></span>
  - <span data-ttu-id="f389b-125">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="f389b-125">Import-Csv</span></span>
  - <span data-ttu-id="f389b-126">Out-File</span><span class="sxs-lookup"><span data-stu-id="f389b-126">Out-File</span></span>
  - <span data-ttu-id="f389b-127">Select-String</span><span class="sxs-lookup"><span data-stu-id="f389b-127">Select-String</span></span>
  - <span data-ttu-id="f389b-128">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="f389b-128">Send-MailMessage</span></span>

## <a name="the-byte-order-mark"></a><span data-ttu-id="f389b-129">Пометка порядка байтов</span><span class="sxs-lookup"><span data-stu-id="f389b-129">The byte-order-mark</span></span>

<span data-ttu-id="f389b-130">Символ-пометка (BOM) — это _сигнатура в Юникоде_ в первых нескольких байтах файла или текстового потока, указывающих, какая кодировка Юникода используется для данных.</span><span class="sxs-lookup"><span data-stu-id="f389b-130">The byte-order-mark (BOM) is a _Unicode signature_ in the first few bytes of a file or text stream that indicate which Unicode encoding used for the data.</span></span> <span data-ttu-id="f389b-131">Дополнительные сведения см. в статье [метка порядка байтов](https://wikipedia.org/wiki/Byte_order_mark) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="f389b-131">For more information, see the [Byte order mark](https://wikipedia.org/wiki/Byte_order_mark) article in Wikipedia.</span></span>

<span data-ttu-id="f389b-132">В Windows PowerShell любая Кодировка Юникода, за исключением `UTF7` , всегда создает спецификацию.</span><span class="sxs-lookup"><span data-stu-id="f389b-132">In Windows PowerShell, any Unicode encoding, except `UTF7`, always creates a BOM.</span></span> <span data-ttu-id="f389b-133">По умолчанию PowerShell Core имеет значение `utf8NoBOM` для всех текстовых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f389b-133">PowerShell Core defaults to `utf8NoBOM` for all text output.</span></span>

<span data-ttu-id="f389b-134">Для обеспечения оптимальной совместимости Избегайте использования спецификаций в файлах UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f389b-134">For best overall compatibility, avoid using BOMs in UTF-8 files.</span></span> <span data-ttu-id="f389b-135">Платформы UNIX и служебные программы Unix-Heritage, которые также используются на платформах Windows, не поддерживают спецификации.</span><span class="sxs-lookup"><span data-stu-id="f389b-135">Unix platforms and Unix-heritage utilities also used on Windows Platforms don't support BOMs.</span></span>

<span data-ttu-id="f389b-136">Аналогичным образом `UTF7` следует избегать кодирования.</span><span class="sxs-lookup"><span data-stu-id="f389b-136">Similarly, `UTF7` encoding should be avoided.</span></span> <span data-ttu-id="f389b-137">UTF-7 не является стандартной кодировкой Юникода и записывается без спецификации во всех версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f389b-137">UTF-7 is not a standard Unicode encoding and is written without a BOM in all versions of PowerShell.</span></span>

<span data-ttu-id="f389b-138">Создание сценариев PowerShell на платформе, похожем на UNIX, или использовании кросс-платформенного редактора в Windows, например Visual Studio Code, приводит к созданию файла, закодированного с помощью `UTF8NoBOM` .</span><span class="sxs-lookup"><span data-stu-id="f389b-138">Creating PowerShell scripts on a Unix-like platform or using a cross-platform editor on Windows, such as Visual Studio Code, results in a file encoded using `UTF8NoBOM`.</span></span> <span data-ttu-id="f389b-139">Эти файлы прекрасно работают в PowerShell Core, но могут нарушить работу Windows PowerShell, если файл содержит символы, отличные от ASCII.</span><span class="sxs-lookup"><span data-stu-id="f389b-139">These files work fine on PowerShell Core, but may break in Windows PowerShell if the file contains non-Ascii characters.</span></span>

<span data-ttu-id="f389b-140">Если в скриптах необходимо использовать символы, отличные от ASCII, сохраните их как UTF-8 с помощью BOM.</span><span class="sxs-lookup"><span data-stu-id="f389b-140">If you need to use non-Ascii characters in your scripts, save them as UTF-8 with BOM.</span></span> <span data-ttu-id="f389b-141">Без спецификации Windows PowerShell ошибочно интерпретирует скрипт как закодированный в устаревшей кодовой странице ANSI.</span><span class="sxs-lookup"><span data-stu-id="f389b-141">Without the BOM, Windows PowerShell misinterprets your script as being encoded in the legacy "ANSI" codepage.</span></span> <span data-ttu-id="f389b-142">И наоборот, файлы, имеющие СПЕЦИФИКАЦИю UTF-8, могут быть проблематичными для платформ, подобных Unix.</span><span class="sxs-lookup"><span data-stu-id="f389b-142">Conversely, files that do have the UTF-8 BOM can be problematic on Unix-like platforms.</span></span> <span data-ttu-id="f389b-143">Многие средства UNIX, такие как `cat` ,, `sed` `awk` и некоторые редакторы, например, `gedit` не узнают, как обрабатывать спецификацию.</span><span class="sxs-lookup"><span data-stu-id="f389b-143">Many Unix tools such as `cat`, `sed`, `awk`, and some editors such as `gedit` don't know how to treat the BOM.</span></span>

## <a name="character-encoding-in-windows-powershell"></a><span data-ttu-id="f389b-144">Кодировка символов в Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f389b-144">Character encoding in Windows PowerShell</span></span>

<span data-ttu-id="f389b-145">В PowerShell 5,1 параметр **Encoding** поддерживает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f389b-145">In PowerShell 5.1, the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="f389b-146">`Ascii` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="f389b-146">`Ascii` Uses Ascii (7-bit) character set.</span></span>
- <span data-ttu-id="f389b-147">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f389b-147">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="f389b-148">`BigEndianUTF32` Использует UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f389b-148">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="f389b-149">`Byte` Кодирует набор символов в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="f389b-149">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="f389b-150">`Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).</span><span class="sxs-lookup"><span data-stu-id="f389b-150">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="f389b-151">`Oem` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="f389b-151">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="f389b-152">`String` аналогичен `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="f389b-152">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="f389b-153">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f389b-153">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="f389b-154">`Unknown` аналогичен `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="f389b-154">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="f389b-155">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f389b-155">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>
- <span data-ttu-id="f389b-156">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="f389b-156">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="f389b-157">`UTF8` Использует UTF-8 (с BOM).</span><span class="sxs-lookup"><span data-stu-id="f389b-157">`UTF8` Uses UTF-8 (with BOM).</span></span>

<span data-ttu-id="f389b-158">В общем случае Windows PowerShell по умолчанию использует кодировку Юникод [UTF-16LE](https://wikipedia.org/wiki/UTF-16) .</span><span class="sxs-lookup"><span data-stu-id="f389b-158">In general, Windows PowerShell uses the Unicode [UTF-16LE](https://wikipedia.org/wiki/UTF-16) encoding by default.</span></span> <span data-ttu-id="f389b-159">Однако кодировка по умолчанию, используемая командлетами в Windows PowerShell, не согласуется.</span><span class="sxs-lookup"><span data-stu-id="f389b-159">However, the default encoding used by cmdlets in Windows PowerShell is not consistent.</span></span>

> [!NOTE]
> <span data-ttu-id="f389b-160">При использовании любой кодировки Юникода, за исключением `UTF7` , всегда создает спецификацию.</span><span class="sxs-lookup"><span data-stu-id="f389b-160">Using any Unicode encoding, except `UTF7`, always creates a BOM.</span></span>

<span data-ttu-id="f389b-161">Для командлетов, записывающих выходные данные в файлы:</span><span class="sxs-lookup"><span data-stu-id="f389b-161">For cmdlets that write output to files:</span></span>

- <span data-ttu-id="f389b-162">`Out-File` и операторы перенаправления `>` и `>>` создают UTF-16LE, который, в свою очередь, отличается от `Set-Content` и `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="f389b-162">`Out-File` and the redirection operators `>` and `>>` create UTF-16LE, which notably differs from `Set-Content` and `Add-Content`.</span></span>

- <span data-ttu-id="f389b-163">`New-ModuleManifest` а `Export-CliXml` также создавать файлы UTF-16LE.</span><span class="sxs-lookup"><span data-stu-id="f389b-163">`New-ModuleManifest` and `Export-CliXml` also create UTF-16LE files.</span></span>

- <span data-ttu-id="f389b-164">Если целевой файл пуст или не существует, `Set-Content` и `Add-Content` Используйте `Default` кодировку.</span><span class="sxs-lookup"><span data-stu-id="f389b-164">When the target file is empty or doesn't exist, `Set-Content` and `Add-Content` use `Default` encoding.</span></span> <span data-ttu-id="f389b-165">`Default` — это кодировка, определяемая кодовой страницей устаревшей версии ANSI на языке активного системы.</span><span class="sxs-lookup"><span data-stu-id="f389b-165">`Default` is the encoding specified by the active system locale's ANSI legacy code page.</span></span>

- <span data-ttu-id="f389b-166">`Export-Csv` создает `Ascii` файлы, но использует другую кодировку при использовании параметра **append** (см. ниже).</span><span class="sxs-lookup"><span data-stu-id="f389b-166">`Export-Csv` creates `Ascii` files but uses different encoding when using **Append** parameter (see below).</span></span>

- <span data-ttu-id="f389b-167">`Export-PSSession` по умолчанию создает файлы UTF-8 с BOM.</span><span class="sxs-lookup"><span data-stu-id="f389b-167">`Export-PSSession` creates UTF-8 files with BOM by default.</span></span>

- <span data-ttu-id="f389b-168">`New-Item -Type File -Value` создает файл UTF-8 с кодировкой BOM.</span><span class="sxs-lookup"><span data-stu-id="f389b-168">`New-Item -Type File -Value` creates a BOM-less UTF-8 file.</span></span>

- <span data-ttu-id="f389b-169">`Send-MailMessage` по `Default` умолчанию использует кодировку.</span><span class="sxs-lookup"><span data-stu-id="f389b-169">`Send-MailMessage` uses `Default` encoding by default.</span></span>

- <span data-ttu-id="f389b-170">`Start-Transcript` создает `Utf8` файлы с помощью спецификации.</span><span class="sxs-lookup"><span data-stu-id="f389b-170">`Start-Transcript` creates `Utf8` files with a BOM.</span></span> <span data-ttu-id="f389b-171">При использовании параметра **append** кодировка может отличаться (см. ниже).</span><span class="sxs-lookup"><span data-stu-id="f389b-171">When the **Append** parameter is used, the encoding can be different (see below).</span></span>

<span data-ttu-id="f389b-172">Для команд, которые добавляют к существующему файлу:</span><span class="sxs-lookup"><span data-stu-id="f389b-172">For commands that append to an existing file:</span></span>

- <span data-ttu-id="f389b-173">`Out-File -Append` и `>>` оператор перенаправления не пытается сопоставить кодировку содержимого существующего целевого файла.</span><span class="sxs-lookup"><span data-stu-id="f389b-173">`Out-File -Append` and the `>>` redirection operator make no attempt to match the encoding of the existing target file's content.</span></span> <span data-ttu-id="f389b-174">Вместо этого они используют кодировку по умолчанию, если не используется параметр **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="f389b-174">Instead, they use the default encoding unless the **Encoding** parameter is used.</span></span> <span data-ttu-id="f389b-175">При добавлении содержимого необходимо использовать исходную кодировку файлов.</span><span class="sxs-lookup"><span data-stu-id="f389b-175">You must use the files original encoding when appending content.</span></span>

- <span data-ttu-id="f389b-176">При отсутствии явного параметра **кодировки** `Add-Content` обнаруживает существующую кодировку и автоматически применяет ее к новому содержимому.</span><span class="sxs-lookup"><span data-stu-id="f389b-176">In the absence of an explicit **Encoding** parameter, `Add-Content` detects the existing encoding and automatically applies it to the new content.</span></span> <span data-ttu-id="f389b-177">Если имеющееся содержимое не имеет BOM, `Default` используется кодировка ANSI.</span><span class="sxs-lookup"><span data-stu-id="f389b-177">If the existing content has no BOM, `Default` ANSI encoding is used.</span></span> <span data-ttu-id="f389b-178">Поведение аналогично `Add-Content` в PowerShell Core (V6 и более поздних версиях), кроме кодировки по умолчанию — `Utf8` .</span><span class="sxs-lookup"><span data-stu-id="f389b-178">The behavior of `Add-Content` is the same in PowerShell Core (v6 and higher) except the default encoding is `Utf8`.</span></span>

- <span data-ttu-id="f389b-179">`Export-Csv -Append` соответствует существующей кодировке, если целевой файл содержит СПЕЦИФИКАЦИю.</span><span class="sxs-lookup"><span data-stu-id="f389b-179">`Export-Csv -Append` matches the existing encoding when the target file contains a BOM.</span></span> <span data-ttu-id="f389b-180">В отсутствие спецификации используется `Utf8` Кодировка.</span><span class="sxs-lookup"><span data-stu-id="f389b-180">In the absence of a BOM, it uses `Utf8` encoding.</span></span>

- <span data-ttu-id="f389b-181">`Start-Transcript -Append` соответствует существующей кодировке файлов, включающих СПЕЦИФИКАЦИю.</span><span class="sxs-lookup"><span data-stu-id="f389b-181">`Start-Transcript -Append` matches the existing encoding of files that include a BOM.</span></span> <span data-ttu-id="f389b-182">При отсутствии спецификации по умолчанию используется `Ascii` Кодировка.</span><span class="sxs-lookup"><span data-stu-id="f389b-182">In the absence of a BOM, it defaults to `Ascii` encoding.</span></span> <span data-ttu-id="f389b-183">Такая кодировка может привести к утере данных или повреждению символов, если данные в записи содержат многобайтовые символы.</span><span class="sxs-lookup"><span data-stu-id="f389b-183">This encoding can result in data loss or character corruption when the data in the transcript contains multibyte characters.</span></span>

<span data-ttu-id="f389b-184">Для командлетов, считывающих строковые данные в отсутствие спецификации:</span><span class="sxs-lookup"><span data-stu-id="f389b-184">For cmdlets that read string data in the absence of a BOM:</span></span>

- <span data-ttu-id="f389b-185">`Get-Content` и `Import-PowerShellDataFile` использует `Default` кодировку ANSI.</span><span class="sxs-lookup"><span data-stu-id="f389b-185">`Get-Content` and `Import-PowerShellDataFile` uses the `Default` ANSI encoding.</span></span> <span data-ttu-id="f389b-186">ANSI также используется механизмом PowerShell при чтении исходного кода из файлов.</span><span class="sxs-lookup"><span data-stu-id="f389b-186">ANSI is also what the PowerShell engine uses when it reads source code from files.</span></span>

- <span data-ttu-id="f389b-187">`Import-Csv`, `Import-CliXml` и `Select-String` предполагают `Utf8` отсутствие спецификации.</span><span class="sxs-lookup"><span data-stu-id="f389b-187">`Import-Csv`, `Import-CliXml`, and `Select-String` assume `Utf8` in the absence of a BOM.</span></span>

## <a name="character-encoding-in-powershell-core"></a><span data-ttu-id="f389b-188">Кодировка символов в PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="f389b-188">Character encoding in PowerShell Core</span></span>

<span data-ttu-id="f389b-189">В PowerShell Core (V6 и более поздних версий) параметр **Encoding** поддерживает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f389b-189">In PowerShell Core (v6 and higher), the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="f389b-190">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="f389b-190">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="f389b-191">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f389b-191">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="f389b-192">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="f389b-192">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="f389b-193">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="f389b-193">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="f389b-194">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="f389b-194">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="f389b-195">`utf8`: Кодирует в формате UTF-8 (без спецификации).</span><span class="sxs-lookup"><span data-stu-id="f389b-195">`utf8`: Encodes in UTF-8 format (no BOM).</span></span>
- <span data-ttu-id="f389b-196">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="f389b-196">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="f389b-197">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="f389b-197">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="f389b-198">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="f389b-198">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="f389b-199">По умолчанию PowerShell Core имеет значение `utf8NoBOM` для всех выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f389b-199">PowerShell Core defaults to `utf8NoBOM` for all output.</span></span>

<span data-ttu-id="f389b-200">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="f389b-200">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="f389b-201">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage).</span><span class="sxs-lookup"><span data-stu-id="f389b-201">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage).</span></span>

## <a name="changing-the-default-encoding"></a><span data-ttu-id="f389b-202">Изменение кодировки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f389b-202">Changing the default encoding</span></span>

<span data-ttu-id="f389b-203">В PowerShell есть две переменные по умолчанию, которые можно использовать для изменения поведения кодировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f389b-203">PowerShell has two default variables that can be used to change the default encoding behavior.</span></span>

- `$PSDefaultParameterValues`
- `$OutputEncoding`

<span data-ttu-id="f389b-204">Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f389b-204">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="f389b-205">Начиная с PowerShell 5,1, операторы перенаправления ( `>` и `>>` ) вызывают `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="f389b-205">Beginning in PowerShell 5.1, the redirection operators (`>` and `>>`) call the `Out-File` cmdlet.</span></span> <span data-ttu-id="f389b-206">Таким образом, можно задать кодировку по умолчанию для них с помощью `$PSDefaultParameterValues` переменной предпочтений, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f389b-206">Therefore, you can set the default encoding of them using the `$PSDefaultParameterValues` preference variable as shown in this example:</span></span>

```powershell
$PSDefaultParameterValues['Out-File:Encoding'] = 'utf8'
```

<span data-ttu-id="f389b-207">Используйте следующую инструкцию, чтобы изменить кодировку по умолчанию для всех командлетов, имеющих параметр **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="f389b-207">Use the following statement to change the default encoding for all cmdlets that have the **Encoding** parameter.</span></span>

```powershell
$PSDefaultParameterValues['*:Encoding'] = 'utf8'
```

> [!IMPORTANT]
> <span data-ttu-id="f389b-208">При размещении этой команды в профиле PowerShell предпочтение влияет на глобальные параметры сеанса, влияющие на все команды и скрипты, которые явно не задают кодировку.</span><span class="sxs-lookup"><span data-stu-id="f389b-208">Putting this command in your PowerShell profile makes the preference a session-global setting that affects all commands and scripts that do not explicitly specify an encoding.</span></span>
>
> <span data-ttu-id="f389b-209">Аналогичным образом следует включить такие команды в скрипты или модули, которые должны вести себя одинаково.</span><span class="sxs-lookup"><span data-stu-id="f389b-209">Similarly, you should include such commands in your scripts or modules that you want to behave the same way.</span></span> <span data-ttu-id="f389b-210">Использование этих команд гарантирует, что командлеты ведут себя одинаково даже при запуске другого пользователя, на другом компьютере или в другой версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f389b-210">Using these commands ensure that cmdlets behave the same way even when run by another user, on a different computer, or in a different version of PowerShell.</span></span>

<span data-ttu-id="f389b-211">Автоматическая переменная `$OutputEncoding` влияет на кодирование, используемое PowerShell для взаимодействия с внешними программами.</span><span class="sxs-lookup"><span data-stu-id="f389b-211">The automatic variable `$OutputEncoding` affects the encoding PowerShell uses to communicate with external programs.</span></span> <span data-ttu-id="f389b-212">Он не влияет на кодировку, которую операторы перенаправления вывода и командлеты PowerShell используют для сохранения в файлах.</span><span class="sxs-lookup"><span data-stu-id="f389b-212">It has no effect on the encoding that the output redirection operators and PowerShell cmdlets use to save to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="f389b-213">См. также</span><span class="sxs-lookup"><span data-stu-id="f389b-213">See also</span></span>

- [<span data-ttu-id="f389b-214">Общие сведения о кодировании символов в .NET</span><span class="sxs-lookup"><span data-stu-id="f389b-214">Introduction to character encoding in .NET</span></span>](/dotnet/standard/base-types/character-encoding-introduction)
- [<span data-ttu-id="f389b-215">Кодовые страницы — приложения Win32</span><span class="sxs-lookup"><span data-stu-id="f389b-215">Code Pages - Win32 apps</span></span>](/windows/win32/intl/code-pages)
- [<span data-ttu-id="f389b-216">Стандарт Юникода</span><span class="sxs-lookup"><span data-stu-id="f389b-216">The Unicode Standard</span></span>](https://www.unicode.org/standard/standard.html)
- [<span data-ttu-id="f389b-217">Кодирование. кодовая страница</span><span class="sxs-lookup"><span data-stu-id="f389b-217">Encoding.CodePage</span></span>](/dotnet/api/system.text.encoding.codepage)
- [<span data-ttu-id="f389b-218">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="f389b-218">UTF-16LE</span></span>](https://wikipedia.org/wiki/UTF-16)
- [<span data-ttu-id="f389b-219">Метка порядка байтов</span><span class="sxs-lookup"><span data-stu-id="f389b-219">Byte order mark</span></span>](https://wikipedia.org/wiki/Byte_order_mark)
- [<span data-ttu-id="f389b-220">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="f389b-220">about_Preference_Variables</span></span>](about_Preference_Variables.md)
