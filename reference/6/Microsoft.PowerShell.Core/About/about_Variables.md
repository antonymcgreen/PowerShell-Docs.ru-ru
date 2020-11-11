---
description: Описывает, как переменные хранят значения, которые можно использовать в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: 2a6daa33cc671bd287b395aa4e1dd6f871c26bf9
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483168"
---
# <a name="about-variables"></a><span data-ttu-id="9fa56-104">О переменных</span><span class="sxs-lookup"><span data-stu-id="9fa56-104">About Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="9fa56-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="9fa56-105">Short description</span></span>

<span data-ttu-id="9fa56-106">Описывает, как переменные хранят значения, которые можно использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-106">Describes how variables store values that can be used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9fa56-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9fa56-107">Long description</span></span>

<span data-ttu-id="9fa56-108">Все типы значений можно хранить в переменных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-108">You can store all types of values in PowerShell variables.</span></span> <span data-ttu-id="9fa56-109">Например, можно сохранить результаты команд и сохранить элементы, используемые в командах и выражениях, таких как имена, пути, параметры и значения.</span><span class="sxs-lookup"><span data-stu-id="9fa56-109">For example, store the results of commands, and store elements that are used in commands and expressions, such as names, paths, settings, and values.</span></span>

<span data-ttu-id="9fa56-110">Переменная — это единица памяти, в которой хранятся значения.</span><span class="sxs-lookup"><span data-stu-id="9fa56-110">A variable is a unit of memory in which values are stored.</span></span> <span data-ttu-id="9fa56-111">В PowerShell переменные представлены текстовыми строками, которые начинаются со знака доллара ( `$` ), например `$a` , `$process` или `$my_var` .</span><span class="sxs-lookup"><span data-stu-id="9fa56-111">In PowerShell, variables are represented by text strings that begin with a dollar sign (`$`), such as `$a`, `$process`, or `$my_var`.</span></span>

<span data-ttu-id="9fa56-112">Имена переменных не учитывают регистр и могут содержать пробелы и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="9fa56-112">Variable names aren't case-sensitive, and can include spaces and special characters.</span></span> <span data-ttu-id="9fa56-113">Однако имена переменных, которые содержат специальные символы и пробелы, трудно использовать, поэтому их следует избегать.</span><span class="sxs-lookup"><span data-stu-id="9fa56-113">But, variable names that include special characters and spaces are difficult to use and should be avoided.</span></span> <span data-ttu-id="9fa56-114">Дополнительные сведения см. в разделе [имена переменных, которые содержат специальные символы](#variable-names-that-include-special-characters).</span><span class="sxs-lookup"><span data-stu-id="9fa56-114">For more information, see [Variable names that include special characters](#variable-names-that-include-special-characters).</span></span>

<span data-ttu-id="9fa56-115">В PowerShell существует несколько различных типов переменных.</span><span class="sxs-lookup"><span data-stu-id="9fa56-115">There are several different types of variables in PowerShell.</span></span>

- <span data-ttu-id="9fa56-116">Пользовательские переменные: созданные пользователем переменные создаются и обслуживаются пользователем.</span><span class="sxs-lookup"><span data-stu-id="9fa56-116">User-created variables: User-created variables are created and maintained by the user.</span></span> <span data-ttu-id="9fa56-117">По умолчанию переменные, создаваемые в командной строке PowerShell, существуют только в том случае, если открыто окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-117">By default, the variables that you create at the PowerShell command line exist only while the PowerShell window is open.</span></span> <span data-ttu-id="9fa56-118">При закрытии окон PowerShell переменные удаляются.</span><span class="sxs-lookup"><span data-stu-id="9fa56-118">When the PowerShell windows is closed, the variables are deleted.</span></span> <span data-ttu-id="9fa56-119">Чтобы сохранить переменную, добавьте ее в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-119">To save a variable, add it to your PowerShell profile.</span></span> <span data-ttu-id="9fa56-120">Кроме того, можно создавать переменные в скриптах с глобальной областью, сценарием или локальными областями.</span><span class="sxs-lookup"><span data-stu-id="9fa56-120">You can also create variables in scripts with global, script, or local scope.</span></span>

- <span data-ttu-id="9fa56-121">Автоматические переменные: автоматические переменные хранят состояние PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-121">Automatic variables: Automatic variables store the state of PowerShell.</span></span> <span data-ttu-id="9fa56-122">Эти переменные создаются с помощью PowerShell, а PowerShell изменяет их значения в соответствии с требованиями, чтобы поддерживать их точность.</span><span class="sxs-lookup"><span data-stu-id="9fa56-122">These variables are created by PowerShell, and PowerShell changes their values as required to maintain their accuracy.</span></span> <span data-ttu-id="9fa56-123">Пользователи не могут изменять значения этих переменных.</span><span class="sxs-lookup"><span data-stu-id="9fa56-123">Users can't change the value of these variables.</span></span> <span data-ttu-id="9fa56-124">Например, `$PSHOME` переменная хранит путь к каталогу установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-124">For example, the `$PSHOME` variable stores the path to the PowerShell installation directory.</span></span>

  <span data-ttu-id="9fa56-125">Дополнительные сведения, список и описание автоматических переменных см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9fa56-125">For more information, a list, and a description of the automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="9fa56-126">Привилегированные переменные. переменные предпочтений сохраняют настройки пользователя для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-126">Preference variables: Preference variables store user preferences for PowerShell.</span></span> <span data-ttu-id="9fa56-127">Эти переменные создаются с помощью PowerShell и заполняются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9fa56-127">These variables are created by PowerShell and are populated with default values.</span></span> <span data-ttu-id="9fa56-128">Пользователи могут изменять значения этих переменных.</span><span class="sxs-lookup"><span data-stu-id="9fa56-128">Users can change the values of these variables.</span></span> <span data-ttu-id="9fa56-129">Например, `$MaximumHistoryCount` переменная определяет максимальное количество записей в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="9fa56-129">For example, the `$MaximumHistoryCount` variable determines the maximum number of entries in the session history.</span></span>

  <span data-ttu-id="9fa56-130">Дополнительные сведения, список и описание переменных предпочтений см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9fa56-130">For more information, a list, and a description of the preference variables, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="working-with-variables"></a><span data-ttu-id="9fa56-131">Работа с переменными</span><span class="sxs-lookup"><span data-stu-id="9fa56-131">Working with variables</span></span>

<span data-ttu-id="9fa56-132">Чтобы создать новую переменную, используйте инструкцию присваивания, чтобы присвоить значение переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-132">To create a new variable, use an assignment statement to assign a value to the variable.</span></span> <span data-ttu-id="9fa56-133">Не нужно объявлять переменную перед ее использованием.</span><span class="sxs-lookup"><span data-stu-id="9fa56-133">You don't have to declare the variable before using it.</span></span> <span data-ttu-id="9fa56-134">По умолчанию все переменные имеют значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="9fa56-134">The default value of all variables is `$null`.</span></span>

<span data-ttu-id="9fa56-135">Чтобы получить список всех переменных в сеансе PowerShell, введите `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="9fa56-135">To get a list of all the variables in your PowerShell session, type `Get-Variable`.</span></span> <span data-ttu-id="9fa56-136">Имена переменных отображаются без знака доллара ( `$` ), который используется для ссылки на переменные.</span><span class="sxs-lookup"><span data-stu-id="9fa56-136">The variable names are displayed without the preceding dollar (`$`) sign that is used to reference variables.</span></span>

<span data-ttu-id="9fa56-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fa56-137">For example:</span></span>

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

<span data-ttu-id="9fa56-138">Переменные удобно использовать для хранения результатов команд.</span><span class="sxs-lookup"><span data-stu-id="9fa56-138">Variables are useful for storing the results of commands.</span></span>

<span data-ttu-id="9fa56-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fa56-139">For example:</span></span>

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

<span data-ttu-id="9fa56-140">Чтобы отобразить значение переменной, введите имя переменной, перед которым следует знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="9fa56-140">To display the value of a variable, type the variable name, preceded by a dollar sign (`$`).</span></span>

<span data-ttu-id="9fa56-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fa56-141">For example:</span></span>

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

<span data-ttu-id="9fa56-142">Чтобы изменить значение переменной, присвойте переменной новое значение.</span><span class="sxs-lookup"><span data-stu-id="9fa56-142">To change the value of a variable, assign a new value to the variable.</span></span>

<span data-ttu-id="9fa56-143">В следующих примерах показано значение `$MyVariable` переменной, изменяется значение переменной, а затем отображается новое значение.</span><span class="sxs-lookup"><span data-stu-id="9fa56-143">The following examples display the value of the `$MyVariable` variable, changes the value of the variable, and then displays the new value.</span></span>

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

<span data-ttu-id="9fa56-144">Чтобы удалить значение переменной, используйте `Clear-Variable` командлет или измените значение на `$null` .</span><span class="sxs-lookup"><span data-stu-id="9fa56-144">To delete the value of a variable, use the `Clear-Variable` cmdlet or change the value to `$null`.</span></span>

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

<span data-ttu-id="9fa56-145">Чтобы удалить переменную, используйте [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) или [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span><span class="sxs-lookup"><span data-stu-id="9fa56-145">To delete the variable, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) or [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span></span>

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

## <a name="types-of-variables"></a><span data-ttu-id="9fa56-146">Типы переменных</span><span class="sxs-lookup"><span data-stu-id="9fa56-146">Types of variables</span></span>

<span data-ttu-id="9fa56-147">В переменную можно хранить любой тип объекта, включая целые числа, строки, массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="9fa56-147">You can store any type of object in a variable, including integers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="9fa56-148">И — объекты, представляющие процессы, службы, журналы событий и компьютеры.</span><span class="sxs-lookup"><span data-stu-id="9fa56-148">And, objects that represent processes, services, event logs, and computers.</span></span>

<span data-ttu-id="9fa56-149">Переменные PowerShell слабо типизированы, а это означает, что они не ограничиваются определенным типом объекта.</span><span class="sxs-lookup"><span data-stu-id="9fa56-149">PowerShell variables are loosely typed, which means that they aren't limited to a particular type of object.</span></span> <span data-ttu-id="9fa56-150">Одна переменная может даже содержать коллекцию или массив различных типов объектов в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="9fa56-150">A single variable can even contain a collection, or array, of different types of objects at the same time.</span></span>

<span data-ttu-id="9fa56-151">Тип данных переменной определяется типами .NET значений этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-151">The data type of a variable is determined by the .NET types of the values of the variable.</span></span> <span data-ttu-id="9fa56-152">Чтобы просмотреть тип объекта переменной, используйте [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span><span class="sxs-lookup"><span data-stu-id="9fa56-152">To view a variable's object type, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span></span>

<span data-ttu-id="9fa56-153">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fa56-153">For example:</span></span>

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

<span data-ttu-id="9fa56-154">Можно использовать атрибут типа и нотацию приведения, чтобы гарантировать, что переменная может содержать только определенные типы объектов или объекты, которые могут быть преобразованы в этот тип.</span><span class="sxs-lookup"><span data-stu-id="9fa56-154">You can use a type attribute and cast notation to ensure that a variable can contain only specific object types or objects that can be converted to that type.</span></span> <span data-ttu-id="9fa56-155">При попытке присвоить значение другому типу PowerShell пытается преобразовать значение в его тип.</span><span class="sxs-lookup"><span data-stu-id="9fa56-155">If you try to assign a value of another type, PowerShell tries to convert the value to its type.</span></span> <span data-ttu-id="9fa56-156">Если тип не может быть преобразован, инструкция присваивания завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9fa56-156">If the type can't be converted, the assignment statement fails.</span></span>

<span data-ttu-id="9fa56-157">Чтобы использовать нотацию CAST, введите имя типа, заключенное в квадратные скобки, перед именем переменной (в левой части оператора присваивания).</span><span class="sxs-lookup"><span data-stu-id="9fa56-157">To use cast notation, enter a type name, enclosed in brackets, before the variable name (on the left side of the assignment statement).</span></span> <span data-ttu-id="9fa56-158">В следующем примере создается `$number` переменная, которая может содержать только целые числа, `$words` переменную, которая может содержать только строки, и `$dates` переменную, которая может содержать только объекты **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="9fa56-158">The following example creates a `$number` variable that can contain only integers, a `$words` variable that can contain only strings, and a `$dates` variable that can contain only **DateTime** objects.</span></span>

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

## <a name="using-variables-in-commands-and-expressions"></a><span data-ttu-id="9fa56-159">Использование переменных в командах и выражениях</span><span class="sxs-lookup"><span data-stu-id="9fa56-159">Using variables in commands and expressions</span></span>

<span data-ttu-id="9fa56-160">Чтобы использовать переменную в команде или выражении, введите имя переменной, перед которым следует знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="9fa56-160">To use a variable in a command or expression, type the variable name, preceded by the dollar (`$`) sign.</span></span>

<span data-ttu-id="9fa56-161">Если имя переменной и знак доллара не заключены в кавычки или заключены в двойные кавычки ( `"` ), значение переменной используется в команде или выражении.</span><span class="sxs-lookup"><span data-stu-id="9fa56-161">If the variable name and dollar sign aren't enclosed in quotation marks, or if they're enclosed in double quotation (`"`) marks, the value of the variable is used in the command or expression.</span></span>

<span data-ttu-id="9fa56-162">Если имя переменной и знак доллара заключены в одинарные кавычки ( `'` ), в выражении используется имя переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-162">If the variable name and dollar sign are enclosed in single quotation (`'`) marks, the variable name is used in the expression.</span></span>

<span data-ttu-id="9fa56-163">Дополнительные сведения об использовании кавычек в PowerShell см. в разделе [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="9fa56-163">For more information about using quotation marks in PowerShell, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="9fa56-164">В этом примере получается значение `$PROFILE` переменной, которая является путем к файлу профиля пользователя PowerShell в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-164">This example gets the value of the `$PROFILE` variable, which is the path to the PowerShell user profile file in the PowerShell console.</span></span>

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

<span data-ttu-id="9fa56-165">В этом примере показаны две команды, которые могут открыть профиль PowerShell в **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="9fa56-165">In this example, two commands are shown that can open the PowerShell profile in **notepad.exe**.</span></span> <span data-ttu-id="9fa56-166">В примере с символами двойной кавычки ( `"` ) используется значение переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-166">The example with double-quote (`"`) marks uses the variable's value.</span></span>

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

<span data-ttu-id="9fa56-167">В следующих примерах используются одиночные `'` кавычки (), которые обрабатывают переменную как литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="9fa56-167">The following examples use single-quote (`'`) marks that treat the variable as literal text.</span></span>

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

## <a name="variable-names-that-include-special-characters"></a><span data-ttu-id="9fa56-168">Имена переменных, содержащие специальные символы</span><span class="sxs-lookup"><span data-stu-id="9fa56-168">Variable names that include special characters</span></span>

<span data-ttu-id="9fa56-169">Имена переменных начинаются с символа доллара ( `$` ) и могут содержать буквенно-цифровые символы и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="9fa56-169">Variable names begin with a dollar (`$`) sign and can include alphanumeric characters and special characters.</span></span> <span data-ttu-id="9fa56-170">Длина имени переменной ограничена только доступной памятью.</span><span class="sxs-lookup"><span data-stu-id="9fa56-170">The variable name length is limited only by available memory.</span></span>

<span data-ttu-id="9fa56-171">Рекомендуется, чтобы имена переменных включали только буквенно-цифровые символы и символ подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="9fa56-171">The best practice is that variable names include only alphanumeric characters and the underscore (`_`) character.</span></span> <span data-ttu-id="9fa56-172">Имена переменных, содержащие пробелы и другие специальные символы, трудно использовать, поэтому их следует избегать.</span><span class="sxs-lookup"><span data-stu-id="9fa56-172">Variable names that include spaces and other special characters, are difficult to use and should be avoided.</span></span>

<span data-ttu-id="9fa56-173">Буквенно-цифровые имена переменных могут содержать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="9fa56-173">Alphanumeric variable names can contain these characters:</span></span>

- <span data-ttu-id="9fa56-174">Символы Юникода из следующих категорий: **Lu** , **LL** , **lt** , **LM** , **with** или **ND**.</span><span class="sxs-lookup"><span data-stu-id="9fa56-174">Unicode characters from these categories: **Lu** , **Ll** , **Lt** , **Lm** , **Lo** , or **Nd**.</span></span>
- <span data-ttu-id="9fa56-175">Символ подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="9fa56-175">Underscore (`_`) character.</span></span>
- <span data-ttu-id="9fa56-176">Символ вопросительного `?` знака ().</span><span class="sxs-lookup"><span data-stu-id="9fa56-176">Question mark (`?`) character.</span></span>

<span data-ttu-id="9fa56-177">В следующем списке содержатся описания категорий Юникода.</span><span class="sxs-lookup"><span data-stu-id="9fa56-177">The following list contains the Unicode category descriptions.</span></span> <span data-ttu-id="9fa56-178">Дополнительные сведения см. в разделе [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span><span class="sxs-lookup"><span data-stu-id="9fa56-178">For more information, see [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span></span>

- <span data-ttu-id="9fa56-179">**Lu** — упперкаселеттер</span><span class="sxs-lookup"><span data-stu-id="9fa56-179">**Lu** - UppercaseLetter</span></span>
- <span data-ttu-id="9fa56-180">**LL** -ловеркаселеттер</span><span class="sxs-lookup"><span data-stu-id="9fa56-180">**Ll** - LowercaseLetter</span></span>
- <span data-ttu-id="9fa56-181">**Lt** — титлекаселеттер</span><span class="sxs-lookup"><span data-stu-id="9fa56-181">**Lt** - TitlecaseLetter</span></span>
- <span data-ttu-id="9fa56-182">**LM** -модифиерлеттер</span><span class="sxs-lookup"><span data-stu-id="9fa56-182">**Lm** - ModifierLetter</span></span>
- <span data-ttu-id="9fa56-183">**Lo** Осерлеттер</span><span class="sxs-lookup"><span data-stu-id="9fa56-183">**Lo** - OtherLetter</span></span>
- <span data-ttu-id="9fa56-184">**ND** -деЦималдигитнумбер</span><span class="sxs-lookup"><span data-stu-id="9fa56-184">**Nd** - DecimalDigitNumber</span></span>

<span data-ttu-id="9fa56-185">Чтобы создать или отобразить имя переменной, содержащей пробелы или специальные символы, заключите имя переменной в символы фигурных скобок ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="9fa56-185">To create or display a variable name that includes spaces or special characters, enclose the variable name with the curly braces (`{}`) characters.</span></span>
<span data-ttu-id="9fa56-186">Фигурные скобки направляют PowerShell для интерпретации символов имени переменной как литералов.</span><span class="sxs-lookup"><span data-stu-id="9fa56-186">The curly braces direct PowerShell to interpret the variable name's characters as literals.</span></span>

<span data-ttu-id="9fa56-187">В именах специальных символьных переменных могут содержаться следующие символы:</span><span class="sxs-lookup"><span data-stu-id="9fa56-187">Special character variable names can contain these characters:</span></span>

- <span data-ttu-id="9fa56-188">Любой символ Юникода со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="9fa56-188">Any Unicode character, with the following exceptions:</span></span>
  - <span data-ttu-id="9fa56-189">Символ закрывающей фигурной скобки ( `}` ) (U + 007D).</span><span class="sxs-lookup"><span data-stu-id="9fa56-189">The closing curly brace (`}`) character (U+007D).</span></span>
  - <span data-ttu-id="9fa56-190">Символ обратной кавычки ( `` ` `` ) (U + 0060).</span><span class="sxs-lookup"><span data-stu-id="9fa56-190">The backtick (`` ` ``) character (U+0060).</span></span> <span data-ttu-id="9fa56-191">Обратная шкала используется для экранирования символов Юникода, чтобы они обрабатывались как литералы.</span><span class="sxs-lookup"><span data-stu-id="9fa56-191">The backtick is used to escape Unicode characters so they're treated as literals.</span></span>

<span data-ttu-id="9fa56-192">PowerShell содержит зарезервированные переменные `$$` , такие как, `$?` , и `$^` `$_` , которые содержат буквенно-цифровые и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="9fa56-192">PowerShell has reserved variables such as `$$`, `$?`, `$^`, and `$_` that contain alphanumeric and special characters.</span></span> <span data-ttu-id="9fa56-193">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_automatic_variables.md).</span><span class="sxs-lookup"><span data-stu-id="9fa56-193">For more information, see [about_Automatic_Variables](about_automatic_variables.md).</span></span>

<span data-ttu-id="9fa56-194">Например, следующая команда создает переменную с именем `save-items` .</span><span class="sxs-lookup"><span data-stu-id="9fa56-194">For example, the following command creates the variable named `save-items`.</span></span> <span data-ttu-id="9fa56-195">Фигурные скобки ( `{}` ) необходимы, так как имя переменной включает `-` Специальный символ дефис ().</span><span class="sxs-lookup"><span data-stu-id="9fa56-195">The curly braces (`{}`) are needed because variable name includes a hyphen (`-`) special character.</span></span>

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

<span data-ttu-id="9fa56-196">Следующая команда возвращает дочерние элементы в каталоге, представленном `ProgramFiles(x86)` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="9fa56-196">The following command gets the child items in the directory that is represented by the `ProgramFiles(x86)` environment variable.</span></span>

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

<span data-ttu-id="9fa56-197">Чтобы сослаться на имя переменной, включающую фигурные скобки, заключите имя переменной в фигурные скобки и используйте символ обратной кавычки для экранирования фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="9fa56-197">To reference a variable name that includes braces, enclose the variable name in braces, and use the backtick character to escape the braces.</span></span> <span data-ttu-id="9fa56-198">Например, чтобы создать переменную с именем `this{value}is` Type:</span><span class="sxs-lookup"><span data-stu-id="9fa56-198">For example, to create a variable named `this{value}is` type:</span></span>

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a><span data-ttu-id="9fa56-199">Переменные и область</span><span class="sxs-lookup"><span data-stu-id="9fa56-199">Variables and scope</span></span>

<span data-ttu-id="9fa56-200">По умолчанию переменные доступны только в области, в которой они созданы.</span><span class="sxs-lookup"><span data-stu-id="9fa56-200">By default, variables are only available in the scope in which they're created.</span></span>

<span data-ttu-id="9fa56-201">Например, переменная, созданная в функции, доступна только внутри функции.</span><span class="sxs-lookup"><span data-stu-id="9fa56-201">For example, a variable that you create in a function is available only within the function.</span></span> <span data-ttu-id="9fa56-202">Переменная, создаваемая в скрипте, доступна только внутри скрипта.</span><span class="sxs-lookup"><span data-stu-id="9fa56-202">A variable that you create in a script is available only within the script.</span></span> <span data-ttu-id="9fa56-203">Если вы помещаете скрипт в точку, переменная добавляется в текущую область.</span><span class="sxs-lookup"><span data-stu-id="9fa56-203">If you dot-source the script, the variable is added to the current scope.</span></span> <span data-ttu-id="9fa56-204">Дополнительные сведения см. в разделе [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="9fa56-204">For more information, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="9fa56-205">С помощью модификатора области можно изменить область действия по умолчанию для переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-205">You can use a scope modifier to change the default scope of the variable.</span></span> <span data-ttu-id="9fa56-206">Следующее выражение создает переменную с именем `Computers` .</span><span class="sxs-lookup"><span data-stu-id="9fa56-206">The following expression creates a variable named `Computers`.</span></span> <span data-ttu-id="9fa56-207">Переменная имеет глобальную область, даже если она создается в скрипте или функции.</span><span class="sxs-lookup"><span data-stu-id="9fa56-207">The variable has a global scope, even when it's created in a script or function.</span></span>

```powershell
$Global:Computers = "Server01"
```

<span data-ttu-id="9fa56-208">Для любого скрипта или команды, выполняемой вне сеанса, необходим `Using` Модификатор области для внедрения значений переменных из области вызывающего сеанса, чтобы код сеанса мог получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="9fa56-208">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span>

<span data-ttu-id="9fa56-209">Дополнительные сведения см. в разделе [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9fa56-209">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="saving-variables"></a><span data-ttu-id="9fa56-210">Сохранение переменных</span><span class="sxs-lookup"><span data-stu-id="9fa56-210">Saving variables</span></span>

<span data-ttu-id="9fa56-211">Создаваемые переменные доступны только в том сеансе, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="9fa56-211">Variables that you create are available only in the session in which you create them.</span></span> <span data-ttu-id="9fa56-212">При закрытии сеанса они теряются.</span><span class="sxs-lookup"><span data-stu-id="9fa56-212">They're lost when you close your session.</span></span>

<span data-ttu-id="9fa56-213">Чтобы создать переменную в каждом запущенном сеансе PowerShell, добавьте переменную в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-213">To create the variable in every PowerShell session that you start, add the variable to your PowerShell profile.</span></span>

<span data-ttu-id="9fa56-214">Например, чтобы изменить значение `$VerbosePreference` переменной в каждом сеансе PowerShell, добавьте следующую команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa56-214">For example, to change the value of the `$VerbosePreference` variable in every PowerShell session, add the following command to your PowerShell profile.</span></span>

```powershell
$VerbosePreference = "Continue"
```

<span data-ttu-id="9fa56-215">Эту команду можно добавить в профиль PowerShell, открыв `$PROFILE` файл в текстовом редакторе, например **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="9fa56-215">You can add this command to your PowerShell profile by opening the `$PROFILE` file in a text editor, such as **notepad.exe**.</span></span> <span data-ttu-id="9fa56-216">Дополнительные сведения о профилях PowerShell см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9fa56-216">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="the-variable-drive"></a><span data-ttu-id="9fa56-217">Переменная: диск</span><span class="sxs-lookup"><span data-stu-id="9fa56-217">The Variable: drive</span></span>

<span data-ttu-id="9fa56-218">Поставщик переменных PowerShell создает `Variable:` диск, который выглядит и действует как диск файловой системы, но содержит переменные в сеансе и их значения.</span><span class="sxs-lookup"><span data-stu-id="9fa56-218">The PowerShell Variable provider creates a `Variable:` drive that looks and acts like a file system drive, but it contains the variables in your session and their values.</span></span>

<span data-ttu-id="9fa56-219">Чтобы перейти на `Variable:` диск, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9fa56-219">To change to the `Variable:` drive, use the following command:</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="9fa56-220">Чтобы получить список элементов и переменных на `Variable:` диске, используйте `Get-Item` `Get-ChildItem` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="9fa56-220">To list the items and variables in the `Variable:` drive, use the `Get-Item` or `Get-ChildItem` cmdlets.</span></span>

```powershell
Get-ChildItem Variable:
```

<span data-ttu-id="9fa56-221">Чтобы получить значение определенной переменной, используйте нотацию файловой системы, чтобы указать имя диска и имя переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-221">To get the value of a particular variable, use file system notation to specify the name of the drive and the name of the variable.</span></span> <span data-ttu-id="9fa56-222">Например, чтобы получить `$PSCulture` автоматическую переменную, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9fa56-222">For example, to get the `$PSCulture` automatic variable, use the following command.</span></span>

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

<span data-ttu-id="9fa56-223">Чтобы просмотреть дополнительные сведения о `Variable:` диске и поставщике переменных PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="9fa56-223">To display more information about the `Variable:` drive and the PowerShell Variable provider, type:</span></span>

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a><span data-ttu-id="9fa56-224">Синтаксис переменных с путями поставщика</span><span class="sxs-lookup"><span data-stu-id="9fa56-224">Variable syntax with provider paths</span></span>

<span data-ttu-id="9fa56-225">Путь к поставщику можно добавить с помощью символа доллара ( `$` ) и получить доступ к содержимому любого поставщика, реализующего интерфейс [иконтенткмдлетпровидер](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) .</span><span class="sxs-lookup"><span data-stu-id="9fa56-225">You can prefix a provider path with the dollar (`$`) sign, and access the content of any provider that implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>

<span data-ttu-id="9fa56-226">Следующие встроенные поставщики PowerShell поддерживают эту нотацию:</span><span class="sxs-lookup"><span data-stu-id="9fa56-226">The following built-in PowerShell providers support this notation:</span></span>

- [<span data-ttu-id="9fa56-227">about_Environment_Provider</span><span class="sxs-lookup"><span data-stu-id="9fa56-227">about_Environment_Provider</span></span>](about_Environment_Provider.md)
- [<span data-ttu-id="9fa56-228">about_Variable_Provider</span><span class="sxs-lookup"><span data-stu-id="9fa56-228">about_Variable_Provider</span></span>](about_Variable_Provider.md)
- [<span data-ttu-id="9fa56-229">about_Function_Provider</span><span class="sxs-lookup"><span data-stu-id="9fa56-229">about_Function_Provider</span></span>](about_Function_Provider.md)
- [<span data-ttu-id="9fa56-230">about_Alias_Provider</span><span class="sxs-lookup"><span data-stu-id="9fa56-230">about_Alias_Provider</span></span>](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a><span data-ttu-id="9fa56-231">Командлеты переменных</span><span class="sxs-lookup"><span data-stu-id="9fa56-231">The variable cmdlets</span></span>

<span data-ttu-id="9fa56-232">PowerShell включает набор командлетов, предназначенных для управления переменными.</span><span class="sxs-lookup"><span data-stu-id="9fa56-232">PowerShell includes a set of cmdlets that are designed to manage variables.</span></span>

<span data-ttu-id="9fa56-233">Чтобы получить список командлетов, введите:</span><span class="sxs-lookup"><span data-stu-id="9fa56-233">To list the cmdlets, type:</span></span>

```powershell
Get-Command -Noun Variable
```

<span data-ttu-id="9fa56-234">Чтобы получить справку по конкретному командлету, введите:</span><span class="sxs-lookup"><span data-stu-id="9fa56-234">To get help for a specific cmdlet, type:</span></span>

```powershell
Get-Help <cmdlet-name>
```

| <span data-ttu-id="9fa56-235">Имя командлета</span><span class="sxs-lookup"><span data-stu-id="9fa56-235">Cmdlet Name</span></span>       | <span data-ttu-id="9fa56-236">Описание</span><span class="sxs-lookup"><span data-stu-id="9fa56-236">Description</span></span>                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | <span data-ttu-id="9fa56-237">Удаляет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-237">Deletes the value of a variable.</span></span>           |
| `Get-Variable`    | <span data-ttu-id="9fa56-238">Получает переменные в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="9fa56-238">Gets the variables in the current console.</span></span> |
| `New-Variable`    | <span data-ttu-id="9fa56-239">Создает новую переменную.</span><span class="sxs-lookup"><span data-stu-id="9fa56-239">Creates a new variable.</span></span>                    |
| `Remove-Variable` | <span data-ttu-id="9fa56-240">Удаляет переменную и ее значение.</span><span class="sxs-lookup"><span data-stu-id="9fa56-240">Deletes a variable and its value.</span></span>          |
| `Set-Variable`    | <span data-ttu-id="9fa56-241">Изменяет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="9fa56-241">Changes the value of a variable.</span></span>           |

## <a name="see-also"></a><span data-ttu-id="9fa56-242">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9fa56-242">See also</span></span>

[<span data-ttu-id="9fa56-243">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="9fa56-243">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="9fa56-244">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="9fa56-244">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="9fa56-245">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="9fa56-245">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="9fa56-246">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="9fa56-246">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="9fa56-247">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="9fa56-247">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="9fa56-248">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="9fa56-248">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="9fa56-249">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="9fa56-249">about_Remote_Variables</span></span>](about_Remote_Variables.md)
