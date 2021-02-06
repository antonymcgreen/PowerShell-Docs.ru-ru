---
description: Описывает, как переменные хранят значения, которые можно использовать в PowerShell.
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: 8d8c8d3098d33980c9c802bf00846a21e8baeb40
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601290"
---
# <a name="about-variables"></a><span data-ttu-id="6789b-103">О переменных</span><span class="sxs-lookup"><span data-stu-id="6789b-103">About Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="6789b-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="6789b-104">Short description</span></span>

<span data-ttu-id="6789b-105">Описывает, как переменные хранят значения, которые можно использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-105">Describes how variables store values that can be used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6789b-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="6789b-106">Long description</span></span>

<span data-ttu-id="6789b-107">Все типы значений можно хранить в переменных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-107">You can store all types of values in PowerShell variables.</span></span> <span data-ttu-id="6789b-108">Например, можно сохранить результаты команд и сохранить элементы, используемые в командах и выражениях, таких как имена, пути, параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="6789b-108">For example, store the results of commands, and store elements that are used in commands and expressions, such as names, paths, settings, and values.</span></span>

<span data-ttu-id="6789b-109">Переменная — это единица памяти, в которой хранятся значения.</span><span class="sxs-lookup"><span data-stu-id="6789b-109">A variable is a unit of memory in which values are stored.</span></span> <span data-ttu-id="6789b-110">В PowerShell переменные представлены текстовыми строками, которые начинаются со знака доллара ( `$` ), например `$a` , `$process` или `$my_var` .</span><span class="sxs-lookup"><span data-stu-id="6789b-110">In PowerShell, variables are represented by text strings that begin with a dollar sign (`$`), such as `$a`, `$process`, or `$my_var`.</span></span>

<span data-ttu-id="6789b-111">Имена переменных не учитывают регистр и могут содержать пробелы и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="6789b-111">Variable names aren't case-sensitive, and can include spaces and special characters.</span></span> <span data-ttu-id="6789b-112">Однако имена переменных, которые содержат специальные символы и пробелы, трудно использовать, поэтому их следует избегать.</span><span class="sxs-lookup"><span data-stu-id="6789b-112">But, variable names that include special characters and spaces are difficult to use and should be avoided.</span></span> <span data-ttu-id="6789b-113">Дополнительные сведения см. в разделе [имена переменных, которые содержат специальные символы](#variable-names-that-include-special-characters).</span><span class="sxs-lookup"><span data-stu-id="6789b-113">For more information, see [Variable names that include special characters](#variable-names-that-include-special-characters).</span></span>

<span data-ttu-id="6789b-114">В PowerShell существует несколько различных типов переменных.</span><span class="sxs-lookup"><span data-stu-id="6789b-114">There are several different types of variables in PowerShell.</span></span>

- <span data-ttu-id="6789b-115">Пользовательские переменные: созданные пользователем переменные создаются и обслуживаются пользователем.</span><span class="sxs-lookup"><span data-stu-id="6789b-115">User-created variables: User-created variables are created and maintained by the user.</span></span> <span data-ttu-id="6789b-116">По умолчанию переменные, создаваемые в командной строке PowerShell, существуют только в том случае, если открыто окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-116">By default, the variables that you create at the PowerShell command line exist only while the PowerShell window is open.</span></span> <span data-ttu-id="6789b-117">При закрытии окон PowerShell переменные удаляются.</span><span class="sxs-lookup"><span data-stu-id="6789b-117">When the PowerShell windows is closed, the variables are deleted.</span></span> <span data-ttu-id="6789b-118">Чтобы сохранить переменную, добавьте ее в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-118">To save a variable, add it to your PowerShell profile.</span></span> <span data-ttu-id="6789b-119">Кроме того, можно создавать переменные в скриптах с глобальной областью, сценарием или локальными областями.</span><span class="sxs-lookup"><span data-stu-id="6789b-119">You can also create variables in scripts with global, script, or local scope.</span></span>

- <span data-ttu-id="6789b-120">Автоматические переменные: автоматические переменные хранят состояние PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-120">Automatic variables: Automatic variables store the state of PowerShell.</span></span> <span data-ttu-id="6789b-121">Эти переменные создаются с помощью PowerShell, а PowerShell изменяет их значения в соответствии с требованиями, чтобы поддерживать их точность.</span><span class="sxs-lookup"><span data-stu-id="6789b-121">These variables are created by PowerShell, and PowerShell changes their values as required to maintain their accuracy.</span></span> <span data-ttu-id="6789b-122">Пользователи не могут изменять значения этих переменных.</span><span class="sxs-lookup"><span data-stu-id="6789b-122">Users can't change the value of these variables.</span></span> <span data-ttu-id="6789b-123">Например, `$PSHOME` переменная хранит путь к каталогу установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-123">For example, the `$PSHOME` variable stores the path to the PowerShell installation directory.</span></span>

  <span data-ttu-id="6789b-124">Дополнительные сведения, список и описание автоматических переменных см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="6789b-124">For more information, a list, and a description of the automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="6789b-125">Привилегированные переменные. переменные предпочтений сохраняют настройки пользователя для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-125">Preference variables: Preference variables store user preferences for PowerShell.</span></span> <span data-ttu-id="6789b-126">Эти переменные создаются с помощью PowerShell и заполняются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6789b-126">These variables are created by PowerShell and are populated with default values.</span></span> <span data-ttu-id="6789b-127">Пользователи могут изменять значения этих переменных.</span><span class="sxs-lookup"><span data-stu-id="6789b-127">Users can change the values of these variables.</span></span> <span data-ttu-id="6789b-128">Например, `$MaximumHistoryCount` переменная определяет максимальное количество записей в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="6789b-128">For example, the `$MaximumHistoryCount` variable determines the maximum number of entries in the session history.</span></span>

  <span data-ttu-id="6789b-129">Дополнительные сведения, список и описание переменных предпочтений см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="6789b-129">For more information, a list, and a description of the preference variables, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="working-with-variables"></a><span data-ttu-id="6789b-130">Работа с переменными</span><span class="sxs-lookup"><span data-stu-id="6789b-130">Working with variables</span></span>

<span data-ttu-id="6789b-131">Чтобы создать новую переменную, используйте инструкцию присваивания, чтобы присвоить значение переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-131">To create a new variable, use an assignment statement to assign a value to the variable.</span></span> <span data-ttu-id="6789b-132">Не нужно объявлять переменную перед ее использованием.</span><span class="sxs-lookup"><span data-stu-id="6789b-132">You don't have to declare the variable before using it.</span></span> <span data-ttu-id="6789b-133">По умолчанию все переменные имеют значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="6789b-133">The default value of all variables is `$null`.</span></span>

<span data-ttu-id="6789b-134">Чтобы получить список всех переменных в сеансе PowerShell, введите `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="6789b-134">To get a list of all the variables in your PowerShell session, type `Get-Variable`.</span></span> <span data-ttu-id="6789b-135">Имена переменных отображаются без знака доллара ( `$` ), который используется для ссылки на переменные.</span><span class="sxs-lookup"><span data-stu-id="6789b-135">The variable names are displayed without the preceding dollar (`$`) sign that is used to reference variables.</span></span>

<span data-ttu-id="6789b-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="6789b-136">For example:</span></span>

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

<span data-ttu-id="6789b-137">Переменные удобно использовать для хранения результатов команд.</span><span class="sxs-lookup"><span data-stu-id="6789b-137">Variables are useful for storing the results of commands.</span></span>

<span data-ttu-id="6789b-138">Пример:</span><span class="sxs-lookup"><span data-stu-id="6789b-138">For example:</span></span>

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

<span data-ttu-id="6789b-139">Чтобы отобразить значение переменной, введите имя переменной, перед которым следует знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="6789b-139">To display the value of a variable, type the variable name, preceded by a dollar sign (`$`).</span></span>

<span data-ttu-id="6789b-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="6789b-140">For example:</span></span>

```powershell
$MyVariable
```

```Output
1
2
3
```

```powershell
$Today
```

```Output
Tuesday, September 3, 2019 09:46:46
```

<span data-ttu-id="6789b-141">Чтобы изменить значение переменной, присвойте переменной новое значение.</span><span class="sxs-lookup"><span data-stu-id="6789b-141">To change the value of a variable, assign a new value to the variable.</span></span>

<span data-ttu-id="6789b-142">В следующих примерах показано значение `$MyVariable` переменной, изменяется значение переменной, а затем отображается новое значение.</span><span class="sxs-lookup"><span data-stu-id="6789b-142">The following examples display the value of the `$MyVariable` variable, changes the value of the variable, and then displays the new value.</span></span>

```powershell
$MyVariable = 1, 2, 3
$MyVariable
```

```Output
1
2
3
```

```powershell
$MyVariable = "The green cat."
$MyVariable
```

```Output
The green cat.
```

<span data-ttu-id="6789b-143">Чтобы удалить значение переменной, используйте `Clear-Variable` командлет или измените значение на `$null` .</span><span class="sxs-lookup"><span data-stu-id="6789b-143">To delete the value of a variable, use the `Clear-Variable` cmdlet or change the value to `$null`.</span></span>

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

<span data-ttu-id="6789b-144">Чтобы удалить переменную, используйте [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) или [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span><span class="sxs-lookup"><span data-stu-id="6789b-144">To delete the variable, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) or [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span></span>

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

## <a name="types-of-variables"></a><span data-ttu-id="6789b-145">Типы переменных</span><span class="sxs-lookup"><span data-stu-id="6789b-145">Types of variables</span></span>

<span data-ttu-id="6789b-146">В переменную можно хранить любой тип объекта, включая целые числа, строки, массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="6789b-146">You can store any type of object in a variable, including integers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="6789b-147">И — объекты, представляющие процессы, службы, журналы событий и компьютеры.</span><span class="sxs-lookup"><span data-stu-id="6789b-147">And, objects that represent processes, services, event logs, and computers.</span></span>

<span data-ttu-id="6789b-148">Переменные PowerShell слабо типизированы, а это означает, что они не ограничиваются определенным типом объекта.</span><span class="sxs-lookup"><span data-stu-id="6789b-148">PowerShell variables are loosely typed, which means that they aren't limited to a particular type of object.</span></span> <span data-ttu-id="6789b-149">Одна переменная может даже содержать коллекцию или массив различных типов объектов в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="6789b-149">A single variable can even contain a collection, or array, of different types of objects at the same time.</span></span>

<span data-ttu-id="6789b-150">Тип данных переменной определяется типами .NET значений этой переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-150">The data type of a variable is determined by the .NET types of the values of the variable.</span></span> <span data-ttu-id="6789b-151">Чтобы просмотреть тип объекта переменной, используйте [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span><span class="sxs-lookup"><span data-stu-id="6789b-151">To view a variable's object type, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span></span>

<span data-ttu-id="6789b-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="6789b-152">For example:</span></span>

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

<span data-ttu-id="6789b-153">Можно использовать атрибут типа и нотацию приведения, чтобы гарантировать, что переменная может содержать только определенные типы объектов или объекты, которые могут быть преобразованы в этот тип.</span><span class="sxs-lookup"><span data-stu-id="6789b-153">You can use a type attribute and cast notation to ensure that a variable can contain only specific object types or objects that can be converted to that type.</span></span> <span data-ttu-id="6789b-154">При попытке присвоить значение другому типу PowerShell пытается преобразовать значение в его тип.</span><span class="sxs-lookup"><span data-stu-id="6789b-154">If you try to assign a value of another type, PowerShell tries to convert the value to its type.</span></span> <span data-ttu-id="6789b-155">Если тип не может быть преобразован, инструкция присваивания завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6789b-155">If the type can't be converted, the assignment statement fails.</span></span>

<span data-ttu-id="6789b-156">Чтобы использовать нотацию CAST, введите имя типа, заключенное в квадратные скобки, перед именем переменной (в левой части оператора присваивания).</span><span class="sxs-lookup"><span data-stu-id="6789b-156">To use cast notation, enter a type name, enclosed in brackets, before the variable name (on the left side of the assignment statement).</span></span> <span data-ttu-id="6789b-157">В следующем примере создается `$number` переменная, которая может содержать только целые числа, `$words` переменную, которая может содержать только строки, и `$dates` переменную, которая может содержать только объекты **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6789b-157">The following example creates a `$number` variable that can contain only integers, a `$words` variable that can contain only strings, and a `$dates` variable that can contain only **DateTime** objects.</span></span>

```powershell
[int]$number = 8
$number = "12345"  # The string is converted to an integer.
$number = "Hello"
```

```Output
Cannot convert value "Hello" to type "System.Int32". Error: "Input string was
 not in a correct format."
At line:1 char:1
+ $number = "Hello"
+ ~~~~~~~~~~~~~~~~~
+ CategoryInfo          : MetadataError: (:) [],
    ArgumentTransformationMetadataException
+ FullyQualifiedErrorId : RuntimeException
```

```powershell
[string]$words = "Hello"
$words = 2       # The integer is converted to a string.
$words += 10     # The plus (+) sign concatenates the strings.
$words
```

```Output
210
```

```powershell
[datetime] $dates = "09/12/91"  # The string is converted to a DateTime object.
$dates
```

```Output
Thursday, September 12, 1991 00:00:00
```

```powershell
$dates = 10    # The integer is converted to a DateTime object.
$dates
```

```Output
Monday, January 1, 0001 00:00:00
```

## <a name="using-variables-in-commands-and-expressions"></a><span data-ttu-id="6789b-158">Использование переменных в командах и выражениях</span><span class="sxs-lookup"><span data-stu-id="6789b-158">Using variables in commands and expressions</span></span>

<span data-ttu-id="6789b-159">Чтобы использовать переменную в команде или выражении, введите имя переменной, перед которым следует знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="6789b-159">To use a variable in a command or expression, type the variable name, preceded by the dollar (`$`) sign.</span></span>

<span data-ttu-id="6789b-160">Если имя переменной и знак доллара не заключены в кавычки или заключены в двойные кавычки ( `"` ), значение переменной используется в команде или выражении.</span><span class="sxs-lookup"><span data-stu-id="6789b-160">If the variable name and dollar sign aren't enclosed in quotation marks, or if they're enclosed in double quotation (`"`) marks, the value of the variable is used in the command or expression.</span></span>

<span data-ttu-id="6789b-161">Если имя переменной и знак доллара заключены в одинарные кавычки ( `'` ), в выражении используется имя переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-161">If the variable name and dollar sign are enclosed in single quotation (`'`) marks, the variable name is used in the expression.</span></span>

<span data-ttu-id="6789b-162">Дополнительные сведения об использовании кавычек в PowerShell см. в разделе [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="6789b-162">For more information about using quotation marks in PowerShell, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="6789b-163">В этом примере получается значение `$PROFILE` переменной, которая является путем к файлу профиля пользователя PowerShell в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-163">This example gets the value of the `$PROFILE` variable, which is the path to the PowerShell user profile file in the PowerShell console.</span></span>

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

<span data-ttu-id="6789b-164">В этом примере показаны две команды, которые могут открыть профиль PowerShell в **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="6789b-164">In this example, two commands are shown that can open the PowerShell profile in **notepad.exe**.</span></span> <span data-ttu-id="6789b-165">В примере с символами двойной кавычки ( `"` ) используется значение переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-165">The example with double-quote (`"`) marks uses the variable's value.</span></span>

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

<span data-ttu-id="6789b-166">В следующих примерах используются одиночные `'` кавычки (), которые обрабатывают переменную как литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="6789b-166">The following examples use single-quote (`'`) marks that treat the variable as literal text.</span></span>

```powershell
'$PROFILE'
```

```Output
$PROFILE
```

```powershell
'Use the $PROFILE variable.'
```

```Output
Use the $PROFILE variable.
```

## <a name="variable-names-that-include-special-characters"></a><span data-ttu-id="6789b-167">Имена переменных, содержащие специальные символы</span><span class="sxs-lookup"><span data-stu-id="6789b-167">Variable names that include special characters</span></span>

<span data-ttu-id="6789b-168">Имена переменных начинаются с символа доллара ( `$` ) и могут содержать буквенно-цифровые символы и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="6789b-168">Variable names begin with a dollar (`$`) sign and can include alphanumeric characters and special characters.</span></span> <span data-ttu-id="6789b-169">Длина имени переменной ограничена только доступной памятью.</span><span class="sxs-lookup"><span data-stu-id="6789b-169">The variable name length is limited only by available memory.</span></span>

<span data-ttu-id="6789b-170">Рекомендуется, чтобы имена переменных включали только буквенно-цифровые символы и символ подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="6789b-170">The best practice is that variable names include only alphanumeric characters and the underscore (`_`) character.</span></span> <span data-ttu-id="6789b-171">Имена переменных, содержащие пробелы и другие специальные символы, трудно использовать, поэтому их следует избегать.</span><span class="sxs-lookup"><span data-stu-id="6789b-171">Variable names that include spaces and other special characters, are difficult to use and should be avoided.</span></span>

<span data-ttu-id="6789b-172">Буквенно-цифровые имена переменных могут содержать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="6789b-172">Alphanumeric variable names can contain these characters:</span></span>

- <span data-ttu-id="6789b-173">Символы Юникода из следующих категорий: **Lu**, **LL**, **lt**, **LM**, **with** или **ND**.</span><span class="sxs-lookup"><span data-stu-id="6789b-173">Unicode characters from these categories: **Lu**, **Ll**, **Lt**, **Lm**, **Lo**, or **Nd**.</span></span>
- <span data-ttu-id="6789b-174">Символ подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="6789b-174">Underscore (`_`) character.</span></span>
- <span data-ttu-id="6789b-175">Символ вопросительного `?` знака ().</span><span class="sxs-lookup"><span data-stu-id="6789b-175">Question mark (`?`) character.</span></span>

<span data-ttu-id="6789b-176">В следующем списке содержатся описания категорий Юникода.</span><span class="sxs-lookup"><span data-stu-id="6789b-176">The following list contains the Unicode category descriptions.</span></span> <span data-ttu-id="6789b-177">Дополнительные сведения см. в разделе [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span><span class="sxs-lookup"><span data-stu-id="6789b-177">For more information, see [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span></span>

- <span data-ttu-id="6789b-178">**Lu** — упперкаселеттер</span><span class="sxs-lookup"><span data-stu-id="6789b-178">**Lu** - UppercaseLetter</span></span>
- <span data-ttu-id="6789b-179">**LL** -ловеркаселеттер</span><span class="sxs-lookup"><span data-stu-id="6789b-179">**Ll** - LowercaseLetter</span></span>
- <span data-ttu-id="6789b-180">**Lt** — титлекаселеттер</span><span class="sxs-lookup"><span data-stu-id="6789b-180">**Lt** - TitlecaseLetter</span></span>
- <span data-ttu-id="6789b-181">**LM** -модифиерлеттер</span><span class="sxs-lookup"><span data-stu-id="6789b-181">**Lm** - ModifierLetter</span></span>
- <span data-ttu-id="6789b-182"> Осерлеттер</span><span class="sxs-lookup"><span data-stu-id="6789b-182">**Lo** - OtherLetter</span></span>
- <span data-ttu-id="6789b-183">**ND** -деЦималдигитнумбер</span><span class="sxs-lookup"><span data-stu-id="6789b-183">**Nd** - DecimalDigitNumber</span></span>

<span data-ttu-id="6789b-184">Чтобы создать или отобразить имя переменной, содержащей пробелы или специальные символы, заключите имя переменной в символы фигурных скобок ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="6789b-184">To create or display a variable name that includes spaces or special characters, enclose the variable name with the curly braces (`{}`) characters.</span></span>
<span data-ttu-id="6789b-185">Фигурные скобки направляют PowerShell для интерпретации символов имени переменной как литералов.</span><span class="sxs-lookup"><span data-stu-id="6789b-185">The curly braces direct PowerShell to interpret the variable name's characters as literals.</span></span>

<span data-ttu-id="6789b-186">В именах специальных символьных переменных могут содержаться следующие символы:</span><span class="sxs-lookup"><span data-stu-id="6789b-186">Special character variable names can contain these characters:</span></span>

- <span data-ttu-id="6789b-187">Любой символ Юникода со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="6789b-187">Any Unicode character, with the following exceptions:</span></span>
  - <span data-ttu-id="6789b-188">Символ закрывающей фигурной скобки ( `}` ) (U + 007D).</span><span class="sxs-lookup"><span data-stu-id="6789b-188">The closing curly brace (`}`) character (U+007D).</span></span>
  - <span data-ttu-id="6789b-189">Символ обратной кавычки ( `` ` `` ) (U + 0060).</span><span class="sxs-lookup"><span data-stu-id="6789b-189">The backtick (`` ` ``) character (U+0060).</span></span> <span data-ttu-id="6789b-190">Обратная шкала используется для экранирования символов Юникода, чтобы они обрабатывались как литералы.</span><span class="sxs-lookup"><span data-stu-id="6789b-190">The backtick is used to escape Unicode characters so they're treated as literals.</span></span>

<span data-ttu-id="6789b-191">PowerShell содержит зарезервированные переменные `$$` , такие как, `$?` , и `$^` `$_` , которые содержат буквенно-цифровые и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="6789b-191">PowerShell has reserved variables such as `$$`, `$?`, `$^`, and `$_` that contain alphanumeric and special characters.</span></span> <span data-ttu-id="6789b-192">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_automatic_variables.md).</span><span class="sxs-lookup"><span data-stu-id="6789b-192">For more information, see [about_Automatic_Variables](about_automatic_variables.md).</span></span>

<span data-ttu-id="6789b-193">Например, следующая команда создает переменную с именем `save-items` .</span><span class="sxs-lookup"><span data-stu-id="6789b-193">For example, the following command creates the variable named `save-items`.</span></span> <span data-ttu-id="6789b-194">Фигурные скобки ( `{}` ) необходимы, так как имя переменной включает `-` Специальный символ дефис ().</span><span class="sxs-lookup"><span data-stu-id="6789b-194">The curly braces (`{}`) are needed because variable name includes a hyphen (`-`) special character.</span></span>

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

<span data-ttu-id="6789b-195">Следующая команда возвращает дочерние элементы в каталоге, представленном `ProgramFiles(x86)` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="6789b-195">The following command gets the child items in the directory that is represented by the `ProgramFiles(x86)` environment variable.</span></span>

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

<span data-ttu-id="6789b-196">Чтобы сослаться на имя переменной, включающую фигурные скобки, заключите имя переменной в фигурные скобки и используйте символ обратной кавычки для экранирования фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="6789b-196">To reference a variable name that includes braces, enclose the variable name in braces, and use the backtick character to escape the braces.</span></span> <span data-ttu-id="6789b-197">Например, чтобы создать переменную с именем `this{value}is` Type:</span><span class="sxs-lookup"><span data-stu-id="6789b-197">For example, to create a variable named `this{value}is` type:</span></span>

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a><span data-ttu-id="6789b-198">Переменные и область</span><span class="sxs-lookup"><span data-stu-id="6789b-198">Variables and scope</span></span>

<span data-ttu-id="6789b-199">По умолчанию переменные доступны только в области, в которой они созданы.</span><span class="sxs-lookup"><span data-stu-id="6789b-199">By default, variables are only available in the scope in which they're created.</span></span>

<span data-ttu-id="6789b-200">Например, переменная, созданная в функции, доступна только внутри функции.</span><span class="sxs-lookup"><span data-stu-id="6789b-200">For example, a variable that you create in a function is available only within the function.</span></span> <span data-ttu-id="6789b-201">Переменная, создаваемая в скрипте, доступна только внутри скрипта.</span><span class="sxs-lookup"><span data-stu-id="6789b-201">A variable that you create in a script is available only within the script.</span></span> <span data-ttu-id="6789b-202">Если вы помещаете скрипт в точку, переменная добавляется в текущую область.</span><span class="sxs-lookup"><span data-stu-id="6789b-202">If you dot-source the script, the variable is added to the current scope.</span></span> <span data-ttu-id="6789b-203">Дополнительные сведения см. в разделе [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="6789b-203">For more information, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="6789b-204">С помощью модификатора области можно изменить область действия по умолчанию для переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-204">You can use a scope modifier to change the default scope of the variable.</span></span> <span data-ttu-id="6789b-205">Следующее выражение создает переменную с именем `Computers` .</span><span class="sxs-lookup"><span data-stu-id="6789b-205">The following expression creates a variable named `Computers`.</span></span> <span data-ttu-id="6789b-206">Переменная имеет глобальную область, даже если она создается в скрипте или функции.</span><span class="sxs-lookup"><span data-stu-id="6789b-206">The variable has a global scope, even when it's created in a script or function.</span></span>

```powershell
$Global:Computers = "Server01"
```

<span data-ttu-id="6789b-207">Для любого скрипта или команды, выполняемой вне сеанса, необходим `Using` Модификатор области для внедрения значений переменных из области вызывающего сеанса, чтобы код сеанса мог получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="6789b-207">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span>

<span data-ttu-id="6789b-208">Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="6789b-208">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="saving-variables"></a><span data-ttu-id="6789b-209">Сохранение переменных</span><span class="sxs-lookup"><span data-stu-id="6789b-209">Saving variables</span></span>

<span data-ttu-id="6789b-210">Создаваемые переменные доступны только в том сеансе, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="6789b-210">Variables that you create are available only in the session in which you create them.</span></span> <span data-ttu-id="6789b-211">При закрытии сеанса они теряются.</span><span class="sxs-lookup"><span data-stu-id="6789b-211">They're lost when you close your session.</span></span>

<span data-ttu-id="6789b-212">Чтобы создать переменную в каждом запущенном сеансе PowerShell, добавьте переменную в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-212">To create the variable in every PowerShell session that you start, add the variable to your PowerShell profile.</span></span>

<span data-ttu-id="6789b-213">Например, чтобы изменить значение `$VerbosePreference` переменной в каждом сеансе PowerShell, добавьте следующую команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6789b-213">For example, to change the value of the `$VerbosePreference` variable in every PowerShell session, add the following command to your PowerShell profile.</span></span>

```powershell
$VerbosePreference = "Continue"
```

<span data-ttu-id="6789b-214">Эту команду можно добавить в профиль PowerShell, открыв `$PROFILE` файл в текстовом редакторе, например **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="6789b-214">You can add this command to your PowerShell profile by opening the `$PROFILE` file in a text editor, such as **notepad.exe**.</span></span> <span data-ttu-id="6789b-215">Дополнительные сведения о профилях PowerShell см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6789b-215">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="the-variable-drive"></a><span data-ttu-id="6789b-216">Переменная: диск</span><span class="sxs-lookup"><span data-stu-id="6789b-216">The Variable: drive</span></span>

<span data-ttu-id="6789b-217">Поставщик переменных PowerShell создает `Variable:` диск, который выглядит и действует как диск файловой системы, но содержит переменные в сеансе и их значения.</span><span class="sxs-lookup"><span data-stu-id="6789b-217">The PowerShell Variable provider creates a `Variable:` drive that looks and acts like a file system drive, but it contains the variables in your session and their values.</span></span>

<span data-ttu-id="6789b-218">Чтобы перейти на `Variable:` диск, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6789b-218">To change to the `Variable:` drive, use the following command:</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="6789b-219">Чтобы получить список элементов и переменных на `Variable:` диске, используйте `Get-Item` `Get-ChildItem` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="6789b-219">To list the items and variables in the `Variable:` drive, use the `Get-Item` or `Get-ChildItem` cmdlets.</span></span>

```powershell
Get-ChildItem Variable:
```

<span data-ttu-id="6789b-220">Чтобы получить значение определенной переменной, используйте нотацию файловой системы, чтобы указать имя диска и имя переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-220">To get the value of a particular variable, use file system notation to specify the name of the drive and the name of the variable.</span></span> <span data-ttu-id="6789b-221">Например, чтобы получить `$PSCulture` автоматическую переменную, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="6789b-221">For example, to get the `$PSCulture` automatic variable, use the following command.</span></span>

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

<span data-ttu-id="6789b-222">Чтобы просмотреть дополнительные сведения о `Variable:` диске и поставщике переменных PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="6789b-222">To display more information about the `Variable:` drive and the PowerShell Variable provider, type:</span></span>

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a><span data-ttu-id="6789b-223">Синтаксис переменных с путями поставщика</span><span class="sxs-lookup"><span data-stu-id="6789b-223">Variable syntax with provider paths</span></span>

<span data-ttu-id="6789b-224">Путь к поставщику можно добавить с помощью символа доллара ( `$` ) и получить доступ к содержимому любого поставщика, реализующего интерфейс [иконтенткмдлетпровидер](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) .</span><span class="sxs-lookup"><span data-stu-id="6789b-224">You can prefix a provider path with the dollar (`$`) sign, and access the content of any provider that implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>

<span data-ttu-id="6789b-225">Следующие встроенные поставщики PowerShell поддерживают эту нотацию:</span><span class="sxs-lookup"><span data-stu-id="6789b-225">The following built-in PowerShell providers support this notation:</span></span>

- [<span data-ttu-id="6789b-226">about_Environment_Provider</span><span class="sxs-lookup"><span data-stu-id="6789b-226">about_Environment_Provider</span></span>](about_Environment_Provider.md)
- [<span data-ttu-id="6789b-227">about_Variable_Provider</span><span class="sxs-lookup"><span data-stu-id="6789b-227">about_Variable_Provider</span></span>](about_Variable_Provider.md)
- [<span data-ttu-id="6789b-228">about_Function_Provider</span><span class="sxs-lookup"><span data-stu-id="6789b-228">about_Function_Provider</span></span>](about_Function_Provider.md)
- [<span data-ttu-id="6789b-229">about_Alias_Provider</span><span class="sxs-lookup"><span data-stu-id="6789b-229">about_Alias_Provider</span></span>](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a><span data-ttu-id="6789b-230">Командлеты переменных</span><span class="sxs-lookup"><span data-stu-id="6789b-230">The variable cmdlets</span></span>

<span data-ttu-id="6789b-231">PowerShell включает набор командлетов, предназначенных для управления переменными.</span><span class="sxs-lookup"><span data-stu-id="6789b-231">PowerShell includes a set of cmdlets that are designed to manage variables.</span></span>

<span data-ttu-id="6789b-232">Чтобы получить список командлетов, введите:</span><span class="sxs-lookup"><span data-stu-id="6789b-232">To list the cmdlets, type:</span></span>

```powershell
Get-Command -Noun Variable
```

<span data-ttu-id="6789b-233">Чтобы получить справку по конкретному командлету, введите:</span><span class="sxs-lookup"><span data-stu-id="6789b-233">To get help for a specific cmdlet, type:</span></span>

```powershell
Get-Help <cmdlet-name>
```

| <span data-ttu-id="6789b-234">Имя командлета</span><span class="sxs-lookup"><span data-stu-id="6789b-234">Cmdlet Name</span></span>       | <span data-ttu-id="6789b-235">Описание</span><span class="sxs-lookup"><span data-stu-id="6789b-235">Description</span></span>                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | <span data-ttu-id="6789b-236">Удаляет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-236">Deletes the value of a variable.</span></span>           |
| `Get-Variable`    | <span data-ttu-id="6789b-237">Получает переменные в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="6789b-237">Gets the variables in the current console.</span></span> |
| `New-Variable`    | <span data-ttu-id="6789b-238">Создает новую переменную.</span><span class="sxs-lookup"><span data-stu-id="6789b-238">Creates a new variable.</span></span>                    |
| `Remove-Variable` | <span data-ttu-id="6789b-239">Удаляет переменную и ее значение.</span><span class="sxs-lookup"><span data-stu-id="6789b-239">Deletes a variable and its value.</span></span>          |
| `Set-Variable`    | <span data-ttu-id="6789b-240">Изменяет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="6789b-240">Changes the value of a variable.</span></span>           |

## <a name="see-also"></a><span data-ttu-id="6789b-241">См. также</span><span class="sxs-lookup"><span data-stu-id="6789b-241">See also</span></span>

[<span data-ttu-id="6789b-242">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="6789b-242">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="6789b-243">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="6789b-243">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="6789b-244">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="6789b-244">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="6789b-245">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="6789b-245">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="6789b-246">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="6789b-246">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="6789b-247">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="6789b-247">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="6789b-248">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="6789b-248">about_Remote_Variables</span></span>](about_Remote_Variables.md)

