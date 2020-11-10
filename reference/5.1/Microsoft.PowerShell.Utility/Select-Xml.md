---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: 7e3d02dedb9f7809a8f8e1c657987fef8ec38fa9
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387997"
---
# <span data-ttu-id="73abb-103">Select-Xml</span><span class="sxs-lookup"><span data-stu-id="73abb-103">Select-Xml</span></span>

## <span data-ttu-id="73abb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="73abb-104">SYNOPSIS</span></span>
<span data-ttu-id="73abb-105">Выполняет поиск текста в XML-строке или документе.</span><span class="sxs-lookup"><span data-stu-id="73abb-105">Finds text in an XML string or document.</span></span>

## <span data-ttu-id="73abb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73abb-106">SYNTAX</span></span>

### <span data-ttu-id="73abb-107">XML (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="73abb-107">Xml (Default)</span></span>

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="73abb-108">Путь</span><span class="sxs-lookup"><span data-stu-id="73abb-108">Path</span></span>

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="73abb-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73abb-109">LiteralPath</span></span>

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="73abb-110">Content</span><span class="sxs-lookup"><span data-stu-id="73abb-110">Content</span></span>

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="73abb-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73abb-111">DESCRIPTION</span></span>

<span data-ttu-id="73abb-112">Командлет **Select-XML** позволяет использовать запросы XPath для поиска текста в XML-строках и документах.</span><span class="sxs-lookup"><span data-stu-id="73abb-112">The **Select-Xml** cmdlet lets you use XPath queries to search for text in XML strings and documents.</span></span>
<span data-ttu-id="73abb-113">Введите запрос XPath и используйте параметр *Content* , *path* или *XML* , чтобы указать XML-код для поиска.</span><span class="sxs-lookup"><span data-stu-id="73abb-113">Enter an XPath query, and use the *Content* , *Path* , or *Xml* parameter to specify the XML to be searched.</span></span>

## <span data-ttu-id="73abb-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="73abb-114">EXAMPLES</span></span>

### <span data-ttu-id="73abb-115">Пример 1. Выбор узлов AliasProperty</span><span class="sxs-lookup"><span data-stu-id="73abb-115">Example 1: Select AliasProperty nodes</span></span>

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

<span data-ttu-id="73abb-116">Эта команда получает свойства псевдонимов из файла Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="73abb-116">This example gets the alias properties in the Types.ps1xml.</span></span>
<span data-ttu-id="73abb-117">(Сведения об этом файле см. в разделе about_Types.ps1xml.)</span><span class="sxs-lookup"><span data-stu-id="73abb-117">(For information about this file, see about_Types.ps1xml.)</span></span>

<span data-ttu-id="73abb-118">Первая команда сохраняет путь к файлу Types.ps1xml в переменной $Path.</span><span class="sxs-lookup"><span data-stu-id="73abb-118">The first command saves the path to the Types.ps1xml file in the $Path variable.</span></span>

<span data-ttu-id="73abb-119">Вторая команда сохраняет XML-путь в узел AliasProperty в переменной $XPath.</span><span class="sxs-lookup"><span data-stu-id="73abb-119">The second command saves the XML path to the AliasProperty node in the $XPath variable.</span></span>

<span data-ttu-id="73abb-120">Третья команда получает узлы AliasProperty узлы, обозначенные оператором XPath, из файла Types.ps1xml, с помощью командлета **Select-Xml**.</span><span class="sxs-lookup"><span data-stu-id="73abb-120">The third command uses the **Select-Xml** cmdlet to get the AliasProperty nodes that are identified by the XPath statement from the Types.ps1xml file.</span></span>
<span data-ttu-id="73abb-121">Команда использует оператор конвейера для отправки узлов AliasProperty в командлет Select-Object.</span><span class="sxs-lookup"><span data-stu-id="73abb-121">The command uses a pipeline operator to send the AliasProperty nodes to the Select-Object cmdlet.</span></span>
<span data-ttu-id="73abb-122">Параметр *експандпроперти* расширяет объект **node** и возвращает его свойства Name и референцедмембернаме.</span><span class="sxs-lookup"><span data-stu-id="73abb-122">The *ExpandProperty* parameter expands the **Node** object and returns its Name and ReferencedMemberName properties.</span></span>

<span data-ttu-id="73abb-123">В результате выполнения команды отображаются значения Name и ReferencedMemberName для каждого свойства псевдонима в файле Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="73abb-123">The result shows the Name and ReferencedMemberName of each alias property in the Types.ps1xml file.</span></span>
<span data-ttu-id="73abb-124">Например, имеется свойство **Count** , которое является псевдонимом свойства **length** .</span><span class="sxs-lookup"><span data-stu-id="73abb-124">For example, there is a **Count** property that is an alias of the **Length** property.</span></span>

### <span data-ttu-id="73abb-125">Пример 2. ввод XML-документа</span><span class="sxs-lookup"><span data-stu-id="73abb-125">Example 2: Input an XML document</span></span>

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

<span data-ttu-id="73abb-126">В этом примере показано, как использовать параметр *XML* для предоставления XML-документа командлету **Select-XML** .</span><span class="sxs-lookup"><span data-stu-id="73abb-126">This example shows how to use the *XML* parameter to provide an XML document to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="73abb-127">Первая команда использует командлет Get-Content для получения содержимого Types.ps1XML-файла и сохраняет его в переменной $Types.</span><span class="sxs-lookup"><span data-stu-id="73abb-127">The first command uses the Get-Content cmdlet to get the content of the Types.ps1xml file and save it in the $Types variable.</span></span>
<span data-ttu-id="73abb-128">\[XML \] приводит переменную как объект XML.</span><span class="sxs-lookup"><span data-stu-id="73abb-128">The \[xml\] casts the variable as an XML object.</span></span>

<span data-ttu-id="73abb-129">Вторая команда использует командлет **Select-Xml** для получения узлов MethodName из файла Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="73abb-129">The second command uses the **Select-Xml** cmdlet to get the MethodName nodes in the Types.ps1xml file.</span></span>
<span data-ttu-id="73abb-130">С помощью параметра *Xml* команда определяет XML-содержимое из переменной $Types, а с помощью параметра *XPath*  — указывает путь к узлу MethodName.</span><span class="sxs-lookup"><span data-stu-id="73abb-130">The command uses the *Xml* parameter to specify the XML content in the $Types variable and the *XPath* parameter to specify the path to the MethodName node.</span></span>

### <span data-ttu-id="73abb-131">Пример 3. Поиск файлов справки PowerShell</span><span class="sxs-lookup"><span data-stu-id="73abb-131">Example 3: Search PowerShell Help files</span></span>

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

<span data-ttu-id="73abb-132">В этом примере показано, как использовать командлет **Select-XML** для поиска файлов справки по командлетам на основе XML PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73abb-132">This example shows how to use the **Select-Xml** cmdlet to search the PowerShell XML-based cmdlet help files.</span></span>
<span data-ttu-id="73abb-133">В этом примере мы будем искать имя командлета, который служит заголовком для каждого файла справки, а также путь к файлу справки.</span><span class="sxs-lookup"><span data-stu-id="73abb-133">In this example, we'll search for the cmdlet name that serves as a title for each help file and the path to the help file.</span></span>

<span data-ttu-id="73abb-134">Первая команда создает хэш-таблицу, представляющую пространство имен XML, которое используется для файлов справки, и сохраняет ее в переменную $Namespace.</span><span class="sxs-lookup"><span data-stu-id="73abb-134">The first command creates a hash table that represents the XML namespace that is used for the help files and saves it in the $Namespace variable.</span></span>

### <span data-ttu-id="73abb-135">Пример 4. различные способы входа в XML</span><span class="sxs-lookup"><span data-stu-id="73abb-135">Example 4: Different ways to input XML</span></span>

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

<span data-ttu-id="73abb-136">В этом примере показаны два разных способа отправки XML в командлет **Select-XML** .</span><span class="sxs-lookup"><span data-stu-id="73abb-136">This example shows two different ways to send XML to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="73abb-137">Первая команда сохраняет строку here, содержащую XML, в переменной $Xml.</span><span class="sxs-lookup"><span data-stu-id="73abb-137">The first command saves a here-string that contains XML in the $Xml variable.</span></span>
<span data-ttu-id="73abb-138">(Дополнительные сведения о here-строках см. в разделе about_Quoting_Rules.)</span><span class="sxs-lookup"><span data-stu-id="73abb-138">(For more information about here-strings, see about_Quoting_Rules.)</span></span>

### <span data-ttu-id="73abb-139">Пример 5. использование пространства имен xmlns по умолчанию</span><span class="sxs-lookup"><span data-stu-id="73abb-139">Example 5: Use the default xmlns namespace</span></span>

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

<span data-ttu-id="73abb-140">В этом примере показано, как использовать командлет **Select-XML** с XML-документами, использующими пространство имен xmlns по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73abb-140">This example shows how to use the **Select-Xml** cmdlet with XML documents that use the default xmlns namespace.</span></span>
<span data-ttu-id="73abb-141">Команды в этом примере получают заголовки созданных пользователями файлов фрагментов ISE в оболочке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73abb-141">The example gets the titles of Windows PowerShell ISE user-created snippet files.</span></span>
<span data-ttu-id="73abb-142">Подробные сведения о фрагментах см. в разделе New-IseSnippet.</span><span class="sxs-lookup"><span data-stu-id="73abb-142">For information about snippets, see New-IseSnippet.</span></span>

<span data-ttu-id="73abb-143">Первая команда создает хэш-таблицу для пространства имен по умолчанию, используемого файлами фрагмента XML, и назначает его переменной $SnippetNamespace.</span><span class="sxs-lookup"><span data-stu-id="73abb-143">The first command creates a hash table for the default namespace that snippet XML files use and assigns it to the $SnippetNamespace variable.</span></span>
<span data-ttu-id="73abb-144">Значением хэш-таблицы служит URI схемы XMLNS в XML-фрагменте.</span><span class="sxs-lookup"><span data-stu-id="73abb-144">The hash table value is the XMLNS schema URI in the snippet XML.</span></span>
<span data-ttu-id="73abb-145">Имя ключа хэш-таблицы является произвольным.</span><span class="sxs-lookup"><span data-stu-id="73abb-145">The hash table key name, snip, is arbitrary.</span></span>
<span data-ttu-id="73abb-146">Можно использовать любое имя, которое не зарезервировано, но нельзя использовать xmlns.</span><span class="sxs-lookup"><span data-stu-id="73abb-146">You can use any name that is not reserved, but you cannot use xmlns.</span></span>

## <span data-ttu-id="73abb-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73abb-147">PARAMETERS</span></span>

### <span data-ttu-id="73abb-148">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="73abb-148">-Content</span></span>

<span data-ttu-id="73abb-149">Задает строку, которая содержит XML-код для поиска.</span><span class="sxs-lookup"><span data-stu-id="73abb-149">Specifies a string that contains the XML to search.</span></span>
<span data-ttu-id="73abb-150">Можно также передать строки в **Select-XML**.</span><span class="sxs-lookup"><span data-stu-id="73abb-150">You can also pipe strings to **Select-Xml**.</span></span>

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

### <span data-ttu-id="73abb-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73abb-151">-LiteralPath</span></span>

<span data-ttu-id="73abb-152">Задает путь и имена XML-файлов для поиска.</span><span class="sxs-lookup"><span data-stu-id="73abb-152">Specifies the paths and file names of the XML files to search.</span></span>
<span data-ttu-id="73abb-153">В отличие от параметра *Path* , значение параметра *LiteralPath* используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="73abb-153">Unlike *Path* , the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="73abb-154">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="73abb-154">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="73abb-155">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="73abb-155">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="73abb-156">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="73abb-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73abb-157">-Namespace</span><span class="sxs-lookup"><span data-stu-id="73abb-157">-Namespace</span></span>

<span data-ttu-id="73abb-158">Задает хэш-таблицу пространств имен, используемых в XML.</span><span class="sxs-lookup"><span data-stu-id="73abb-158">Specifies a hash table of the namespaces used in the XML.</span></span>
<span data-ttu-id="73abb-159">Используйте формат @ { \<namespaceName\>  =  \<namespaceValue\> }.</span><span class="sxs-lookup"><span data-stu-id="73abb-159">Use the format @{\<namespaceName\> = \<namespaceValue\>}.</span></span>

<span data-ttu-id="73abb-160">Если в XML используется пространство имен по умолчанию, которое начинается с xmlns, используйте произвольный ключ для имени пространства имен.</span><span class="sxs-lookup"><span data-stu-id="73abb-160">When the XML uses the default namespace, which begins with xmlns, use an arbitrary key for the namespace name.</span></span>
<span data-ttu-id="73abb-161">Нельзя использовать xmlns.</span><span class="sxs-lookup"><span data-stu-id="73abb-161">You cannot use xmlns.</span></span>
<span data-ttu-id="73abb-162">В инструкции XPath добавьте в префикс имени узла имя пространства имен и двоеточие, например//Намеспаценаме: node.</span><span class="sxs-lookup"><span data-stu-id="73abb-162">In the XPath statement, prefix each node name with the namespace name and a colon, such as //namespaceName:Node.</span></span>

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

### <span data-ttu-id="73abb-163">-Path</span><span class="sxs-lookup"><span data-stu-id="73abb-163">-Path</span></span>

<span data-ttu-id="73abb-164">Задает путь и имена XML-файлов для поиска.</span><span class="sxs-lookup"><span data-stu-id="73abb-164">Specifies the path and file names of the XML files to search.</span></span>
<span data-ttu-id="73abb-165">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="73abb-165">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="73abb-166">-XML</span><span class="sxs-lookup"><span data-stu-id="73abb-166">-Xml</span></span>

<span data-ttu-id="73abb-167">Задает один или несколько XML-узлов.</span><span class="sxs-lookup"><span data-stu-id="73abb-167">Specifies one or more XML nodes.</span></span>

<span data-ttu-id="73abb-168">XML-документ будет обрабатываться как коллекция XML-узлов.</span><span class="sxs-lookup"><span data-stu-id="73abb-168">An XML document will be processed as a collection of XML nodes.</span></span>
<span data-ttu-id="73abb-169">При передаче XML-документа в **Select-XML** каждый узел документа будет выполнять поиск по отдельности, как это происходит через конвейер.</span><span class="sxs-lookup"><span data-stu-id="73abb-169">If you pipe an XML document to **Select-Xml** , each document node will be searched separately as it comes through the pipeline.</span></span>

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

### <span data-ttu-id="73abb-170">-XPath</span><span class="sxs-lookup"><span data-stu-id="73abb-170">-XPath</span></span>

<span data-ttu-id="73abb-171">Задает поисковый запрос XPath.</span><span class="sxs-lookup"><span data-stu-id="73abb-171">Specifies an XPath search query.</span></span>
<span data-ttu-id="73abb-172">В языке запросов учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="73abb-172">The query language is case-sensitive.</span></span>
<span data-ttu-id="73abb-173">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="73abb-173">This parameter is required.</span></span>

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

### <span data-ttu-id="73abb-174">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="73abb-174">CommonParameters</span></span>

<span data-ttu-id="73abb-175">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73abb-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73abb-176">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="73abb-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="73abb-177">Входные данные</span><span class="sxs-lookup"><span data-stu-id="73abb-177">INPUTS</span></span>

### <span data-ttu-id="73abb-178">System. String или System.Xml.Xmlузел</span><span class="sxs-lookup"><span data-stu-id="73abb-178">System.String or System.Xml.XmlNode</span></span>

<span data-ttu-id="73abb-179">В этот командлет можно передать по конвейеру путь или узел XML.</span><span class="sxs-lookup"><span data-stu-id="73abb-179">You can pipe a path or XML node to this cmdlet.</span></span>

## <span data-ttu-id="73abb-180">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="73abb-180">OUTPUTS</span></span>

### <span data-ttu-id="73abb-181">Microsoft. PowerShell. Commands. Селектксмлинфо</span><span class="sxs-lookup"><span data-stu-id="73abb-181">Microsoft.PowerShell.Commands.SelectXmlInfo</span></span>

## <span data-ttu-id="73abb-182">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="73abb-182">NOTES</span></span>

<span data-ttu-id="73abb-183">XPath — это стандартный язык, предназначенный для определения частей XML-документа.</span><span class="sxs-lookup"><span data-stu-id="73abb-183">XPath is a standard language that is designed to identify parts of an XML document.</span></span> <span data-ttu-id="73abb-184">Дополнительные сведения о языке XPath см. в разделах [Справочник по XPath](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) и фильтры выбора в разделе [Выбор событий](/previous-versions//aa385231(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="73abb-184">For more information about the XPath language, see [XPath Reference](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) and the Selection Filters section of [Event Selection](/previous-versions//aa385231(v=vs.85)).</span></span>

## <span data-ttu-id="73abb-185">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="73abb-185">RELATED LINKS</span></span>

[<span data-ttu-id="73abb-186">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="73abb-186">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
