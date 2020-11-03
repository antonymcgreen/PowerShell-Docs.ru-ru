---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: f4b58605059d85cd2a215969c13f9cc2e5262465
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227734"
---
# ConvertFrom-StringData

## Краткий обзор
Преобразует строку, содержащую одну или несколько пар типа ключ-значение в хэш-таблицу.

## SYNTAX

```
ConvertFrom-StringData [-StringData] <String> [<CommonParameters>]
```

## DESCRIPTION

`ConvertFrom-StringData`Командлет преобразует строку, содержащую одну или несколько пар "ключ — значение", в хэш-таблицу. Так как каждая пара "ключ-значение" должна находиться в отдельной строке, в качестве входного формата часто используются строки. По умолчанию **ключ** должен быть отделен от **значения** знаком равенства ( `=` ).

`ConvertFrom-StringData`Командлет считается безопасным командлетом, который можно использовать в `DATA` разделе скрипта или функции. При использовании в `DATA` разделе содержимое строки должно соответствовать правилам для раздела данных. Дополнительные сведения см. в разделе [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).

`ConvertFrom-StringData` поддерживает последовательности escape-символов, которые разрешены обычными средствами машинного перевода. То есть командлет может интерпретировать обратные косые черты ( `\` ) в виде escape-символов в строковых данных с помощью [метода Regex. Unescape](/dotnet/api/system.text.regularexpressions.regex.unescape)вместо символа обратной кавычки PowerShell ( \` ), который обычно сигнализирует об окончании строки в скрипте. Внутри строки here символ обратного апострофа не работает. Можно также сохранить литеральную обратную косую черту в результатах, отменив ее на предшествующую обратную косую черту следующим образом: `\\` . Неэкранированные символы обратной косой черты, например часто используемые в путях к файлам, могут при обработке расцениваться как недопустимые escape-символы.

## Примеры

### Пример 1. Преобразование строки с одним предложением в кавычки в хэш-таблицу

В этом примере в хэш-таблицу преобразуется строка сообщения пользователя с одинарной кавычкой. В строках с одиночными кавычками значения переменных не подставляются и выражения не вычисляются.
`ConvertFrom-StringData`Командлет преобразует значение `$Here` переменной в хэш-таблицу.

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### Пример 2. Преобразование строки, содержащей комментарий

В этом примере преобразуется строка, содержащая комментарий и несколько пар "ключ-значение", в хэш-таблицу.

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

Значением параметра **StringData** является строка String, а не переменная, содержащая строку String. Допустимы оба формата. Строка here содержит комментарий об одной из строк.
`ConvertFrom-StringData` игнорирует однострочные комментарии, но `#` символ должен быть первым символом, не являющимся пробелом в строке. Все символы в строке после символов `#` игнорируются.

### Пример 3. Преобразование строки в хэш-таблицу

Этот пример преобразует обычную строку в двойных кавычках (а не строку) в хэш-таблицу и сохраняет ее в `$A` переменной.

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

Для соответствия условию, что каждая пара «ключ-значение» должна находиться в отдельной строке, в строке используется символ новой строки в PowerShell ( \` n) для разделения пар.

### Пример 4. Использование ConvertFrom-StringData в разделе данных скрипта

В этом примере показана `ConvertFrom-StringData` команда, используемая в разделе данных скрипта.
Инструкции, расположенные ниже раздела DATA, служат для вывода текста для пользователя.

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

Так как текст содержит имена переменных, его необходимо заключить в одиночные кавычки, чтобы переменные интерпретировались как текст и вместо них не подставлялись значения. В разделе **Data** не допускаются переменные.

### Пример 5. Использование оператора конвейера для передачи строки

В этом примере показано, как можно использовать оператор конвейера ( `|` ) для отправки строки в `ConvertFrom-StringData` . Значение `$Here` переменной передается в, `ConvertFrom-StringData` а результат — в `$Hash` переменную.

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### Пример 6. использование escape-символов для добавления новых строк и возврата символов

В этом примере показано использование escape-символов для создания новых строк и возврата символов в исходные данные. Escape-последовательность `\n` используется для создания новых строк внутри блока текста, связанного с именем или элементом в результирующей хэш-таблице.

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### Пример 7. использование escape-символа обратной косой черты для правильного отображения пути к файлу

В этом примере показано, как использовать escape-символ обратной косой черты в строковых данных, чтобы обеспечить правильное отображение пути к файлу в результирующей `ConvertFrom-StringData` хэш таблице. С помощью двойной обратной косой черты гарантируется правильное представление символов обратной косой черты в выходных данных хэш-таблицы.

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## PARAMETERS

### -StringData

Указывает строку, которую нужно преобразовать. Можно использовать этот параметр или передать строку в `ConvertFrom-StringData` . Имя параметра является необязательным.

Значение этого параметра должно быть строкой, содержащей одну или несколько пар "ключ-значение". Каждая пара "ключ-значение" должна находиться в отдельной строке, или каждая пара должна быть разделена символами новой строки ( \` n).

В строку можно включить комментарии, но комментарии не могут находиться в той же строке, что и пара "ключ-значение". `ConvertFrom-StringData` игнорирует однострочные комментарии. `#`Символ должен быть первым символом, отличным от пробела, в строке. Все символы в строке после символов `#` игнорируются. Комментарии не включаются в хэш-таблицу.

Строка Here — это строка, состоящая из одной или нескольких строк. Кавычки в текстовой строке обрабатываются буквально как часть строковых данных. Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

Строку, содержащую пару "ключ-значение", можно передать в `ConvertFrom-StringData` .

## Выходные данные

### System.Collections.Hashtable

Этот командлет возвращает хэш-таблицу, которая создается из пар "ключ-значение".

## ПРИМЕЧАНИЯ

Строка here — это строка, содержащая одну или несколько строк с кавычками, которые интерпретируются буквально.

Этот командлет может быть полезен в сценариях, отображающих пользовательские сообщения на нескольких языках. Хэш-таблицы, напоминающие словари, позволяют изолировать текстовые строки от кода, например в файлах ресурсов, и форматировать текстовые строки для использования в средствах перевода.

## Связанные ссылки
