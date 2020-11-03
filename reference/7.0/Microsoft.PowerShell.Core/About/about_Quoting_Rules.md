---
description: Описывает правила использования одинарных и двойных кавычек в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: 8e30640c74976ac79634f5f7f648aafc16977f31
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232198"
---
# <a name="about-quoting-rules"></a>О правилах заключения в кавычки

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает правила использования одинарных и двойных кавычек в PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Кавычки используются для указания литеральной строки. Строку можно заключать в одинарные кавычки ( `'` ) или двойные кавычки ( `"` ).

Кавычки также используются для создания строки String. Строка Here — это строка, заключенная в одинарные кавычки или двойные кавычки, в которой кавычки обрабатываются буквально. Строка here может охватывать несколько строк. Все строки в этой строке считаются строками, даже если они не заключены в кавычки.

В командах к удаленным компьютерам кавычки определяют части команды, выполняемые на удаленном компьютере. В удаленном сеансе кавычки также определяют, будут ли переменные в команде интерпретироваться первыми на локальном компьютере или на удаленном компьютере.

### <a name="single-and-double-quoted-strings"></a>СТРОКИ С ОДИНАРНЫМИ И ДВОЙНЫМИ КАВЫЧКАМИ

При заключении строки в двойные кавычки (строка, заключенная в двойные кавычки) имена переменных, которым предшествует знак доллара ( `$` ), заменяются значением переменной перед передачей строки в команду для обработки.

Пример:

```powershell
$i = 5
"The value of $i is $i."
```

Выходные данные этой команды:

```Output
The value of 5 is 5.
```

Кроме того, в строке с двойными кавычками вычисляются выражения, а результат вставляется в строку. Пример:

```powershell
"The value of $(2+3) is 5."
```

Выходные данные этой команды:

```Output
The value of 5 is 5.
```

При заключении строки в одинарные кавычки (строка, состоящих из одной кавычки) строка передается в команду точно так же, как при ее вводе. Подстановка не выполняется. Пример:

```powershell
$i = 5
'The value of $i is $i.'
```

Выходные данные этой команды:

```Output
The value $i is $i.
```

Аналогичным образом выражения в строках с одинарными кавычками не оцениваются. Они обрабатываются как литералы. Пример:

```powershell
'The value of $(2+3) is 5.'
```

Выходные данные этой команды:

```Output
The value of $(2+3) is 5.
```

Чтобы предотвратить замену значения переменной в строке двойных кавычек, используйте символ обратной кавычки ( `` ` `` ) (ASCII 96), который является escape-символом PowerShell.

В следующем примере символ обратной кавычки, предшествующий первой переменной $i, не доставит PowerShell заменить имя переменной значением.
Пример:

```powershell
$i = 5
"The value of `$i is $i."
```

Выходные данные этой команды:

```Output
The value $i is 5.
```

Чтобы в строке отображались двойные кавычки, заключите всю строку в одинарные кавычки. Пример:

```powershell
'As they say, "live and learn."'
```

Выходные данные этой команды:

```Output
As they say, "live and learn."
```

Можно также заключить строку, заключенную в одинарные кавычки, в строку в двойных кавычках. Пример:

```powershell
"As they say, 'live and learn.'"
```

Выходные данные этой команды:

```Output
As they say, 'live and learn.'
```

Или двойные кавычки вокруг двойных кавычек. Пример:

```powershell
"As they say, ""live and learn."""
```

Выходные данные этой команды:

```Output
As they say, "live and learn."
```

Чтобы включить одинарную кавычку в строку с одинарной кавычкой, используйте вторую последовательную одинарную кавычку. Пример:

```powershell
'don''t'
```

Выходные данные этой команды:

```Output
don't
```

Чтобы заставить PowerShell интерпретировать двойные кавычки буквально, используйте символ обратной черты. Это предотвращает интерпретацию кавычек в PowerShell как строкового разделителя. Пример:

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

Поскольку содержимое строк с одинарной кавычкой интерпретируется буквально, то символ обратной косой черты рассматривается как литеральный символ и отображается в выходных данных.

### <a name="here-strings"></a>СТРОКИ

Правила предложения для этой строки немного отличаются.

Строка Here — это строка, заключенная в одинарные кавычки или двойные кавычки, в которой кавычки обрабатываются буквально. Строка here может охватывать несколько строк. Все строки в этой строке считаются строками, даже если они не заключены в кавычки.

Как и обычные строки, переменные заменяются значениями в строках, заключенных в двойные кавычки. В строках с одинарной кавычкой (String) переменные не заменяются значениями.

Здесь можно использовать текстовые строки для любого текста, но они особенно полезны для следующих типов текста:

- Текст, содержащий литеральные кавычки
- Несколько строк текста, например текст в HTML или XML
- Текст справки для скрипта или документа функции

Строка в строке может иметь любой из следующих форматов, где `<Enter>` представляет скрытый символ перевода строки или перехода на новую строку, который добавляется при нажатии клавиши <kbd>Ввод</kbd> .

Двойные кавычки:

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

Одинарные кавычки:

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

В любом формате закрывающие кавычки должны быть первыми символами в строке.

Строка here содержит весь текст между двумя скрытыми символами. В этой строке все кавычки обрабатываются буквально. Пример:

```powershell
@"
For help, type "get-help"
"@
```

Выходные данные этой команды:

```Output
For help, type "get-help"
```

Использование строки "строка" может упростить, используя строку в команде. Пример:

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

Выходные данные этой команды:

```Output
Use a quotation mark (') to begin a string.
```

В строках с одинарными кавычками (строки) переменные обрабатываются буквально и воспроизводится точно. Пример:

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

Выходные данные этой команды:

```Output
The $profile variable contains the path
of your PowerShell profile.
```

В строках, заключенных в двойные кавычки, переменные заменяются значениями. Пример:

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

Выходные данные этой команды:

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

Здесь строки обычно используются для назначения нескольких строк переменной. Например, следующая строка here присваивает $page переменной страницу XML.

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

Здесь также удобно использовать для ввода `ConvertFrom-StringData` командлет, который преобразует строки в хэш-таблицы в виде строк.
Для получения дополнительной информации см. `ConvertFrom-StringData`.

## <a name="see-also"></a>СМ. ТАКЖЕ

[about_Special_Characters](about_Special_Characters.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
