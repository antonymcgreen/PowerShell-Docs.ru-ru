---
external help file: ISE-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229717"
---
# Get-IseSnippet

## Краткий обзор
Возвращает фрагменты кода, созданные пользователем.

## SYNTAX

```
Get-IseSnippet [<CommonParameters>]
```

## DESCRIPTION

`Get-IseSnippet`Командлет возвращает файлы ps1xml, содержащие многократно используемые текстовые фрагменты, созданные пользователем. Он работает только в интегрированной среде сценариев (ISE) Windows PowerShell.

При использовании `New-IseSnippet` командлета для создания фрагмента кода `New-IseSnippet` создает `<SnippetTitle>.Snippets.ps1xml` файл в `$home\Documents\WindowsPowerShell\Snippets` каталоге.
`Get-IseSnippet` Возвращает файлы фрагментов кода в каталоге фрагментов кода.

Этот командлет не получает встроенные фрагменты кода или фрагменты кода, которые импортируются из модулей с помощью `Import-IseSnippet` командлета.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. получение всех определяемых пользователем фрагментов кода

Этот пример получает все фрагменты кода, определяемые пользователем, в каталоге фрагментов кода.

```powershell
Get-IseSnippet
```

### Пример 2. копирование всех пользовательских фрагментов данных с удаленных компьютеров в общий каталог

В этом примере все созданные пользователем фрагменты кода копируются из группы удаленных компьютеров в каталог общих фрагментов.

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

`Invoke-Command` выполняется `Get-IseSnippet` на компьютерах в `Servers.txt` файле. Оператор конвейера ( `|` ) отправляет файлы фрагментов в `Copy-Item` командлет, который копирует их в каталог, указанный параметром **Destination** .

### Пример 3. Отображение заголовка и текста каждого фрагмента кода на локальном компьютере

В этом примере `Get-IseSnippet` `Select-Xml` командлеты и используются для вывода заголовка и текста каждого фрагмента кода на локальном компьютере.

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### Пример 4. Отображение заголовка и описания всех фрагментов кода в сеансе

В этом примере отображаются заголовок и описание всех фрагментов в сеансе, включая встроенные фрагменты кода, пользовательские фрагменты и импортированные фрагменты кода.

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

`$PSISE`Переменная представляет собой хостную программу интегрированной среды сценариев Windows PowerShell. Свойство **CurrentPowerShellTab** `$PSISE` переменной представляет текущий сеанс. Свойство **Snippets** представляет фрагменты кода в текущем сеансе.

`$PSISE.CurrentPowerShellTab.Snippets`Команда возвращает объект **Microsoft. PowerShell. host. ISE. ISESnippet** , представляющий фрагмент, в отличие от `Get-IseSnippet` командлета. `Get-IseSnippet` Возвращает объект File (System. IO. FileInfo), представляющий файл фрагмента.

`Format-Table`Командлет отображает свойства **Дисплайтитле** и **Description** фрагментов кода в таблице.

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### System. IO. FileInfo

Этот командлет возвращает файловый объект, представляющий файл фрагмента.

## ПРИМЕЧАНИЯ

* `New-IseSnippet`Командлет сохраняет новые созданные пользователем фрагменты в неподписанных файлах. ps1xml. Таким образом, Windows PowerShell не может добавить их в сеанс, для которого действует политика выполнения **AllSigned** или **Restricted** . В сеансе **Restricted** или **AllSigned** можно создать, получить и импортировать созданные пользователем неподписанные фрагменты кода, но их нельзя использовать в сеансе.

  Чтобы использовать неподписанные пользовательские фрагменты кода, `Get-IseSnippet` возвращаемые командлетом, измените политику выполнения, а затем перезапустите интегрированную среду сценариев Windows PowerShell.

  Дополнительные сведения о политиках выполнения Windows PowerShell см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## Связанные ссылки

[New-IseSnippet](New-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
