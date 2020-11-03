---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: 552e37f8bef096ec7d072d41186f8919bc58f630
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228153"
---
# <span data-ttu-id="c226e-103">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="c226e-103">Import-LocalizedData</span></span>

## <span data-ttu-id="c226e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c226e-104">SYNOPSIS</span></span>
<span data-ttu-id="c226e-105">Импортирует данные, зависящие от языка, в сценарии и функции в зависимости от языка и региональных параметров пользовательского интерфейса, выбранного для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c226e-105">Imports language-specific data into scripts and functions based on the UI culture that is selected for the operating system.</span></span>

## <span data-ttu-id="c226e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c226e-106">SYNTAX</span></span>

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="c226e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c226e-107">DESCRIPTION</span></span>

<span data-ttu-id="c226e-108">Командлет **Import-LocalizedData** динамически получает строки из подкаталога, имя которого соответствует языку пользовательского интерфейса, заданному для текущего пользователя операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c226e-108">The **Import-LocalizedData** cmdlet dynamically retrieves strings from a subdirectory whose name matches the UI language set for the current user of the operating system.</span></span>
<span data-ttu-id="c226e-109">Его задачей является включение сценариев для отображения сообщений для пользователей на языке пользовательского интерфейса, выбранного текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="c226e-109">It is designed to enable scripts to display user messages in the UI language selected by the current user.</span></span>

<span data-ttu-id="c226e-110">**Import-локализеддата** импортирует данные из файлов PSD1 в подкаталогах, зависящих от языка, и сохраняет их в локальной переменной, указанной в команде.</span><span class="sxs-lookup"><span data-stu-id="c226e-110">**Import-LocalizedData** imports data from .psd1 files in language-specific subdirectories of the script directory and saves them in a local variable that is specified in the command.</span></span>
<span data-ttu-id="c226e-111">Командлет выбирает подкаталог и файл на основе значения автоматической переменной $PSUICulture.</span><span class="sxs-lookup"><span data-stu-id="c226e-111">The cmdlet selects the subdirectory and file based on the value of the $PSUICulture automatic variable.</span></span>
<span data-ttu-id="c226e-112">При использовании локальной переменной в сценарии для отображения сообщения для пользователя сообщение отображается на языке пользовательского интерфейса пользователя.</span><span class="sxs-lookup"><span data-stu-id="c226e-112">When you use the local variable in the script to display a user message, the message appears in the user's UI language.</span></span>

<span data-ttu-id="c226e-113">Для указания дополнительного языка и региональных параметров пользовательского интерфейса, пути и имени файла, а также для добавления поддерживаемых команд и отключения сообщений об ошибке (которые появляются, если не найдены PSD1-файлы) можно использовать параметры командлета **Import-LocalizedData** .</span><span class="sxs-lookup"><span data-stu-id="c226e-113">You can use the parameters of **Import-LocalizedData** to specify an alternate UI culture, path, and file name, to add supported commands, and to suppress the error message that appears if the .psd1 files are not found.</span></span>

<span data-ttu-id="c226e-114">Командлет **Import-LocalizedData** поддерживает инициативу интернационализации сценариев, которая была представлена в Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="c226e-114">The **Import-LocalizedData** cmdlet supports the script internationalization initiative that was introduced in Windows PowerShell 2.0.</span></span>
<span data-ttu-id="c226e-115">Целью этой инициативы является повышение качества обслуживания пользователей по всему миру благодаря упрощению написания сценариев для отображения сообщений для пользователя на языке интерфейса текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c226e-115">This initiative aims to better serve users worldwide by making it easy for scripts to display user messages in the UI language of the current user.</span></span>
<span data-ttu-id="c226e-116">Дополнительные сведения об этом и формате psd1ных файлов см. в разделе about_Script_Internationalization.</span><span class="sxs-lookup"><span data-stu-id="c226e-116">For more information about this and about the format of the .psd1 files, see about_Script_Internationalization.</span></span>

## <span data-ttu-id="c226e-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="c226e-117">EXAMPLES</span></span>

### <span data-ttu-id="c226e-118">Пример 1. Импорт текстовых строк</span><span class="sxs-lookup"><span data-stu-id="c226e-118">Example 1: Import text strings</span></span>

```
PS C:\> Import-LocalizedData -BindingVariable "Messages"
```

<span data-ttu-id="c226e-119">Эта команда импортирует текстовые строки в переменную $Messages.</span><span class="sxs-lookup"><span data-stu-id="c226e-119">This command imports text strings into the $Messages variable.</span></span>
<span data-ttu-id="c226e-120">Она использует значения по умолчанию для всех остальных параметров командлета.</span><span class="sxs-lookup"><span data-stu-id="c226e-120">It uses the default values of all other cmdlet parameters.</span></span>

<span data-ttu-id="c226e-121">Если команда включена в сценарий Archives.ps1 в каталоге C:\Test, и значение автоматической переменной $PsUICulture — zh-CN, командлет **Import-LocalizedData** импортирует файл Archives.psd1 в каталоге C:\test\zh-CN в переменную $Messages.</span><span class="sxs-lookup"><span data-stu-id="c226e-121">If the command is included in the Archives.ps1 script in the C:\Test directory, and the value of the $PsUICulture automatic variable is zh-CN, **Import-LocalizedData** imports the Archives.psd1 file in the C:\test\zh-CN directory into the $Messages variable.</span></span>

### <span data-ttu-id="c226e-122">Пример 2. Импорт локализованных строк данных</span><span class="sxs-lookup"><span data-stu-id="c226e-122">Example 2: Import localized data strings</span></span>

```
PS C:\> Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"

Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

<span data-ttu-id="c226e-123">Эта команда выполняется из командной строки; а не в сценарии.</span><span class="sxs-lookup"><span data-stu-id="c226e-123">This command is run at the command line; not in a script.</span></span>
<span data-ttu-id="c226e-124">Он получает локализованные строки данных из файла Test.psd1 и отображает их в командной строке.</span><span class="sxs-lookup"><span data-stu-id="c226e-124">It gets localized data strings from the Test.psd1 file and displays them at the command line.</span></span>
<span data-ttu-id="c226e-125">Поскольку команда не используется в сценарии, параметр *FileName* является обязательным.</span><span class="sxs-lookup"><span data-stu-id="c226e-125">Because the command is not used in a script, the *FileName* parameter is required.</span></span>
<span data-ttu-id="c226e-126">В команде используется параметр *UICulture* для указания языка и региональных параметров en-US.</span><span class="sxs-lookup"><span data-stu-id="c226e-126">The command uses the *UICulture* parameter to specify the en-US culture.</span></span>

<span data-ttu-id="c226e-127">Командлет **Import-локализеддата** Возвращает хэш-таблицу, содержащую локализованные строки данных.</span><span class="sxs-lookup"><span data-stu-id="c226e-127">**Import-LocalizedData** returns a hash table that contains the localized data strings.</span></span>

### <span data-ttu-id="c226e-128">Пример 3. Импорт строк языка и региональных параметров пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c226e-128">Example 3: Import UI culture strings</span></span>

```
PS C:\> Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

<span data-ttu-id="c226e-129">Эта команда импортирует текстовые строки в переменную $MsgTbl скрипта.</span><span class="sxs-lookup"><span data-stu-id="c226e-129">This command imports text strings into the $MsgTbl variable of a script.</span></span>

<span data-ttu-id="c226e-130">Она использует параметр *UICulture* , чтобы дать командлету указание импортировать данные из файла Simple.psd1 в подкаталог ar-SA каталога C:\Data\Localized.</span><span class="sxs-lookup"><span data-stu-id="c226e-130">It uses the *UICulture* parameter to direct the cmdlet to import data from the Simple.psd1 file in the ar-SA subdirectory of C:\Data\Localized.</span></span>

### <span data-ttu-id="c226e-131">Пример 4. Импорт локализованных данных в скрипт</span><span class="sxs-lookup"><span data-stu-id="c226e-131">Example 4: Import localized data into a script</span></span>

```
PS C:\> # In C:\Test\en-US\Test.psd1:

ConvertFrom-StringData @'

# English strings

Msg1 = "The Name parameter is missing from the command."
Msg2 = "This command requires the credentials of a member of the Administrators group on the computer."
Msg3 = "Use $_ to represent the object that is being processed."
'@

# In C:\Test\Test.ps1

Import-LocalizedData -BindingVariable "Messages"
Write-Host $Messages.Msg2

# In PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

<span data-ttu-id="c226e-132">В этом примере показано, как использовать локализованные данные в простом сценарии.</span><span class="sxs-lookup"><span data-stu-id="c226e-132">This example shows how to use localized data in a simple script.</span></span>

<span data-ttu-id="c226e-133">В первой части примера показано содержимое файла Test.psd1.</span><span class="sxs-lookup"><span data-stu-id="c226e-133">The first part of the example shows the contents of the Test.psd1 file.</span></span>
<span data-ttu-id="c226e-134">Он содержит команду ConvertFrom-StringData, преобразующую ряд именованных текстовых строк в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="c226e-134">It contains a ConvertFrom-StringData command that converts a series of named text strings into a hash table.</span></span>
<span data-ttu-id="c226e-135">Файл Test.psd1 находится в подкаталоге en-US каталога C:\Test, содержащего сценарий.</span><span class="sxs-lookup"><span data-stu-id="c226e-135">The Test.psd1 file is located in the en-US subdirectory of the C:\Test directory that contains the script.</span></span>

<span data-ttu-id="c226e-136">Во второй части примера показано содержимое сценария Test.ps1.</span><span class="sxs-lookup"><span data-stu-id="c226e-136">The second part of the example shows the contents of the Test.ps1 script.</span></span>
<span data-ttu-id="c226e-137">Он содержит команду **Import-локализеддата** , которая импортирует данные из соответствующего PSD1-файла в переменную $messages и команду Write-Host, записывающую одно из сообщений в $Messagesую переменную в главное приложение.</span><span class="sxs-lookup"><span data-stu-id="c226e-137">It contains an **Import-LocalizedData** command that imports the data from the matching .psd1 file into the $Messages variable and a Write-Host command that writes one of the messages in the $Messages variable to the host program.</span></span>

<span data-ttu-id="c226e-138">В последней части примера выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="c226e-138">The last part of the example runs the script.</span></span>
<span data-ttu-id="c226e-139">Выходные данные показывают, что отображается правильное сообщение для пользователя на языке пользовательского интерфейса, заданном для текущего пользователя операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c226e-139">The output shows that it displays the correct user message in the UI language set for the current user of the operating system.</span></span>

### <span data-ttu-id="c226e-140">Пример 5. Замена текстовых строк по умолчанию в скрипте</span><span class="sxs-lookup"><span data-stu-id="c226e-140">Example 5: Replace default text strings in a script</span></span>

```
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@ }
Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

<span data-ttu-id="c226e-141">В этом примере показано, как использовать командлет **Import-LocalizedData** для замены текстовых строк по умолчанию, определенных в разделе DATA сценария.</span><span class="sxs-lookup"><span data-stu-id="c226e-141">This example shows how to use **Import-LocalizedData** to replace default text strings defined in the DATA section of a script.</span></span>

<span data-ttu-id="c226e-142">В этом примере раздел данных скрипта TestScript.ps1 содержит команду ConvertFrom-StringData, которая преобразует содержимое раздела данных в хэш-таблицу и сохраняет в значении переменной $UserMessages.</span><span class="sxs-lookup"><span data-stu-id="c226e-142">In this example, the DATA section of the TestScript.ps1 script contains a ConvertFrom-StringData command that converts the contents of the DATA section to a hash table and stores in the value of the $UserMessages variable.</span></span>

<span data-ttu-id="c226e-143">Сценарий также включает команду **Import-LocalizedData** , которая импортирует хэш-таблицу преобразованных текстовых строк из файла TestScript.psd1 в подкаталоге, указанном значением переменной $PsUICulture.</span><span class="sxs-lookup"><span data-stu-id="c226e-143">The script also includes an **Import-LocalizedData** command, which imports a hash table of translated text strings from the TestScript.psd1 file in the subdirectory specified by the value of the $PsUICulture variable.</span></span>
<span data-ttu-id="c226e-144">Если команда находит PSD1-файл, она сохраняет переведенные строки из файла в значение той же переменной $UserMessages, перезаписывая хэш-таблицу, сохраненную логикой раздела DATA.</span><span class="sxs-lookup"><span data-stu-id="c226e-144">If the command finds the .psd1 file, it saves the translated strings from the file in the value of the same $UserMessages variable, overwriting the hash table saved by the DATA section logic.</span></span>

<span data-ttu-id="c226e-145">Третья команда отображает первое сообщение в переменной $UserMessages.</span><span class="sxs-lookup"><span data-stu-id="c226e-145">The third command displays the first message in the $UserMessages variable.</span></span>

<span data-ttu-id="c226e-146">Если команда **Import-LocalizedData** находит PSD1-файл для языка $PsUICulture, значение переменной $UserMessages содержит переведенные текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="c226e-146">If the **Import-LocalizedData** command finds a .psd1 file for the $PsUICulture language, the value of the $UserMessages variable contains the translated text strings.</span></span>
<span data-ttu-id="c226e-147">В случае сбоя команды по какой-либо причине команда отображает текстовые строки по умолчанию, определенные в разделе DATA сценария.</span><span class="sxs-lookup"><span data-stu-id="c226e-147">If the command fails for any reason, the command displays the default text strings defined in the DATA section of the script.</span></span>

### <span data-ttu-id="c226e-148">Пример 6. Отключение сообщений об ошибках, если культура пользовательского интерфейса не найдена</span><span class="sxs-lookup"><span data-stu-id="c226e-148">Example 6: Suppress error messages if the UI culture is not found</span></span>

```
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday PS C:\> .\Day2.ps1
Today is Tuesday
```

<span data-ttu-id="c226e-149">В этом примере показано, как отключить сообщения об ошибках, которые появляются, если командлет **Import-LocalizedData** не может найти каталоги, которые соответствуют языку и региональным параметрам пользовательского интерфейса текущего пользователя, или PSD1-файл для сценария в этих каталогах.</span><span class="sxs-lookup"><span data-stu-id="c226e-149">This example shows how to suppress the error messages that appear when **Import-LocalizedData** cannot find the directories that match the user's UI culture or cannot find a .psd1 file for the script in those directories.</span></span>

<span data-ttu-id="c226e-150">Для отключения сообщений об ошибке можно использовать общий параметр *ErrorAction* со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="c226e-150">You can use the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the error message.</span></span>
<span data-ttu-id="c226e-151">Это особенно удобно, если вы предоставили пользовательские сообщения на языке по умолчанию или на резервной, и сообщение об ошибке не требуется.</span><span class="sxs-lookup"><span data-stu-id="c226e-151">This is especially useful when you have provided user messages in a default or fallback language, and no error message is needed.</span></span>

<span data-ttu-id="c226e-152">В этом примере сравниваются два сценария, Day1.ps1 и Day2.ps1, которые включают команду **Import-LocalizedData** .</span><span class="sxs-lookup"><span data-stu-id="c226e-152">This example compares two scripts, Day1.ps1 and Day2.ps1, that include an **Import-LocalizedData** command.</span></span>
<span data-ttu-id="c226e-153">Скрипты идентичны, за исключением того, что Day2 использует общий параметр *ErrorAction* со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="c226e-153">The scripts are identical, except that Day2 uses the *ErrorAction* common parameter with a value of SilentlyContinue.</span></span>

<span data-ttu-id="c226e-154">Пример вывода показывает результаты выполнения обоих сценариев, если для языка и региональных параметров пользовательского интерфейса задано значение fr-BE, и для этого языка и параметров интерфейса не найдены соответствующие файлы или каталоги.</span><span class="sxs-lookup"><span data-stu-id="c226e-154">The sample output shows the results of running both scripts when the UI culture is set to fr-BE and there are no matching files or directories for that UI culture.</span></span>
<span data-ttu-id="c226e-155">Day1.ps1 отображает сообщение об ошибке и данные на английском языке.</span><span class="sxs-lookup"><span data-stu-id="c226e-155">Day1.ps1 displays an error message and English output.</span></span>
<span data-ttu-id="c226e-156">Day2.ps1 отображает только данные на английском языке.</span><span class="sxs-lookup"><span data-stu-id="c226e-156">Day2.ps1 just displays the English output.</span></span>

## <span data-ttu-id="c226e-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c226e-157">PARAMETERS</span></span>

### <span data-ttu-id="c226e-158">-Баседиректори</span><span class="sxs-lookup"><span data-stu-id="c226e-158">-BaseDirectory</span></span>

<span data-ttu-id="c226e-159">Указывает базовый каталог, в котором находятся PSD1-файлы</span><span class="sxs-lookup"><span data-stu-id="c226e-159">Specifies the base directory where the .psd1 files are located.</span></span>
<span data-ttu-id="c226e-160">По умолчанию используется каталог, в котором расположен сценарий.</span><span class="sxs-lookup"><span data-stu-id="c226e-160">The default is the directory where the script is located.</span></span>
<span data-ttu-id="c226e-161">**Import-LocalizedData** выполняет поиск PSD1-файлов для сценария во вложенных подкаталогах базового каталога, определяемых языком.</span><span class="sxs-lookup"><span data-stu-id="c226e-161">**Import-LocalizedData** searches for the .psd1 file for the script in a language-specific subdirectory of the base directory.</span></span>

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

### <span data-ttu-id="c226e-162">-Биндингвариабле</span><span class="sxs-lookup"><span data-stu-id="c226e-162">-BindingVariable</span></span>

<span data-ttu-id="c226e-163">Задает переменную, в которую импортируются текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="c226e-163">Specifies the variable into which the text strings are imported.</span></span>
<span data-ttu-id="c226e-164">Введите имя переменной без знака доллара ($).</span><span class="sxs-lookup"><span data-stu-id="c226e-164">Enter a variable name without a dollar sign ($).</span></span>

<span data-ttu-id="c226e-165">В Windows PowerShell 2.0 этот параметр является обязательным.</span><span class="sxs-lookup"><span data-stu-id="c226e-165">In Windows PowerShell 2.0, this parameter is required.</span></span>
<span data-ttu-id="c226e-166">В Windows PowerShell 3.0 этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c226e-166">In Windows PowerShell 3.0, this parameter is optional.</span></span>
<span data-ttu-id="c226e-167">Если опустить этот параметр, командлет **Import-LocalizedData** возвращает хэш-таблицу текстовых строк.</span><span class="sxs-lookup"><span data-stu-id="c226e-167">If you omit this parameter, **Import-LocalizedData** returns a hash table of the text strings.</span></span>
<span data-ttu-id="c226e-168">Хэш-таблица передается по конвейеру или отображается в командной строке.</span><span class="sxs-lookup"><span data-stu-id="c226e-168">The hash table is passed down the pipeline or displayed at the command line.</span></span>

<span data-ttu-id="c226e-169">При использовании **Import-LocalizedData** для замены текстовых строк по умолчанию, указанных в разделе DATA сценария, назначьте раздел DATA переменной и введите имя переменной раздела DATA в значение параметра *BindingVariable* .</span><span class="sxs-lookup"><span data-stu-id="c226e-169">When using **Import-LocalizedData** to replace default text strings specified in the DATA section of a script, assign the DATA section to a variable and enter the name of the DATA section variable in the value of the *BindingVariable* parameter.</span></span>
<span data-ttu-id="c226e-170">Затем, когда командлет **Import-LocalizedData** сохранит импортированное содержимое в *BindingVariable* , импортированные данные будут заменены текстовыми строками по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c226e-170">Then, when **Import-LocalizedData** saves the imported content in the *BindingVariable* , the imported data will replace the default text strings.</span></span>
<span data-ttu-id="c226e-171">Если вы не указываете текстовые строки по умолчанию, можно выбрать любое имя переменной.</span><span class="sxs-lookup"><span data-stu-id="c226e-171">If you are not specifying default text strings, you can select any variable name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Variable

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c226e-172">-FileName</span><span class="sxs-lookup"><span data-stu-id="c226e-172">-FileName</span></span>

<span data-ttu-id="c226e-173">Задает имя файла данных (PSD1) для импорта.</span><span class="sxs-lookup"><span data-stu-id="c226e-173">Specifies the name of the data file (.psd1) to be imported.</span></span>
<span data-ttu-id="c226e-174">Введите имя файла.</span><span class="sxs-lookup"><span data-stu-id="c226e-174">Enter a file name.</span></span>
<span data-ttu-id="c226e-175">Можно указать имя файла, которое не включает расширение имени файла (PSD1), или имя файла, включающее его.</span><span class="sxs-lookup"><span data-stu-id="c226e-175">You can specify a file name that does not include its .psd1 file name extension, or you can specify the file name including the .psd1 file name extension.</span></span>

<span data-ttu-id="c226e-176">Параметр *FileName* является обязательным, если командлет **Import-LocalizedData** не используется в сценарии.</span><span class="sxs-lookup"><span data-stu-id="c226e-176">The *FileName* parameter is required when **Import-LocalizedData** is not used in a script.</span></span>
<span data-ttu-id="c226e-177">В противном случае параметр является необязательным, и значение по умолчанию — базовое имя сценария.</span><span class="sxs-lookup"><span data-stu-id="c226e-177">Otherwise, the parameter is optional and the default value is the base name of the script.</span></span>
<span data-ttu-id="c226e-178">Этот параметр можно использовать для отправки командлету **Import-LocalizedData** указания найти данные для другого PSD1-файла.</span><span class="sxs-lookup"><span data-stu-id="c226e-178">You can use this parameter to direct **Import-LocalizedData** to search for a different .psd1 file.</span></span>

<span data-ttu-id="c226e-179">Например, если имя *файла* не указано и сценарий имеет FindFiles.ps1, то **Import-локализеддата** ищет файл данных FindFiles.psd1.</span><span class="sxs-lookup"><span data-stu-id="c226e-179">For example, if the *FileName* is omitted and the script name is FindFiles.ps1, **Import-LocalizedData** searches for the FindFiles.psd1 data file.</span></span>

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

### <span data-ttu-id="c226e-180">-Суппортедкомманд</span><span class="sxs-lookup"><span data-stu-id="c226e-180">-SupportedCommand</span></span>

<span data-ttu-id="c226e-181">Задает командлеты и функции, которые создают только данные.</span><span class="sxs-lookup"><span data-stu-id="c226e-181">Specifies cmdlets and functions that generate only data.</span></span>

<span data-ttu-id="c226e-182">Используйте этот параметр для включения командлетов и функций, которые вы написали или протестировали.</span><span class="sxs-lookup"><span data-stu-id="c226e-182">Use this parameter to include cmdlets and functions that you have written or tested.</span></span>
<span data-ttu-id="c226e-183">Дополнительные сведения см. в разделе about_Script_Internationalization.</span><span class="sxs-lookup"><span data-stu-id="c226e-183">For more information, see about_Script_Internationalization.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c226e-184">-UICulture</span><span class="sxs-lookup"><span data-stu-id="c226e-184">-UICulture</span></span>

<span data-ttu-id="c226e-185">Указывает дополнительный язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c226e-185">Specifies an alternate UI culture.</span></span>
<span data-ttu-id="c226e-186">Значение по умолчанию — значение автоматической переменной $PsUICulture.</span><span class="sxs-lookup"><span data-stu-id="c226e-186">The default is the value of the $PsUICulture automatic variable.</span></span>
<span data-ttu-id="c226e-187">Введите язык и региональные параметры пользовательского интерфейса в \<language\> - \<region\> формате, например en-US, de-de или AR-SA.</span><span class="sxs-lookup"><span data-stu-id="c226e-187">Enter a UI culture in \<language\>-\<region\> format, such as en-US, de-DE, or ar-SA.</span></span>

<span data-ttu-id="c226e-188">Значение параметра *UICulture* определяет зависящий от языка подкаталог (в пределах базового каталога), из которого командлет **Import-LocalizedData** получает PSD1-файл для сценария.</span><span class="sxs-lookup"><span data-stu-id="c226e-188">The value of the *UICulture* parameter determines the language-specific subdirectory (within the base directory) from which **Import-LocalizedData** gets the .psd1 file for the script.</span></span>

<span data-ttu-id="c226e-189">Командлет выполняет поиск подкаталога с тем же именем, что и значение параметра *UICulture* , или $PsUICultureую автоматическую переменную, например DE-de или AR-SA.</span><span class="sxs-lookup"><span data-stu-id="c226e-189">The cmdlet searches for a subdirectory with the same name as the value of the *UICulture* parameter or the $PsUICulture automatic variable, such as de-DE or ar-SA.</span></span>
<span data-ttu-id="c226e-190">Если не удается найти каталог или каталог не содержит PSD1-файл для скрипта, он ищет подкаталог с именем кода языка, например de или AR.</span><span class="sxs-lookup"><span data-stu-id="c226e-190">If it cannot find the directory, or the directory does not contain a .psd1 file for the script, it searches for a subdirectory with the name of the language code, such as de or ar.</span></span>
<span data-ttu-id="c226e-191">Если не удается найти подкаталог или PSD1-файл, команда завершается ошибкой, и данные отображаются на языке по умолчанию, указанном в сценарии.</span><span class="sxs-lookup"><span data-stu-id="c226e-191">If it cannot find the subdirectory or .psd1 file, the command fails and the data is displayed in the default language specified in the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c226e-192">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c226e-192">CommonParameters</span></span>

<span data-ttu-id="c226e-193">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c226e-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c226e-194">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c226e-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c226e-195">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c226e-195">INPUTS</span></span>

### <span data-ttu-id="c226e-196">Нет</span><span class="sxs-lookup"><span data-stu-id="c226e-196">None</span></span>

<span data-ttu-id="c226e-197">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="c226e-197">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c226e-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c226e-198">OUTPUTS</span></span>

### <span data-ttu-id="c226e-199">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="c226e-199">System.Collections.Hashtable</span></span>

<span data-ttu-id="c226e-200">Командлет **Import-локализеддата** сохраняет хэш-таблицу в переменной, заданной значением параметра **биндингвариабле** .</span><span class="sxs-lookup"><span data-stu-id="c226e-200">**Import-LocalizedData** saves the hash table in the variable that is specified by the value of the **BindingVariable** parameter.</span></span>

## <span data-ttu-id="c226e-201">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c226e-201">NOTES</span></span>

* <span data-ttu-id="c226e-202">Перед использованием командлета **Import-LocalizedData** осуществите локализацию сообщений для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c226e-202">Before using **Import-LocalizedData** , localize your user messages.</span></span> <span data-ttu-id="c226e-203">Форматируйте сообщения для каждого языкового стандарта (языка и региональных параметров интерфейса) в хэш-таблицу пар "ключ-значение" и сохраните хэш-таблицу в файл с тем же именем, что и сценарий и расширение имени PSD1-файла.</span><span class="sxs-lookup"><span data-stu-id="c226e-203">Format the messages for each locale (UI culture) in a hash table of key/value pairs, and save the hash table in a file with the same name as the script and a .psd1 file name extension.</span></span> <span data-ttu-id="c226e-204">Создайте в каталоге сценария каталог для каждого поддерживаемого языка и региональных параметров пользовательского интерфейса и сохраните PSD1-файл для каждого языка интерфейса в каталоге с именем языка и региональных параметров данного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c226e-204">Create a directory under the script directory for each supported UI culture, and then save the .psd1 file for each UI culture in the directory with the UI culture name.</span></span>

  <span data-ttu-id="c226e-205">Например, выполните локализацию сообщений для пользователя для языкового стандарта de-DE и форматируйте их в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="c226e-205">For example, localize your user messages for the de-DE locale and format them in a hash table.</span></span>
<span data-ttu-id="c226e-206">Сохраните хэш-таблицу в файл \<ScriptName\>.psd1.</span><span class="sxs-lookup"><span data-stu-id="c226e-206">Save the hash table in a \<ScriptName\>.psd1 file.</span></span>
<span data-ttu-id="c226e-207">Затем создайте подкаталог de-DE в каталоге сценария и сохраните файл \<ScriptName\>.psd1 для de-DE в подкаталоге de-DE.</span><span class="sxs-lookup"><span data-stu-id="c226e-207">Then create a de-DE subdirectory under the script directory, and save the de-DE \<ScriptName\>.psd1 file in the de-DE subdirectory.</span></span>
<span data-ttu-id="c226e-208">Повторите эту процедуру для каждого поддерживаемого решением языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="c226e-208">Repeat this method for each locale that you support.</span></span>

* <span data-ttu-id="c226e-209">**Import-локализеддата** выполняет структурированный поиск локализованных сообщений пользователя для сценария.</span><span class="sxs-lookup"><span data-stu-id="c226e-209">**Import-LocalizedData** performs a structured search for the localized user messages for a script.</span></span>

  <span data-ttu-id="c226e-210">Командлет **Import-локализеддата** начинает поиск в каталоге, где расположен файл скрипта (или значение параметра *баседиректори* ).</span><span class="sxs-lookup"><span data-stu-id="c226e-210">**Import-LocalizedData** begins the search in the directory where the script file is located (or the value of the *BaseDirectory* parameter).</span></span>
<span data-ttu-id="c226e-211">Затем он ищет в базовом каталоге подкаталог с тем же именем, что и значение переменной $PsUICulture (или значение параметра *UICulture* ), например DE-de или AR-SA.</span><span class="sxs-lookup"><span data-stu-id="c226e-211">It then searches within the base directory for a subdirectory with the same name as the value of the $PsUICulture variable (or the value of the *UICulture* parameter), such as de-DE or ar-SA.</span></span>
<span data-ttu-id="c226e-212">Затем он выполняет в этом подкаталоге поиск PSD1-файла с тем же именем, что и имя сценария (или значение параметра *FileName* ).</span><span class="sxs-lookup"><span data-stu-id="c226e-212">Then, it searches in that subdirectory for a .psd1 file with the same name as the script (or the value of the *FileName* parameter).</span></span>

  <span data-ttu-id="c226e-213">Если **Import-локализеддата** не удается найти подкаталог с именем языка и региональных параметров пользовательского интерфейса, или подкаталог не содержит PSD1-файл для скрипта, он выполняет поиск файла. PSD1 для сценария в подкаталоге с именем кода языка, например de или AR.</span><span class="sxs-lookup"><span data-stu-id="c226e-213">If **Import-LocalizedData** cannot find a subdirectory with the name of the UI culture, or the subdirectory does not contain a .psd1 file for the script, it searches for a .psd1 file for the script in a subdirectory with the name of the language code, such as de or ar.</span></span>
<span data-ttu-id="c226e-214">Если не удается найти подкаталог или PSD1-файл, команда завершается ошибкой, данные отображаются на языке по умолчанию, указанном в сценарии, и выводится сообщение об ошибке, поясняющее, что не удалось импортировать данные.</span><span class="sxs-lookup"><span data-stu-id="c226e-214">If it cannot find the subdirectory or .psd1 file, the command fails, the data is displayed in the default language in the script, and an error message is displayed explaining that the data could not be imported.</span></span>
<span data-ttu-id="c226e-215">Чтобы отключить сообщение и корректно завершить его работу, используйте общий параметр *ErrorAction* со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="c226e-215">To suppress the message and fail gracefully, use the *ErrorAction* common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="c226e-216">Если командлет **Import-LocalizedData** находит подкаталог и PSD1-файл, он импортирует хэш-таблицу сообщения для пользователя в значение параметра *BindingVariable* в команде.</span><span class="sxs-lookup"><span data-stu-id="c226e-216">If **Import-LocalizedData** finds the subdirectory and the .psd1 file, it imports the hash table of user messages into the value of the *BindingVariable* parameter in the command.</span></span>
<span data-ttu-id="c226e-217">Затем при отображении сообщения из хэш-таблицы в переменной отображается локализованное сообщение.</span><span class="sxs-lookup"><span data-stu-id="c226e-217">Then, when you display a message from the hash table in the variable, the localized message is displayed.</span></span>

  <span data-ttu-id="c226e-218">Дополнительные сведения см. в разделе [about_Script_Internationalization](../Microsoft.PowerShell.Core/about/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="c226e-218">For more information, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/about/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="c226e-219">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c226e-219">RELATED LINKS</span></span>

[<span data-ttu-id="c226e-220">Write-Host</span><span class="sxs-lookup"><span data-stu-id="c226e-220">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="c226e-221">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="c226e-221">Import-PowerShellDataFile</span></span>](Import-PowerShellDataFile.md)
