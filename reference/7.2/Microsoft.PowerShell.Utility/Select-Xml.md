---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: 7686ade747345b7c770772067007b8abf13aac3d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602081"
---
# <span data-ttu-id="cef24-102">Select-Xml</span><span class="sxs-lookup"><span data-stu-id="cef24-102">Select-Xml</span></span>

## <span data-ttu-id="cef24-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cef24-103">SYNOPSIS</span></span>
<span data-ttu-id="cef24-104">Выполняет поиск текста в XML-строке или документе.</span><span class="sxs-lookup"><span data-stu-id="cef24-104">Finds text in an XML string or document.</span></span>

## <span data-ttu-id="cef24-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cef24-105">SYNTAX</span></span>

### <span data-ttu-id="cef24-106">XML (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cef24-106">Xml (Default)</span></span>

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="cef24-107">Путь</span><span class="sxs-lookup"><span data-stu-id="cef24-107">Path</span></span>

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="cef24-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cef24-108">LiteralPath</span></span>

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="cef24-109">Содержимое</span><span class="sxs-lookup"><span data-stu-id="cef24-109">Content</span></span>

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="cef24-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cef24-110">DESCRIPTION</span></span>

<span data-ttu-id="cef24-111">Командлет **Select-XML** позволяет использовать запросы XPath для поиска текста в XML-строках и документах.</span><span class="sxs-lookup"><span data-stu-id="cef24-111">The **Select-Xml** cmdlet lets you use XPath queries to search for text in XML strings and documents.</span></span>
<span data-ttu-id="cef24-112">Введите запрос XPath и используйте параметр *Content*, *path* или *XML* , чтобы указать XML-код для поиска.</span><span class="sxs-lookup"><span data-stu-id="cef24-112">Enter an XPath query, and use the *Content*, *Path*, or *Xml* parameter to specify the XML to be searched.</span></span>

## <span data-ttu-id="cef24-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="cef24-113">EXAMPLES</span></span>

### <span data-ttu-id="cef24-114">Пример 1. Выбор узлов AliasProperty</span><span class="sxs-lookup"><span data-stu-id="cef24-114">Example 1: Select AliasProperty nodes</span></span>

```
PS C:\> $Path = "$Pshome\Types.ps1xml"
PS C:\> $XPath = "/Types/Type/Members/AliasProperty"
PS C:\> Select-Xml -Path $Path -XPath $Xpath | Select-Object -ExpandProperty Node
Name                 ReferencedMemberName
----                 --------------------
Count                Length
Name                 Key
Name                 ServiceName
RequiredServices     ServicesDependedOn
ProcessName          Name
Handles              Handlecount
VM                   VirtualSize
WS                   WorkingSetSize
Name                 ProcessName
Handles              Handlecount
VM                   VirtualMemorySize
WS                   WorkingSet
PM                   PagedMemorySize
NPM                  NonpagedSystemMemorySize
Name                 __Class
Namespace            ModuleName
```

<span data-ttu-id="cef24-115">Эта команда получает свойства псевдонимов из файла Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="cef24-115">This example gets the alias properties in the Types.ps1xml.</span></span>
<span data-ttu-id="cef24-116">(Сведения об этом файле см. в разделе about_Types.ps1xml.)</span><span class="sxs-lookup"><span data-stu-id="cef24-116">(For information about this file, see about_Types.ps1xml.)</span></span>

<span data-ttu-id="cef24-117">Первая команда сохраняет путь к файлу Types.ps1xml в переменной $Path.</span><span class="sxs-lookup"><span data-stu-id="cef24-117">The first command saves the path to the Types.ps1xml file in the $Path variable.</span></span>

<span data-ttu-id="cef24-118">Вторая команда сохраняет XML-путь в узел AliasProperty в переменной $XPath.</span><span class="sxs-lookup"><span data-stu-id="cef24-118">The second command saves the XML path to the AliasProperty node in the $XPath variable.</span></span>

<span data-ttu-id="cef24-119">Третья команда получает узлы AliasProperty узлы, обозначенные оператором XPath, из файла Types.ps1xml, с помощью командлета **Select-Xml**.</span><span class="sxs-lookup"><span data-stu-id="cef24-119">The third command uses the **Select-Xml** cmdlet to get the AliasProperty nodes that are identified by the XPath statement from the Types.ps1xml file.</span></span>
<span data-ttu-id="cef24-120">Команда использует оператор конвейера для отправки узлов AliasProperty в командлет Select-Object.</span><span class="sxs-lookup"><span data-stu-id="cef24-120">The command uses a pipeline operator to send the AliasProperty nodes to the Select-Object cmdlet.</span></span>
<span data-ttu-id="cef24-121">Параметр *експандпроперти* расширяет объект **node** и возвращает его свойства Name и референцедмембернаме.</span><span class="sxs-lookup"><span data-stu-id="cef24-121">The *ExpandProperty* parameter expands the **Node** object and returns its Name and ReferencedMemberName properties.</span></span>

<span data-ttu-id="cef24-122">В результате выполнения команды отображаются значения Name и ReferencedMemberName для каждого свойства псевдонима в файле Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="cef24-122">The result shows the Name and ReferencedMemberName of each alias property in the Types.ps1xml file.</span></span>
<span data-ttu-id="cef24-123">Например, имеется свойство **Count** , которое является псевдонимом свойства **length** .</span><span class="sxs-lookup"><span data-stu-id="cef24-123">For example, there is a **Count** property that is an alias of the **Length** property.</span></span>

### <span data-ttu-id="cef24-124">Пример 2. ввод XML-документа</span><span class="sxs-lookup"><span data-stu-id="cef24-124">Example 2: Input an XML document</span></span>

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

<span data-ttu-id="cef24-125">В этом примере показано, как использовать параметр *XML* для предоставления XML-документа командлету **Select-XML** .</span><span class="sxs-lookup"><span data-stu-id="cef24-125">This example shows how to use the *XML* parameter to provide an XML document to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="cef24-126">Первая команда использует командлет Get-Content для получения содержимого Types.ps1XML-файла и сохраняет его в переменной $Types.</span><span class="sxs-lookup"><span data-stu-id="cef24-126">The first command uses the Get-Content cmdlet to get the content of the Types.ps1xml file and save it in the $Types variable.</span></span>
<span data-ttu-id="cef24-127">\[XML \] приводит переменную как объект XML.</span><span class="sxs-lookup"><span data-stu-id="cef24-127">The \[xml\] casts the variable as an XML object.</span></span>

<span data-ttu-id="cef24-128">Вторая команда использует командлет **Select-Xml** для получения узлов MethodName из файла Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="cef24-128">The second command uses the **Select-Xml** cmdlet to get the MethodName nodes in the Types.ps1xml file.</span></span>
<span data-ttu-id="cef24-129">С помощью параметра *Xml* команда определяет XML-содержимое из переменной $Types, а с помощью параметра *XPath* — указывает путь к узлу MethodName.</span><span class="sxs-lookup"><span data-stu-id="cef24-129">The command uses the *Xml* parameter to specify the XML content in the $Types variable and the *XPath* parameter to specify the path to the MethodName node.</span></span>

### <span data-ttu-id="cef24-130">Пример 3. Поиск файлов справки PowerShell</span><span class="sxs-lookup"><span data-stu-id="cef24-130">Example 3: Search PowerShell Help files</span></span>

```
PS C:\> $Namespace = @{command = "http://schemas.microsoft.com/maml/dev/command/2004/10"; maml = "http://schemas.microsoft.com/maml/2004/10"; dev = "http://schemas.microsoft.com/maml/dev/2004/10"}

The second command saves the path to the help files in the $Path variable.If there are no help files in this path on your computer, use the Update-Help cmdlet to download the help files. For more information about Updatable Help, see about_Updatable_Help (https://go.microsoft.com/fwlink/?LinkId=235801).
PS C:\> $Path = "$Pshome\en-us\*dll-Help.xml"

The third command uses the **Select-Xml** cmdlet to search the XML for cmdlet names by finding Command:Name element anywhere in the files. It saves the results in the $Xml variable.**Select-Xml** returns a **SelectXmlInfo** object that has a Node property, which is a **System.Xml.XmlElement** object. The Node property has an InnerXML property, which contains the actual XML that is retrieved.
PS C:\> $Xml = Select-Xml -Path $Path -Namespace $Namespace -XPath "//command:name"

The fourth command sends the XML in the $Xml variable to the Format-Table cmdlet. The **Format-Table** command uses a calculated property to get the Node.InnerXML property of each object in the $Xml variable, trim the white space before and after the text, and display it in the table, along with the path to the source file.
PS C:\> $Xml | Format-Table @{Label="Name"; Expression= {($_.node.innerxml).trim()}}, Path -AutoSize

Name                    Path
----                    ----
Export-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-Counter             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-WinEvent            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Import-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Add-Computer            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Add-Content             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Checkpoint-Computer     C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
...
```

<span data-ttu-id="cef24-131">В этом примере показано, как использовать командлет **Select-XML** для поиска файлов справки по командлетам на основе XML PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cef24-131">This example shows how to use the **Select-Xml** cmdlet to search the PowerShell XML-based cmdlet help files.</span></span>
<span data-ttu-id="cef24-132">В этом примере мы будем искать имя командлета, который служит заголовком для каждого файла справки, а также путь к файлу справки.</span><span class="sxs-lookup"><span data-stu-id="cef24-132">In this example, we'll search for the cmdlet name that serves as a title for each help file and the path to the help file.</span></span>

<span data-ttu-id="cef24-133">Первая команда создает хэш-таблицу, представляющую пространство имен XML, которое используется для файлов справки, и сохраняет ее в переменную $Namespace.</span><span class="sxs-lookup"><span data-stu-id="cef24-133">The first command creates a hash table that represents the XML namespace that is used for the help files and saves it in the $Namespace variable.</span></span>

### <span data-ttu-id="cef24-134">Пример 4. различные способы входа в XML</span><span class="sxs-lookup"><span data-stu-id="cef24-134">Example 4: Different ways to input XML</span></span>

```
PS C:\> $Xml = @"
<?xml version="1.0" encoding="utf-8"?>
<Book>
  <projects>
    <project name="Book1" date="2009-01-20">
      <editions>
        <edition language="English">En.Book1.com</edition>
        <edition language="German">Ge.Book1.Com</edition>
        <edition language="French">Fr.Book1.com</edition>
        <edition language="Polish">Pl.Book1.com</edition>
      </editions>
    </project>
  </projects>
</Book>
"@

The second command uses the *Content* parameter of **Select-Xml** to specify the XML in the $Xml variable.
PS C:\> Select-Xml -Content $Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com

The third command is equivalent to the second. It uses a pipeline operator (|) to send the XML in the $Xml variable to the **Select-Xml** cmdlet.
PS C:\> $Xml | Select-Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com
```

<span data-ttu-id="cef24-135">В этом примере показаны два разных способа отправки XML в командлет **Select-XML** .</span><span class="sxs-lookup"><span data-stu-id="cef24-135">This example shows two different ways to send XML to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="cef24-136">Первая команда сохраняет строку here, содержащую XML, в переменной $Xml.</span><span class="sxs-lookup"><span data-stu-id="cef24-136">The first command saves a here-string that contains XML in the $Xml variable.</span></span>
<span data-ttu-id="cef24-137">(Дополнительные сведения о here-строках см. в разделе about_Quoting_Rules.)</span><span class="sxs-lookup"><span data-stu-id="cef24-137">(For more information about here-strings, see about_Quoting_Rules.)</span></span>

### <span data-ttu-id="cef24-138">Пример 5. использование пространства имен xmlns по умолчанию</span><span class="sxs-lookup"><span data-stu-id="cef24-138">Example 5: Use the default xmlns namespace</span></span>

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

<span data-ttu-id="cef24-139">В этом примере показано, как использовать командлет **Select-XML** с XML-документами, использующими пространство имен xmlns по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cef24-139">This example shows how to use the **Select-Xml** cmdlet with XML documents that use the default xmlns namespace.</span></span>
<span data-ttu-id="cef24-140">Команды в этом примере получают заголовки созданных пользователями файлов фрагментов ISE в оболочке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cef24-140">The example gets the titles of Windows PowerShell ISE user-created snippet files.</span></span>
<span data-ttu-id="cef24-141">Подробные сведения о фрагментах см. в разделе New-IseSnippet.</span><span class="sxs-lookup"><span data-stu-id="cef24-141">For information about snippets, see New-IseSnippet.</span></span>

<span data-ttu-id="cef24-142">Первая команда создает хэш-таблицу для пространства имен по умолчанию, используемого файлами фрагмента XML, и назначает его переменной $SnippetNamespace.</span><span class="sxs-lookup"><span data-stu-id="cef24-142">The first command creates a hash table for the default namespace that snippet XML files use and assigns it to the $SnippetNamespace variable.</span></span>
<span data-ttu-id="cef24-143">Значением хэш-таблицы служит URI схемы XMLNS в XML-фрагменте.</span><span class="sxs-lookup"><span data-stu-id="cef24-143">The hash table value is the XMLNS schema URI in the snippet XML.</span></span>
<span data-ttu-id="cef24-144">Имя ключа хэш-таблицы является произвольным.</span><span class="sxs-lookup"><span data-stu-id="cef24-144">The hash table key name, snip, is arbitrary.</span></span>
<span data-ttu-id="cef24-145">Можно использовать любое имя, которое не зарезервировано, но нельзя использовать xmlns.</span><span class="sxs-lookup"><span data-stu-id="cef24-145">You can use any name that is not reserved, but you cannot use xmlns.</span></span>

## <span data-ttu-id="cef24-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cef24-146">PARAMETERS</span></span>

### <span data-ttu-id="cef24-147">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="cef24-147">-Content</span></span>

<span data-ttu-id="cef24-148">Задает строку, которая содержит XML-код для поиска.</span><span class="sxs-lookup"><span data-stu-id="cef24-148">Specifies a string that contains the XML to search.</span></span>
<span data-ttu-id="cef24-149">Можно также передать строки в **Select-XML**.</span><span class="sxs-lookup"><span data-stu-id="cef24-149">You can also pipe strings to **Select-Xml**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Content
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cef24-150">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cef24-150">-LiteralPath</span></span>

<span data-ttu-id="cef24-151">Задает путь и имена XML-файлов для поиска.</span><span class="sxs-lookup"><span data-stu-id="cef24-151">Specifies the paths and file names of the XML files to search.</span></span>
<span data-ttu-id="cef24-152">В отличие от параметра *Path*, значение параметра *LiteralPath* используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="cef24-152">Unlike *Path*, the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="cef24-153">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="cef24-153">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="cef24-154">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="cef24-154">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="cef24-155">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="cef24-155">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cef24-156">-Namespace</span><span class="sxs-lookup"><span data-stu-id="cef24-156">-Namespace</span></span>

<span data-ttu-id="cef24-157">Задает хэш-таблицу пространств имен, используемых в XML.</span><span class="sxs-lookup"><span data-stu-id="cef24-157">Specifies a hash table of the namespaces used in the XML.</span></span>
<span data-ttu-id="cef24-158">Используйте формат @ { \<namespaceName\>  =  \<namespaceValue\> }.</span><span class="sxs-lookup"><span data-stu-id="cef24-158">Use the format @{\<namespaceName\> = \<namespaceValue\>}.</span></span>

<span data-ttu-id="cef24-159">Если в XML используется пространство имен по умолчанию, которое начинается с xmlns, используйте произвольный ключ для имени пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cef24-159">When the XML uses the default namespace, which begins with xmlns, use an arbitrary key for the namespace name.</span></span>
<span data-ttu-id="cef24-160">Нельзя использовать xmlns.</span><span class="sxs-lookup"><span data-stu-id="cef24-160">You cannot use xmlns.</span></span>
<span data-ttu-id="cef24-161">В инструкции XPath добавьте в префикс имени узла имя пространства имен и двоеточие, например//Намеспаценаме: node.</span><span class="sxs-lookup"><span data-stu-id="cef24-161">In the XPath statement, prefix each node name with the namespace name and a colon, such as //namespaceName:Node.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cef24-162">-Path</span><span class="sxs-lookup"><span data-stu-id="cef24-162">-Path</span></span>

<span data-ttu-id="cef24-163">Задает путь и имена XML-файлов для поиска.</span><span class="sxs-lookup"><span data-stu-id="cef24-163">Specifies the path and file names of the XML files to search.</span></span>
<span data-ttu-id="cef24-164">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cef24-164">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="cef24-165">-XML</span><span class="sxs-lookup"><span data-stu-id="cef24-165">-Xml</span></span>

<span data-ttu-id="cef24-166">Задает один или несколько XML-узлов.</span><span class="sxs-lookup"><span data-stu-id="cef24-166">Specifies one or more XML nodes.</span></span>

<span data-ttu-id="cef24-167">XML-документ будет обрабатываться как коллекция XML-узлов.</span><span class="sxs-lookup"><span data-stu-id="cef24-167">An XML document will be processed as a collection of XML nodes.</span></span>
<span data-ttu-id="cef24-168">При передаче XML-документа в **Select-XML** каждый узел документа будет выполнять поиск по отдельности, как это происходит через конвейер.</span><span class="sxs-lookup"><span data-stu-id="cef24-168">If you pipe an XML document to **Select-Xml**, each document node will be searched separately as it comes through the pipeline.</span></span>

```yaml
Type: System.Xml.XmlNode[]
Parameter Sets: Xml
Aliases: Node

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cef24-169">-XPath</span><span class="sxs-lookup"><span data-stu-id="cef24-169">-XPath</span></span>

<span data-ttu-id="cef24-170">Задает поисковый запрос XPath.</span><span class="sxs-lookup"><span data-stu-id="cef24-170">Specifies an XPath search query.</span></span>
<span data-ttu-id="cef24-171">В языке запросов учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="cef24-171">The query language is case-sensitive.</span></span>
<span data-ttu-id="cef24-172">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cef24-172">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cef24-173">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cef24-173">CommonParameters</span></span>

<span data-ttu-id="cef24-174">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cef24-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cef24-175">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cef24-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cef24-176">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cef24-176">INPUTS</span></span>

### <span data-ttu-id="cef24-177">System. String или System.Xml.Xmlузел</span><span class="sxs-lookup"><span data-stu-id="cef24-177">System.String or System.Xml.XmlNode</span></span>

<span data-ttu-id="cef24-178">В этот командлет можно передать по конвейеру путь или узел XML.</span><span class="sxs-lookup"><span data-stu-id="cef24-178">You can pipe a path or XML node to this cmdlet.</span></span>

## <span data-ttu-id="cef24-179">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cef24-179">OUTPUTS</span></span>

### <span data-ttu-id="cef24-180">Microsoft. PowerShell. Commands. Селектксмлинфо</span><span class="sxs-lookup"><span data-stu-id="cef24-180">Microsoft.PowerShell.Commands.SelectXmlInfo</span></span>

## <span data-ttu-id="cef24-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cef24-181">NOTES</span></span>

<span data-ttu-id="cef24-182">XPath — это стандартный язык, предназначенный для определения частей XML-документа.</span><span class="sxs-lookup"><span data-stu-id="cef24-182">XPath is a standard language that is designed to identify parts of an XML document.</span></span> <span data-ttu-id="cef24-183">Дополнительные сведения о языке XPath см. в разделах [Справочник по XPath](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) и фильтры выбора в разделе [Выбор событий](/previous-versions//aa385231(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="cef24-183">For more information about the XPath language, see [XPath Reference](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) and the Selection Filters section of [Event Selection](/previous-versions//aa385231(v=vs.85)).</span></span>

## <span data-ttu-id="cef24-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cef24-184">RELATED LINKS</span></span>

[<span data-ttu-id="cef24-185">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="cef24-185">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
