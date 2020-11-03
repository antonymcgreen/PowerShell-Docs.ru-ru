---
description: Описывает разделы данных, которые изолируют текстовые строки и другие данные, предназначенные только для чтения, из логики скрипта.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: b4bd56148ab9f5d50a6ebaf5bf0894c8066796ff
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231517"
---
# <a name="about-data-sections"></a><span data-ttu-id="83698-104">Разделы данных</span><span class="sxs-lookup"><span data-stu-id="83698-104">About Data Sections</span></span>

## <a name="short-description"></a><span data-ttu-id="83698-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="83698-105">Short Description</span></span>
<span data-ttu-id="83698-106">Описывает разделы данных, которые изолируют текстовые строки и другие данные, предназначенные только для чтения, из логики скрипта.</span><span class="sxs-lookup"><span data-stu-id="83698-106">Explains Data sections, which isolate text strings and other read-only data from script logic.</span></span>

## <a name="long-description"></a><span data-ttu-id="83698-107">Полное описание</span><span class="sxs-lookup"><span data-stu-id="83698-107">Long Description</span></span>

<span data-ttu-id="83698-108">Скрипты, разработанные для PowerShell, могут содержать один или несколько разделов данных, содержащих только данные.</span><span class="sxs-lookup"><span data-stu-id="83698-108">Scripts that are designed for PowerShell can have one or more Data sections that contain only data.</span></span> <span data-ttu-id="83698-109">Можно включить один или несколько разделов данных в любой сценарий, функцию или расширенную функцию.</span><span class="sxs-lookup"><span data-stu-id="83698-109">You can include one or more Data sections in any script, function, or advanced function.</span></span> <span data-ttu-id="83698-110">Содержимое раздела данных ограничено указанным подмножеством языка сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83698-110">The content of the Data section is restricted to a specified subset of the PowerShell scripting language.</span></span>

<span data-ttu-id="83698-111">Отделение данных от логики кода упрощает выявление и управление логикой и данными.</span><span class="sxs-lookup"><span data-stu-id="83698-111">Separating data from code logic makes it easier to identify and manage both logic and data.</span></span> <span data-ttu-id="83698-112">Он позволяет иметь отдельные строковые файлы ресурсов для текста, например сообщения об ошибках и строки справки.</span><span class="sxs-lookup"><span data-stu-id="83698-112">It lets you have separate string resource files for text, such as error messages and Help strings.</span></span> <span data-ttu-id="83698-113">Он также изолирует логику кода, которая упрощает тестирование безопасности и проверки.</span><span class="sxs-lookup"><span data-stu-id="83698-113">It also isolates the code logic, which facilitates security and validation tests.</span></span>

<span data-ttu-id="83698-114">В PowerShell раздел данных используется для поддержки интернационализации сценариев.</span><span class="sxs-lookup"><span data-stu-id="83698-114">In PowerShell, the Data section is used to support script internationalization.</span></span>
<span data-ttu-id="83698-115">Разделы данных можно использовать для упрощения изоляции, обнаружения и обработки строк, которые будут переведены на множество языков пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="83698-115">You can use Data sections to make it easier to isolate, locate, and process strings that will be translated into many user interface (UI) languages.</span></span>

<span data-ttu-id="83698-116">Раздел данных является функцией PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="83698-116">The Data section is a PowerShell 2.0 feature.</span></span> <span data-ttu-id="83698-117">Скрипты с разделами данных не будут выполняться в PowerShell 1,0 без версии.</span><span class="sxs-lookup"><span data-stu-id="83698-117">Scripts with Data sections will not run in PowerShell 1.0 without revision.</span></span>

### <a name="syntax"></a><span data-ttu-id="83698-118">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83698-118">Syntax</span></span>

<span data-ttu-id="83698-119">Синтаксис для раздела данных выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83698-119">The syntax for a Data section is as follows:</span></span>

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

<span data-ttu-id="83698-120">Требуется ключевое слово Data.</span><span class="sxs-lookup"><span data-stu-id="83698-120">The Data keyword is required.</span></span> <span data-ttu-id="83698-121">Не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="83698-121">It is not case-sensitive.</span></span> <span data-ttu-id="83698-122">Разрешенное содержимое ограничено следующими элементами:</span><span class="sxs-lookup"><span data-stu-id="83698-122">The permitted content is limited to the following elements:</span></span>

- <span data-ttu-id="83698-123">Все операторы PowerShell, Кроме `-match`</span><span class="sxs-lookup"><span data-stu-id="83698-123">All PowerShell operators, except `-match`</span></span>
- <span data-ttu-id="83698-124">`If``Else`операторы, и `ElseIf`</span><span class="sxs-lookup"><span data-stu-id="83698-124">`If`, `Else`, and `ElseIf` statements</span></span>
- <span data-ttu-id="83698-125">Следующие автоматические переменные: `$PsCulture` , `$PsUICulture` , `$True` , `$False` и `$Null`</span><span class="sxs-lookup"><span data-stu-id="83698-125">The following automatic variables: `$PsCulture`, `$PsUICulture`, `$True`, `$False`, and `$Null`</span></span>
- <span data-ttu-id="83698-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="83698-126">Comments</span></span>
- <span data-ttu-id="83698-127">Конвейеры</span><span class="sxs-lookup"><span data-stu-id="83698-127">Pipelines</span></span>
- <span data-ttu-id="83698-128">Операторы, разделенные точкой с запятой ( `;` )</span><span class="sxs-lookup"><span data-stu-id="83698-128">Statements separated by semicolons (`;`)</span></span>
- <span data-ttu-id="83698-129">Литералы, например следующие:</span><span class="sxs-lookup"><span data-stu-id="83698-129">Literals, such as the following:</span></span>

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

- <span data-ttu-id="83698-130">Командлеты, разрешенные в разделе данных.</span><span class="sxs-lookup"><span data-stu-id="83698-130">Cmdlets that are permitted in a Data section.</span></span> <span data-ttu-id="83698-131">По умолчанию разрешен только `ConvertFrom-StringData` командлет.</span><span class="sxs-lookup"><span data-stu-id="83698-131">By default, only the `ConvertFrom-StringData` cmdlet is permitted.</span></span>
- <span data-ttu-id="83698-132">Командлеты, разрешенные в разделе данных с помощью `-SupportedCommand` параметра.</span><span class="sxs-lookup"><span data-stu-id="83698-132">Cmdlets that you permit in a Data section by using the `-SupportedCommand` parameter.</span></span>

<span data-ttu-id="83698-133">При использовании `ConvertFrom-StringData` командлета в разделе данных можно заключать пары "ключ-значение" в строки с одинарными кавычками или двойными кавычками или в строках с одинарными кавычками или двойными кавычками.</span><span class="sxs-lookup"><span data-stu-id="83698-133">When you use the `ConvertFrom-StringData` cmdlet in a Data section, you can enclose the key-value pairs in single-quoted or double-quoted strings or in single-quoted or double-quoted here-strings.</span></span> <span data-ttu-id="83698-134">Однако строки, содержащие переменные и части выражения, должны быть заключены в строки с одинарными кавычками или в строках с одинарными кавычками, чтобы эти переменные не были развернуты, а части выражения не были исполняемыми.</span><span class="sxs-lookup"><span data-stu-id="83698-134">However, strings that contain variables and subexpressions must be enclosed in single-quoted strings or in single-quoted here-strings so that the variables are not expanded and the subexpressions are not executable.</span></span>

### <a name="-supportedcommand"></a><span data-ttu-id="83698-135">-Суппортедкомманд</span><span class="sxs-lookup"><span data-stu-id="83698-135">-SupportedCommand</span></span>

<span data-ttu-id="83698-136">`-SupportedCommand`Параметр позволяет указать, что командлет или функция создает только данные.</span><span class="sxs-lookup"><span data-stu-id="83698-136">The `-SupportedCommand` parameter allows you to indicate that a cmdlet or function generates only data.</span></span> <span data-ttu-id="83698-137">Он предназначен для того, чтобы разрешить пользователям включать командлеты и функции в раздел данных, который они записали или протестировали.</span><span class="sxs-lookup"><span data-stu-id="83698-137">It is designed to allow users to include cmdlets and functions in a data section that they have written or tested.</span></span>

<span data-ttu-id="83698-138">Значение `-SupportedCommand` представляет собой разделенный запятыми список из одного или нескольких имен командлетов или функций.</span><span class="sxs-lookup"><span data-stu-id="83698-138">The value of `-SupportedCommand` is a comma-separated list of one or more cmdlet or function names.</span></span>

<span data-ttu-id="83698-139">Например, в следующем разделе данных содержится командлет, созданный пользователем, `Format-XML` который форматирует данные в XML-файле:</span><span class="sxs-lookup"><span data-stu-id="83698-139">For example, the following data section includes a user-written cmdlet, `Format-XML`, that formats data in an XML file:</span></span>

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a><span data-ttu-id="83698-140">Использование раздела данных</span><span class="sxs-lookup"><span data-stu-id="83698-140">Using a Data Section</span></span>

<span data-ttu-id="83698-141">Чтобы использовать содержимое раздела данных, назначьте его переменной и используйте нотацию переменной для доступа к содержимому.</span><span class="sxs-lookup"><span data-stu-id="83698-141">To use the content of a Data section, assign it to a variable and use variable notation to access the content.</span></span>

<span data-ttu-id="83698-142">Например, следующий раздел данных содержит `ConvertFrom-StringData` команду, преобразующую данную строку в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="83698-142">For example, the following data section contains a `ConvertFrom-StringData` command that converts the here-string into a hash table.</span></span> <span data-ttu-id="83698-143">Хэш-таблица назначается `$TextMsgs` переменной.</span><span class="sxs-lookup"><span data-stu-id="83698-143">The hash table is assigned to the `$TextMsgs` variable.</span></span>

<span data-ttu-id="83698-144">`$TextMsgs`Переменная не входит в раздел данных.</span><span class="sxs-lookup"><span data-stu-id="83698-144">The `$TextMsgs` variable is not part of the data section.</span></span>

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="83698-145">Чтобы получить доступ к ключам и значениям в хэш-таблице в `$TextMsgs` , используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="83698-145">To access the keys and values in hash table in `$TextMsgs`, use the following commands.</span></span>

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

<span data-ttu-id="83698-146">Кроме того, можно добавить имя переменной в определение раздела данных.</span><span class="sxs-lookup"><span data-stu-id="83698-146">Alternately, you can put the variable name in the definition of the Data section.</span></span> <span data-ttu-id="83698-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="83698-147">For example:</span></span>

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

<span data-ttu-id="83698-148">Результат аналогичен предыдущему примеру.</span><span class="sxs-lookup"><span data-stu-id="83698-148">The result is the same as the previous example.</span></span>

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a><span data-ttu-id="83698-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="83698-149">Examples</span></span>

<span data-ttu-id="83698-150">Простые строки данных.</span><span class="sxs-lookup"><span data-stu-id="83698-150">Simple data strings.</span></span>

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

<span data-ttu-id="83698-151">Строки, включающие разрешенные переменные.</span><span class="sxs-lookup"><span data-stu-id="83698-151">Strings that include permitted variables.</span></span>

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

<span data-ttu-id="83698-152">Строка с одинарной кавычкой, которая использует `ConvertFrom-StringData` командлет:</span><span class="sxs-lookup"><span data-stu-id="83698-152">A single-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="83698-153">Строка, заключенная в двойные кавычки, с использованием `ConvertFrom-StringData` командлета:</span><span class="sxs-lookup"><span data-stu-id="83698-153">A double-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

<span data-ttu-id="83698-154">Раздел данных, содержащий пользовательский командлет, создающий данные:</span><span class="sxs-lookup"><span data-stu-id="83698-154">A data section that includes a user-written cmdlet that generates data:</span></span>

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a><span data-ttu-id="83698-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="83698-155">See Also</span></span>

[<span data-ttu-id="83698-156">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="83698-156">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="83698-157">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="83698-157">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="83698-158">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="83698-158">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="83698-159">about_If</span><span class="sxs-lookup"><span data-stu-id="83698-159">about_If</span></span>](about_If.md)

[<span data-ttu-id="83698-160">about_Operators</span><span class="sxs-lookup"><span data-stu-id="83698-160">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="83698-161">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="83698-161">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="83698-162">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="83698-162">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="83698-163">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="83698-163">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="83698-164">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="83698-164">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
