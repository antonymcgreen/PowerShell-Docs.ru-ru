---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: fa5de857b70ec05d30c42fbf8e51a9411d823018
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603944"
---
# <span data-ttu-id="9ebff-102">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="9ebff-102">Import-LocalizedData</span></span>

## <span data-ttu-id="9ebff-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9ebff-103">SYNOPSIS</span></span>
<span data-ttu-id="9ebff-104">Импортирует данные, зависящие от языка, в сценарии и функции в зависимости от языка и региональных параметров пользовательского интерфейса, выбранного для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9ebff-104">Imports language-specific data into scripts and functions based on the UI culture that is selected for the operating system.</span></span>

## <span data-ttu-id="9ebff-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ebff-105">SYNTAX</span></span>

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="9ebff-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ebff-106">DESCRIPTION</span></span>

<span data-ttu-id="9ebff-107">`Import-LocalizedData`Командлет динамически извлекает строки из подкаталога, имя которого соответствует языку пользовательского интерфейса, заданному для текущего пользователя операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9ebff-107">The `Import-LocalizedData` cmdlet dynamically retrieves strings from a subdirectory whose name matches the UI language set for the current user of the operating system.</span></span> <span data-ttu-id="9ebff-108">Его задачей является включение сценариев для отображения сообщений для пользователей на языке пользовательского интерфейса, выбранного текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="9ebff-108">It is designed to enable scripts to display user messages in the UI language selected by the current user.</span></span>

<span data-ttu-id="9ebff-109">`Import-LocalizedData` импортирует данные из `.psd1` файлов в подкаталогах, зависящих от языка, в каталоге скрипта и сохраняет их в локальной переменной, указанной в команде.</span><span class="sxs-lookup"><span data-stu-id="9ebff-109">`Import-LocalizedData` imports data from `.psd1` files in language-specific subdirectories of the script directory and saves them in a local variable that is specified in the command.</span></span> <span data-ttu-id="9ebff-110">Командлет выбирает подкаталог и файл на основе значения `$PSUICulture` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="9ebff-110">The cmdlet selects the subdirectory and file based on the value of the `$PSUICulture` automatic variable.</span></span> <span data-ttu-id="9ebff-111">При использовании локальной переменной в сценарии для отображения сообщения для пользователя сообщение отображается на языке пользовательского интерфейса пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ebff-111">When you use the local variable in the script to display a user message, the message appears in the user's UI language.</span></span>

<span data-ttu-id="9ebff-112">Параметры можно использовать `Import-LocalizedData` для указания альтернативного языка и региональных параметров пользовательского интерфейса, пути и имени файла, добавления поддерживаемых команд и подавления сообщения об ошибке, которое появляется, если `.psd1` файлы не найдены.</span><span class="sxs-lookup"><span data-stu-id="9ebff-112">You can use the parameters of `Import-LocalizedData` to specify an alternate UI culture, path, and filename, to add supported commands, and to suppress the error message that appears if the `.psd1` files are not found.</span></span>

<span data-ttu-id="9ebff-113">`Import-LocalizedData`Командлет поддерживает инициативы по многоязыковой поддержке сценариев, которая появилась в Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="9ebff-113">The `Import-LocalizedData` cmdlet supports the script internationalization initiative that was introduced in Windows PowerShell 2.0.</span></span> <span data-ttu-id="9ebff-114">Целью этой инициативы является повышение качества обслуживания пользователей по всему миру благодаря упрощению написания сценариев для отображения сообщений для пользователя на языке интерфейса текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ebff-114">This initiative aims to better serve users worldwide by making it easy for scripts to display user messages in the UI language of the current user.</span></span> <span data-ttu-id="9ebff-115">Дополнительные сведения об этом и формате `.psd1` файлов см. в разделе [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="9ebff-115">For more information about this and about the format of the `.psd1` files, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="9ebff-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="9ebff-116">EXAMPLES</span></span>

### <span data-ttu-id="9ebff-117">Пример 1. Импорт текстовых строк</span><span class="sxs-lookup"><span data-stu-id="9ebff-117">Example 1: Import text strings</span></span>

<span data-ttu-id="9ebff-118">В этом примере текстовые строки импортируются в `$Messages` переменную.</span><span class="sxs-lookup"><span data-stu-id="9ebff-118">This example imports text strings into the `$Messages` variable.</span></span> <span data-ttu-id="9ebff-119">Она использует значения по умолчанию для всех остальных параметров командлета.</span><span class="sxs-lookup"><span data-stu-id="9ebff-119">It uses the default values of all other cmdlet parameters.</span></span>

```powershell
Import-LocalizedData -BindingVariable "Messages"
```

<span data-ttu-id="9ebff-120">Если команда включена в скрипт Archives.ps1 в `C:\Test` каталоге, а значение `$PsUICulture` автоматической переменной — zh-CN, `Import-LocalizedData` импортирует `Archives.psd1` файл в `C:\test\zh-CN` каталог в `$Messages` переменную.</span><span class="sxs-lookup"><span data-stu-id="9ebff-120">If the command is included in the Archives.ps1 script in the `C:\Test` directory, and the value of the `$PsUICulture` automatic variable is zh-CN, `Import-LocalizedData` imports the `Archives.psd1` file in the `C:\test\zh-CN` directory into the `$Messages` variable.</span></span>

### <span data-ttu-id="9ebff-121">Пример 2. Импорт локализованных строк данных</span><span class="sxs-lookup"><span data-stu-id="9ebff-121">Example 2: Import localized data strings</span></span>

<span data-ttu-id="9ebff-122">Этот пример выполняется в командной строке, а не в сценарии.</span><span class="sxs-lookup"><span data-stu-id="9ebff-122">This example is run at the command line not in a script.</span></span> <span data-ttu-id="9ebff-123">Он получает локализованные строки данных из файла Test.psd1 и отображает их в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9ebff-123">It gets localized data strings from the Test.psd1 file and displays them at the command line.</span></span> <span data-ttu-id="9ebff-124">Поскольку команда не используется в сценарии, параметр **FileName** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9ebff-124">Because the command is not used in a script, the **FileName** parameter is required.</span></span> <span data-ttu-id="9ebff-125">В команде используется параметр **UICulture** для указания языка и региональных параметров en-US.</span><span class="sxs-lookup"><span data-stu-id="9ebff-125">The command uses the **UICulture** parameter to specify the en-US culture.</span></span>

```powershell
Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"
```

```Output
Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

<span data-ttu-id="9ebff-126">`Import-LocalizedData` Возвращает хэш-таблицу, содержащую локализованные строки данных.</span><span class="sxs-lookup"><span data-stu-id="9ebff-126">`Import-LocalizedData` returns a hash table that contains the localized data strings.</span></span>

### <span data-ttu-id="9ebff-127">Пример 3. Импорт строк языка и региональных параметров пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9ebff-127">Example 3: Import UI culture strings</span></span>

```powershell
Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

<span data-ttu-id="9ebff-128">Эта команда импортирует текстовые строки в `$MsgTbl` переменную скрипта.</span><span class="sxs-lookup"><span data-stu-id="9ebff-128">This command imports text strings into the `$MsgTbl` variable of a script.</span></span>

<span data-ttu-id="9ebff-129">Он использует параметр **UICulture** , чтобы направить командлет для импорта данных из `Simple.psd1` файла в `ar-SA` подкаталог `C:\Data\Localized` .</span><span class="sxs-lookup"><span data-stu-id="9ebff-129">It uses the **UICulture** parameter to direct the cmdlet to import data from the `Simple.psd1` file in the `ar-SA` subdirectory of `C:\Data\Localized`.</span></span>

### <span data-ttu-id="9ebff-130">Пример 4. Импорт локализованных данных в скрипт</span><span class="sxs-lookup"><span data-stu-id="9ebff-130">Example 4: Import localized data into a script</span></span>

<span data-ttu-id="9ebff-131">В этом примере показано, как использовать локализованные данные в простом сценарии.</span><span class="sxs-lookup"><span data-stu-id="9ebff-131">This example shows how to use localized data in a simple script.</span></span>

```powershell
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

# In Windows PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

<span data-ttu-id="9ebff-132">В первой части примера показано содержимое `Test.psd1` файла.</span><span class="sxs-lookup"><span data-stu-id="9ebff-132">The first part of the example shows the contents of the `Test.psd1` file.</span></span> <span data-ttu-id="9ebff-133">Он содержит `ConvertFrom-StringData` команду, преобразующую ряд именованных текстовых строк в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="9ebff-133">It contains a `ConvertFrom-StringData` command that converts a series of named text strings into a hash table.</span></span> <span data-ttu-id="9ebff-134">`Test.psd1`Файл находится в подкаталоге en-US `C:\Test` каталога, который содержит скрипт.</span><span class="sxs-lookup"><span data-stu-id="9ebff-134">The `Test.psd1` file is located in the en-US subdirectory of the `C:\Test` directory that contains the script.</span></span>

<span data-ttu-id="9ebff-135">Во второй части примера показано содержимое `Test.ps1` скрипта.</span><span class="sxs-lookup"><span data-stu-id="9ebff-135">The second part of the example shows the contents of the `Test.ps1` script.</span></span> <span data-ttu-id="9ebff-136">Он содержит `Import-LocalizedData` команду, которая импортирует данные из соответствующего `.psd1` файла в `$Messages` переменную и `Write-Host` команду, записывающую одно из сообщений `$Messages` переменной в программу размещения.</span><span class="sxs-lookup"><span data-stu-id="9ebff-136">It contains an `Import-LocalizedData` command that imports the data from the matching `.psd1` file into the `$Messages` variable and a `Write-Host` command that writes one of the messages in the `$Messages` variable to the host program.</span></span>

<span data-ttu-id="9ebff-137">В последней части примера выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ebff-137">The last part of the example runs the script.</span></span> <span data-ttu-id="9ebff-138">Выходные данные показывают, что отображается правильное сообщение для пользователя на языке пользовательского интерфейса, заданном для текущего пользователя операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9ebff-138">The output shows that it displays the correct user message in the UI language set for the current user of the operating system.</span></span>

### <span data-ttu-id="9ebff-139">Пример 5. Замена текстовых строк по умолчанию в скрипте</span><span class="sxs-lookup"><span data-stu-id="9ebff-139">Example 5: Replace default text strings in a script</span></span>

<span data-ttu-id="9ebff-140">В этом примере показано, как использовать `Import-LocalizedData` для замены текстовых строк по умолчанию, определенных в разделе данных скрипта.</span><span class="sxs-lookup"><span data-stu-id="9ebff-140">This example shows how to use `Import-LocalizedData` to replace default text strings defined in the DATA section of a script.</span></span>

```powershell
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@
}

Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

<span data-ttu-id="9ebff-141">В этом примере раздел данных скрипта TestScript.ps1 содержит `ConvertFrom-StringData` команду, преобразующую содержимое раздела данных в хэш-таблицу и сохраняющую в значении `$UserMessages` переменной.</span><span class="sxs-lookup"><span data-stu-id="9ebff-141">In this example, the DATA section of the TestScript.ps1 script contains a `ConvertFrom-StringData` command that converts the contents of the DATA section to a hash table and stores in the value of the `$UserMessages` variable.</span></span>

<span data-ttu-id="9ebff-142">Скрипт также включает `Import-LocalizedData` команду, которая импортирует хэш-таблицу переведенных текстовых строк из файла TestScript.psd1 в подкаталоге, заданном значением `$PsUICulture` переменной.</span><span class="sxs-lookup"><span data-stu-id="9ebff-142">The script also includes an `Import-LocalizedData` command, which imports a hash table of translated text strings from the TestScript.psd1 file in the subdirectory specified by the value of the `$PsUICulture` variable.</span></span> <span data-ttu-id="9ebff-143">Если команда находит `.psd1` файл, то она сохраняет переведенные строки из файла в значении той же `$UserMessages` переменной, перезаписывая хэш-таблицу, сохраненную логикой раздела данных.</span><span class="sxs-lookup"><span data-stu-id="9ebff-143">If the command finds the `.psd1` file, it saves the translated strings from the file in the value of the same `$UserMessages` variable, overwriting the hash table saved by the DATA section logic.</span></span>

<span data-ttu-id="9ebff-144">Третья команда отображает первое сообщение в `$UserMessages` переменной.</span><span class="sxs-lookup"><span data-stu-id="9ebff-144">The third command displays the first message in the `$UserMessages` variable.</span></span>

<span data-ttu-id="9ebff-145">Если `Import-LocalizedData` команда находит `.psd1` файл для `$PsUICulture` языка, значение `$UserMessages` переменной содержит переведенные текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="9ebff-145">If the `Import-LocalizedData` command finds a `.psd1` file for the `$PsUICulture` language, the value of the `$UserMessages` variable contains the translated text strings.</span></span> <span data-ttu-id="9ebff-146">В случае сбоя команды по какой-либо причине команда отображает текстовые строки по умолчанию, определенные в разделе DATA сценария.</span><span class="sxs-lookup"><span data-stu-id="9ebff-146">If the command fails for any reason, the command displays the default text strings defined in the DATA section of the script.</span></span>

### <span data-ttu-id="9ebff-147">Пример 6. Отключение сообщений об ошибках, если культура пользовательского интерфейса не найдена</span><span class="sxs-lookup"><span data-stu-id="9ebff-147">Example 6: Suppress error messages if the UI culture is not found</span></span>

<span data-ttu-id="9ebff-148">В этом примере показано, как подавлять сообщения об ошибках, отображаемые, когда `Import-LocalizedData` не удается найти каталоги, соответствующие культуре пользовательского интерфейса пользователя, или не удается найти `.psd1` файл для скрипта в этих каталогах.</span><span class="sxs-lookup"><span data-stu-id="9ebff-148">This example shows how to suppress the error messages that appear when `Import-LocalizedData` cannot find the directories that match the user's UI culture or cannot find a `.psd1` file for the script in those directories.</span></span>

```powershell
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday

PS C:\> .\Day2.ps1
Today is Tuesday
```

<span data-ttu-id="9ebff-149">Для отключения сообщений об ошибке можно использовать общий параметр **ErrorAction** со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="9ebff-149">You can use the **ErrorAction** common parameter with a value of SilentlyContinue to suppress the error message.</span></span> <span data-ttu-id="9ebff-150">Это особенно удобно, если вы предоставили пользовательские сообщения на языке по умолчанию или на резервной, и сообщение об ошибке не требуется.</span><span class="sxs-lookup"><span data-stu-id="9ebff-150">This is especially useful when you have provided user messages in a default or fallback language, and no error message is needed.</span></span>

<span data-ttu-id="9ebff-151">В этом примере сравниваются два скрипта `Day1.ps1` и Day2.ps1, которые включают `Import-LocalizedData` команду.</span><span class="sxs-lookup"><span data-stu-id="9ebff-151">This example compares two scripts, `Day1.ps1` and Day2.ps1, that include an `Import-LocalizedData` command.</span></span> <span data-ttu-id="9ebff-152">Скрипты идентичны, за исключением того, что Day2 использует общий параметр **ErrorAction** со значением `SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="9ebff-152">The scripts are identical, except that Day2 uses the **ErrorAction** common parameter with a value of `SilentlyContinue`.</span></span>

<span data-ttu-id="9ebff-153">В примере выходных данных показаны результаты выполнения обоих скриптов, если для языка и региональных параметров пользовательского интерфейса задано значение, `fr-BE` а для этого языка и региональных параметров пользовательского интерфейса нет соответствующих файлов или каталогов.</span><span class="sxs-lookup"><span data-stu-id="9ebff-153">The sample output shows the results of running both scripts when the UI culture is set to `fr-BE` and there are no matching files or directories for that UI culture.</span></span> <span data-ttu-id="9ebff-154">`Day1.ps1` Отображает сообщение об ошибке и вывод на английском языке.</span><span class="sxs-lookup"><span data-stu-id="9ebff-154">`Day1.ps1` displays an error message and English output.</span></span> <span data-ttu-id="9ebff-155">`Day2.ps1` просто отображает вывод на английском языке.</span><span class="sxs-lookup"><span data-stu-id="9ebff-155">`Day2.ps1` just displays the English output.</span></span>

## <span data-ttu-id="9ebff-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ebff-156">PARAMETERS</span></span>

### <span data-ttu-id="9ebff-157">-Баседиректори</span><span class="sxs-lookup"><span data-stu-id="9ebff-157">-BaseDirectory</span></span>

<span data-ttu-id="9ebff-158">Указывает базовый каталог, в котором `.psd1` находятся файлы.</span><span class="sxs-lookup"><span data-stu-id="9ebff-158">Specifies the base directory where the `.psd1` files are located.</span></span> <span data-ttu-id="9ebff-159">По умолчанию используется каталог, в котором расположен сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ebff-159">The default is the directory where the script is located.</span></span> <span data-ttu-id="9ebff-160">`Import-LocalizedData` выполняет поиск `.psd1` файла скрипта в подкаталоге конкретного языка базового каталога.</span><span class="sxs-lookup"><span data-stu-id="9ebff-160">`Import-LocalizedData` searches for the `.psd1` file for the script in a language-specific subdirectory of the base directory.</span></span>

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

### <span data-ttu-id="9ebff-161">-Биндингвариабле</span><span class="sxs-lookup"><span data-stu-id="9ebff-161">-BindingVariable</span></span>

<span data-ttu-id="9ebff-162">Задает переменную, в которую импортируются текстовые строки.</span><span class="sxs-lookup"><span data-stu-id="9ebff-162">Specifies the variable into which the text strings are imported.</span></span> <span data-ttu-id="9ebff-163">Введите имя переменной без знака доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="9ebff-163">Enter a variable name without a dollar sign (`$`).</span></span>

<span data-ttu-id="9ebff-164">В Windows PowerShell 2.0 этот параметр является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9ebff-164">In Windows PowerShell 2.0, this parameter is required.</span></span> <span data-ttu-id="9ebff-165">В Windows PowerShell 3.0 этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9ebff-165">In Windows PowerShell 3.0, this parameter is optional.</span></span> <span data-ttu-id="9ebff-166">Если опустить этот параметр, `Import-LocalizedData` возвращает хэш-таблицу текстовых строк.</span><span class="sxs-lookup"><span data-stu-id="9ebff-166">If you omit this parameter, `Import-LocalizedData` returns a hash table of the text strings.</span></span> <span data-ttu-id="9ebff-167">Хэш-таблица передается по конвейеру или отображается в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9ebff-167">The hash table is passed down the pipeline or displayed at the command line.</span></span>

<span data-ttu-id="9ebff-168">При использовании `Import-LocalizedData` для замены текстовых строк по умолчанию, указанных в разделе данных скрипта, назначьте раздел данных переменной и введите имя переменной раздела данных в значении параметра **биндингвариабле** .</span><span class="sxs-lookup"><span data-stu-id="9ebff-168">When using `Import-LocalizedData` to replace default text strings specified in the DATA section of a script, assign the DATA section to a variable and enter the name of the DATA section variable in the value of the **BindingVariable** parameter.</span></span> <span data-ttu-id="9ebff-169">Затем при `Import-LocalizedData` сохранении импортированного содержимого в **биндингвариабле** импортированные данные заменят текстовые строки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ebff-169">Then, when `Import-LocalizedData` saves the imported content in the **BindingVariable**, the imported data will replace the default text strings.</span></span> <span data-ttu-id="9ebff-170">Если вы не указываете текстовые строки по умолчанию, можно выбрать любое имя переменной.</span><span class="sxs-lookup"><span data-stu-id="9ebff-170">If you are not specifying default text strings, you can select any variable name.</span></span>

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

### <span data-ttu-id="9ebff-171">-FileName</span><span class="sxs-lookup"><span data-stu-id="9ebff-171">-FileName</span></span>

<span data-ttu-id="9ebff-172">Указывает имя файла данных ( `.psd1)` для импорта).</span><span class="sxs-lookup"><span data-stu-id="9ebff-172">Specifies the name of the data file (`.psd1)` to be imported.</span></span> <span data-ttu-id="9ebff-173">Введите имя файла.</span><span class="sxs-lookup"><span data-stu-id="9ebff-173">Enter a file name.</span></span> <span data-ttu-id="9ebff-174">Можно указать имя файла, который не включает `.psd1` расширение имени файла, или можно указать имя файла, включая `.psd1` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="9ebff-174">You can specify a file name that does not include its `.psd1` file name extension, or you can specify the file name including the `.psd1` file name extension.</span></span> <span data-ttu-id="9ebff-175">Файлы данных должны сохраняться в Юникоде или UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9ebff-175">Data files should be saved as Unicode or UTF-8.</span></span>

<span data-ttu-id="9ebff-176">Параметр **filename** является обязательным, если `Import-LocalizedData` не используется в скрипте.</span><span class="sxs-lookup"><span data-stu-id="9ebff-176">The **FileName** parameter is required when `Import-LocalizedData` is not used in a script.</span></span>
<span data-ttu-id="9ebff-177">В противном случае параметр является необязательным, и значение по умолчанию — базовое имя сценария.</span><span class="sxs-lookup"><span data-stu-id="9ebff-177">Otherwise, the parameter is optional and the default value is the base name of the script.</span></span> <span data-ttu-id="9ebff-178">С помощью этого параметра можно направить `Import-LocalizedData` Поиск другого `.psd1` файла.</span><span class="sxs-lookup"><span data-stu-id="9ebff-178">You can use this parameter to direct `Import-LocalizedData` to search for a different `.psd1` file.</span></span>

<span data-ttu-id="9ebff-179">Например, если имя **файла** не указано и сценарий имеет значение FindFiles.ps1, `Import-LocalizedData` выполняется поиск файла данных FindFiles.psd1.</span><span class="sxs-lookup"><span data-stu-id="9ebff-179">For example, if the **FileName** is omitted and the script name is FindFiles.ps1, `Import-LocalizedData` searches for the FindFiles.psd1 data file.</span></span>

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

### <span data-ttu-id="9ebff-180">-Суппортедкомманд</span><span class="sxs-lookup"><span data-stu-id="9ebff-180">-SupportedCommand</span></span>

<span data-ttu-id="9ebff-181">Задает командлеты и функции, которые создают только данные.</span><span class="sxs-lookup"><span data-stu-id="9ebff-181">Specifies cmdlets and functions that generate only data.</span></span>

<span data-ttu-id="9ebff-182">Используйте этот параметр для включения командлетов и функций, которые вы написали или протестировали.</span><span class="sxs-lookup"><span data-stu-id="9ebff-182">Use this parameter to include cmdlets and functions that you have written or tested.</span></span> <span data-ttu-id="9ebff-183">Дополнительные сведения см. в разделе [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="9ebff-183">For more information, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

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

### <span data-ttu-id="9ebff-184">-UICulture</span><span class="sxs-lookup"><span data-stu-id="9ebff-184">-UICulture</span></span>

<span data-ttu-id="9ebff-185">Указывает дополнительный язык и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9ebff-185">Specifies an alternate UI culture.</span></span>
<span data-ttu-id="9ebff-186">Значением по умолчанию является значение `$PsUICulture` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="9ebff-186">The default is the value of the `$PsUICulture` automatic variable.</span></span>
<span data-ttu-id="9ebff-187">Введите язык и региональные параметры пользовательского интерфейса в `<language>-<region>` формате, например `en-US` , `de-DE` или `ar-SA` .</span><span class="sxs-lookup"><span data-stu-id="9ebff-187">Enter a UI culture in `<language>-<region>` format, such as `en-US`, `de-DE`, or `ar-SA`.</span></span>

<span data-ttu-id="9ebff-188">Значение параметра **UICulture** определяет подкаталог, зависящий от языка (в базовом каталоге), из которого `Import-LocalizedData` получает `.psd1` файл для скрипта.</span><span class="sxs-lookup"><span data-stu-id="9ebff-188">The value of the **UICulture** parameter determines the language-specific subdirectory (within the base directory) from which `Import-LocalizedData` gets the `.psd1` file for the script.</span></span>

<span data-ttu-id="9ebff-189">Командлет ищет подкаталог с тем же именем, что и значение параметра **UICulture** `$PsUICulture` , или автоматически изменяемую переменную, например `de-DE` или `ar-SA` .</span><span class="sxs-lookup"><span data-stu-id="9ebff-189">The cmdlet searches for a subdirectory with the same name as the value of the **UICulture** parameter or the `$PsUICulture` automatic variable, such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="9ebff-190">Если не удается найти каталог или каталог не содержит `.psd1` файл для скрипта, он ищет подкаталог с именем кода языка, например de или AR.</span><span class="sxs-lookup"><span data-stu-id="9ebff-190">If it cannot find the directory, or the directory does not contain a `.psd1` file for the script, it searches for a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="9ebff-191">Если не удается найти подкаталог или `.psd1` файл, команда завершается ошибкой и данные отображаются на языке по умолчанию, указанном в скрипте.</span><span class="sxs-lookup"><span data-stu-id="9ebff-191">If it cannot find the subdirectory or `.psd1` file, the command fails and the data is displayed in the default language specified in the script.</span></span>

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

### <span data-ttu-id="9ebff-192">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9ebff-192">CommonParameters</span></span>

<span data-ttu-id="9ebff-193">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ebff-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ebff-194">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ebff-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ebff-195">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9ebff-195">INPUTS</span></span>

### <span data-ttu-id="9ebff-196">None</span><span class="sxs-lookup"><span data-stu-id="9ebff-196">None</span></span>

<span data-ttu-id="9ebff-197">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="9ebff-197">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9ebff-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9ebff-198">OUTPUTS</span></span>

### <span data-ttu-id="9ebff-199">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="9ebff-199">System.Collections.Hashtable</span></span>

<span data-ttu-id="9ebff-200">`Import-LocalizedData` сохраняет хэш-таблицу в переменной, заданной значением параметра **биндингвариабле** .</span><span class="sxs-lookup"><span data-stu-id="9ebff-200">`Import-LocalizedData` saves the hash table in the variable that is specified by the value of the **BindingVariable** parameter.</span></span>

## <span data-ttu-id="9ebff-201">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9ebff-201">NOTES</span></span>

- <span data-ttu-id="9ebff-202">Прежде чем использовать `Import-LocalizedData` , локализовать пользовательские сообщения.</span><span class="sxs-lookup"><span data-stu-id="9ebff-202">Before using `Import-LocalizedData`, localize your user messages.</span></span> <span data-ttu-id="9ebff-203">Отформатируйте сообщения для каждого языкового стандарта (язык и региональные параметры пользовательского интерфейса) в хэш-таблице пар "ключ-значение" и сохраните хэш-таблицу в файле с тем же именем, что и у скрипта, и `.psd1` расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="9ebff-203">Format the messages for each locale (UI culture) in a hash table of key-value pairs, and save the hash table in a file with the same name as the script and a `.psd1` file name extension.</span></span> <span data-ttu-id="9ebff-204">Создайте каталог в каталоге script для каждой поддерживаемой культуры пользовательского интерфейса, а затем сохраните `.psd1` файл для каждого языка и региональных параметров пользовательского интерфейса в каталоге с именем языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9ebff-204">Create a directory under the script directory for each supported UI culture, and then save the `.psd1` file for each UI culture in the directory with the UI culture name.</span></span>

  <span data-ttu-id="9ebff-205">Например, выполните локализацию сообщений для пользователя для языкового стандарта de-DE и форматируйте их в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="9ebff-205">For example, localize your user messages for the de-DE locale and format them in a hash table.</span></span>
  <span data-ttu-id="9ebff-206">Сохраните хэш-таблицу в `<ScriptName>.psd1` файле.</span><span class="sxs-lookup"><span data-stu-id="9ebff-206">Save the hash table in a `<ScriptName>.psd1` file.</span></span> <span data-ttu-id="9ebff-207">Затем создайте `de-DE` подкаталог в каталоге script и сохраните немецкий `<ScriptName\>.psd1` файл в `de-DE` подкаталоге.</span><span class="sxs-lookup"><span data-stu-id="9ebff-207">Then create a `de-DE` subdirectory under the script directory, and save the German `<ScriptName\>.psd1` file in the `de-DE` subdirectory.</span></span>
  <span data-ttu-id="9ebff-208">Повторите эту процедуру для каждого поддерживаемого решением языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="9ebff-208">Repeat this method for each locale that you support.</span></span>

- <span data-ttu-id="9ebff-209">`Import-LocalizedData` выполняет структурированный поиск локализованных сообщений пользователя для скрипта.</span><span class="sxs-lookup"><span data-stu-id="9ebff-209">`Import-LocalizedData` performs a structured search for the localized user messages for a script.</span></span>

  <span data-ttu-id="9ebff-210">`Import-LocalizedData` начинает поиск в каталоге, где расположен файл скрипта (или значение параметра **баседиректори** ).</span><span class="sxs-lookup"><span data-stu-id="9ebff-210">`Import-LocalizedData` begins the search in the directory where the script file is located (or the value of the **BaseDirectory** parameter).</span></span> <span data-ttu-id="9ebff-211">Затем он ищет в базовом каталоге подкаталог с тем же именем, что и значение `$PsUICulture` переменной (или значение параметра **UICulture** ), например `de-DE` или `ar-SA` .</span><span class="sxs-lookup"><span data-stu-id="9ebff-211">It then searches within the base directory for a subdirectory with the same name as the value of the `$PsUICulture` variable (or the value of the **UICulture** parameter), such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="9ebff-212">Затем он ищет в этом подкаталоге `.psd1` файл с тем же именем, что и у скрипта (или значение параметра **filename** ).</span><span class="sxs-lookup"><span data-stu-id="9ebff-212">Then, it searches in that subdirectory for a `.psd1` file with the same name as the script (or the value of the **FileName** parameter).</span></span>

  <span data-ttu-id="9ebff-213">Если `Import-LocalizedData` не удается найти подкаталог с именем языка и региональных параметров пользовательского интерфейса, или подкаталог не содержит `.psd1` файл для скрипта, он ищет `.psd1` файл скрипта в подкаталоге с именем кода языка, например de или AR.</span><span class="sxs-lookup"><span data-stu-id="9ebff-213">If `Import-LocalizedData` cannot find a subdirectory with the name of the UI culture, or the subdirectory does not contain a `.psd1` file for the script, it searches for a `.psd1` file for the script in a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="9ebff-214">Если не удается найти подкаталог или `.psd1` файл, команда завершается ошибкой, данные отображаются на языке по умолчанию в скрипте, и отображается сообщение об ошибке, объясняющее, что данные не удалось импортировать.</span><span class="sxs-lookup"><span data-stu-id="9ebff-214">If it cannot find the subdirectory or `.psd1` file, the command fails, the data is displayed in the default language in the script, and an error message is displayed explaining that the data could not be imported.</span></span> <span data-ttu-id="9ebff-215">Чтобы отключить сообщение и корректно завершить его работу, используйте общий параметр **ErrorAction** со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="9ebff-215">To suppress the message and fail gracefully, use the **ErrorAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="9ebff-216">Если `Import-LocalizedData` находит подкаталог и `.psd1` файл, он импортирует хэш-таблицу пользовательских сообщений в значение параметра **биндингвариабле** в команде.</span><span class="sxs-lookup"><span data-stu-id="9ebff-216">If `Import-LocalizedData` finds the subdirectory and the `.psd1` file, it imports the hash table of user messages into the value of the **BindingVariable** parameter in the command.</span></span> <span data-ttu-id="9ebff-217">Затем при отображении сообщения из хэш-таблицы в переменной отображается локализованное сообщение.</span><span class="sxs-lookup"><span data-stu-id="9ebff-217">Then, when you display a message from the hash table in the variable, the localized message is displayed.</span></span>

  <span data-ttu-id="9ebff-218">Дополнительные сведения см. в разделе [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="9ebff-218">For more information, see [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="9ebff-219">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9ebff-219">RELATED LINKS</span></span>

[<span data-ttu-id="9ebff-220">Write-Host</span><span class="sxs-lookup"><span data-stu-id="9ebff-220">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="9ebff-221">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="9ebff-221">Import-PowerShellDataFile</span></span>](Import-PowerShellDataFile.md)

