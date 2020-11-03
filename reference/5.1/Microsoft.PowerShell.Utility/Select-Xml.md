---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: eb5684ed281b3ba05629528bb12b44577f8c050a
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229741"
---
# Select-Xml

## Краткий обзор
Выполняет поиск текста в XML-строке или документе.

## SYNTAX

### XML (по умолчанию)

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### Путь

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### LiteralPath

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### Content

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Select-XML** позволяет использовать запросы XPath для поиска текста в XML-строках и документах.
Введите запрос XPath и используйте параметр *Content* , *path* или *XML* , чтобы указать XML-код для поиска.

## Примеры

### Пример 1. Выбор узлов AliasProperty

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

Эта команда получает свойства псевдонимов из файла Types.ps1xml.
(Сведения об этом файле см. в разделе about_Types.ps1xml.)

Первая команда сохраняет путь к файлу Types.ps1xml в переменной $Path.

Вторая команда сохраняет XML-путь в узел AliasProperty в переменной $XPath.

Третья команда получает узлы AliasProperty узлы, обозначенные оператором XPath, из файла Types.ps1xml, с помощью командлета **Select-Xml**.
Команда использует оператор конвейера для отправки узлов AliasProperty в командлет Select-Object.
Параметр *експандпроперти* расширяет объект **node** и возвращает его свойства Name и референцедмембернаме.

В результате выполнения команды отображаются значения Name и ReferencedMemberName для каждого свойства псевдонима в файле Types.ps1xml.
Например, имеется свойство **Count** , которое является псевдонимом свойства **length** .

### Пример 2. ввод XML-документа

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

В этом примере показано, как использовать параметр *XML* для предоставления XML-документа командлету **Select-XML** .

Первая команда использует командлет Get-Content для получения содержимого Types.ps1XML-файла и сохраняет его в переменной $Types.
\[XML \] приводит переменную как объект XML.

Вторая команда использует командлет **Select-Xml** для получения узлов MethodName из файла Types.ps1xml.
С помощью параметра *Xml* команда определяет XML-содержимое из переменной $Types, а с помощью параметра *XPath*  — указывает путь к узлу MethodName.

### Пример 3. Поиск файлов справки PowerShell

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

В этом примере показано, как использовать командлет **Select-XML** для поиска файлов справки по командлетам на основе XML PowerShell.
В этом примере мы будем искать имя командлета, который служит заголовком для каждого файла справки, а также путь к файлу справки.

Первая команда создает хэш-таблицу, представляющую пространство имен XML, которое используется для файлов справки, и сохраняет ее в переменную $Namespace.

### Пример 4. различные способы входа в XML

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

В этом примере показаны два разных способа отправки XML в командлет **Select-XML** .

Первая команда сохраняет строку here, содержащую XML, в переменной $Xml.
(Дополнительные сведения о here-строках см. в разделе about_Quoting_Rules.)

### Пример 5. использование пространства имен xmlns по умолчанию

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

В этом примере показано, как использовать командлет **Select-XML** с XML-документами, использующими пространство имен xmlns по умолчанию.
Команды в этом примере получают заголовки созданных пользователями файлов фрагментов ISE в оболочке Windows PowerShell.
Подробные сведения о фрагментах см. в разделе New-IseSnippet.

Первая команда создает хэш-таблицу для пространства имен по умолчанию, используемого файлами фрагмента XML, и назначает его переменной $SnippetNamespace.
Значением хэш-таблицы служит URI схемы XMLNS в XML-фрагменте.
Имя ключа хэш-таблицы является произвольным.
Можно использовать любое имя, которое не зарезервировано, но нельзя использовать xmlns.

## PARAMETERS

### — Содержимое

Задает строку, которая содержит XML-код для поиска.
Можно также передать строки в **Select-XML**.

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

### -LiteralPath

Задает путь и имена XML-файлов для поиска.
В отличие от параметра *Path* , значение параметра *LiteralPath* используется в точности так, как вводится.
Никакие символы не интерпретируются как знаки подстановки.
Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

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

### -Namespace

Задает хэш-таблицу пространств имен, используемых в XML.
Используйте формат @ { \<namespaceName\>  =  \<namespaceValue\> }.

Если в XML используется пространство имен по умолчанию, которое начинается с xmlns, используйте произвольный ключ для имени пространства имен.
Нельзя использовать xmlns.
В инструкции XPath добавьте в префикс имени узла имя пространства имен и двоеточие, например//Намеспаценаме: node.

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

### -Path

Задает путь и имена XML-файлов для поиска.
Можно использовать подстановочные знаки.

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

### -XML

Задает один или несколько XML-узлов.

XML-документ будет обрабатываться как коллекция XML-узлов.
При передаче XML-документа в **Select-XML** каждый узел документа будет выполнять поиск по отдельности, как это происходит через конвейер.

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

### -XPath

Задает поисковый запрос XPath.
В языке запросов учитывается регистр.
Этот параметр обязателен.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. String или System.Xml.Xmlузел

В этот командлет можно передать по конвейеру путь или узел XML.

## Выходные данные

### Microsoft. PowerShell. Commands. Селектксмлинфо

## ПРИМЕЧАНИЯ

* XPath — это стандартный язык, предназначенный для определения частей XML-документа. Дополнительные сведения о языке XPath см. в разделах [Справочник по XPath](https://msdn.microsoft.com/library/ms256115) и фильтры выбора в [выборе событий](https://msdn.microsoft.com/library/aa385231) в библиотеке MSDN.

## Связанные ссылки

[ConvertTo-Xml](ConvertTo-Xml.md)
