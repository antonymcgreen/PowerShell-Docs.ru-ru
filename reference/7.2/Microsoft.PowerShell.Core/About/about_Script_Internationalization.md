---
description: Описание возможностей интернационализации сценариев, упрощающих выполнение сценариев для вывода сообщений и инструкций пользователям на языке пользовательского интерфейса.
Locale: en-US
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_internationalization?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Internationalization
ms.openlocfilehash: 283ea6788e76b481c912fc5672350efd2e8bafaa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603974"
---
# <a name="about-script-internationalization"></a><span data-ttu-id="93f79-103">О международной локализации сценариев</span><span class="sxs-lookup"><span data-stu-id="93f79-103">About Script Internationalization</span></span>

## <a name="short-description"></a><span data-ttu-id="93f79-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="93f79-104">Short Description</span></span>
<span data-ttu-id="93f79-105">Описание возможностей интернационализации сценариев, упрощающих выполнение сценариев для вывода сообщений и инструкций пользователям на языке пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="93f79-105">Describes the script internationalization features that make it easy for scripts to display messages and instructions to users in their user interface (UI) language.</span></span>

## <a name="long-description"></a><span data-ttu-id="93f79-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="93f79-106">Long Description</span></span>

<span data-ttu-id="93f79-107">Возможности интернационализации сценариев PowerShell позволяют лучше обслуживать пользователей по всему миру за счет отображения справки и сообщений пользователя на языке пользователя.</span><span class="sxs-lookup"><span data-stu-id="93f79-107">The PowerShell script internationalization features allow you to better serve users throughout the world by displaying help and user messages in the user's language.</span></span>

<span data-ttu-id="93f79-108">Функции интернационализации сценариев запрашивают язык и региональные параметры пользовательского интерфейса операционной системы во время выполнения, импортируют соответствующие переведенные текстовые строки и отображают их пользователю.</span><span class="sxs-lookup"><span data-stu-id="93f79-108">The script internationalization features query the UI culture of the operating system during execution, import the appropriate translated text strings, and display them to the user.</span></span> <span data-ttu-id="93f79-109">Раздел данных позволяет хранить текстовые строки отдельно от кода, чтобы они были легко идентифицированы и извлечены.</span><span class="sxs-lookup"><span data-stu-id="93f79-109">The Data section lets you store text strings separate from code so they are easily identified and extracted.</span></span> <span data-ttu-id="93f79-110">Новый командлет, `ConvertFrom-StringData` преобразует текстовые строки в хэш-таблицы, подобные словарям, чтобы упростить перевод.</span><span class="sxs-lookup"><span data-stu-id="93f79-110">A new cmdlet, `ConvertFrom-StringData`, converts text strings into dictionary-like hash tables to facilitate translation.</span></span>

<span data-ttu-id="93f79-111">Для поддержки текста международных справочных сведений PowerShell предоставляет следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="93f79-111">To support international Help text, PowerShell includes the following features:</span></span>

- <span data-ttu-id="93f79-112">Раздел данных, разделяющий текстовые строки из инструкций кода.</span><span class="sxs-lookup"><span data-stu-id="93f79-112">A Data section that separates text strings from code instructions.</span></span> <span data-ttu-id="93f79-113">Дополнительные сведения о разделе данных см. в статье [about_Data_Sections](about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="93f79-113">For more information about the Data section, see [about_Data_Sections](about_Data_Sections.md).</span></span>

- <span data-ttu-id="93f79-114">Новые автоматические переменные `$PSCulture` и `$PSUICulture` .</span><span class="sxs-lookup"><span data-stu-id="93f79-114">New automatic variables, `$PSCulture` and `$PSUICulture`.</span></span> <span data-ttu-id="93f79-115">`$PSCulture` хранит имя языка пользовательского интерфейса, используемого в системе для таких элементов, как дата, время и валюта.</span><span class="sxs-lookup"><span data-stu-id="93f79-115">`$PSCulture` stores the name of the UI language used on the system for elements such as the date, time, and currency.</span></span> <span data-ttu-id="93f79-116">`$PSUICulture`Переменная хранит имя языка пользовательского интерфейса, используемого в системе для элементов пользовательского интерфейса, таких как меню и текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="93f79-116">The `$PSUICulture` variable stores the name of the UI language used on the system for user interface elements such as menus and text strings.</span></span>

- <span data-ttu-id="93f79-117">Командлет, `ConvertFrom-StringData` , который преобразует текстовые строки в хэш-таблицы, подобные словарям, для упрощения перевода.</span><span class="sxs-lookup"><span data-stu-id="93f79-117">A cmdlet, `ConvertFrom-StringData`, that converts text strings into dictionary-like hash tables to facilitate translation.</span></span> <span data-ttu-id="93f79-118">Дополнительные сведения см. в разделе [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).</span><span class="sxs-lookup"><span data-stu-id="93f79-118">For more information, see [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).</span></span>

- <span data-ttu-id="93f79-119">Новый тип файла, `.psd1` , который хранит переведенные текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="93f79-119">A new file type, `.psd1`, that stores translated text strings.</span></span> <span data-ttu-id="93f79-120">`.psd1`Файлы хранятся в подкаталогах, зависящих от языка каталога сценариев.</span><span class="sxs-lookup"><span data-stu-id="93f79-120">The `.psd1` files are stored in language-specific subdirectories of the script directory.</span></span>

- <span data-ttu-id="93f79-121">Командлет, `Import-LocalizedData` , который импортирует переведенные текстовые строки для указанного языка в скрипт во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="93f79-121">A cmdlet, `Import-LocalizedData`, that imports translated text strings for a specified language into a script at runtime.</span></span> <span data-ttu-id="93f79-122">Этот командлет распознает и импортирует строки на любом языке, поддерживаемом Windows.</span><span class="sxs-lookup"><span data-stu-id="93f79-122">This cmdlet recognizes and imports strings in any Windows-supported language.</span></span> <span data-ttu-id="93f79-123">Дополнительные сведения см. в разделе [Import-локализеддата](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).</span><span class="sxs-lookup"><span data-stu-id="93f79-123">For more information see [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).</span></span>

### <a name="the-data-section-storing-default-strings"></a><span data-ttu-id="93f79-124">Раздел Data: хранение строк по умолчанию</span><span class="sxs-lookup"><span data-stu-id="93f79-124">The Data Section: Storing Default Strings</span></span>

<span data-ttu-id="93f79-125">Используйте раздел данных в скрипте для хранения текстовых строк на языке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93f79-125">Use a Data section in the script to store the text strings in the default language.</span></span> <span data-ttu-id="93f79-126">Расположите строки в парах "ключ-значение" в строке ниже.</span><span class="sxs-lookup"><span data-stu-id="93f79-126">Arrange the strings in key/value pairs in a here-string.</span></span> <span data-ttu-id="93f79-127">Каждая пара "ключ-значение" должна находиться в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="93f79-127">Each key/value pair must be on a separate line.</span></span> <span data-ttu-id="93f79-128">При включении комментариев комментарии должны находиться в разных строках.</span><span class="sxs-lookup"><span data-stu-id="93f79-128">If you include comments, the comments must be on separate lines.</span></span>

<span data-ttu-id="93f79-129">`ConvertFrom-StringData`Командлет преобразует пары "ключ-значение" в строке ниже в хэш-таблицу, которая хранится в значении переменной раздела данных.</span><span class="sxs-lookup"><span data-stu-id="93f79-129">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a dictionary-like hash table that is stored in the value of the Data section variable.</span></span>

<span data-ttu-id="93f79-130">В следующем примере раздел данных `World.ps1` скрипта содержит набор сообщений о состоянии English-United (EN-US) для сценария.</span><span class="sxs-lookup"><span data-stu-id="93f79-130">In the following example, the Data section of the `World.ps1` script includes the English-United States (en-US) set of prompt messages for a script.</span></span> <span data-ttu-id="93f79-131">`ConvertFrom-StringData`Командлет преобразует строки в хэш-таблицу и сохраняет их в `$msgtable` переменной.</span><span class="sxs-lookup"><span data-stu-id="93f79-131">The `ConvertFrom-StringData` cmdlet converts the strings into a hash table and stores them in the `$msgtable` variable.</span></span>

```powershell
$msgTable = Data {
    #culture="en-US"
    ConvertFrom-StringData @'
    helloWorld = Hello, World.
    errorMsg1 = You cannot leave the user name field blank.
    promptMsg = Please enter your user name.
'@
}
```

<span data-ttu-id="93f79-132">Дополнительные сведения о строках см. в разделе [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="93f79-132">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

### <a name="psd1-files-storing-translated-strings"></a><span data-ttu-id="93f79-133">Файлы PSD1: хранение переведенных строк</span><span class="sxs-lookup"><span data-stu-id="93f79-133">PSD1 Files: Storing Translated Strings</span></span>

<span data-ttu-id="93f79-134">Сохраните сообщения сценария для каждого языка пользовательского интерфейса в отдельных текстовых файлах с тем же именем, что и у скрипта, и `.psd1` расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="93f79-134">Save the script messages for each UI language in separate text files with the same name as the script and the `.psd1` file name extension.</span></span> <span data-ttu-id="93f79-135">Храните файлы в подкаталогах каталога script с именами языков и региональных параметров в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="93f79-135">Store the files in subdirectories of the script directory with names of cultures in the following format:</span></span>

`<language>-<region>`

<span data-ttu-id="93f79-136">Примеры: de-DE, AR-SA и zh-Ханс</span><span class="sxs-lookup"><span data-stu-id="93f79-136">Examples: de-DE, ar-SA, and zh-Hans</span></span>

<span data-ttu-id="93f79-137">Например, если `World.ps1` Сценарий хранится в `C:\Scripts` каталоге, необходимо создать структуру каталогов файлов, похожую на следующую:</span><span class="sxs-lookup"><span data-stu-id="93f79-137">For example, if the `World.ps1` script is stored in the `C:\Scripts` directory, you would create a file directory structure that resembles the following:</span></span>

```
C:\Scripts
C:\Scripts\World.ps1
C:\Scripts\de-DE\World.psd1
C:\Scripts\ar-SA\World.psd1
C:\Scripts\zh-CN\World.psd1
...
```

<span data-ttu-id="93f79-138">Файл в подкаталоге `World.psd1` de-de каталога скрипта может содержать следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="93f79-138">The `World.psd1` file in the de-DE subdirectory of the script directory might include the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = Hallo, Welt.
errorMsg1 = Das Feld Benutzername darf nicht leer sein.
promptMsg = Geben Sie Ihren Benutzernamen ein.
'@
```

<span data-ttu-id="93f79-139">Аналогичным образом `World.psd1` файл в подкаталоге AR-SA каталога скрипта может содержать следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="93f79-139">Similarly, the `World.psd1` file in the ar-SA subdirectory of the script directory might includes the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = مرحبًا أيها العالَم
errorMsg1 = لا يمكنك ترك حقل اسم المستخدم فارغًا
promptMsg = يرجى إدخال اسم المستخدم الخاص بك
'@
```

### <a name="import-localizeddata-dynamic-retrieval-of-translated-strings"></a><span data-ttu-id="93f79-140">Import-Локализеддата: динамическое извлечение переведенных строк</span><span class="sxs-lookup"><span data-stu-id="93f79-140">Import-LocalizedData: Dynamic Retrieval of Translated Strings</span></span>

<span data-ttu-id="93f79-141">Чтобы получить строки в языке пользовательского интерфейса текущего пользователя, используйте `Import-LocalizedData` командлет.</span><span class="sxs-lookup"><span data-stu-id="93f79-141">To retrieve the strings in the UI language of the current user, use the `Import-LocalizedData` cmdlet.</span></span>

<span data-ttu-id="93f79-142">`Import-LocalizedData` находит значение `$PSUICulture` автоматической переменной и импортирует содержимое `<script-name>.psd1` файлов в подкаталоге, который соответствует `$PSUICulture` значению.</span><span class="sxs-lookup"><span data-stu-id="93f79-142">`Import-LocalizedData` finds the value of the `$PSUICulture` automatic variable and imports the content of the `<script-name>.psd1` files in the subdirectory that matches the `$PSUICulture` value.</span></span> <span data-ttu-id="93f79-143">Затем он сохраняет импортированное содержимое в переменной, заданной значением параметра **биндингвариабле** .</span><span class="sxs-lookup"><span data-stu-id="93f79-143">Then, it saves the imported content in the variable specified by the value of the **BindingVariable** parameter.</span></span>

```powershell
Import-LocalizedData -BindingVariable msgTable
```

<span data-ttu-id="93f79-144">Например, если `Import-LocalizedData` команда отображается в `C:\Scripts\World.ps1` скрипте, а значение `$PSUICulture` равно "AR-SA", `Import-LocalizedData` находит следующий файл:</span><span class="sxs-lookup"><span data-stu-id="93f79-144">For example, if the `Import-LocalizedData` command appears in the `C:\Scripts\World.ps1` script and the value of `$PSUICulture` is "ar-SA", `Import-LocalizedData` finds the following file:</span></span>

`C:\Scripts\ar-SA\World.psd1`

<span data-ttu-id="93f79-145">Затем он импортирует арабские текстовые строки из файла в `$msgTable` переменную, заменяя все строки по умолчанию, которые могут быть определены в разделе данных `World.ps1` скрипта.</span><span class="sxs-lookup"><span data-stu-id="93f79-145">Then, it imports the Arabic text strings from the file into the `$msgTable` variable, replacing any default strings that might be defined in the Data section of the `World.ps1` script.</span></span>

<span data-ttu-id="93f79-146">В результате, когда скрипт использует `$msgTable` переменную для отображения пользовательских сообщений, сообщения отображаются на арабском языке.</span><span class="sxs-lookup"><span data-stu-id="93f79-146">As a result, when the script uses the `$msgTable` variable to display user messages, the messages are displayed in Arabic.</span></span>

<span data-ttu-id="93f79-147">Например, следующий сценарий отображает сообщение "введите имя пользователя" на арабском языке:</span><span class="sxs-lookup"><span data-stu-id="93f79-147">For example, the following script displays the "Please enter your user name" message in Arabic:</span></span>

```powershell
if (!($username)) { $msgTable.promptMsg }
```

<span data-ttu-id="93f79-148">Если `Import-LocalizedData` не удается найти `.psd1` файл, соответствующий значению `$PSUIculture` , значение `$msgTable` не заменяется, а вызов `$msgTable.promptMsg` отображает резервные строки en-US.</span><span class="sxs-lookup"><span data-stu-id="93f79-148">If `Import-LocalizedData` cannot find a `.psd1` file that matches the value of `$PSUIculture`, the value of `$msgTable` is not replaced, and the call to `$msgTable.promptMsg` displays the fallback en-US strings.</span></span>

## <a name="examples"></a><span data-ttu-id="93f79-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="93f79-149">Examples</span></span>

<span data-ttu-id="93f79-150">В этом примере показано, как в скрипте используются возможности интернационализации скриптов для отображения дня недели пользователям на языке, установленном на компьютере.</span><span class="sxs-lookup"><span data-stu-id="93f79-150">This example shows how the script internationalization features are used in a script to display a day of the week to users in the language that is set on the computer.</span></span>

<span data-ttu-id="93f79-151">Ниже приведен полный список Sample1.ps1 файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="93f79-151">The following is a complete listing of the Sample1.ps1 script file.</span></span>

<span data-ttu-id="93f79-152">Сценарий начинается с раздела данных с именем Day ($Day), который содержит `ConvertFrom-StringData` команду.</span><span class="sxs-lookup"><span data-stu-id="93f79-152">The script begins with a Data section named Day ($Day) that contains a `ConvertFrom-StringData` command.</span></span> <span data-ttu-id="93f79-153">Выражение, отправленное в, `ConvertFrom-StringData` — это строка, содержащая названия дней в языке и региональных параметрах пользовательского интерфейса по умолчанию en-US в парах "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="93f79-153">The expression submitted to `ConvertFrom-StringData` is a here-string that contains the day names in the default UI culture, en-US, in key/value pairs.</span></span> <span data-ttu-id="93f79-154">`ConvertFrom-StringData`Командлет преобразует пары "ключ-значение" в строке ниже в хэш-таблицу и сохраняет ее в значении `$Day` переменной.</span><span class="sxs-lookup"><span data-stu-id="93f79-154">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a hash table and then saves it in the value of the `$Day` variable.</span></span>

<span data-ttu-id="93f79-155">`Import-LocalizedData`Команда импортирует содержимое `.psd1` файла в каталоге, который соответствует значению `$PSUICulture` автоматической переменной, и сохраняет его в `$Day` переменной, заменяя значения `$Day` , определенные в разделе данных.</span><span class="sxs-lookup"><span data-stu-id="93f79-155">The `Import-LocalizedData` command imports the contents of the `.psd1` file in the directory that matches the value of the `$PSUICulture` automatic variable and then saves it in the `$Day` variable, replacing the values of `$Day` that are defined in the Data section.</span></span>

<span data-ttu-id="93f79-156">Остальные команды загружают строки в массив и отображают их.</span><span class="sxs-lookup"><span data-stu-id="93f79-156">The remaining commands load the strings into an array and display them.</span></span>

```powershell
$Day = Data {
#culture="en-US"
ConvertFrom-StringData -StringData @'
    messageDate = Today is
    d0 = Sunday
    d1 = Monday
    d2 = Tuesday
    d3 = Wednesday
    d4 = Thursday
    d5 = Friday
    d6 = Saturday
'@
}

Import-LocalizedData -BindingVariable Day

#Build an array of weekdays.
$a = $Day.d0, $Day.d1, $Day.d2, $Day.d3, $Day.d4, $Day.d5, $Day.d6

# Get the day of the week as a number (Monday = 1).
# Index into $a to get the name of the day.
# Use string formatting to build a sentence.

"{0} {1}" -f $Day.messageDate, $a[(Get-Date -UFormat %u)] | Out-Host
```

<span data-ttu-id="93f79-157">`.psd1`Файлы, поддерживающие скрипт, сохраняются в подкаталогах каталога script с именами, соответствующими `$PSUICulture` значениям.</span><span class="sxs-lookup"><span data-stu-id="93f79-157">The `.psd1` files that support the script are saved in subdirectories of the script directory with names that match the `$PSUICulture` values.</span></span>

<span data-ttu-id="93f79-158">Ниже приведен полный список `.\de-DE\sample1.psd1` .</span><span class="sxs-lookup"><span data-stu-id="93f79-158">The following is a complete listing of `.\de-DE\sample1.psd1`:</span></span>

```powershell
# culture="de-DE"
ConvertFrom-StringData @'
    messageDate = Heute ist
    d0 = Sonntag
    d1 = Montag
    d2 = Dienstag
    d3 = Mittwoch
    d4 = Donnerstag
    d5 = Freitag
    d6 = Samstag
'@
```

<span data-ttu-id="93f79-159">В результате при запуске Sample.ps1 в системе, для которой значение `$PSUICulture` равно de-de, выходные данные скрипта будут:</span><span class="sxs-lookup"><span data-stu-id="93f79-159">As a result, when you run Sample.ps1 on a system on which the value of `$PSUICulture` is de-DE, the output of the script is:</span></span>

```Output
Heute ist Freitag
```

## <a name="see-also"></a><span data-ttu-id="93f79-160">См. также</span><span class="sxs-lookup"><span data-stu-id="93f79-160">See also</span></span>

- [<span data-ttu-id="93f79-161">about_Data_Sections</span><span class="sxs-lookup"><span data-stu-id="93f79-161">about_Data_Sections</span></span>](about_Data_Sections.md)
- [<span data-ttu-id="93f79-162">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="93f79-162">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="93f79-163">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="93f79-163">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="93f79-164">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="93f79-164">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="93f79-165">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="93f79-165">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
- [<span data-ttu-id="93f79-166">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="93f79-166">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

