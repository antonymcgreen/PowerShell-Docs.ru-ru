---
description: Описание процесса написания разделов справки на основе комментариев для функций и скриптов.
keywords: powershell,командлет
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: 0eadaffa2dd783ac172f53d1b252cb261908876d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231738"
---
# <a name="about-comment-based-help"></a>Сведения о справке на основе комментариев

## <a name="short-description"></a>Краткое описание
Описание процесса написания разделов справки на основе комментариев для функций и скриптов.

## <a name="long-description"></a>Подробное описание

Разделы справки на основе комментариев можно писать для функций и скриптов с помощью специальных ключевых слов комментария справки.

Командлет [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) отображает справку на основе комментариев в том же формате, в котором отображаются разделы справки по командлетам, созданные на основе XML-файлов. Пользователи могут использовать все параметры `Get-Help` , такие как **Detailed** , **Full** , **examples** и **Online** , для просмотра содержимого справки на основе комментариев.

Также можно создавать файлы справки на основе XML для функций и скриптов. Чтобы разрешить `Get-Help` командлету найти файл справки на основе XML для функции или скрипта, используйте `.ExternalHelp` ключевое слово. Без этого ключевого слова `Get-Help` не удается найти разделы справки на основе XML для функций и скриптов.

В этом разделе объясняется, как создавать разделы справки для функций и скриптов. Сведения о том, как отображать разделы справки для функций и скриптов, см. в разделе [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).

Командлеты [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) и [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) работают только с файлами XML. Обновляемая Справка не поддерживает разделы справки на основе комментариев.

## <a name="syntax-for-comment-based-help"></a>Синтаксис для справки на основе комментариев

Синтаксис для справки на основе комментариев выглядит следующим образом:

```
# .<help keyword>
# <help content>
```

or

```
<#
.<help keyword>
<help content>
#>
```

Справка на основе комментариев записывается в виде набора комментариев. Символ комментария можно ввести `#` перед каждой строкой комментариев или использовать `<#` `#>` символы и для создания блока комментариев. Все строки внутри блока комментариев обрабатываются как комментарии.

Все строки в разделе справки на основе комментариев должны быть непрерывными. Если раздел справки на основе комментариев следует за комментарием, который не является частью раздела справки, должна существовать хотя бы одна пустая строка между последней строкой комментария, отличной от справки, и началом справки на основе комментариев.

Ключевые слова определяют каждый раздел справки на основе комментариев. Каждому ключевому слову справки на основе комментариев предшествует точка `.` . Ключевые слова могут отображаться в любом порядке. Имена ключевых слов не учитывают регистр.

Например, `.Description` ключевое слово предшествует описанию функции или скрипта.

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

Блок комментариев должен содержать по крайней мере одно ключевое слово. Некоторые ключевые слова, такие как `.EXAMPLE` , могут встречаться много раз в одном блоке комментариев. Содержимое справки для каждого ключевого слова начинается в строке после ключевого слова и может охватывать несколько строк.

## <a name="syntax-for-comment-based-help-in-functions"></a>Синтаксис для справки на основе комментариев в функциях

Справка на основе комментариев для функции может находиться в одном из трех расположений:

- В начале тела функции.
- В конце тела функции.
- Перед `function` ключевым словом. Между последней строкой справки функции и ключевым словом не может быть больше одной пустой строки `function` .

Пример:

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

или диспетчер конфигурации служб

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

or

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a>Синтаксис для справки на основе комментариев в скриптах

Справка на основе комментариев для сценария может находиться в одном из двух расположений в скрипте.

- В начале файла скрипта. Справка по скрипту может предшествоваться в сценарии только по комментариям и пустым строкам.

  Если первый элемент в теле скрипта (после справки) является объявлением функции, то между концом справки скрипта и объявлением функции должно быть по крайней мере две пустые строки. В противном случае Справка интерпретируется как Справка по функции, а не справку по сценарию.

- В конце файла скрипта. Однако если сценарий подписан, поместите справку на основе комментариев в начало файла скрипта. Конец скрипта занят блоком сигнатур.

Пример:

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

или диспетчер конфигурации служб

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a>Синтаксис для справки на основе комментариев в модулях скриптов

В модуле скрипта `.psm1` Справка на основе комментариев использует синтаксис для функций, а не синтаксис скриптов. Синтаксис скрипта нельзя использовать для предоставления справки для всех функций, определенных в модуле скрипта.

Например, если вы используете `.ExternalHelp` ключевое слово для выявления файлов справки на основе XML для функций в модуле скрипта, необходимо добавить `.ExternalHelp` комментарий к каждой функции.

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a>Ключевые слова справки на основе комментариев

Ниже приведены допустимые ключевые слова справки на основе комментариев. Они перечислены в том порядке, в котором они обычно отображаются в разделе справки, а также их предполагаемое использование. Эти ключевые слова могут отображаться в любом порядке в справке на основе комментариев и не учитывают регистр.

### <a name="synopsis"></a>. Краткий обзор

Краткое описание функции или скрипта. Это ключевое слово может использоваться только один раз в каждом разделе.

### <a name="description"></a>. NОПИСАНИЕ

Подробное описание функции или скрипта. Это ключевое слово может использоваться только один раз в каждом разделе.

### <a name="parameter"></a>. ПАРАМЕТР

Описание параметра. Добавьте `.PARAMETER` ключевое слово для каждого параметра в синтаксисе функции или скрипта.

Введите имя параметра в той же строке, что и `.PARAMETER` ключевое слово. Введите описание параметра в строки после `.PARAMETER` ключевого слова. Windows PowerShell интерпретирует весь текст между `.PARAMETER` строками, а также ключевое слово Next или конец блока комментариев как часть описания параметра.
Описание может включать разрывы абзацев.

```
.PARAMETER  <Parameter-Name>
```

Ключевые слова параметров могут использоваться в любом порядке в блоке комментариев, но синтаксис функции или скрипта определяет порядок, в котором параметры (и их описания) отображаются в разделе справки. Чтобы изменить порядок, измените синтаксис.

Можно также указать описание параметра, разместив комментарий в функции или синтаксисе скрипта непосредственно перед именем переменной параметра. Чтобы это работало, необходимо также иметь блок комментариев, содержащий по крайней мере одно ключевое слово.

Если используются как комментарий синтаксиса, так и `.PARAMETER` ключевое слово, используется описание, связанное с `.PARAMETER` ключевым словом, и комментарий синтаксиса игнорируется.

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a>. Например

Пример команды, которая использует функцию или скрипт, при необходимости за которой следует пример выходных данных и описание. Повторите это ключевое слово для каждого примера.

### <a name="inputs"></a>. ВХОДА

Типы объектов .NET, которые можно передать в функцию или скрипт. Можно также включить описание входных объектов.

### <a name="outputs"></a>. ВЫХОДНЫЕ

Тип .NET объектов, возвращаемых командлетом. Можно также включить описание возвращаемых объектов.

### <a name="notes"></a>. Заметки О

Дополнительные сведения о функции или скрипте.

### <a name="link"></a>. ССЫЛКУ

Имя связанного раздела. Значение отображается в строке под запятыми. LINK "и должен предшествовать символом комментария `#` или включаться в блок комментариев.

Повторите `.LINK` ключевое слово для каждого связанного раздела.

Это содержимое отображается в разделе "связанные ссылки" раздела справки.

`.Link`Содержимое ключевого слова может также включать универсальный код ресурса (URI) в Интернет-версию того же раздела справки. Версия в Интернете открывается при использовании параметра **Online** для `Get-Help` . URI должен начинаться с "http" или "HTTPS".

### <a name="component"></a>. СМ

Имя технологии или компонента, используемых функцией или сценарием или с которым она связана. Параметр **компонента** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .

### <a name="role"></a>. ROLE

Имя роли пользователя для раздела справки. Параметр **Role** объекта `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .

### <a name="functionality"></a>. ВОЗМОЖНОСТИ

Ключевые слова, описывающие предполагаемое использование функции. Параметр **функций функции** `Get-Help` использует это значение для фильтрации результатов поиска, возвращаемых `Get-Help` .

### <a name="forwardhelptargetname"></a>. форвардхелптаржетнаме

Выполняет перенаправление в раздел справки для указанной команды. Вы можете перенаправить пользователей в любой раздел справки, включая разделы справки для функции, скрипта, командлета или поставщика.

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a>. форвардхелпкатегори

Указывает категорию справки для элемента в `.ForwardHelpTargetName` . Допустимые значения: `Alias` , `Cmdlet` , `HelpFile` , `Function` , `Provider` , `General` , `FAQ` , `Glossary` ,,, `ScriptCommand` `ExternalScript` `Filter` или `All` . Используйте это ключевое слово, чтобы избежать конфликтов при наличии команд с одинаковыми именами.

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a>. ремотехелпрунспаце

Указывает сеанс, содержащий раздел справки. Введите переменную, содержащую объект **PSSession** . Это ключевое слово используется командлетом [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) для поиска разделов справки для экспортированных команд.

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a>. екстерналхелп

Указывает файл справки на основе XML для скрипта или функции.

```powershell
# .EXTERNALHELP <XML Help File>
```

`.ExternalHelp`Ключевое слово требуется при документировании функции или скрипта в XML-файлах. Без этого ключевого слова `Get-Help` не удается найти файл справки на основе XML для функции или скрипта.

`.ExternalHelp`Ключевое слово имеет приоритет над другими ключевыми словами справки на основе комментариев. Если `.ExternalHelp` параметр существует, не `Get-Help` отображает справку на основе комментариев, даже если не удается найти раздел справки, соответствующий значению `.ExternalHelp` ключевого слова.

Если функция экспортируется модулем, в качестве значения `.ExternalHelp` ключевого слова необходимо указать имя файла без пути. `Get-Help` ищет указанное имя файла в подкаталоге, зависящем от языка, в каталоге модуля. Нет никаких требований к имени файла справки на основе XML для функции, но рекомендуется использовать следующий формат:

```
<ScriptModule.psm1>-help.xml
```

Если функция не включена в модуль, включите путь к файлу справки на основе XML. Если значение содержит путь и путь содержит подкаталоги, относящиеся к пользовательскому интерфейсу, то `Get-Help` Поиск в подкаталогах выполняется рекурсивно для XML-файла с именем скрипта или функции в соответствии со стандартами переключения языка, установленными для Windows, так же, как и в каталоге модуля.

Дополнительные сведения о формате файла справки на основе XML см. в статье Создание [справки по командлетам](https://go.microsoft.com/fwlink/?LinkID=123415) в библиотеке MSDN.

## <a name="autogenerated-content"></a>Автоматически созданное содержимое

Командлет автоматически создает имя, синтаксис, список параметров, таблицу атрибутов параметров, общие параметры и примечания `Get-Help` .

### <a name="name"></a>name

Раздел **имени** раздела справки по функции берется из имени функции в синтаксисе функции. **Имя** раздела справки по скрипту берется из имени файла скрипта. Чтобы изменить имя или его регистр букв, измените синтаксис функции или имя файла скрипта.

### <a name="syntax"></a>Синтаксис

Раздел **синтаксиса** раздела справки создается на основе синтаксиса функции или скрипта. Чтобы добавить подробные сведения в синтаксис раздела справки, например тип .NET параметра, добавьте подробные сведения в синтаксис. Если не указать тип параметра, тип **объекта** будет вставлен в качестве значения по умолчанию.

### <a name="parameter-list"></a>Список параметров

Список параметров в разделе справки создается на основе синтаксиса функции или скрипта, а также из описаний, добавленных с помощью `.Parameter` ключевого слова. Параметры функции отображаются в разделе **Parameters** раздела справки в том же порядке, в котором они отображаются в синтаксисе функции или сценария. В синтаксисе также берется написание и капитализация имен параметров. На него не влияет имя параметра, заданное `.Parameter` ключевым словом.

### <a name="common-parameters"></a>Общие параметры

**Общие параметры** добавляются к синтаксису и списку параметров раздела справки, даже если они не оказывают никакого влияния. Дополнительные сведения об общих параметрах см. в разделе [about_CommonParameters](about_CommonParameters.md).

### <a name="parameter-attribute-table"></a>Таблица атрибутов параметра

`Get-Help` формирует таблицу атрибутов параметров, которые отображаются при использовании параметра **Full** или **параметра** `Get-Help` . Значения атрибутов **Required** , **позицией** и значения **по умолчанию** берутся из синтаксиса функции или скрипта.

Значения по умолчанию и значение для **Accept подстановочных знаков** не отображаются в таблице атрибутов параметров, даже если они определены в функции или скрипте. Чтобы помочь пользователям, укажите эти сведения в описании параметра.

### <a name="remarks"></a>Remarks

Раздел **"Примечания** " раздела справки автоматически создается на основе имени функции или скрипта. Нельзя изменить или повлиять на его содержимое.

## <a name="examples"></a>Примеры

### <a name="comment-based-help-for-a-function"></a>Справка на основе комментариев для функции

Следующий пример функции включает в себя справку на основе комментариев:

```powershell
function Add-Extension
{
param ([string]$Name,[string]$Extension = "txt")
$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.

.PARAMETER Name
Specifies the file name.

.PARAMETER Extension
Specifies the extension. "Txt" is the default.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

Будут получены следующие результаты.

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

PARAMETERS

-Name
Specifies the file name.

Required?                    false
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-Extension
Specifies the extension. "Txt" is the default.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type
"get-help about_commonparameters".

INPUTS
None. You cannot pipe objects to Add-Extension.

OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a>Описания параметров в синтаксисе функции

Этот пример аналогичен предыдущему, за исключением того, что описания параметров вставляются в синтаксис функции. Этот формат наиболее удобен при кратком описании.

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a>Справка на основе комментариев для сценария

Следующий пример скрипта включает в себя справку на основе комментариев. Обратите внимание на пустые строки между закрывающим `#>` и `Param` оператором. В скрипте, не имеющем `Param` оператора, в разделе справки и первом объявлении функции должно быть по крайней мере две пустые строки между последним комментарием. Без этих пустых строк `Get-Help` связывает раздел справки с функцией, а не со сценарием.

```powershell
<#
.SYNOPSIS

Performs monthly data updates.

.DESCRIPTION

The Update-Month.ps1 script updates the registry with new data generated
during the past month and generates a report.

.PARAMETER InputPath
Specifies the path to the CSV-based input file.

.PARAMETER OutputPath
Specifies the name and path for the CSV-based output file. By default,
MonthlyUpdates.ps1 generates a name from the date and time it runs, and
saves the output in the local directory.

.INPUTS

None. You cannot pipe objects to Update-Month.ps1.

.OUTPUTS

None. Update-Month.ps1 does not generate any output.

.EXAMPLE

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

Следующая команда получает справку по скрипту. Так как скрипт не находится в каталоге, указанном в `$env:Path` переменной среды, `Get-Help` команда, которая получает справку по скрипту, должна указывать путь к скрипту.

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

-InputPath
Specifies the path to the CSV-based input file.

Required?                    true
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-OutputPath
Specifies the name and path for the CSV-based output file. By
default, MonthlyUpdates.ps1 generates a name from the date
and time it runs, and saves the output in the local directory.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type,
"get-help about_commonparameters".

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a>Перенаправление в XML-файл

Вы можете писать разделы справки на основе XML для функций и скриптов. Хотя справку на основе комментариев проще реализовать, для обновляемой справки и получения разделов справки на нескольких языках требуется справка на основе XML.

В следующем примере показаны первые несколько строк скрипта Update-Month.ps1.
В скрипте используется `.ExternalHelp` ключевое слово, чтобы указать путь к разделу справки на основе XML для скрипта.

Обратите внимание, что значение `.ExternalHelp` ключевого слова отображается в той же строке, что и ключевое слово. Любое другое размещение является неэффективным.

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

В следующих примерах показаны три допустимые позиции `.ExternalHelp` ключевого слова в функции.

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a>Перенаправление на другой раздел справки

Следующий код является выдержкой из начала встроенной функции справки в PowerShell, которая отображает один экран текста справки за раз.
Поскольку в разделе справки для `Get-Help` командлета описана функция справки, функция Help использует `.ForwardHelpTargetName` `.ForwardHelpCategory` Ключевые слова и для перенаправления пользователя в `Get-Help` раздел справки по командлету.

```powershell
function help
{

<#
.FORWARDHELPTARGETNAME Get-Help
.FORWARDHELPCATEGORY Cmdlet
#>
[CmdletBinding(DefaultParameterSetName='AllUsersView')]
param(
[Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
[System.String]
${Name},
...
```

Эта функция используется в следующей команде:

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a>См. также статью

[about_Functions](about_Functions.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Scripts](about_Scripts.md)

[Написание справки по командлетам](https://go.microsoft.com/fwlink/?LinkID=123415)
