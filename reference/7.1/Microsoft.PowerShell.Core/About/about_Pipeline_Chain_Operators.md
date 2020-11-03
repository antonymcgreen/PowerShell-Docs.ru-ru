---
description: Описывает цепочки конвейеров с помощью `&&` `||` операторов и в PowerShell.
ms.date: 09/30/2019
schema: 2.0.0
Locale: en-US
keywords: powershell,командлет
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: 38895ff9acda9ead031c9be58904ac132364a584
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231678"
---
# <a name="about-pipeline-chain-operators"></a>Сведения об операторах цепочки конвейеров

## <a name="short-description"></a>Краткое описание

Описывает цепочки конвейеров с помощью `&&` `||` операторов и в PowerShell.

## <a name="long-description"></a>Подробное описание

Начиная с PowerShell 7, PowerShell реализует `&&` операторы и `||` для условного сцепления конвейеров. Эти операторы известны в PowerShell как *Операторы цепочки конвейеров* и похожи на [списки и или](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) в оболочках POSIX, таких как bash, ЗШ и SH, а также на [символы условной обработки](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) в командной оболочке Windows (cmd.exe).

Оператор `&&` выполняет конвейер в правой части, если конвейер в левой части был выполнен успешно. И наоборот, оператор `||` выполняет конвейер в правой части, если конвейер в левой части не удалось выполнить.

Для определения того, был ли выполнен конвейер, эти операторы используют переменные `$?` и `$LASTEXITCODE`. Это позволяет использовать их с собственными командами, а не только с командлетами или функциями. Пример:

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a>Примеры

#### <a name="two-successful-commands"></a>Две успешные команды

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a>Первая команда завершается неудачно, что привело к невыполнению второго

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a>Первая команда выполняется, поэтому вторая команда не выполняется

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a>Первая команда завершается ошибкой, поэтому выполняется Вторая команда.

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

Успешное завершение конвейера определяется значением `$?` переменной, которое PowerShell автоматически задает после выполнения конвейера в зависимости от состояния выполнения.
Это означает, что операторы цепочки конвейера имеют следующие эквиваленты:

```powershell
Test-Command '1' && Test-Command '2'
```

работает так же, как

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

and

```powershell
Test-Command '1' || Test-Command '2'
```

работает так же, как

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a>Назначение из цепочек конвейера

Назначение переменной из цепочки конвейера выполняется путем объединения всех конвейеров в цепочке:

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

Если во время назначения из цепочки конвейера возникает ошибка, связанная со сценарием, то назначение не выполняется.

```powershell
try
{
    $result = Write-Output 'Value' && $(throw 'Bad')
}
catch
{
    # Do nothing, just squash the error
}

"Result: $result"
```

```Output
Result:
```

### <a name="operator-syntax-and-precedence"></a>Синтаксис операторов и их приоритет

В отличие от других операторов `&&` и для обработки `||` конвейеров, а не для таких выражений, как `+` или `-and` , например.

`&&` и `||` имеют более низкий приоритет, чем конвейер ( `|` ) или перенаправление ( `>` ), но более высокий приоритет по сравнению с операторами задания ( `&` ), присваиванием ( `=` ) или точкой с запятой ( `;` ). Это означает, что конвейеры в цепочке конвейера могут быть перенаправлены по отдельности, а все цепочки конвейеров могут быть фоновыми, назначены переменным или разделены инструкциями.

Чтобы использовать синтаксис более низкого приоритета в цепочке конвейера, рассмотрите возможность использования круглых скобок `(...)` .
Аналогично, чтобы внедрить инструкцию в цепочку конвейера, `$(...)` можно использовать часть выражения.
Это может быть полезно для объединения машинных команд с потоком управления:

```powershell
foreach ($file in 'file1','file2','file3')
{
    # When find succeeds, the loop breaks
    find $file && Write-Output "Found $file" && $(break)
}
```

```Output
find: file1: No such file or directory
file2
Found file2
```

Начиная с PowerShell 7, поведение этих синтаксисов было изменено так, чтобы `$?` оно было задано как ожидается при успешном или неудачном выполнении команды в круглых скобках или части выражения.

Как и большинство других операторов в PowerShell, они `&&` `||` также имеют *левую ассоциативность* , то есть группируются слева. Пример:

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

будет группироваться как:

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

эквивалентно:

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a>Взаимодействие с ошибкой

Операторы цепочки конвейеров не применяют к ошибкам. Если инструкция в цепочке конвейера вызывает ошибку, завершающуюся сценарием, то цепь конвейера завершается.

Пример:

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

Даже если ошибка перехвачена, цепь конвейера по-прежнему завершается:

```powershell
try
{
    $(throw 'Bad') || Write-Output '2'
}
catch
{
    Write-Output "Caught: $_"
}
Write-Output 'Done'
```

```Output
Caught: Bad
Done
```

Если ошибка не завершается или завершается только конвейер, то цепь конвейера будет продолжаться, в соответствии со значением `$?` :

```powershell
function Test-NonTerminatingError
{
    [CmdletBinding()]
    param()

    $exception = [System.Exception]::new('BAD')
    $errorId = 'BAD'
    $errorCategory = 'NotSpecified'

    $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

    $PSCmdlet.WriteError($errorRecord)
}

Test-NonTerminatingError || Write-Output 'Second'
```

```Output
Test-NonTerminatingError: BAD
Second
```

### <a name="chaining-pipelines-rather-than-commands"></a>Сцепление конвейеров, а не команд

Операторы цепочки конвейеров по имени можно использовать для сцепления конвейеров, а не просто команд. Это соответствует поведению других оболочек, но может усложнить *успешно* определить:

```powershell
function Test-NotTwo
{
    [CmdletBinding()]
    param(
      [Parameter(ValueFromPipeline)]
      $Input
    )

    process
    {
        if ($Input -ne 2)
        {
            return $Input
        }

        $exception = [System.Exception]::new('Input is 2')
        $errorId = 'InputTwo'
        $errorCategory = 'InvalidData'

        $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

        $PSCmdlet.WriteError($errorRecord)
    }
}

1,2,3 | Test-NotTwo && Write-Output 'All done!'
```

```Output
1
Test-NotTwo : Input is 2
3
```

Обратите внимание, что `Write-Output 'All done!'` не выполняется, поскольку считается `Test-NotTwo` неудачным после создания неустранимой ошибки.

## <a name="see-also"></a>См. также статью

- [about_Operators](about_Operators.md)
- [about_Automatic_Variables](about_Automatic_Variables.md)
- [about_pipelines](about_pipelines.md)

