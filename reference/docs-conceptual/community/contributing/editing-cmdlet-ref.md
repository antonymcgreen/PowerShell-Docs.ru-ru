---
title: Изменение справочных статей
description: В этой статье приводятся правила, касающиеся редактирования справки по командлетам и других справочных статей в документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 3c6f1b4fc27ca8ece7ec30317daf4ed2a6bc9228
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060329"
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

Файлы `About_*` теперь обрабатываются средством [Pandoc][], а не PlatyPS. Файлы `About_*` форматируются так, чтобы они были максимально совместимы со всеми версиями PowerShell и средствами публикации.

Основные рекомендации по форматированию.

- Ограничьте длину строк 80 символами.
- Длина строк в блоках кода и таблицах ограничена 76 символами, так как при преобразовании средством Pandoc в обычный текст они получают отступ в четыре пробела.
- Ширина таблиц должна быть не более 76 символов.
  - Переносите содержимое ячеек по строкам вручную.
  - Используйте открывающие и закрывающие символы `|` в каждой строке.
  - Рабочий пример см. в разделе [about_Comparison_Operators][about-example].
- Использование специальных символов Pandoc `\`, `$` и `<`:
  - в заголовке эти символы должны быть экранированы с помощью начального символа `\` или заключены в обратные апострофы (`` ` ``);
  - в абзаце эти символы должны включаться во фрагменты кода. Пример:

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

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
[about-example]: https://github.com/MicrosoftDocs/PowerShell-Docs/reference/5.1/Microsoft.PowerShell.Core/About/about_Comparison_Operators.md
[Pandoc]: https://pandoc.org
