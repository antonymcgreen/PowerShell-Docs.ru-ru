---
title: Основные сведения о кодировке файлов в VS Code и PowerShell
description: Настройка кодировки файлов в VS Code и PowerShell
ms.date: 02/28/2019
ms.openlocfilehash: 1333c5aedd5abd16078ac32979f19f38818a26c8
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809900"
---
# <a name="understanding-file-encoding-in-vs-code-and-powershell"></a><span data-ttu-id="9918a-103">Основные сведения о кодировке файлов в VS Code и PowerShell</span><span class="sxs-lookup"><span data-stu-id="9918a-103">Understanding file encoding in VS Code and PowerShell</span></span>

<span data-ttu-id="9918a-104">При использовании VS Code для создания и редактирования сценариев PowerShell очень важно, чтобы ваши файлы сохранялись в правильной кодировке символов.</span><span class="sxs-lookup"><span data-stu-id="9918a-104">When using VS Code to create and edit PowerShell scripts, it is important that your files are saved using the correct character encoding format.</span></span>

## <a name="what-is-file-encoding-and-why-is-it-important"></a><span data-ttu-id="9918a-105">Что такое кодировка и почему она важна?</span><span class="sxs-lookup"><span data-stu-id="9918a-105">What is file encoding and why is it important?</span></span>

<span data-ttu-id="9918a-106">VS Code управляет интерфейсом ввода строки символов в буфер пользователем и чтения-записи блоков байтов в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="9918a-106">VS Code manages the interface between a human entering strings of characters into a buffer and reading/writing blocks of bytes to the filesystem.</span></span> <span data-ttu-id="9918a-107">При сохранении файла в VS Code используется кодирование текста для определения того, какие байты получит каждый символ.</span><span class="sxs-lookup"><span data-stu-id="9918a-107">When VS Code saves a file, it uses a text encoding to decide what bytes each character becomes.</span></span>

<span data-ttu-id="9918a-108">Аналогичным образом, когда оболочка PowerShell запускает скрипт, ей необходимо преобразовать байты из файла в символы для преобразования файла в программу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9918a-108">Similarly, when PowerShell runs a script it must convert the bytes in a file to characters to reconstruct the file into a PowerShell program.</span></span> <span data-ttu-id="9918a-109">Так как VS Code записывает файл, а PowerShell считывает файл, этим средствам необходимо использовать одну и ту же систему кодировки.</span><span class="sxs-lookup"><span data-stu-id="9918a-109">Since VS Code writes the file and PowerShell reads the file, they need to use the same encoding system.</span></span> <span data-ttu-id="9918a-110">Этот процесс синтаксического анализа скрипта PowerShell идет так: *байты* -> *символы* -> *лексемы* ->  *дерево абстрактного синтаксиса* -> *выполнение*.</span><span class="sxs-lookup"><span data-stu-id="9918a-110">This process of parsing a PowerShell script goes: *bytes* -> *characters* -> *tokens* -> *abstract syntax tree* -> *execution*.</span></span>

<span data-ttu-id="9918a-111">И VS Code, и PowerShell устанавливаются с подходящей конфигурацией кодировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9918a-111">Both VS Code and PowerShell are installed with a sensible default encoding configuration.</span></span> <span data-ttu-id="9918a-112">Тем не менее кодировка по умолчанию, используемая PowerShell, была изменена с выпуском PowerShell Core (версии 6.x).</span><span class="sxs-lookup"><span data-stu-id="9918a-112">However, the default encoding used by PowerShell has changed with the release of PowerShell Core (v6.x).</span></span> <span data-ttu-id="9918a-113">Чтобы избежать проблем с PowerShell и расширениями PowerShell в VS Code, необходимо настроить параметры VS Code и PowerShell должным образом.</span><span class="sxs-lookup"><span data-stu-id="9918a-113">To ensure you have no problems using PowerShell or the PowerShell extension in VS Code, you need to configure your VS Code and PowerShell settings properly.</span></span>

## <a name="common-causes-of-encoding-issues"></a><span data-ttu-id="9918a-114">Распространенные причины проблемы с кодировкой</span><span class="sxs-lookup"><span data-stu-id="9918a-114">Common causes of encoding issues</span></span>

<span data-ttu-id="9918a-115">Проблемы с кодировкой возникают, если кодировка VS Code в целом или вашего файла скрипта не совпадает с кодировкой, ожидаемой в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9918a-115">Encoding problems occur when the encoding of VS Code or your script file does not match the expected encoding of PowerShell.</span></span> <span data-ttu-id="9918a-116">В PowerShell нет способа автоматически определить кодировку файла.</span><span class="sxs-lookup"><span data-stu-id="9918a-116">There is no way for PowerShell to automatically determine the file encoding.</span></span>

<span data-ttu-id="9918a-117">Проблемы с кодировкой более вероятны при использовании символов не из [7-разрядной кодировки ASCII](https://ascii.cl/).</span><span class="sxs-lookup"><span data-stu-id="9918a-117">You're more likely to have encoding problems when you're using characters not in the [7-bit ASCII character set](https://ascii.cl/).</span></span> <span data-ttu-id="9918a-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="9918a-118">For example:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="9918a-119">Расширенные небуквенные символы, такие как длинное тире (`—`), неразрывный пробел (` `) или левая двойная кавычка (`"`).</span><span class="sxs-lookup"><span data-stu-id="9918a-119">Extended non-letter characters like em-dash (`—`), non-breaking space (` `) or left double quotation mark (`"`)</span></span>
- <span data-ttu-id="9918a-120">Латинские символы с диакритикой (`É`, `ü`)</span><span class="sxs-lookup"><span data-stu-id="9918a-120">Accented latin characters (`É`, `ü`)</span></span>
- <span data-ttu-id="9918a-121">Нелатинские символы, такие как кириллица (`Д`, `Ц`)</span><span class="sxs-lookup"><span data-stu-id="9918a-121">Non-latin characters like Cyrillic (`Д`, `Ц`)</span></span>
- <span data-ttu-id="9918a-122">Символы иероглифического письма (`本`, `화`, `が`).</span><span class="sxs-lookup"><span data-stu-id="9918a-122">CJK characters (`本`, `화`, `が`)</span></span>

<span data-ttu-id="9918a-123">Распространенные причины проблем с кодировкой:</span><span class="sxs-lookup"><span data-stu-id="9918a-123">Common reasons for encoding issues are:</span></span>

- <span data-ttu-id="9918a-124">Параметры кодировок по умолчанию VS Code и PowerShell не были изменены.</span><span class="sxs-lookup"><span data-stu-id="9918a-124">The encodings of VS Code and PowerShell have not been changed from their defaults.</span></span> <span data-ttu-id="9918a-125">В версиях до PowerShell 5.1 (включительно) кодировка по умолчанию отличается от используемой в VS Code.</span><span class="sxs-lookup"><span data-stu-id="9918a-125">For PowerShell 5.1 and below, the default encoding is different from VS Code's.</span></span>
- <span data-ttu-id="9918a-126">Открыт другой редактор, и файл перезаписан в новой кодировке.</span><span class="sxs-lookup"><span data-stu-id="9918a-126">Another editor has opened and overwritten the file in a new encoding.</span></span> <span data-ttu-id="9918a-127">Это часто происходит с интегрированной средой сценариев.</span><span class="sxs-lookup"><span data-stu-id="9918a-127">This often happens with the ISE.</span></span>
- <span data-ttu-id="9918a-128">Файл возвращается в систему управления версиями в кодировке, отличающейся от той, которая ожидается в VS Code или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9918a-128">The file is checked into source control in an encoding that is different from what VS Code or PowerShell expects.</span></span> <span data-ttu-id="9918a-129">Это может произойти, когда участники совместной работы используют редакторы с различными конфигурациями кодировок.</span><span class="sxs-lookup"><span data-stu-id="9918a-129">This can happen when collaborators use editors with different encoding configurations.</span></span>

### <a name="how-to-tell-when-you-have-encoding-issues"></a><span data-ttu-id="9918a-130">Как определить наличие проблемы с кодировкой</span><span class="sxs-lookup"><span data-stu-id="9918a-130">How to tell when you have encoding issues</span></span>

<span data-ttu-id="9918a-131">Часто ошибки кодирования в скриптах представляются как ошибки синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="9918a-131">Often encoding errors present themselves as parse errors in scripts.</span></span> <span data-ttu-id="9918a-132">Если вы видите странные последовательности символов в скрипте, это может быть проблемой.</span><span class="sxs-lookup"><span data-stu-id="9918a-132">If you find strange character sequences in your script, this can be the problem.</span></span> <span data-ttu-id="9918a-133">В примере ниже тире (`–`) отображается в виде символов `â&euro;"`:</span><span class="sxs-lookup"><span data-stu-id="9918a-133">In the example below, an en-dash (`–`) appears as the characters `â&euro;"`:</span></span>

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â&euro;"From $from â&euro;"To $recipient1 â&euro;"Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

<span data-ttu-id="9918a-134">Эта проблема возникает, так как VS Code кодирует символ `–` в UTF-8 как байты `0xE2 0x80 0x93`.</span><span class="sxs-lookup"><span data-stu-id="9918a-134">This problem occurs because VS Code encodes the character `–` in UTF-8 as the bytes `0xE2 0x80 0x93`.</span></span> <span data-ttu-id="9918a-135">Если эти байты декодируются в кодировке Windows-1252, они интерпретируются как символы `â&euro;"`.</span><span class="sxs-lookup"><span data-stu-id="9918a-135">When these bytes are decoded as Windows-1252, they are interpreted as the characters `â&euro;"`.</span></span>

<span data-ttu-id="9918a-136">Некоторые странные последовательности символов, которые можно видеть:</span><span class="sxs-lookup"><span data-stu-id="9918a-136">Some strange character sequences that you might see include:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="9918a-137">`â&euro;"` вместо `–`.</span><span class="sxs-lookup"><span data-stu-id="9918a-137">`â&euro;"` instead of `–`</span></span>
- <span data-ttu-id="9918a-138">`â&euro;"` вместо `—`.</span><span class="sxs-lookup"><span data-stu-id="9918a-138">`â&euro;"` instead of `—`</span></span>
- <span data-ttu-id="9918a-139">`Ã„2` вместо `Ä`.</span><span class="sxs-lookup"><span data-stu-id="9918a-139">`Ã„2` instead of `Ä`</span></span>
- <span data-ttu-id="9918a-140">`Â` вместо ` ` (неразрывный пробел);</span><span class="sxs-lookup"><span data-stu-id="9918a-140">`Â` instead of ` `  (a non-breaking space)</span></span>
- <span data-ttu-id="9918a-141">`Ã&copy;` вместо `é`.</span><span class="sxs-lookup"><span data-stu-id="9918a-141">`Ã&copy;` instead of `é`</span></span>
<!-- markdownlint-enable MD038 -->

<span data-ttu-id="9918a-142">Этот удобный [справочник](https://www.i18nqa.com/debug/utf8-debug.html) перечисляет распространенные шаблоны, которые указывают на проблему между кодировками UTF-8 и Windows-1252.</span><span class="sxs-lookup"><span data-stu-id="9918a-142">This handy [reference](https://www.i18nqa.com/debug/utf8-debug.html) lists the common patterns that indicate a UTF-8/Windows-1252 encoding problem.</span></span>

## <a name="how-the-powershell-extension-in-vs-code-interacts-with-encodings"></a><span data-ttu-id="9918a-143">Взаимодействие расширения PowerShell для VS Code с кодировками</span><span class="sxs-lookup"><span data-stu-id="9918a-143">How the PowerShell extension in VS Code interacts with encodings</span></span>

<span data-ttu-id="9918a-144">Расширение PowerShell взаимодействует со скриптами несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="9918a-144">The PowerShell extension interacts with scripts in a number of ways:</span></span>

1. <span data-ttu-id="9918a-145">При изменении скриптов в VS Code содержимое отправляется из VS Code в расширение.</span><span class="sxs-lookup"><span data-stu-id="9918a-145">When scripts are edited in VS Code, the contents are sent by VS Code to the extension.</span></span> <span data-ttu-id="9918a-146">[Протокол языкового сервера][] требует, чтобы это содержимое передавалось в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9918a-146">The [Language Server Protocol][] mandates that this content is transferred in UTF-8.</span></span> <span data-ttu-id="9918a-147">Таким образом, расширение не сможет получить неправильную кодировку.</span><span class="sxs-lookup"><span data-stu-id="9918a-147">Therefore, it is not possible for the extension to get the wrong encoding.</span></span>
2. <span data-ttu-id="9918a-148">При выполнении скриптов в интегрированной консоли они считываются оболочкой PowerShell непосредственно из файла.</span><span class="sxs-lookup"><span data-stu-id="9918a-148">When scripts are executed directly in the Integrated Console, they're read from the file by PowerShell directly.</span></span> <span data-ttu-id="9918a-149">Если кодировка PowerShell отличается от кодировки VS Code, может произойти сбой.</span><span class="sxs-lookup"><span data-stu-id="9918a-149">If PowerShell's encoding differs from VS Code's, something can go wrong here.</span></span>
3. <span data-ttu-id="9918a-150">Когда скрипт, который открыт в VS Code, ссылается на другой скрипт, который не был открыт в VS Code, расширение загружает содержимое второго скрипта из файловой системы.</span><span class="sxs-lookup"><span data-stu-id="9918a-150">When a script that is open in VS Code references another script that is not open in VS Code, the extension falls back to loading that script's content from the file system.</span></span> <span data-ttu-id="9918a-151">Расширение PowerShell по умолчанию использует кодировку UTF-8, но при этом применяет обнаружение [метки порядка байтов][] (BOM), чтобы выбрать правильную кодировку.</span><span class="sxs-lookup"><span data-stu-id="9918a-151">The PowerShell extension defaults to UTF-8 encoding, but uses [byte-order mark][], or BOM, detection to select the correct encoding.</span></span>

<span data-ttu-id="9918a-152">Проблема возникает при предположении кодировки, не использующей BOM (такой как [UTF-8][] без метки порядка байтов или [Windows-1252][]).</span><span class="sxs-lookup"><span data-stu-id="9918a-152">The problem occurs when assuming the encoding of BOM-less formats (like [UTF-8][] with no BOM and [Windows-1252][]).</span></span> <span data-ttu-id="9918a-153">Расширение PowerShell по умолчанию использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9918a-153">The PowerShell extension defaults to UTF-8.</span></span> <span data-ttu-id="9918a-154">Расширение не может изменить параметры кодировки в VS Code.</span><span class="sxs-lookup"><span data-stu-id="9918a-154">The extension cannot change VS Code's encoding settings.</span></span> <span data-ttu-id="9918a-155">Дополнительные сведения см. в разделе [Проблема № 824](https://github.com/Microsoft/VSCode/issues/824).</span><span class="sxs-lookup"><span data-stu-id="9918a-155">For more information, see [issue #824](https://github.com/Microsoft/VSCode/issues/824).</span></span>

## <a name="choosing-the-right-encoding"></a><span data-ttu-id="9918a-156">Выбор подходящей кодировки</span><span class="sxs-lookup"><span data-stu-id="9918a-156">Choosing the right encoding</span></span>

<span data-ttu-id="9918a-157">Различные системы и приложения могут использовать различные кодировки:</span><span class="sxs-lookup"><span data-stu-id="9918a-157">Different systems and applications can use different encodings:</span></span>

- <span data-ttu-id="9918a-158">В .NET Standard, в Интернете и в среде Linux теперь в основном используется кодировка UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9918a-158">In .NET Standard, on the web, and in the Linux world, UTF-8 is now the dominant encoding.</span></span>
- <span data-ttu-id="9918a-159">Во многих приложениях .NET Framework используется [UTF-16][].</span><span class="sxs-lookup"><span data-stu-id="9918a-159">Many .NET Framework applications use [UTF-16][].</span></span> <span data-ttu-id="9918a-160">По историческим причинам ее иногда называют "Юникод"; сейчас этот термин относится к более широкому [стандарту](https://en.wikipedia.org/wiki/Unicode), охватывающему UTF-8 и UTF-16.</span><span class="sxs-lookup"><span data-stu-id="9918a-160">For historical reasons, this is sometimes called "Unicode", a term that now refers to a broad [standard](https://en.wikipedia.org/wiki/Unicode) that includes both UTF-8 and UTF-16.</span></span>
- <span data-ttu-id="9918a-161">В Windows многие приложения, которые были созданы еще до распространения Юникода, по-прежнему могут по умолчанию использовать Windows-1252.</span><span class="sxs-lookup"><span data-stu-id="9918a-161">On Windows, many native applications that predate Unicode continue to use Windows-1252 by default.</span></span>

<span data-ttu-id="9918a-162">Кодировки Юникода также используют понятие метки порядка следования байтов (BOM).</span><span class="sxs-lookup"><span data-stu-id="9918a-162">Unicode encodings also have the concept of a byte-order mark (BOM).</span></span> <span data-ttu-id="9918a-163">BOM ставится в начале текста, чтобы декодер мог определить, какая кодировка используется в тексте.</span><span class="sxs-lookup"><span data-stu-id="9918a-163">BOMs occur at the beginning of text to tell a decoder which encoding the text is using.</span></span> <span data-ttu-id="9918a-164">Для многобайтовых кодировок BOM также указывает [порядок следования байтов](https://en.wikipedia.org/wiki/Endianness) кодировки.</span><span class="sxs-lookup"><span data-stu-id="9918a-164">For multi-byte encodings, the BOM also indicates [endianness](https://en.wikipedia.org/wiki/Endianness) of the encoding.</span></span> <span data-ttu-id="9918a-165">BOM представляются байтами, которые редко встречаются в тексте в Юникоде. Это позволяет сделать обоснованное предположение, что текст записан в Юникоде, если присутствует метка BOM.</span><span class="sxs-lookup"><span data-stu-id="9918a-165">BOMs are designed to be bytes that rarely occur in non-Unicode text, allowing a reasonable guess that text is Unicode when a BOM is present.</span></span>

<span data-ttu-id="9918a-166">BOM не являются обязательными; в мире Linux они не так популярны, поскольку во всех прочих местах используется надежное соглашение UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9918a-166">BOMs are optional and their adoption isn't as popular in the Linux world because a dependable convention of UTF-8 is used everywhere.</span></span> <span data-ttu-id="9918a-167">Большинство приложений Linux предполагают, что текстовый ввод кодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9918a-167">Most Linux applications presume that text input is encoded in UTF-8.</span></span> <span data-ttu-id="9918a-168">Хотя многие приложения Linux могут распознавать и правильно обрабатывать BOM, некоторые этого не делают, что приводит к появлению артефактов в тексте, открываемом с помощью этих приложений.</span><span class="sxs-lookup"><span data-stu-id="9918a-168">While many Linux applications will recognize and correctly handle a BOM, a number do not, leading to artifacts in text manipulated with those applications.</span></span>

<span data-ttu-id="9918a-169">**Таким образом**:</span><span class="sxs-lookup"><span data-stu-id="9918a-169">**Therefore**:</span></span>

- <span data-ttu-id="9918a-170">Если вы работаете в основном с приложениями Windows и Windows PowerShell, следует предпочтительно использовать такие кодировки, как UTF-8 с BOM или UTF-16.</span><span class="sxs-lookup"><span data-stu-id="9918a-170">If you work primarily with Windows applications and Windows PowerShell, you should prefer an encoding like UTF-8 with BOM or UTF-16.</span></span>
- <span data-ttu-id="9918a-171">Если вы работаете на разных платформах, следует отдавать предпочтение UTF-8 с BOM.</span><span class="sxs-lookup"><span data-stu-id="9918a-171">If you work across platforms, you should prefer UTF-8 with BOM.</span></span>
- <span data-ttu-id="9918a-172">Если вы работаете главным образом в контексте Linux, следует отдавать предпочтение UTF-8 без BOM.</span><span class="sxs-lookup"><span data-stu-id="9918a-172">If you work mainly in Linux-associated contexts, you should prefer UTF-8 without BOM.</span></span>
- <span data-ttu-id="9918a-173">Windows-1252 и latin-1 — устаревшие кодировки, которых по возможности следует избегать.</span><span class="sxs-lookup"><span data-stu-id="9918a-173">Windows-1252 and latin-1 are essentially legacy encodings that you should avoid if possible.</span></span>
  <span data-ttu-id="9918a-174">Тем не менее некоторые приложения предыдущих версий в Windows зависят от их.</span><span class="sxs-lookup"><span data-stu-id="9918a-174">However, some older Windows applications may depend on them.</span></span>
- <span data-ttu-id="9918a-175">Также стоит отметить, что подписывание скриптов [зависит от кодировки](https://github.com/PowerShell/PowerShell/issues/3466), то есть изменение кодировки в подписанном скрипте потребует повторного подписывания.</span><span class="sxs-lookup"><span data-stu-id="9918a-175">It's also worth noting that script signing is [encoding-dependent](https://github.com/PowerShell/PowerShell/issues/3466), meaning a change of encoding on a signed script will require resigning.</span></span>

## <a name="configuring-vs-code"></a><span data-ttu-id="9918a-176">Настройка VS Code</span><span class="sxs-lookup"><span data-stu-id="9918a-176">Configuring VS Code</span></span>

<span data-ttu-id="9918a-177">Кодировка VS Code по умолчанию — UTF-8 без метки порядка байтов.</span><span class="sxs-lookup"><span data-stu-id="9918a-177">VS Code's default encoding is UTF-8 without BOM.</span></span>

<span data-ttu-id="9918a-178">Чтобы задать [Кодировка в VS Code][], перейдите к параметрам VS Code (<kbd>CTRL</kbd>+<kbd>,</kbd>) и задайте параметр `"files.encoding"`:</span><span class="sxs-lookup"><span data-stu-id="9918a-178">To set [VS Code's encoding][], go to the VS Code settings (<kbd>Ctrl</kbd>+<kbd>,</kbd>) and set the `"files.encoding"` setting:</span></span>

```json
"files.encoding": "utf8bom"
```

<span data-ttu-id="9918a-179">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9918a-179">Some possible values are:</span></span>

- <span data-ttu-id="9918a-180">`utf8`: [UTF-8] без метки порядка байтов</span><span class="sxs-lookup"><span data-stu-id="9918a-180">`utf8`: [UTF-8] without BOM</span></span>
- <span data-ttu-id="9918a-181">`utf8bom`: [UTF-8] с меткой порядка байтов</span><span class="sxs-lookup"><span data-stu-id="9918a-181">`utf8bom`: [UTF-8] with BOM</span></span>
- <span data-ttu-id="9918a-182">`utf16le`: [UTF-16] с прямым порядком байтов</span><span class="sxs-lookup"><span data-stu-id="9918a-182">`utf16le`: Little endian [UTF-16]</span></span>
- <span data-ttu-id="9918a-183">`utf16be`: [UTF-16] с обратным порядком байтов</span><span class="sxs-lookup"><span data-stu-id="9918a-183">`utf16be`: Big endian [UTF-16]</span></span>
- <span data-ttu-id="9918a-184">`windows1252`: [Windows-1252]</span><span class="sxs-lookup"><span data-stu-id="9918a-184">`windows1252`: [Windows-1252]</span></span>

<span data-ttu-id="9918a-185">Должен отобразиться раскрывающийся список представления графического пользовательского интерфейса или дополнение в представлении JSON.</span><span class="sxs-lookup"><span data-stu-id="9918a-185">You should get a dropdown for this in the GUI view, or completions for it in the JSON view.</span></span>

<span data-ttu-id="9918a-186">Чтобы обеспечить автоматическое определение кодировки, если это возможно, можно также добавить следующее:</span><span class="sxs-lookup"><span data-stu-id="9918a-186">You can also add the following to autodetect encoding when possible:</span></span>

```json
"files.autoGuessEncoding": true
```

<span data-ttu-id="9918a-187">Если вы не хотите, чтобы эти параметры влияли на все типы файлов, в VS Code можно задавать конфигурации для каждого языка отдельно.</span><span class="sxs-lookup"><span data-stu-id="9918a-187">If you don't want these settings to affect all files types, VS Code also allows per-language configurations.</span></span> <span data-ttu-id="9918a-188">Создать параметр для конкретного языка можно, поместив параметры в поле `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="9918a-188">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="9918a-189">Пример:</span><span class="sxs-lookup"><span data-stu-id="9918a-189">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

## <a name="configuring-powershell"></a><span data-ttu-id="9918a-190">Настройка PowerShell</span><span class="sxs-lookup"><span data-stu-id="9918a-190">Configuring PowerShell</span></span>

<span data-ttu-id="9918a-191">В PowerShell кодировка по умолчанию зависит от версии:</span><span class="sxs-lookup"><span data-stu-id="9918a-191">PowerShell's default encoding varies depending on version:</span></span>

- <span data-ttu-id="9918a-192">В PowerShell 6+ кодировка по умолчанию на всех платформах — UTF-8 без метки порядка байтов.</span><span class="sxs-lookup"><span data-stu-id="9918a-192">In PowerShell 6+, the default encoding is UTF-8 without BOM on all platforms.</span></span>
- <span data-ttu-id="9918a-193">В Windows PowerShell кодировка по умолчанию — обычно Windows-1252, расширение [latin-1][], которое также называется ISO 8859-1.</span><span class="sxs-lookup"><span data-stu-id="9918a-193">In Windows PowerShell, the default encoding is usually Windows-1252, an extension of [latin-1][], also known as ISO 8859-1.</span></span>

<span data-ttu-id="9918a-194">В PowerShell 5 + можно определить кодировку по умолчанию так:</span><span class="sxs-lookup"><span data-stu-id="9918a-194">In PowerShell 5+ you can find your default encoding with this:</span></span>

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

<span data-ttu-id="9918a-195">Следующий [скрипт](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) может использоваться для определения кодировки, которую ваш сеанс PowerShell выводит для скрипта, где нет метки порядка байтов.</span><span class="sxs-lookup"><span data-stu-id="9918a-195">The following [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) can be used to determine what encoding your PowerShell session infers for a script without a BOM.</span></span>

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

<span data-ttu-id="9918a-196">Можно настроить PowerShell так, чтобы использовать заданную кодировку в более общем виде с помощью параметров профиля.</span><span class="sxs-lookup"><span data-stu-id="9918a-196">It's possible to configure PowerShell to use a given encoding more generally using profile settings.</span></span>
<span data-ttu-id="9918a-197">См. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="9918a-197">See the following articles:</span></span>

- <span data-ttu-id="9918a-198">[Ответ [@mklement0] о кодировке PowerShell на сайте StackOverflow](https://stackoverflow.com/a/40098904).</span><span class="sxs-lookup"><span data-stu-id="9918a-198">[@mklement0]'s [answer about PowerShell encoding on StackOverflow](https://stackoverflow.com/a/40098904).</span></span>
- <span data-ttu-id="9918a-199">[Запись блога [@rkeithhill] об обработке входных данных в UTF-8 без метки порядка байтов в PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span><span class="sxs-lookup"><span data-stu-id="9918a-199">[@rkeithhill]'s [blog post about dealing with BOM-less UTF-8 input in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span></span>

<span data-ttu-id="9918a-200">Заставить PowerShell использовать конкретную кодировку для входных данных невозможно.</span><span class="sxs-lookup"><span data-stu-id="9918a-200">It's not possible to force PowerShell to use a specific input encoding.</span></span> <span data-ttu-id="9918a-201">PowerShell 5.1 и более ранние версии по умолчанию используют кодировку Windows-1252, если отсутствует BOM.</span><span class="sxs-lookup"><span data-stu-id="9918a-201">PowerShell 5.1 and below default to Windows-1252 encoding when there's no BOM.</span></span> <span data-ttu-id="9918a-202">По причинам совместимости лучше сохранять скрипты в Юникоде с меткой порядка байтов.</span><span class="sxs-lookup"><span data-stu-id="9918a-202">For interoperability reasons, it's best to save scripts in a Unicode format with a BOM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9918a-203">Любые другие имеющиеся у вас инструменты для работы со скриптами PowerShell могут зависеть от выбранных параметров кодировки или преобразовывать скрипты в другую кодировку.</span><span class="sxs-lookup"><span data-stu-id="9918a-203">Any other tools you have that touch PowerShell scripts may be affected by your encoding choices or re-encode your scripts to another encoding.</span></span>

### <a name="existing-scripts"></a><span data-ttu-id="9918a-204">Существующие скрипты</span><span class="sxs-lookup"><span data-stu-id="9918a-204">Existing scripts</span></span>

<span data-ttu-id="9918a-205">Скрипты, которые уже находятся в файловой системе, могут нуждаться в повторном кодировании в указанную вами кодировку.</span><span class="sxs-lookup"><span data-stu-id="9918a-205">Scripts already on the file system may need to be re-encoded to your new chosen encoding.</span></span> <span data-ttu-id="9918a-206">В нижней строке VS Code вы увидите метку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9918a-206">In the bottom bar of VS Code, you'll see the label UTF-8.</span></span> <span data-ttu-id="9918a-207">Щелкните ее, чтобы открыть панель действий, и выберите команду **Сохранить с кодировкой**.</span><span class="sxs-lookup"><span data-stu-id="9918a-207">Click it to open the action bar and select **Save with encoding**.</span></span> <span data-ttu-id="9918a-208">Теперь вы можете выбрать новую кодировку для этого файла.</span><span class="sxs-lookup"><span data-stu-id="9918a-208">You can now pick a new encoding for that file.</span></span> <span data-ttu-id="9918a-209">Подробные инструкции см. в разделе [Кодировка в VS Code][].</span><span class="sxs-lookup"><span data-stu-id="9918a-209">See [VS Code's encoding][] for full instructions.</span></span>

<span data-ttu-id="9918a-210">Если вам нужно повторно кодировать несколько файлов, можно использовать следующий скрипт:</span><span class="sxs-lookup"><span data-stu-id="9918a-210">If you need to re-encode multiple files, you can use the following script:</span></span>

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="9918a-211">Интегрированная среда сценариев (ISE) PowerShell</span><span class="sxs-lookup"><span data-stu-id="9918a-211">The PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="9918a-212">При редактировании скриптов с помощью интегрированной среды сценариев PowerShell необходимо синхронизировать здесь параметры кодировки.</span><span class="sxs-lookup"><span data-stu-id="9918a-212">If you also edit scripts using the PowerShell ISE, you need to synchronize your encoding settings there.</span></span>

<span data-ttu-id="9918a-213">Интегрированная среда сценариев должна учитывать метку порядка байтов, но можно также использовать отражение для [задания кодировки](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span><span class="sxs-lookup"><span data-stu-id="9918a-213">The ISE should honor a BOM, but it's also possible to use reflection to [set the encoding](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span></span>
<span data-ttu-id="9918a-214">Обратите внимание, что это значение не сохраняется между запусками.</span><span class="sxs-lookup"><span data-stu-id="9918a-214">Note that this wouldn't be persisted between startups.</span></span>

### <a name="source-control-software"></a><span data-ttu-id="9918a-215">Система управления версиями</span><span class="sxs-lookup"><span data-stu-id="9918a-215">Source control software</span></span>

<span data-ttu-id="9918a-216">Некоторые системы управления версиями, например git, игнорируют кодировки; git отслеживает только байты.</span><span class="sxs-lookup"><span data-stu-id="9918a-216">Some source control tools, such as git, ignore encodings; git just tracks the bytes.</span></span> <span data-ttu-id="9918a-217">Поведение других, например Azure DevOps или Mercurial, может отличаться.</span><span class="sxs-lookup"><span data-stu-id="9918a-217">Others, like Azure DevOps or Mercurial, may not.</span></span> <span data-ttu-id="9918a-218">Даже некоторые средства, основанные на git, полагаются на декодирование текста.</span><span class="sxs-lookup"><span data-stu-id="9918a-218">Even some git-based tools rely on decoding text.</span></span>

<span data-ttu-id="9918a-219">Если это так, убедитесь, что вы:</span><span class="sxs-lookup"><span data-stu-id="9918a-219">When this is the case, make sure you:</span></span>

- <span data-ttu-id="9918a-220">Настроили кодировку в системе управления версиями в соответствии с вашей конфигурацией VS Code.</span><span class="sxs-lookup"><span data-stu-id="9918a-220">Configure the text encoding in your source control to match your VS Code configuration.</span></span>
- <span data-ttu-id="9918a-221">Сделали так, что все файлы добавляются в систему управления версиями в соответствующей кодировке.</span><span class="sxs-lookup"><span data-stu-id="9918a-221">Ensure all your files are checked into source control in the relevant encoding.</span></span>
- <span data-ttu-id="9918a-222">Остерегайтесь изменять кодировки, полученные через систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="9918a-222">Be wary of changes to the encoding received through source control.</span></span> <span data-ttu-id="9918a-223">Ключевым признаком здесь будет разностный файл, который указывает, что изменения отсутствуют (так как изменены байты, но не символы).</span><span class="sxs-lookup"><span data-stu-id="9918a-223">A key sign of this is a diff indicating changes but where nothing seems to have changed (because bytes have but characters have not).</span></span>

### <a name="collaborators-environments"></a><span data-ttu-id="9918a-224">Среды других участников</span><span class="sxs-lookup"><span data-stu-id="9918a-224">Collaborators' environments</span></span>

<span data-ttu-id="9918a-225">Настроив систему управления версиями, убедитесь также, что параметры других участников, работающих над теми файлами, к которым вы предоставляете общий доступ, не переопределяют кодировку путем повторного кодирования файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9918a-225">On top of configuring source control, ensure that your collaborators on any files you share don't have settings that override your encoding by re-encoding PowerShell files.</span></span>

### <a name="other-programs"></a><span data-ttu-id="9918a-226">Другие программы</span><span class="sxs-lookup"><span data-stu-id="9918a-226">Other programs</span></span>

<span data-ttu-id="9918a-227">Все другие программы, которые считывают или записывают скрипты PowerShell, могут перекодировать их.</span><span class="sxs-lookup"><span data-stu-id="9918a-227">Any other program that reads or writes a PowerShell script may re-encode it.</span></span>

<span data-ttu-id="9918a-228">Некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="9918a-228">Some examples are:</span></span>

- <span data-ttu-id="9918a-229">Использование буфера обмена для копирования и вставки скрипта.</span><span class="sxs-lookup"><span data-stu-id="9918a-229">Using the clipboard to copy and paste a script.</span></span> <span data-ttu-id="9918a-230">Такое часто встречается в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="9918a-230">This is common in scenarios like:</span></span>
  - <span data-ttu-id="9918a-231">Копирование скрипта в виртуальную машину.</span><span class="sxs-lookup"><span data-stu-id="9918a-231">Copying a script into a VM</span></span>
  - <span data-ttu-id="9918a-232">Копирование скрипта из электронной почты или с веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="9918a-232">Copying a script out of an email or webpage</span></span>
  - <span data-ttu-id="9918a-233">Копирование скрипта через документ Microsoft Word или PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="9918a-233">Copying a script into or out of a Microsoft Word or PowerPoint document</span></span>
- <span data-ttu-id="9918a-234">Другие текстовые редакторы, например:</span><span class="sxs-lookup"><span data-stu-id="9918a-234">Other text editors, such as:</span></span>
  - <span data-ttu-id="9918a-235">Блокнот;</span><span class="sxs-lookup"><span data-stu-id="9918a-235">Notepad</span></span>
  - <span data-ttu-id="9918a-236">vim;</span><span class="sxs-lookup"><span data-stu-id="9918a-236">vim</span></span>
  - <span data-ttu-id="9918a-237">любой другой редактор скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9918a-237">Any other PowerShell script editor</span></span>
- <span data-ttu-id="9918a-238">Служебные программы редактирования текста, например:</span><span class="sxs-lookup"><span data-stu-id="9918a-238">Text editing utilities, like:</span></span>
  - `Get-Content`/`Set-Content`/`Out-File`
  - <span data-ttu-id="9918a-239">Операторы перенаправления PowerShell, такие как `>` и `>>`.</span><span class="sxs-lookup"><span data-stu-id="9918a-239">PowerShell redirection operators like `>` and `>>`</span></span>
  - `sed`/`awk`
- <span data-ttu-id="9918a-240">Программы передачи файлов, такие как:</span><span class="sxs-lookup"><span data-stu-id="9918a-240">File transfer programs, like:</span></span>
  - <span data-ttu-id="9918a-241">Веб-браузер при скачивании скриптов.</span><span class="sxs-lookup"><span data-stu-id="9918a-241">A web browser, when downloading scripts</span></span>
  - <span data-ttu-id="9918a-242">Общий файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="9918a-242">A file share</span></span>

<span data-ttu-id="9918a-243">Некоторые из этих средств работают с байтами, а не с текстом, но другие позволяют настраивать кодировки.</span><span class="sxs-lookup"><span data-stu-id="9918a-243">Some of these tools deal in bytes rather than text, but others offer encoding configurations.</span></span> <span data-ttu-id="9918a-244">В случаях, когда необходимо настроить кодировку, используйте те же параметры, что и в вашем редакторе, чтобы предотвратить возникновение проблем.</span><span class="sxs-lookup"><span data-stu-id="9918a-244">In those cases where you need to configure an encoding, you need to make it the same as your editor encoding to prevent problems.</span></span>

## <a name="other-resources-on-encoding-in-powershell"></a><span data-ttu-id="9918a-245">Другие ресурсы о кодировках в PowerShell</span><span class="sxs-lookup"><span data-stu-id="9918a-245">Other resources on encoding in PowerShell</span></span>

<span data-ttu-id="9918a-246">Существует несколько других достойных публикаций на тему кодировок и настройки кодирования в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9918a-246">There are a few other nice posts on encoding and configuring encoding in PowerShell that are worth a read:</span></span>

- <span data-ttu-id="9918a-247">[Обзор [@mklement0] о кодировке PowerShell на сайте StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8).</span><span class="sxs-lookup"><span data-stu-id="9918a-247">[@mklement0]'s [summary of PowerShell encoding on StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span></span>
- <span data-ttu-id="9918a-248">Предыдущие проблемы с кодировками, найденные в VS Code и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9918a-248">Previous issues opened on VS Code-PowerShell for encoding problems:</span></span>
  - [<span data-ttu-id="9918a-249">#1308</span><span class="sxs-lookup"><span data-stu-id="9918a-249">#1308</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1308)
  - [<span data-ttu-id="9918a-250">#1628</span><span class="sxs-lookup"><span data-stu-id="9918a-250">#1628</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1628)
  - [<span data-ttu-id="9918a-251">#1680</span><span class="sxs-lookup"><span data-stu-id="9918a-251">#1680</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1680)
  - [<span data-ttu-id="9918a-252">#1744</span><span class="sxs-lookup"><span data-stu-id="9918a-252">#1744</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1744)
  - [<span data-ttu-id="9918a-253">#1751</span><span class="sxs-lookup"><span data-stu-id="9918a-253">#1751</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1751)
- [<span data-ttu-id="9918a-254">Классическая статья *Joel on Software* про Юникод</span><span class="sxs-lookup"><span data-stu-id="9918a-254">The classic *Joel on Software* write up about Unicode</span></span>](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [<span data-ttu-id="9918a-255">Кодировка в .NET Standard</span><span class="sxs-lookup"><span data-stu-id="9918a-255">Encoding in .NET Standard</span></span>](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)

[@mklement0]: https://github.com/mklement0
[@rkeithhill]: https://github.com/rkeithhill
[Windows-1252]: https://wikipedia.org/wiki/Windows-1252
[latin-1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[UTF-8]: https://wikipedia.org/wiki/UTF-8
[метки порядка байтов]: https://wikipedia.org/wiki/Byte_order_mark
[byte-order mark]: https://wikipedia.org/wiki/Byte_order_mark
[UTF-16]: https://wikipedia.org/wiki/UTF-16
[Протокол языкового сервера]: https://microsoft.github.io/language-server-protocol/
[Language Server Protocol]: https://microsoft.github.io/language-server-protocol/
[Кодировка в VS Code]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[VS Code's encoding]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
