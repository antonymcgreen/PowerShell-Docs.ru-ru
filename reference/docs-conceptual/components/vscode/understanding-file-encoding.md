---
title: Основные сведения о кодировке файлов в VSCode и PowerShell
description: Настройка кодировки в VSCode и PowerShell
ms.date: 02/28/2019
ms.openlocfilehash: f3b133b4bee7688821a5960429e2f26b69b01e12
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251480"
---
# <a name="understanding-file-encoding-in-vscode-and-powershell"></a><span data-ttu-id="5663b-103">Основные сведения о кодировке файлов в VSCode и PowerShell</span><span class="sxs-lookup"><span data-stu-id="5663b-103">Understanding file encoding in VSCode and PowerShell</span></span>

<span data-ttu-id="5663b-104">При использовании Visual STUDIO Code для создания и редактирования сценариев PowerShell, очень важно, что ваши файлы сохраняются в формате кодирования верного символа.</span><span class="sxs-lookup"><span data-stu-id="5663b-104">When using VS Code to create and edit PowerShell scripts, it is important that your files are saved using the correct character encoding format.</span></span>

## <a name="what-is-file-encoding-and-why-is-it-important"></a><span data-ttu-id="5663b-105">Что такое кодирование и почему важно?</span><span class="sxs-lookup"><span data-stu-id="5663b-105">What is file encoding and why is it important?</span></span>

<span data-ttu-id="5663b-106">VSCode управляет интерфейсом между человека ввода строки символов в буфер и чтения/записи блоки байтов в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="5663b-106">VSCode manages the interface between a human entering strings of characters into a buffer and reading/writing blocks of bytes to the filesystem.</span></span> <span data-ttu-id="5663b-107">Когда файл сохраняется в VSCode, в нем кодировки для этого текста.</span><span class="sxs-lookup"><span data-stu-id="5663b-107">When VSCode saves a file, it uses a text encoding to do this.</span></span>

<span data-ttu-id="5663b-108">Аналогичным образом при PowerShell запускает сценарий, его необходимо преобразовать байтов в файле символов для восстановления файла в программу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5663b-108">Similarly, when PowerShell runs a script it must convert the bytes in a file to characters to reconstruct the file into a PowerShell program.</span></span> <span data-ttu-id="5663b-109">Поскольку VSCode записывает файл, а PowerShell считывает файл, им необходимо использовать ту же систему кодировки.</span><span class="sxs-lookup"><span data-stu-id="5663b-109">Since VSCode writes the file and PowerShell reads the file, they need to use the same encoding system.</span></span> <span data-ttu-id="5663b-110">Идет процесс синтаксический анализ скрипта PowerShell: *байт* -> *символов* -> *маркеры*  ->   *дерево абстрактного синтаксиса* -> *выполнения*.</span><span class="sxs-lookup"><span data-stu-id="5663b-110">This process of parsing a PowerShell script goes: *bytes* -> *characters* -> *tokens* -> *abstract syntax tree* -> *execution*.</span></span>

<span data-ttu-id="5663b-111">VSCode и PowerShell устанавливаются с конфигурацией кодировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5663b-111">Both VSCode and PowerShell are installed with a sensible default encoding configuration.</span></span> <span data-ttu-id="5663b-112">Тем не менее кодировка по умолчанию, используемые PowerShell был изменен с выпуском PowerShell Core (версии 6.x).</span><span class="sxs-lookup"><span data-stu-id="5663b-112">However, the default encoding used by PowerShell has changed with the release of PowerShell Core (v6.x).</span></span> <span data-ttu-id="5663b-113">Чтобы можно было без проблем, с помощью PowerShell или расширения PowerShell в VSCode, необходимо настроить параметры VSCode и PowerShell должным образом.</span><span class="sxs-lookup"><span data-stu-id="5663b-113">To ensure you have no problems using PowerShell or the PowerShell extension in VSCode, you need to configure your VSCode and PowerShell settings properly.</span></span>

## <a name="common-causes-of-encoding-issues"></a><span data-ttu-id="5663b-114">Распространенные причины проблемы кодирования</span><span class="sxs-lookup"><span data-stu-id="5663b-114">Common causes of encoding issues</span></span>

<span data-ttu-id="5663b-115">Кодировки проблемы возникают, если кодировка VSCode или свой файл сценария не совпадает с ожидаемая кодировка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5663b-115">Encoding problems occur when the encoding of VSCode or your script file does not match the expected encoding of PowerShell.</span></span> <span data-ttu-id="5663b-116">Нет способа для PowerShell, чтобы автоматически определить кодировку файла.</span><span class="sxs-lookup"><span data-stu-id="5663b-116">There is no way for PowerShell to automatically determine the file encoding.</span></span>

<span data-ttu-id="5663b-117">Вы скорее кодирования проблемы при использовании символов не в [7-разрядной кодировке ASCII](https://ascii.cl/).</span><span class="sxs-lookup"><span data-stu-id="5663b-117">You're more likely to have encoding problems when you're using characters not in the [7-bit ASCII character set](https://ascii.cl/).</span></span> <span data-ttu-id="5663b-118">Например:</span><span class="sxs-lookup"><span data-stu-id="5663b-118">For example:</span></span>

- <span data-ttu-id="5663b-119">Надстрочными знаками латинские символы (`É`, `ü`)</span><span class="sxs-lookup"><span data-stu-id="5663b-119">Accented latin characters (`É`, `ü`)</span></span>
- <span data-ttu-id="5663b-120">Азиатского знаки, такие как кириллица (`Д`, `Ц`)</span><span class="sxs-lookup"><span data-stu-id="5663b-120">Non-latin characters like Cyrillic (`Д`, `Ц`)</span></span>
- <span data-ttu-id="5663b-121">Китайский хан (`脚`, `本`)</span><span class="sxs-lookup"><span data-stu-id="5663b-121">Han Chinese (`脚`, `本`)</span></span>

<span data-ttu-id="5663b-122">Представлены распространенные причины проблем кодирования:</span><span class="sxs-lookup"><span data-stu-id="5663b-122">Common reasons for encoding issues are:</span></span>

- <span data-ttu-id="5663b-123">Настройки по умолчанию не были изменены кодировок VSCode и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5663b-123">The encodings of VSCode and PowerShell have not been changed from their defaults.</span></span> <span data-ttu-id="5663b-124">В PowerShell 5.1 и ниже, значение по умолчанию кодировка отличается от в VSCode.</span><span class="sxs-lookup"><span data-stu-id="5663b-124">For PowerShell 5.1 and below, the default encoding is different from VSCode's.</span></span>
- <span data-ttu-id="5663b-125">Другой редактор открытых и перезаписать файл в новая кодировка.</span><span class="sxs-lookup"><span data-stu-id="5663b-125">Another editor has opened and overwritten the file in a new encoding.</span></span> <span data-ttu-id="5663b-126">Это часто происходит на интегрированную среду Сценариев.</span><span class="sxs-lookup"><span data-stu-id="5663b-126">This often happens with the ISE.</span></span>
- <span data-ttu-id="5663b-127">Файл возвращается в систему управления версиями в кодировке, отличный от какие VSCode или PowerShell ожидает.</span><span class="sxs-lookup"><span data-stu-id="5663b-127">The file is checked into source control in an encoding that is different from what VSCode or PowerShell expects.</span></span> <span data-ttu-id="5663b-128">Это может произойти, когда участники совместной работы использовать редакторы с различными конфигурациями кодирования.</span><span class="sxs-lookup"><span data-stu-id="5663b-128">This can happen when collaborators use editors with different encoding configurations.</span></span>

### <a name="how-to-tell-when-you-have-encoding-issues"></a><span data-ttu-id="5663b-129">Инструкции по определению, при наличии проблемы кодирования</span><span class="sxs-lookup"><span data-stu-id="5663b-129">How to tell when you have encoding issues</span></span>

<span data-ttu-id="5663b-130">Часто кодирования ошибки представляют как ошибки в скриптах синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="5663b-130">Often encoding errors present themselves as parse errors in scripts.</span></span> <span data-ttu-id="5663b-131">Если вы нашли последовательности странное символов в скрипте, это может быть проблема.</span><span class="sxs-lookup"><span data-stu-id="5663b-131">If you find strange character sequences in your script, this can be the problem.</span></span> <span data-ttu-id="5663b-132">В примере ниже, тире (`–`) отображается в виде символов `â€“`:</span><span class="sxs-lookup"><span data-stu-id="5663b-132">In the example below, an en-dash (`–`) appears as the characters `â€“`:</span></span>

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â€“From $from â€“To $recipient1 â€“Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

<span data-ttu-id="5663b-133">Эта проблема возникает, так как VSCode кодирует и символ `–` в UTF-8 в качестве байты `0xE2 0x80 0x93`.</span><span class="sxs-lookup"><span data-stu-id="5663b-133">This problem occurs because VSCode encodes the character `–` in UTF-8 as the bytes `0xE2 0x80 0x93`.</span></span>
<span data-ttu-id="5663b-134">Если эти байты декодируются как Windows-1252, они интерпретируются как символы `â€“`.</span><span class="sxs-lookup"><span data-stu-id="5663b-134">When these bytes are decoded as Windows-1252, they are interpreted as the characters `â€“`.</span></span>

<span data-ttu-id="5663b-135">Некоторые последовательности странное символов, которые можно встретить включают:</span><span class="sxs-lookup"><span data-stu-id="5663b-135">Some strange character sequences that you might see include:</span></span>

- <span data-ttu-id="5663b-136">`â€“` вместо `–`;</span><span class="sxs-lookup"><span data-stu-id="5663b-136">`â€“` instead of `–`</span></span>
- <span data-ttu-id="5663b-137">`â€”` вместо `—`;</span><span class="sxs-lookup"><span data-stu-id="5663b-137">`â€”` instead of `—`</span></span>
- <span data-ttu-id="5663b-138">`Ã„2` вместо `Ä`;</span><span class="sxs-lookup"><span data-stu-id="5663b-138">`Ã„2` instead of `Ä`</span></span>
- <span data-ttu-id="5663b-139">`Â` вместо ` ` (неразрывный пробел);</span><span class="sxs-lookup"><span data-stu-id="5663b-139">`Â` instead of ` `  (a non-breaking space)</span></span>
- <span data-ttu-id="5663b-140">`Ã©` вместо `é`.</span><span class="sxs-lookup"><span data-stu-id="5663b-140">`Ã©` instead of `é`</span></span>

<span data-ttu-id="5663b-141">Этот удобный [ссылку](https://www.i18nqa.com/debug/utf8-debug.html) перечислены распространенные шаблоны, которые указывают на проблему кодировки UTF-8/Windows-1252.</span><span class="sxs-lookup"><span data-stu-id="5663b-141">This handy [reference](https://www.i18nqa.com/debug/utf8-debug.html) lists the common patterns that indicate a UTF-8/Windows-1252 encoding problem.</span></span>

## <a name="how-the-powershell-extension-in-vscode-interacts-with-encodings"></a><span data-ttu-id="5663b-142">Взаимодействие с кодировками расширения PowerShell в VSCode</span><span class="sxs-lookup"><span data-stu-id="5663b-142">How the PowerShell extension in VSCode interacts with encodings</span></span>

<span data-ttu-id="5663b-143">Расширения PowerShell взаимодействует со сценариями в несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="5663b-143">The PowerShell extension interacts with scripts in a number of ways:</span></span>

1. <span data-ttu-id="5663b-144">При изменении скриптов в VSCode, содержимое отправляются VSCode для расширения.</span><span class="sxs-lookup"><span data-stu-id="5663b-144">When scripts are edited in VSCode, the contents are sent by VSCode to the extension.</span></span> <span data-ttu-id="5663b-145">[Протокол языкового сервера][] требует, что это содержимое передается в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5663b-145">The [Language Server Protocol][] mandates that this content is transferred in UTF-8.</span></span> <span data-ttu-id="5663b-146">Таким образом он не поддерживается для расширения для получения неправильная кодировка.</span><span class="sxs-lookup"><span data-stu-id="5663b-146">Therefore, it is not possible for the extension to get the wrong encoding.</span></span>
2. <span data-ttu-id="5663b-147">При выполнении скрипта непосредственно в интегрированной консоли, они все считываемые из файла PowerShell непосредственно.</span><span class="sxs-lookup"><span data-stu-id="5663b-147">When scripts are executed directly in the Integrated Console, they're read from the file by PowerShell directly.</span></span> <span data-ttu-id="5663b-148">Кодирование tf PowerShell отличается от его VSCode, что-нибудь может пойти не так здесь.</span><span class="sxs-lookup"><span data-stu-id="5663b-148">Tf PowerShell's encoding differs from VSCode's, something can go wrong here.</span></span>
3. <span data-ttu-id="5663b-149">Когда скрипт, который открыт в VSCode ссылается на другой сценарий, который не был открыт в VSCode, расширение возвращается к загрузке содержимого этого скрипта из файловой системы.</span><span class="sxs-lookup"><span data-stu-id="5663b-149">When a script that is open in VSCode references another script that is not open in VSCode, the extension falls back to loading that script's content from the file system.</span></span> <span data-ttu-id="5663b-150">Расширения PowerShell по умолчанию используется кодировка UTF-8, но использует [метка порядка следования байтов][], или Спецификации, обнаружения, чтобы выбрать правильную кодировку.</span><span class="sxs-lookup"><span data-stu-id="5663b-150">The PowerShell extension defaults to UTF-8 encoding, but uses [byte-order mark][], or BOM, detection to select the correct encoding.</span></span>

<span data-ttu-id="5663b-151">Проблема возникает, когда при условии, что кодировка менее Спецификации форматов (таких как [UTF-8][] без метки следования байтов и [Windows-1252][]).</span><span class="sxs-lookup"><span data-stu-id="5663b-151">The problem occurs when assuming the encoding of BOM-less formats (like [UTF-8][] with no BOM and [Windows-1252][]).</span></span>
<span data-ttu-id="5663b-152">Расширения PowerShell по умолчанию используется UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5663b-152">The PowerShell extension defaults to UTF-8.</span></span> <span data-ttu-id="5663b-153">Расширение нельзя изменить параметры кодирования в VSCode.</span><span class="sxs-lookup"><span data-stu-id="5663b-153">The extension cannot change VSCode's encoding settings.</span></span>
<span data-ttu-id="5663b-154">Дополнительные сведения см. в разделе [выдавать #824](https://github.com/Microsoft/vscode/issues/824).</span><span class="sxs-lookup"><span data-stu-id="5663b-154">For more information, see [issue #824](https://github.com/Microsoft/vscode/issues/824).</span></span>

## <a name="choosing-the-right-encoding"></a><span data-ttu-id="5663b-155">Выборе правой кодировки</span><span class="sxs-lookup"><span data-stu-id="5663b-155">Choosing the right encoding</span></span>

<span data-ttu-id="5663b-156">Различные системы и приложения можно использовать различные кодировки:</span><span class="sxs-lookup"><span data-stu-id="5663b-156">Different systems and applications can use different encodings:</span></span>

- <span data-ttu-id="5663b-157">В .NET Standard в Интернете и в среде Linux теперь главный кодирования является UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5663b-157">In .NET Standard, on the web, and in the Linux world, UTF-8 is now the dominant encoding.</span></span>
- <span data-ttu-id="5663b-158">Во многих приложениях .NET Framework используется [UTF-16][].</span><span class="sxs-lookup"><span data-stu-id="5663b-158">Many .NET Framework applications use [UTF-16][].</span></span> <span data-ttu-id="5663b-159">По историческим причинам, это иногда называется «Unicode», что теперь термин относится к более широкие [стандартный](https://en.wikipedia.org/wiki/Unicode) UTF-8 и UTF-16.</span><span class="sxs-lookup"><span data-stu-id="5663b-159">For historical reasons, this is sometimes called "Unicode", a term that now refers to a broad [standard](https://en.wikipedia.org/wiki/Unicode) that includes both UTF-8 and UTF-16.</span></span>
- <span data-ttu-id="5663b-160">На Windows многие собственного приложения, которые предшествуют Юникода по-прежнему использовать Windows-1252, по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5663b-160">On Windows, many native applications that predate Unicode continue to use Windows-1252 by default.</span></span>

<span data-ttu-id="5663b-161">Кодировки Юникод есть концепция порядка следования байтов (BOM) пометить.</span><span class="sxs-lookup"><span data-stu-id="5663b-161">Unicode encodings also have the concept of a byte-order mark (BOM).</span></span> <span data-ttu-id="5663b-162">Спецификации находиться в начале текста, чтобы определить декодер, какая кодировка используется текст.</span><span class="sxs-lookup"><span data-stu-id="5663b-162">BOMs occur at the beginning of text to tell a decoder which encoding the text is using.</span></span> <span data-ttu-id="5663b-163">Для многобайтовых кодировок, также указывает Спецификации [порядка следования байтов](https://en.wikipedia.org/wiki/Endianness) кодировки.</span><span class="sxs-lookup"><span data-stu-id="5663b-163">For multi-byte encodings, the BOM also indicates [endianness](https://en.wikipedia.org/wiki/Endianness) of the encoding.</span></span> <span data-ttu-id="5663b-164">Спецификации предназначены для байтов, которые редко происходят в Юникод текста, позволяя обоснованные предположения, что текст является Юникода, если метка BOM присутствует.</span><span class="sxs-lookup"><span data-stu-id="5663b-164">BOMs are designed to be bytes that rarely occur in non-Unicode text, allowing a reasonable guess that text is Unicode when a BOM is present.</span></span>

<span data-ttu-id="5663b-165">Спецификации являются необязательными и их внедрения не же популярной в мире Linux, поскольку везде используется соглашение о надежной UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5663b-165">BOMs are optional and their adoption isn't as popular in the Linux world because a dependable convention of UTF-8 is used everywhere.</span></span> <span data-ttu-id="5663b-166">Большинство приложений Linux предположить, что текстовое поле кодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5663b-166">Most Linux applications presume that text input is encoded in UTF-8.</span></span> <span data-ttu-id="5663b-167">Хотя многие приложения Linux будет распознавать и правильно обрабатывать Спецификации, номер этого не сделать, что приводит к артефактов в тексте, управлять с помощью этих приложений.</span><span class="sxs-lookup"><span data-stu-id="5663b-167">While many Linux applications will recognize and correctly handle a BOM, a number do not, leading to artifacts in text manipulated with those applications.</span></span>

<span data-ttu-id="5663b-168">**Таким образом**:</span><span class="sxs-lookup"><span data-stu-id="5663b-168">**Therefore**:</span></span>

- <span data-ttu-id="5663b-169">Если вы работаете в основном с приложениями Windows и Windows PowerShell, вы предпочитаете, кодировки как UTF-8 с метки порядка БАЙТОВ или UTF-16.</span><span class="sxs-lookup"><span data-stu-id="5663b-169">If you work primarily with Windows applications and Windows PowerShell, you should prefer an encoding like UTF-8 with BOM or UTF-16.</span></span>
- <span data-ttu-id="5663b-170">Если вы работаете на платформах, следует отдавать предпочтение UTF-8 с метки порядка БАЙТОВ.</span><span class="sxs-lookup"><span data-stu-id="5663b-170">If you work across platforms, you should prefer UTF-8 with BOM.</span></span>
- <span data-ttu-id="5663b-171">Если вы работаете главным образом в контекстах, связанной с Linux, следует отдавать предпочтение UTF-8 без метки порядка БАЙТОВ.</span><span class="sxs-lookup"><span data-stu-id="5663b-171">If you work mainly in Linux-associated contexts, you should prefer UTF-8 without BOM.</span></span>
- <span data-ttu-id="5663b-172">Windows-1252 и дополнительная латиница-1, устаревших кодировок, по возможности следует избегать.</span><span class="sxs-lookup"><span data-stu-id="5663b-172">Windows-1252 and latin-1 are essentially legacy encodings that you should avoid if possible.</span></span>
  <span data-ttu-id="5663b-173">Тем не менее некоторые приложения предыдущих версий Windows зависит от их.</span><span class="sxs-lookup"><span data-stu-id="5663b-173">However, some older Windows applications may depend on them.</span></span>
- <span data-ttu-id="5663b-174">Также стоит отметить, что подпись сценариев [кодировка зависит от](https://github.com/PowerShell/PowerShell/issues/3466), то есть изменения кодировки на сценарий со знаком потребует повторного подписывания.</span><span class="sxs-lookup"><span data-stu-id="5663b-174">It's also worth noting that script signing is [encoding-dependent](https://github.com/PowerShell/PowerShell/issues/3466), meaning a change of encoding on a signed script will require resigning.</span></span>

## <a name="configuring-vscode"></a><span data-ttu-id="5663b-175">Настройка VSCode</span><span class="sxs-lookup"><span data-stu-id="5663b-175">Configuring VSCode</span></span>

<span data-ttu-id="5663b-176">В VSCode кодировка по умолчанию — UTF-8 без метки порядка БАЙТОВ.</span><span class="sxs-lookup"><span data-stu-id="5663b-176">VSCode's default encoding is UTF-8 without BOM.</span></span>

<span data-ttu-id="5663b-177">Чтобы задать [Кодирование в VSCode][], перейдите к параметрам VSCode (<kbd>Ctrl<kbd>+</kbd>,</kbd>) и задайте `"files.encoding"` параметр:</span><span class="sxs-lookup"><span data-stu-id="5663b-177">To set [VSCode's encoding][], go to the VSCode settings (<kbd>Ctrl<kbd>+</kbd>,</kbd>) and set the `"files.encoding"` setting:</span></span>

```json
"files.encoding": "utf8bom"
```

<span data-ttu-id="5663b-178">Ниже приведены некоторые возможные значения.</span><span class="sxs-lookup"><span data-stu-id="5663b-178">Some possible values are:</span></span>

- <span data-ttu-id="5663b-179">`utf8`: [UTF-8] без метки порядка БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="5663b-179">`utf8`: [UTF-8] without BOM</span></span>
- <span data-ttu-id="5663b-180">`utf8bom`: [UTF-8] с метки порядка БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="5663b-180">`utf8bom`: [UTF-8] with BOM</span></span>
- <span data-ttu-id="5663b-181">`utf16le`: Little endian [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="5663b-181">`utf16le`: Little endian [UTF-16]</span></span>
- <span data-ttu-id="5663b-182">`utf16be`: Big endian [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="5663b-182">`utf16be`: Big endian [UTF-16]</span></span>
- <span data-ttu-id="5663b-183">`windows1252`: [Windows-1252]</span><span class="sxs-lookup"><span data-stu-id="5663b-183">`windows1252`: [Windows-1252]</span></span>

<span data-ttu-id="5663b-184">Должен отобразиться раскрывающийся список для этого в представлении графического пользовательского интерфейса, или просмотреть завершений для него в JSON.</span><span class="sxs-lookup"><span data-stu-id="5663b-184">You should get a dropdown for this in the GUI view, or completions for it in the JSON view.</span></span>

<span data-ttu-id="5663b-185">Чтобы обеспечить автоматическое определение кодировки, если это возможно, можно также добавить следующие:</span><span class="sxs-lookup"><span data-stu-id="5663b-185">You can also add the following to autodetect encoding when possible:</span></span>

```json
"files.autoGuessEncoding": true
```

<span data-ttu-id="5663b-186">Если вы не хотите эти параметры влияют на все типы файлов, VSCode также позволяет конфигурации каждого языка.</span><span class="sxs-lookup"><span data-stu-id="5663b-186">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="5663b-187">Создание параметра конкретного языка, поместив параметры `[<language-name>]` поля.</span><span class="sxs-lookup"><span data-stu-id="5663b-187">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="5663b-188">Например:</span><span class="sxs-lookup"><span data-stu-id="5663b-188">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

## <a name="configuring-powershell"></a><span data-ttu-id="5663b-189">Настройка PowerShell</span><span class="sxs-lookup"><span data-stu-id="5663b-189">Configuring PowerShell</span></span>

<span data-ttu-id="5663b-190">PowerShell кодировка по умолчанию зависит от версии:</span><span class="sxs-lookup"><span data-stu-id="5663b-190">PowerShell's default encoding varies depending on version:</span></span>

- <span data-ttu-id="5663b-191">В PowerShell 6 + кодировку по умолчанию — UTF-8 без метки порядка БАЙТОВ на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="5663b-191">In PowerShell 6+, the default encoding is UTF-8 without BOM on all platforms.</span></span>
- <span data-ttu-id="5663b-192">В Windows PowerShell, кодировка по умолчанию обычно является Windows-1252, расширение [Латиница 1][], которая также называется ISO 8859-1.</span><span class="sxs-lookup"><span data-stu-id="5663b-192">In Windows PowerShell, the default encoding is usually Windows-1252, an extension of [latin-1][], also known as ISO 8859-1.</span></span>

<span data-ttu-id="5663b-193">В PowerShell 5 + можно найти кодирования по умолчанию с этим:</span><span class="sxs-lookup"><span data-stu-id="5663b-193">In PowerShell 5+ you can find your default encoding with this:</span></span>

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

<span data-ttu-id="5663b-194">Следующие [скрипт](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) может использоваться для определения того, что кодирование сеанс PowerShell выводит для сценарий без метки порядка БАЙТОВ.</span><span class="sxs-lookup"><span data-stu-id="5663b-194">The following [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) can be used to determine what encoding your PowerShell session infers for a script without a BOM.</span></span>

```powershell
$badBytes = [byte[]]@(0xC3, 0x80)
$utf8Str = [System.Text.Encoding]::UTF8.GetString($badBytes)
$bytes = [System.Text.Encoding]::ASCII.GetBytes('Write-Output "') + [byte[]]@(0xC3, 0x80) + [byte[]]@(0x22)
$path = Join-Path ([System.IO.Path]::GetTempPath()) 'encodingtest.ps1'

try
{
    [System.IO.File]::WriteAllBytes($path, $bytes)

    switch (& $path)
    {
        $utf8Str
        {
            return 'UTF-8'
            break
        }

        default
        {
            return 'Windows-1252'
            break
        }
    }
}
finally
{
    Remove-Item $path
}
```

<span data-ttu-id="5663b-195">Это можно настроить PowerShell для использования в заданной кодировке более обычно с помощью параметров профиля.</span><span class="sxs-lookup"><span data-stu-id="5663b-195">It's possible to configure PowerShell to use a given encoding more generally using profile settings.</span></span> <span data-ttu-id="5663b-196">См. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="5663b-196">See the following articles:</span></span>

- <span data-ttu-id="5663b-197">[@mklement0]в [ответов о кодировании PowerShell на сайте StackOverflow](https://stackoverflow.com/a/40098904).</span><span class="sxs-lookup"><span data-stu-id="5663b-197">[@mklement0]'s [answer about PowerShell encoding on StackOverflow](https://stackoverflow.com/a/40098904).</span></span>
- <span data-ttu-id="5663b-198">[@rkeithhill]в [записи блога об обработке входных данных менее метки порядка БАЙТОВ UTF-8 в PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span><span class="sxs-lookup"><span data-stu-id="5663b-198">[@rkeithhill]'s [blog post about dealing with BOM-less UTF-8 input in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span></span>

<span data-ttu-id="5663b-199">Не поддерживается для принудительного PowerShell, чтобы использовать конкретную кодировку ввода.</span><span class="sxs-lookup"><span data-stu-id="5663b-199">It's not possible to force PowerShell to use a specific input encoding.</span></span> <span data-ttu-id="5663b-200">PowerShell 5.1 и более ранних версий по умолчанию для Windows-1252, кодировку, если присутствует BOM.</span><span class="sxs-lookup"><span data-stu-id="5663b-200">PowerShell 5.1 and below default to Windows-1252 encoding when there's no BOM.</span></span> <span data-ttu-id="5663b-201">По причинам совместимости лучше сохранить скрипты в формате Юникод с метки порядка БАЙТОВ.</span><span class="sxs-lookup"><span data-stu-id="5663b-201">For interoperability reasons, it's best to save scripts in a Unicode format with a BOM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5663b-202">Любые другие инструменты у вас есть что сенсорный PowerShell скриптов может зависеть от выбранных параметров кодирования или преобразовывать скрипты в другой кодировке.</span><span class="sxs-lookup"><span data-stu-id="5663b-202">Any other tools you have that touch PowerShell scripts may be affected by your encoding choices or re-encode your scripts to another encoding.</span></span>

### <a name="existing-scripts"></a><span data-ttu-id="5663b-203">Существующие сценарии</span><span class="sxs-lookup"><span data-stu-id="5663b-203">Existing scripts</span></span>

<span data-ttu-id="5663b-204">Скрипты, которые уже находятся в файловой системе может потребоваться повторно кодироваться ваш новый указанную кодировку.</span><span class="sxs-lookup"><span data-stu-id="5663b-204">Scripts already on the file system may need to be re-encoded to your new chosen encoding.</span></span> <span data-ttu-id="5663b-205">В нижней строке из VSCode вы увидите метки UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5663b-205">In the bottom bar of VSCode, you'll see the label UTF-8.</span></span> <span data-ttu-id="5663b-206">Щелкните его, чтобы открыть панели действий и выберите **сохранить с кодировкой**.</span><span class="sxs-lookup"><span data-stu-id="5663b-206">Click it to open the action bar and select **Save with encoding**.</span></span> <span data-ttu-id="5663b-207">Теперь вы можете выбрать новая кодировка для этого файла.</span><span class="sxs-lookup"><span data-stu-id="5663b-207">You can now pick a new encoding for that file.</span></span> <span data-ttu-id="5663b-208">См. в разделе [Кодирование в VSCode][] подробные инструкции.</span><span class="sxs-lookup"><span data-stu-id="5663b-208">See [VSCode's encoding][] for full instructions.</span></span>

<span data-ttu-id="5663b-209">Если вам нужно повторно закодировать несколько файлов, можно использовать следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="5663b-209">If you need to re-encode multiple files, you can use the following script:</span></span>

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="5663b-210">Интегрированная среда сценариев (ISE) PowerShell</span><span class="sxs-lookup"><span data-stu-id="5663b-210">The PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="5663b-211">При редактировании скриптов с помощью интегрированной среды Сценариев PowerShell, необходимо синхронизировать ваш кодирования параметров.</span><span class="sxs-lookup"><span data-stu-id="5663b-211">If you also edit scripts using the PowerShell ISE, you need to synchronize your encoding settings there.</span></span>

<span data-ttu-id="5663b-212">Интегрированная среда Сценариев следует принять метки порядка БАЙТОВ, но это также можно использовать отражение для [выберите кодировку](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span><span class="sxs-lookup"><span data-stu-id="5663b-212">The ISE should honor a BOM, but it's also possible to use reflection to [set the encoding](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span></span>
<span data-ttu-id="5663b-213">Обратите внимание на то, что это не сохраняется между начинающих компаний.</span><span class="sxs-lookup"><span data-stu-id="5663b-213">Note that this wouldn't be persisted between startups.</span></span>

### <a name="source-control-software"></a><span data-ttu-id="5663b-214">Программное обеспечение управления версиями</span><span class="sxs-lookup"><span data-stu-id="5663b-214">Source control software</span></span>

<span data-ttu-id="5663b-215">Некоторые инструментов системы управления версиями, например git, игнорировать кодировки; git отслеживает только байты.</span><span class="sxs-lookup"><span data-stu-id="5663b-215">Some source control tools, such as git, ignore encodings; git just tracks the bytes.</span></span>
<span data-ttu-id="5663b-216">Другие, например TFS или Mercurial, может отличаться.</span><span class="sxs-lookup"><span data-stu-id="5663b-216">Others, like TFS or Mercurial, may not.</span></span> <span data-ttu-id="5663b-217">Даже некоторые средства, основанных на git, зависят от того, декодирование текста.</span><span class="sxs-lookup"><span data-stu-id="5663b-217">Even some git-based tools rely on decoding text.</span></span>

<span data-ttu-id="5663b-218">Если это так, убедитесь, что вы:</span><span class="sxs-lookup"><span data-stu-id="5663b-218">When this is the case, make sure you:</span></span>

- <span data-ttu-id="5663b-219">Настройка кодировки в системе управления версиями в соответствии с вашей конфигурации VSCode текста.</span><span class="sxs-lookup"><span data-stu-id="5663b-219">Configure the text encoding in your source control to match your VSCode configuration.</span></span>
- <span data-ttu-id="5663b-220">Убедитесь, что все файлы проверяются в систему управления версиями в соответствующей кодировки.</span><span class="sxs-lookup"><span data-stu-id="5663b-220">Ensure all your files are checked into source control in the relevant encoding.</span></span>
- <span data-ttu-id="5663b-221">Будьте осторожны при изменениях в кодировку, полученные через систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5663b-221">Be wary of changes to the encoding received through source control.</span></span> <span data-ttu-id="5663b-222">Ключа признаком этого является diff, указывает, что изменения, но где ничего были изменены (так как имеют байт, но не иметь символов).</span><span class="sxs-lookup"><span data-stu-id="5663b-222">A key sign of this is a diff indicating changes but where nothing seems to have changed (because bytes have but characters have not).</span></span>

### <a name="collaborators-environments"></a><span data-ttu-id="5663b-223">Средах других участников</span><span class="sxs-lookup"><span data-stu-id="5663b-223">Collaborators' environments</span></span>

<span data-ttu-id="5663b-224">На основе Настройка системы управления версиями, убедитесь, что других участников на все файлы, которые вы предоставляете общий доступ не имеют параметры, которые переопределяют кодирования путем повторного кодирования файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5663b-224">On top of configuring source control, ensure that your collaborators on any files you share don't have settings that override your encoding by re-encoding PowerShell files.</span></span>

### <a name="other-programs"></a><span data-ttu-id="5663b-225">Другие программы</span><span class="sxs-lookup"><span data-stu-id="5663b-225">Other programs</span></span>

<span data-ttu-id="5663b-226">Все другие программы, считывает или записывает сценарий PowerShell может повторно кодировать его.</span><span class="sxs-lookup"><span data-stu-id="5663b-226">Any other program that reads or writes a PowerShell script may re-encode it.</span></span>

<span data-ttu-id="5663b-227">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="5663b-227">Some examples are:</span></span>

- <span data-ttu-id="5663b-228">Использование буфера обмена для копирования и вставки сценария.</span><span class="sxs-lookup"><span data-stu-id="5663b-228">Using the clipboard to copy and paste a script.</span></span> <span data-ttu-id="5663b-229">Такое часто встречается в сценариях, например:</span><span class="sxs-lookup"><span data-stu-id="5663b-229">This is common in scenarios like:</span></span>
  - <span data-ttu-id="5663b-230">Копирование скрипта в виртуальную Машину</span><span class="sxs-lookup"><span data-stu-id="5663b-230">Copying a script into a VM</span></span>
  - <span data-ttu-id="5663b-231">Скопировав сценарий из электронной почты или веб-страницы</span><span class="sxs-lookup"><span data-stu-id="5663b-231">Copying a script out of an email or webpage</span></span>
  - <span data-ttu-id="5663b-232">Копирование скрипта в или из документа Microsoft Word или PowerPoint</span><span class="sxs-lookup"><span data-stu-id="5663b-232">Copying a script into or out of a Microsoft Word or PowerPoint document</span></span>
- <span data-ttu-id="5663b-233">Других текстовых редакторов, таких как:</span><span class="sxs-lookup"><span data-stu-id="5663b-233">Other text editors, such as:</span></span>
  - <span data-ttu-id="5663b-234">Блокнот</span><span class="sxs-lookup"><span data-stu-id="5663b-234">Notepad</span></span>
  - <span data-ttu-id="5663b-235">VIM</span><span class="sxs-lookup"><span data-stu-id="5663b-235">vim</span></span>
  - <span data-ttu-id="5663b-236">Любой редактор скриптов PowerShell</span><span class="sxs-lookup"><span data-stu-id="5663b-236">Any other PowerShell script editor</span></span>
- <span data-ttu-id="5663b-237">Текст, редактирование служебные программы, например:</span><span class="sxs-lookup"><span data-stu-id="5663b-237">Text editing utilities, like:</span></span>
  - `Get-Content`/`Set-Content`/`Out-File`
  - <span data-ttu-id="5663b-238">Операторы перенаправления PowerShell, такие как `>` и `>>`</span><span class="sxs-lookup"><span data-stu-id="5663b-238">PowerShell redirection operators like `>` and `>>`</span></span>
  - `sed`/`awk`
- <span data-ttu-id="5663b-239">Файл программы передачи, таких как:</span><span class="sxs-lookup"><span data-stu-id="5663b-239">File transfer programs, like:</span></span>
  - <span data-ttu-id="5663b-240">Веб-браузер, при загрузке сценариев</span><span class="sxs-lookup"><span data-stu-id="5663b-240">A web browser, when downloading scripts</span></span>
  - <span data-ttu-id="5663b-241">Общей папки</span><span class="sxs-lookup"><span data-stu-id="5663b-241">A file share</span></span>

<span data-ttu-id="5663b-242">Некоторые из этих средств работать в байтах, а не текст, но другие предлагают кодирования конфигураций.</span><span class="sxs-lookup"><span data-stu-id="5663b-242">Some of these tools deal in bytes rather than text, but others offer encoding configurations.</span></span> <span data-ttu-id="5663b-243">В таких случаях, когда необходимо настроить кодировки необходимо сделать его так же, как ваш редактор, кодирование, чтобы предотвратить возникновение проблем.</span><span class="sxs-lookup"><span data-stu-id="5663b-243">In those cases where you need to configure an encoding, you need to make it the same as your editor encoding to prevent problems.</span></span>

## <a name="other-resources-on-encoding-in-powershell"></a><span data-ttu-id="5663b-244">Другие ресурсы о кодировании в PowerShell</span><span class="sxs-lookup"><span data-stu-id="5663b-244">Other resources on encoding in PowerShell</span></span>

<span data-ttu-id="5663b-245">Существует несколько других неплохо сообщений на кодировании и настройка кодирование в PowerShell, обязательно прочитайте:</span><span class="sxs-lookup"><span data-stu-id="5663b-245">There are a few other nice posts on encoding and configuring encoding in PowerShell that are worth a read:</span></span>

- <span data-ttu-id="5663b-246">[@mklement0]в [Сводка шифрования PowerShell на сайте StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span><span class="sxs-lookup"><span data-stu-id="5663b-246">[@mklement0]'s [summary of PowerShell encoding on StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span></span>
- <span data-ttu-id="5663b-247">Предыдущие выпуски, открытый в vscode с помощью PowerShell для кодирования проблемы:</span><span class="sxs-lookup"><span data-stu-id="5663b-247">Previous issues opened on vscode-PowerShell for encoding problems:</span></span>
  - [<span data-ttu-id="5663b-248">#1308</span><span class="sxs-lookup"><span data-stu-id="5663b-248">#1308</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1308)
  - [<span data-ttu-id="5663b-249">#1628</span><span class="sxs-lookup"><span data-stu-id="5663b-249">#1628</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1628)
  - [<span data-ttu-id="5663b-250">#1680</span><span class="sxs-lookup"><span data-stu-id="5663b-250">#1680</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1680)
  - [<span data-ttu-id="5663b-251">#1744</span><span class="sxs-lookup"><span data-stu-id="5663b-251">#1744</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1744)
  - [<span data-ttu-id="5663b-252">#1751</span><span class="sxs-lookup"><span data-stu-id="5663b-252">#1751</span></span>](https://github.com/PowerShell/vscode-powershell/issues/1751)
- [<span data-ttu-id="5663b-253">Классической *Joel on Software* пишу Юникода</span><span class="sxs-lookup"><span data-stu-id="5663b-253">The classic *Joel on Software* write up about Unicode</span></span>](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [<span data-ttu-id="5663b-254">Кодировки в .NET Standard</span><span class="sxs-lookup"><span data-stu-id="5663b-254">Encoding in .NET Standard</span></span>](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)


[@mklement0]: https://github.com/mklement0
[@rkeithhill]: https://github.com/rkeithhill
[Windows-1252]: https://wikipedia.org/wiki/Windows-1252
[Латиница 1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[latin-1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[UTF-8]: https://wikipedia.org/wiki/UTF-8
[Метка порядка следования байтов]: https://wikipedia.org/wiki/Byte_order_mark
[byte-order mark]: https://wikipedia.org/wiki/Byte_order_mark
[UTF-16]: https://wikipedia.org/wiki/UTF-16
[Протокол языкового сервера]: https://microsoft.github.io/language-server-protocol/
[Language Server Protocol]: https://microsoft.github.io/language-server-protocol/
[Кодирование в VSCode]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[VSCode's encoding]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support