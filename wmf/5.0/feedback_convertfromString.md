---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: fcf2adf67f36edb534df3e2a849459fb20e1c2de
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085360"
---
# <a name="extract-and-parse-structured-objects-out-of-string"></a>Извлечение и анализ структурированных объектов вне строки

Здесь также расширена функциональность командлета `ConvertFrom-String`:

- Удалено свойство текста экстента по умолчанию. Теперь его можно включить с помощью параметра -IncludeExtent.

- Исправлены многие ошибки в алгоритмах обучения благодаря отзывам MVP и участников сообщества.

- Новый параметр -UpdateTemplate для сохранения результатов алгоритма обучения в комментарий внутри файла шаблона. Это делает затраты на процесс обучения (являющийся самым медленным этапом) единовременными. Выполнение Convert-String с шаблоном, содержащим закодированный обучающий алгоритм, теперь осуществляется практически мгновенно.

## <a name="extract-and-parse-structured-objects-out-of-string-content"></a>Извлечение и анализ структурированных объектов вне строки

При сотрудничестве с [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F) был добавлен новый командлет `ConvertFrom-String`.

Он поддерживает два режима: базовый анализ с разделением и анализ с управлением автоматически создаваемым примером.

Анализ с разделением, используемый по умолчанию, разбивает входные данные с помощью пробелов и присваивает имена свойств получаемым группам. Разделитель можно настроить:

```powershell
"Hello World" | ConvertFrom-String | Format-Table -Auto
```

```output
P1     P2
--     --
Hello  World
```

Командлет также поддерживает анализ с управлением автоматически создаваемым примером, основанные на исследованиях технологии [FlashExtract](https://www.microsoft.com/en-us/research/publication/flashextract-framework-data-extraction-examples/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fsumitg%2Fflashextract.html) в [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F).

Для начала рассмотрим текстовую адресную книгу:

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA

    Thomas Hardy

    Seattle, WA

    Christina Berglund

    Redmond, WA

    Hanna Moos

    Puyallup, WA
```

Скопируйте несколько примеров в файл, который будет использоваться в качестве шаблона:

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA
```

Заключите извлекаемые данные в фигурные скобки, при этом им присваивается имя. Поскольку свойство **Name** (и другие связанные с ним свойства) могут встречаться несколько раз, используйте звездочку (\*), чтобы указать, что результат представлен несколькими записями (вместо извлечения множества свойств в одну запись):

```
    {Name\*:Ana Trujillo}

    {City:Redmond}, {State:WA}

    {Name\*:Antonio Moreno}

    {City:Renton}, {State:WA}
```

Используя этот набор примеров, `ConvertFrom-String` может автоматически извлекать выходные данные на основе объектов из входных файлов с аналогичной структурой.

```powershell
Get-Content .\addresses.output.txt | ConvertFrom-String -TemplateFile .\addresses.template.txt | Format-Table -Auto
```

```output
ExtentText                     Name               City     State
----------                     ----               ----     -----
Ana Trujillo...                Ana Trujillo       Redmond  WA
Antonio Moreno...              Antonio Moreno     Renton   WA
Thomas Hardy...                Thomas Hardy       Seattle  WA
Christina Berglund...          Christina Berglund Redmond  WA
Hanna Moos...                  Hanna Moos         Puyallup WA
```

В целях дополнительной обработки извлеченного текста свойство **ExtentText** может фиксировать необработанный текст, из которого извлекалась запись. Чтобы дать отзыв об этой функции или предоставить содержимое, для которого у вас не получается составить примеры, отправьте сообщение электронной почты на адрес <psdmfb@microsoft.com>.