---
description: Описывает команду языка, которую можно использовать для прохода по всем элементам в коллекции элементов.
keywords: powershell,командлет
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach
ms.openlocfilehash: f1f00df8b0f07dd945994860897584d883ef2ce4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232049"
---
# <a name="about-foreach"></a>О ForEach

## <a name="short-description"></a>Краткое описание
Описывает команду языка, которую можно использовать для прохода по всем элементам в коллекции элементов.

## <a name="long-description"></a>Подробное описание

`Foreach`Оператор (также называемый `Foreach` циклом) — это языковая конструкция для пошагового выполнения (прохода) ряда значений в коллекции элементов.

Самый простой и типичный тип коллекции для обхода — массив.
В `Foreach` цикле обычно выполняется одна или несколько команд для каждого элемента в массиве.

## <a name="syntax"></a>Синтаксис

Ниже показан `ForEach` синтаксис.

```
foreach ($<item> in $<collection>){<statement list>}
```

Часть `ForEach` оператора, заключенная в скобки, представляет переменную и коллекцию для итерации. PowerShell автоматически создает переменную `$<item>` при `Foreach` выполнении цикла. До каждой итерации в цикле для переменной задается значение в коллекции.
Блок, следующий за `Foreach` оператором, `{<statement list>}` содержит набор команд для выполнения по отношению к каждому элементу в коллекции.

### <a name="examples"></a>Примеры

Например, `Foreach` цикл в следующем примере отображает значения в `$letterArray` массиве.

```powershell
$letterArray = "a","b","c","d"
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

В этом примере `$letterArray` массив создается и инициализируется со строковыми значениями `"a"` ,, `"b"` `"c"` и `"d"` . При первом `Foreach` выполнении инструкции ей присваивается `$letter` переменная, равная первому элементу в `$letterArray` ( `"a"` ). Затем он использует `Write-Host` командлет для вывода буквы a. В следующий раз в цикле устанавливается `$letter` значение `"b"` и т. д. После того как в `Foreach` цикле отображается буква d, PowerShell завершает цикл.

Вся `Foreach` инструкция должна находиться в одной строке для выполнения в качестве команды в командной строке PowerShell. Инструкция целиком `Foreach` не должна отображаться в одной строке, если вместо этого поместить команду в файл скрипта PS1.

`Foreach` операторы также можно использовать вместе с командлетами, возвращающими коллекцию элементов. В следующем примере оператор foreach проходит по списку элементов, возвращаемых `Get-ChildItem` командлетом.

```powershell
foreach ($file in Get-ChildItem)
{
  Write-Host $file
}
```

Можно уточнить пример с помощью `If` оператора, ограничивающего возвращаемые результаты. В следующем примере `Foreach` оператор выполняет ту же операцию цикла, что и предыдущий пример, но добавляет `If` инструкцию для ограничения результатов до файлов размером более 100 КИЛОБАЙТ (КБ):

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
  }
}
```

В этом примере `Foreach` цикл использует свойство `$file` переменной для выполнения операции сравнения ( `$file.length -gt 100KB` ). `$file`Переменная содержит все свойства объекта, возвращаемые `Get-ChildItem` командлетом. Таким образом, можно вернуть не только имя файла.
В следующем примере PowerShell возвращает длину и последнее время доступа в списке инструкций:

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
    Write-Host $file.length
    Write-Host $file.lastaccesstime
  }
}
```

В этом примере вы не ограничены выполнением одной команды в списке инструкций.

Можно также использовать переменную за пределами `Foreach` цикла и увеличить переменную внутри цикла. В следующем примере подсчитывается размер файлов свыше 100 КБ:

```powershell
$i = 0
foreach ($file in Get-ChildItem) {
  if ($file.length -gt 100KB) {
    Write-Host $file "file size:" ($file.length / 1024).ToString("F0") KB
    $i = $i + 1
  }
}

if ($i -ne 0) {
  Write-Host
  Write-Host $i " file(s) over 100 KB in the current directory."
}
else {
  Write-Host "No files greater than 100 KB in the current directory."
}
```

В предыдущем примере переменной присваивается `$i` значение `0` вне цикла, а переменная увеличивается в цикле для каждого найденного файла, размер которого ПРЕВЫШАЕТ 100 КБ. Когда цикл завершает работу, `If` оператор вычисляет значение, `$i` чтобы отобразить количество всех файлов свыше 100 КБ. Или отображается сообщение о том, что не найдены файлы размером свыше 100 КБ.

В предыдущем примере также показано, как форматировать результаты размера файла:

```powershell
($file.length / 1024).ToString("F0")
```

Значение делится на 1 024 для отображения результатов в килобайтах, а не в байтах, а полученное значение затем форматируется с помощью описателя формата с фиксированной точкой, чтобы удалить из результата все десятичные значения. Значение 0 указывает, что описатель формата не отображает десятичные разряды.

В следующем примере определенная функция анализирует скрипты PowerShell и модули скриптов и возвращает расположение функций, содержащихся в. В примере показано, как использовать `MoveNext` метод (который работает аналогично `skip X` `For` циклу) и `Current` свойство `$foreach` переменной внутри блока скрипта foreach. Функция example может находить функции в скрипте даже в том случае, если обнаружены неоднородные или непротиворечивые определения функций, охватывающие несколько строк.

Дополнительные сведения см. [в разделе Использование перечислителей](about_Automatic_Variables.md#using-enumerators).

```powershell
function Get-FunctionPosition {
  [CmdletBinding()]
  [OutputType('FunctionPosition')]
  param(
    [Parameter(Position = 0, Mandatory,
      ValueFromPipeline, ValueFromPipelineByPropertyName)]
    [ValidateNotNullOrEmpty()]
    [Alias('PSPath')]
    [System.String[]]
    $Path
  )

  process {
    try {
      $filesToProcess = if ($_ -is [System.IO.FileSystemInfo]) {
        Write-Verbose "From pipeline"
        $_
      } else {
        Write-Verbose "From parameter, $Path"
        Get-Item -Path $Path
      }
      $parser = [System.Management.Automation.Language.Parser]
      Write-Verbose "lets start the foreach loop on `$filesToProcess with $($filesToProcess.count) as count"
      foreach ($item in $filesToProcess) {
        Write-Verbose "$item"
        if ($item.PSIsContainer -or
            $item.Extension -notin @('.ps1', '.psm1')) {
          continue
        }
        $tokens = $errors = $null
        $parser::ParseFile($item.FullName, ([REF]$tokens),
          ([REF]$errors)) | Out-Null
        if ($errors) {
          $msg = "File '{0}' has {1} parser errors." -f $item.FullName,
            $errors.Count
          Write-Warning $msg
        }
        :tokenLoop foreach ($token in $tokens) {
          if ($token.Kind -ne 'Function') {
            continue
          }
          $position = $token.Extent.StartLineNumber
          do {
            if (-not $foreach.MoveNext()) {
              break tokenLoop
            }
            $token = $foreach.Current
          } until ($token.Kind -in @('Generic', 'Identifier'))
          $functionPosition = [pscustomobject]@{
            Name       = $token.Text
            LineNumber = $position
            Path       = $item.FullName
          }
          Add-Member -InputObject $functionPosition `
            -TypeName FunctionPosition -PassThru
        }
      }
    }
    catch {
      throw
    }
  }
}
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_If](about_If.md)

[ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)
