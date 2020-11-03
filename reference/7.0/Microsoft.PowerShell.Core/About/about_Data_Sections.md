---
description: Описывает разделы данных, которые изолируют текстовые строки и другие данные, предназначенные только для чтения, из логики скрипта.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: 8532804c59ebcb7dd8f98eac7dc9e0865b21f2b3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231014"
---
# <a name="about-data-sections"></a>Разделы данных

## <a name="short-description"></a>Краткое описание
Описывает разделы данных, которые изолируют текстовые строки и другие данные, предназначенные только для чтения, из логики скрипта.

## <a name="long-description"></a>Полное описание

Скрипты, разработанные для PowerShell, могут содержать один или несколько разделов данных, содержащих только данные. Можно включить один или несколько разделов данных в любой сценарий, функцию или расширенную функцию. Содержимое раздела данных ограничено указанным подмножеством языка сценариев PowerShell.

Отделение данных от логики кода упрощает выявление и управление логикой и данными. Он позволяет иметь отдельные строковые файлы ресурсов для текста, например сообщения об ошибках и строки справки. Он также изолирует логику кода, которая упрощает тестирование безопасности и проверки.

В PowerShell раздел данных используется для поддержки интернационализации сценариев.
Разделы данных можно использовать для упрощения изоляции, обнаружения и обработки строк, которые будут переведены на множество языков пользовательского интерфейса.

Раздел данных является функцией PowerShell 2,0. Скрипты с разделами данных не будут выполняться в PowerShell 1,0 без версии.

### <a name="syntax"></a>Синтаксис

Синтаксис для раздела данных выглядит следующим образом:

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

Требуется ключевое слово Data. Не учитывает регистр. Разрешенное содержимое ограничено следующими элементами:

- Все операторы PowerShell, Кроме `-match`
- `If``Else`операторы, и `ElseIf`
- Следующие автоматические переменные: `$PsCulture` , `$PsUICulture` , `$True` , `$False` и `$Null`
- Комментарии
- Конвейеры
- Операторы, разделенные точкой с запятой ( `;` )
- Литералы, например следующие:

  ```powershell
  a
  1
  1,2,3
  "PowerShell 2.0"
  @( "red", "green", "blue" )
  @{ a = 0x1; b = "great"; c ="script" }
  [XML] @'
  <p> Hello, World </p>
  '@
  ```

- Командлеты, разрешенные в разделе данных. По умолчанию разрешен только `ConvertFrom-StringData` командлет.
- Командлеты, разрешенные в разделе данных с помощью `-SupportedCommand` параметра.

При использовании `ConvertFrom-StringData` командлета в разделе данных можно заключать пары "ключ-значение" в строки с одинарными кавычками или двойными кавычками или в строках с одинарными кавычками или двойными кавычками. Однако строки, содержащие переменные и части выражения, должны быть заключены в строки с одинарными кавычками или в строках с одинарными кавычками, чтобы эти переменные не были развернуты, а части выражения не были исполняемыми.

### <a name="-supportedcommand"></a>-Суппортедкомманд

`-SupportedCommand`Параметр позволяет указать, что командлет или функция создает только данные. Он предназначен для того, чтобы разрешить пользователям включать командлеты и функции в раздел данных, который они записали или протестировали.

Значение `-SupportedCommand` представляет собой разделенный запятыми список из одного или нескольких имен командлетов или функций.

Например, в следующем разделе данных содержится командлет, созданный пользователем, `Format-XML` который форматирует данные в XML-файле:

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a>Использование раздела данных

Чтобы использовать содержимое раздела данных, назначьте его переменной и используйте нотацию переменной для доступа к содержимому.

Например, следующий раздел данных содержит `ConvertFrom-StringData` команду, преобразующую данную строку в хэш-таблицу. Хэш-таблица назначается `$TextMsgs` переменной.

`$TextMsgs`Переменная не входит в раздел данных.

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

Чтобы получить доступ к ключам и значениям в хэш-таблице в `$TextMsgs` , используйте следующие команды.

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

Кроме того, можно добавить имя переменной в определение раздела данных. Пример:

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

Результат аналогичен предыдущему примеру.

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a>Примеры

Простые строки данных.

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

Строки, включающие разрешенные переменные.

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

Строка с одинарной кавычкой, которая использует `ConvertFrom-StringData` командлет:

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

Строка, заключенная в двойные кавычки, с использованием `ConvertFrom-StringData` командлета:

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

Раздел данных, содержащий пользовательский командлет, создающий данные:

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a>См. также:

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_If](about_If.md)

[about_Operators](about_Operators.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Script_Internationalization](about_Script_Internationalization.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
