---
description: Описывает разделы данных, которые изолируют текстовые строки и другие данные, предназначенные только для чтения, из логики скрипта.
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: 1f2a0bae0721bc9adf5b3ba92d5be32d21306a46
ms.sourcegitcommit: 04faa7dc1122bce839295d4891bd8b2f0ecb06ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "99604496"
---
# <a name="about-data-sections"></a><span data-ttu-id="1e2c1-103">Разделы данных</span><span class="sxs-lookup"><span data-stu-id="1e2c1-103">About Data Sections</span></span>

## <a name="short-description"></a><span data-ttu-id="1e2c1-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="1e2c1-104">Short Description</span></span>
<span data-ttu-id="1e2c1-105">Описывает разделы данных, которые изолируют текстовые строки и другие данные, предназначенные только для чтения, из логики скрипта.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-105">Explains Data sections, which isolate text strings and other read-only data from script logic.</span></span>

## <a name="long-description"></a><span data-ttu-id="1e2c1-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="1e2c1-106">Long Description</span></span>

<span data-ttu-id="1e2c1-107">Скрипты, разработанные для PowerShell, могут содержать один или несколько разделов данных, содержащих только данные.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-107">Scripts that are designed for PowerShell can have one or more Data sections that contain only data.</span></span> <span data-ttu-id="1e2c1-108">Можно включить один или несколько разделов данных в любой сценарий, функцию или расширенную функцию.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-108">You can include one or more Data sections in any script, function, or advanced function.</span></span> <span data-ttu-id="1e2c1-109">Содержимое раздела данных ограничено указанным подмножеством языка сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-109">The content of the Data section is restricted to a specified subset of the PowerShell scripting language.</span></span>

<span data-ttu-id="1e2c1-110">Отделение данных от логики кода упрощает выявление и управление логикой и данными.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-110">Separating data from code logic makes it easier to identify and manage both logic and data.</span></span> <span data-ttu-id="1e2c1-111">Он позволяет иметь отдельные строковые файлы ресурсов для текста, например сообщения об ошибках и строки справки.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-111">It lets you have separate string resource files for text, such as error messages and Help strings.</span></span> <span data-ttu-id="1e2c1-112">Он также изолирует логику кода, которая упрощает тестирование безопасности и проверки.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-112">It also isolates the code logic, which facilitates security and validation tests.</span></span>

<span data-ttu-id="1e2c1-113">В PowerShell раздел данных используется для поддержки интернационализации сценариев.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-113">In PowerShell, the Data section is used to support script internationalization.</span></span>
<span data-ttu-id="1e2c1-114">Разделы данных можно использовать для упрощения изоляции, обнаружения и обработки строк, которые будут переведены на множество языков пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-114">You can use Data sections to make it easier to isolate, locate, and process strings that will be translated into many user interface (UI) languages.</span></span>

<span data-ttu-id="1e2c1-115">Раздел данных является функцией PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-115">The Data section is a PowerShell 2.0 feature.</span></span> <span data-ttu-id="1e2c1-116">Скрипты с разделами данных не будут выполняться в PowerShell 1,0 без версии.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-116">Scripts with Data sections will not run in PowerShell 1.0 without revision.</span></span>

### <a name="syntax"></a><span data-ttu-id="1e2c1-117">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e2c1-117">Syntax</span></span>

<span data-ttu-id="1e2c1-118">Синтаксис для раздела данных выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-118">The syntax for a Data section is as follows:</span></span>

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

<span data-ttu-id="1e2c1-119">Требуется ключевое слово Data.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-119">The Data keyword is required.</span></span> <span data-ttu-id="1e2c1-120">Не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-120">It is not case-sensitive.</span></span> <span data-ttu-id="1e2c1-121">Разрешенное содержимое ограничено следующими элементами:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-121">The permitted content is limited to the following elements:</span></span>

- <span data-ttu-id="1e2c1-122">Все операторы PowerShell, Кроме `-match`</span><span class="sxs-lookup"><span data-stu-id="1e2c1-122">All PowerShell operators, except `-match`</span></span>
- <span data-ttu-id="1e2c1-123">`If``Else`операторы, и `ElseIf`</span><span class="sxs-lookup"><span data-stu-id="1e2c1-123">`If`, `Else`, and `ElseIf` statements</span></span>
- <span data-ttu-id="1e2c1-124">Следующие автоматические переменные: `$PsCulture` , `$PsUICulture` , `$True` , `$False` и `$Null`</span><span class="sxs-lookup"><span data-stu-id="1e2c1-124">The following automatic variables: `$PsCulture`, `$PsUICulture`, `$True`, `$False`, and `$Null`</span></span>
- <span data-ttu-id="1e2c1-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1e2c1-125">Comments</span></span>
- <span data-ttu-id="1e2c1-126">Конвейеры</span><span class="sxs-lookup"><span data-stu-id="1e2c1-126">Pipelines</span></span>
- <span data-ttu-id="1e2c1-127">Операторы, разделенные точкой с запятой ( `;` )</span><span class="sxs-lookup"><span data-stu-id="1e2c1-127">Statements separated by semicolons (`;`)</span></span>
- <span data-ttu-id="1e2c1-128">Литералы, например следующие:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-128">Literals, such as the following:</span></span>

  ```powershell
  a
  1
  1,2,3
  "PowerShell 2.0"
  @( "red", "green", "blue" )
  @{ a = 0x1; b = "great"; c ="script" }
  [XML] @'
  <p> Hello, World </p>
  '@
  ```

- <span data-ttu-id="1e2c1-129">Командлеты, разрешенные в разделе данных.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-129">Cmdlets that are permitted in a Data section.</span></span> <span data-ttu-id="1e2c1-130">По умолчанию разрешен только `ConvertFrom-StringData` командлет.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-130">By default, only the `ConvertFrom-StringData` cmdlet is permitted.</span></span>
- <span data-ttu-id="1e2c1-131">Командлеты, разрешенные в разделе данных с помощью `-SupportedCommand` параметра.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-131">Cmdlets that you permit in a Data section by using the `-SupportedCommand` parameter.</span></span>

<span data-ttu-id="1e2c1-132">При использовании `ConvertFrom-StringData` командлета в разделе данных можно заключать пары "ключ-значение" в строки с одинарными кавычками или двойными кавычками или в строках с одинарными кавычками или двойными кавычками.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-132">When you use the `ConvertFrom-StringData` cmdlet in a Data section, you can enclose the key-value pairs in single-quoted or double-quoted strings or in single-quoted or double-quoted here-strings.</span></span> <span data-ttu-id="1e2c1-133">Однако строки, содержащие переменные и части выражения, должны быть заключены в строки с одинарными кавычками или в строках с одинарными кавычками, чтобы эти переменные не были развернуты, а части выражения не были исполняемыми.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-133">However, strings that contain variables and subexpressions must be enclosed in single-quoted strings or in single-quoted here-strings so that the variables are not expanded and the subexpressions are not executable.</span></span>

### <a name="-supportedcommand"></a><span data-ttu-id="1e2c1-134">-Суппортедкомманд</span><span class="sxs-lookup"><span data-stu-id="1e2c1-134">-SupportedCommand</span></span>

<span data-ttu-id="1e2c1-135">`-SupportedCommand`Параметр позволяет указать, что командлет или функция создает только данные.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-135">The `-SupportedCommand` parameter allows you to indicate that a cmdlet or function generates only data.</span></span> <span data-ttu-id="1e2c1-136">Он предназначен для того, чтобы разрешить пользователям включать командлеты и функции в раздел данных, который они записали или протестировали.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-136">It is designed to allow users to include cmdlets and functions in a data section that they have written or tested.</span></span>

<span data-ttu-id="1e2c1-137">Значение `-SupportedCommand` представляет собой разделенный запятыми список из одного или нескольких имен командлетов или функций.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-137">The value of `-SupportedCommand` is a comma-separated list of one or more cmdlet or function names.</span></span>

<span data-ttu-id="1e2c1-138">Например, в следующем разделе данных содержится командлет, созданный пользователем, `Format-Xml` который форматирует данные в XML-файле:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-138">For example, the following data section includes a user-written cmdlet, `Format-Xml`, that formats data in an XML file:</span></span>

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a><span data-ttu-id="1e2c1-139">Использование раздела данных</span><span class="sxs-lookup"><span data-stu-id="1e2c1-139">Using a Data Section</span></span>

<span data-ttu-id="1e2c1-140">Чтобы использовать содержимое раздела данных, назначьте его переменной и используйте нотацию переменной для доступа к содержимому.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-140">To use the content of a Data section, assign it to a variable and use variable notation to access the content.</span></span>

<span data-ttu-id="1e2c1-141">Например, следующий раздел данных содержит `ConvertFrom-StringData` команду, преобразующую данную строку в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-141">For example, the following data section contains a `ConvertFrom-StringData` command that converts the here-string into a hash table.</span></span> <span data-ttu-id="1e2c1-142">Хэш-таблица назначается `$TextMsgs` переменной.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-142">The hash table is assigned to the `$TextMsgs` variable.</span></span>

<span data-ttu-id="1e2c1-143">`$TextMsgs`Переменная не входит в раздел данных.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-143">The `$TextMsgs` variable is not part of the data section.</span></span>

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="1e2c1-144">Чтобы получить доступ к ключам и значениям в хэш-таблице в `$TextMsgs` , используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-144">To access the keys and values in hash table in `$TextMsgs`, use the following commands.</span></span>

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

<span data-ttu-id="1e2c1-145">Кроме того, можно добавить имя переменной в определение раздела данных.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-145">Alternately, you can put the variable name in the definition of the Data section.</span></span> <span data-ttu-id="1e2c1-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-146">For example:</span></span>

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

<span data-ttu-id="1e2c1-147">Результат аналогичен предыдущему примеру.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-147">The result is the same as the previous example.</span></span>

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a><span data-ttu-id="1e2c1-148">Примеры</span><span class="sxs-lookup"><span data-stu-id="1e2c1-148">Examples</span></span>

<span data-ttu-id="1e2c1-149">Простые строки данных.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-149">Simple data strings.</span></span>

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

<span data-ttu-id="1e2c1-150">Строки, включающие разрешенные переменные.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-150">Strings that include permitted variables.</span></span>

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

<span data-ttu-id="1e2c1-151">Строка с одинарной кавычкой, которая использует `ConvertFrom-StringData` командлет:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-151">A single-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="1e2c1-152">Строка, заключенная в двойные кавычки, с использованием `ConvertFrom-StringData` командлета:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-152">A double-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

<span data-ttu-id="1e2c1-153">Раздел данных, содержащий пользовательский командлет, создающий данные:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-153">A data section that includes a user-written cmdlet that generates data:</span></span>

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a><span data-ttu-id="1e2c1-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-154">See Also</span></span>

[<span data-ttu-id="1e2c1-155">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="1e2c1-155">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="1e2c1-156">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="1e2c1-156">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="1e2c1-157">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="1e2c1-157">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="1e2c1-158">about_If</span><span class="sxs-lookup"><span data-stu-id="1e2c1-158">about_If</span></span>](about_If.md)

[<span data-ttu-id="1e2c1-159">about_Operators</span><span class="sxs-lookup"><span data-stu-id="1e2c1-159">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="1e2c1-160">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="1e2c1-160">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="1e2c1-161">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="1e2c1-161">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="1e2c1-162">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="1e2c1-162">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="1e2c1-163">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="1e2c1-163">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

