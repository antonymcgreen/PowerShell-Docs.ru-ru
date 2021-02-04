---
description: Объясняется, как перенаправлять выходные данные из PowerShell в текстовые файлы.
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: bc72f479650d67ed17b5fafef56565ccbebfea13
ms.sourcegitcommit: b9826dcf402db8a2b6d3eab37edb82c6af113343
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "98040871"
---
# <a name="about-redirection"></a>О перенаправлении

## <a name="short-description"></a>Краткое описание
Объясняется, как перенаправлять выходные данные из PowerShell в текстовые файлы.

## <a name="long-description"></a>Подробное описание

По умолчанию PowerShell отправляет выходные данные на узел PowerShell. Обычно это консольное приложение. Однако можно направить вывод в текстовый файл, а вывод ошибок можно перенаправить в обычный поток вывода.

Для перенаправления выходных данных можно использовать следующие методы:

- Используйте `Out-File` командлет, который отправляет выходные данные команды в текстовый файл.
  Как правило, командлет используется, `Out-File` когда необходимо использовать параметры, такие как `Encoding` ,, `Force` `Width` или `NoClobber` .

- Используйте `Tee-Object` командлет, который отправляет выходные данные команды в текстовый файл и отправляет его в конвейер.

- Используйте операторы перенаправления PowerShell. Использование оператора перенаправления с целевым объектом файла функционально эквивалентно конвейеру `Out-File` без дополнительных параметров.

Дополнительные сведения о потоках см. в разделе [about_Output_Streams](about_Output_Streams.md).

### <a name="redirectable-output-streams"></a>Перенаправляемые выходные потоки

PowerShell поддерживает перенаправление следующих выходных потоков.

| Вышестоящий # |      Описание:       | Введено в  |    Записать командлет     |
| -------- | ---------------------- | -------------- | ------------------- |
| 1        | **Успешное завершение** Вышестоящий     | PowerShell 2.0 | `Write-Output`      |
| 2        | **Ошибка при** Вышестоящий       | PowerShell 2.0 | `Write-Error`       |
| 3        | **Предупреждение об ошибке** Вышестоящий     | PowerShell 3.0 | `Write-Warning`     |
| 4        | **Подробный вывод** Вышестоящий     | PowerShell 3.0 | `Write-Verbose`     |
| 5        | **Отладка** Вышестоящий       | PowerShell 3.0 | `Write-Debug`       |
| 6        | **Сведения о** Вышестоящий | PowerShell 5.0 | `Write-Information` |
| *        | Все потоки            | PowerShell 3.0 |                     |

> [!NOTE]
> В PowerShell также присутствует поток **хода выполнения** , но он не поддерживает перенаправление.

### <a name="powershell-redirection-operators"></a>Операторы перенаправления PowerShell

Ниже приведены операторы перенаправления PowerShell, где `n` представляет номер потока. Если поток не указан, по умолчанию используется поток **Success** ( `1` ).

| Оператор |                         Описание                         | Синтаксис |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | Отправить указанный поток в файл.                            | `n>`   |
| `>>`     | **Добавить** указанный поток в файл.                      | `n>>`  |
| `>&1`    | _Перенаправляет_ указанный поток в поток **успешного выполнения** . | `n>&1` |

> [!NOTE]
> В отличие от некоторых оболочек UNIX, другие потоки можно перенаправить только в поток **успешного выполнения** .

## <a name="examples"></a>Примеры

### <a name="example-1-redirect-errors-and-output-to-a-file"></a>Пример 1. ошибки перенаправления и выходные данные в файл

Этот пример выполняется `dir` на одном элементе, который будет выполнен, и один из которых будет иметь ошибку.

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

Он использует `2>&1` для перенаправления потока **ошибок** в поток **успешного** выполнения и `>` отправки результирующего потока **успешного выполнения** в файл с именем. `dir.log`

### <a name="example-2-send-all-success-stream-data-to-a-file"></a>Пример 2. Отправка всех успешных данных потока в файл

В этом примере все **успешные** потоковые данные отправляются в файл с именем `script.log` .

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a>Пример 3. Передача в файл успешных, предупреждающих и ошибочных потоков

В этом примере показано, как можно комбинировать операторы перенаправления для достижения желаемого результата.

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > C:\Temp\redirection.log
```

- `3>&1` перенаправляет поток **предупреждений** в поток **успешного выполнения** .
- `2>&1` перенаправляет поток **ошибок** в поток **успешного выполнения** (который также включает все данные потока **предупреждений** ).
- `>` перенаправляет поток **успешного выполнения** (который теперь содержит потоки **предупреждений** и **ошибок** ) в файл с именем `C:\temp\redirection.log` ).

### <a name="example-4-redirect-all-streams-to-a-file"></a>Пример 4. перенаправление всех потоков в файл

Этот пример отправляет все выходные данные из скрипта, вызываемого `script.ps1` в файл с именем `script.log`

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a>Пример 5. Отключение всех данных Write-Host и информационных потоков

В этом примере подавляются все данные потока информации. Дополнительные сведения о командлетах **информационного** потока см. в статье [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) и [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) .

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a>Пример 6. Отображение влияния настроек действий

Переменные и параметры настройки действия могут изменять содержимое, записываемое в определенный поток. Скрипт в этом примере показывает, как значение влияет на то, `$ErrorActionPreference` что записывается в поток **ошибок** .

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

При выполнении этого скрипта выводится запрос, когда `$ErrorActionPreference` для параметра задано значение `Inquire` .

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

При изучении файла журнала мы увидим следующее:

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a>Примечания

Операторы перенаправления, которые не добавляют данные ( `>` и `n>` ) перезаписывают текущее содержимое указанного файла без предупреждения.

Однако если файл доступен только для чтения, является скрытым или системным файлом, перенаправление **завершается ошибкой**. Операторы добавления перенаправления ( `>>` и `n>>` ) не записывают в файл, доступный только для чтения, но добавляют содержимое в системный или скрытый файл.

Для принудительного перенаправления содержимого в скрытый или системный файл только для чтения используйте `Out-File` командлет со своим `Force` параметром.

При записи в файлы операторы перенаправления используют `UTF8NoBOM` кодировку. Если файл имеет другую кодировку, выходные данные могут быть неправильно отформатированы. Для записи в файлы с другой кодировкой используйте `Out-File` командлет с его `Encoding` параметром.

### <a name="potential-confusion-with-comparison-operators"></a>Потенциальная путаница с операторами сравнения

`>`Оператор не следует путать с оператором сравнения " [больше](about_Comparison_Operators.md#-gt--ge--lt-and--le) " (часто обозначается как `>` в других языках программирования).

В зависимости от сравниваемых объектов выходные данные `>` могут выглядеть правильными (поскольку 36 не превышает 42).

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

Однако проверка локальной файловой системы может видеть, что файл `42` с именем был записан с содержимым `36` .

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

Попытка использовать обратные сравнения `<` (меньше) приводит к системной ошибке:

```powershell
PS> if (36 < 42) { "true" } else { "false" }
ParserError:
Line |
   1 |  if (36 < 42) { "true" } else { "false" }
     |         ~
     | The '<' operator is reserved for future use.
```

Значение, если числовое сравнение является обязательной операцией `-lt` и `-gt` должно использоваться. Дополнительные сведения см. в описании `-gt` оператора в [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).

## <a name="see-also"></a>См. также статью

- [Out-File](xref:Microsoft.PowerShell.Utility.Out-File)
- [Tee-Object](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error)
- [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)
- [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)
- [Write-Output](xref:Microsoft.PowerShell.Utility.Write-Output)
- [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [О потоках вывода](about_Output_Streams.md)
- [about_Operators](about_Operators.md)
- [about_Command_Syntax](about_Command_Syntax.md)
- [about_Path_Syntax](about_Path_Syntax.md)
