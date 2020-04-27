---
title: Изменение справочных статей
description: В этой статье приводятся правила, касающиеся редактирования справки по командлетам и других справочных статей в документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: e135f6cc81ba7537a535a08421e1ca9b2b2af573
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624777"
---
# <a name="editing-reference-articles"></a>Изменение справочных статей

Справочные статьи по командлетам имеют определенную структуру. Она определяется модулем [PlatyPS][].
Средство PlatyPS создает справку по командлетам для модулей PowerShell в разметке Markdown. После редактирования файлов Markdown с помощью PlatyPS создаются MAML-файлы справки, используемые командлетом `Get-Help`.

В коде PlatyPS жестко задана схема для справки по командлетам. Ее описание можно найти в документе [platyPS.schema.md][]. Нарушения схемы приводят к ошибкам сборки, которые необходимо исправить, иначе ваше содержимое не будет принято.

## <a name="general-guidelines"></a>Общие рекомендации

- Не удаляйте заголовки. PlatyPS требует определенного набора заголовков.
- Под заголовками **Input type** (Тип входных данных) и **Output type** (Тип выходных данных) должен быть указан тип. Если командлет не принимает входные данные или не возвращает значение, используйте значение `None` (Нет).
- Огражденные блоки кода допускаются только в разделе [Examples](#structuring-examples) (Примеры).
- Встроенные фрагменты кода можно использовать в любом абзаце.

## <a name="formatting-about_-files"></a>Форматирование файлов About_

Файлы `About_*` записываются в Markdown, но поставляются в виде обычных текстовых файлов. Для преобразования Markdown в обычный текст используется [Pandoc][]. Файлы `About_*` форматируются так, чтобы они были максимально совместимы со всеми версиями PowerShell и средствами публикации.

Основные рекомендации по форматированию.

- Ограничьте длину строк 80 символами. Pandoc делает отступ для некоторых блоков Markdown, чтобы выровнять эти блоки.
  - Длина блоков кода ограничена 76 символами.
  - Длина таблиц ограничена 76 символами.
  - Блоки цитирования (и оповещения) ограничены 78 символами.

- Используйте специальные символы Pandoc в заголовке: `\`, `$` и `<`.
  - Эти символы должны быть экранированы с помощью начального символа `\` или включены во встроенные фрагменты кода с помощью обратных апострофов (`` ` ``).
  - в абзаце эти символы должны включаться во фрагменты кода. Пример:

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- Ширина таблиц должна быть не более 76 символов.
  - Переносите содержимое ячеек по строкам вручную.
  - Используйте открывающие и закрывающие символы `|` в каждой строке.
  - В следующем примере показано, как правильно создать таблицу со сведениями, которые переносятся на несколько строк в ячейке.

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > Ограничение в 76 столбцов применяется только к разделам `About_*`. Широкие столбцы можно использовать в обзорной или справочной документации по командлетам.

## <a name="structuring-examples"></a>Структурирование примеров

В схеме PlatyPS заголовок **EXAMPLES** (Примеры) имеет уровень H2, а заголовок каждого примера — уровень H3.

Внутри примера схема не позволяет разделять блоки кода абзацами. Допустимая схема:

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

Пронумеруйте все примеры и снабдите их краткими заголовками.

Пример:

### <a name="example-1-get-cmdlets-functions-and-aliases"></a>Пример 1: Получение командлетов, функций и псевдонимов

Эта команда получает командлеты, функции и псевдонимы PowerShell, которые устанавливаются на компьютере.

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a>Пример 2. Получение команд в текущем сеансе

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a>Дальнейшие действия

[Контрольный список для редактора](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
