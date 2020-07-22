---
title: Как добавить примеры в раздел справки для командлета
ms.date: 09/12/2016
ms.openlocfilehash: 33a1726f9d52b5a368d5df7962cc17ba9c45246a
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893447"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>Как добавить примеры в раздел справки для командлета

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>Что нужно узнать о примерах в справке по командлетам

- Список всех имен параметров в команде, даже если имена параметров являются необязательными. Это позволяет пользователю легко интерпретировать команду.

- Избегайте псевдонимов и частичных имен параметров, даже если они работают в PowerShell.

- В описании примера объясните рациональное построение команды. Объясните, почему вы выбрали определенные параметры и значения и как использовать переменные.

- Если команда использует выражения, объясните их подробно.

- Если команда использует свойства и методы объектов, особенно свойства, которые не отображаются в отображении по умолчанию, используйте пример как возможность, чтобы сообщить пользователю об объекте.

## <a name="help-views-that-display-examples"></a>Представления справки, в которых отображаются примеры

Примеры отображаются только в подробных и полных представлениях справки по командлетам.

## <a name="adding-an-examples-node"></a>Добавление узла примеров

В следующем коде XML показано, как добавить узел **примеров** , содержащий один узел **примера** . Добавьте дополнительные примеры узлов для каждого из примеров, которые необходимо включить в раздел.

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>Добавление примера заголовка

В следующем коде XML показано, как добавить **заголовок** для примера. **Заголовок** используется для задания примера отдельно от других примеров. PowerShell использует стандартный заголовок, который содержит последовательный пример числа.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>Добавление предшествующих символов

В следующем коде XML показано, как добавить символы, такие как Командная строка Windows PowerShell, которые отображаются непосредственно перед командой example (без каких-либо промежуточных пробелов). PowerShell использует командную строку Windows PowerShell: `C:\PS>` .

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
</command:example>
</command:examples>
```

## <a name="adding-the-command"></a>Добавление команды

В следующем коде XML показано, как добавить фактическую команду в примере. При добавлении команды введите полное имя (не используйте псевдоним) командлетов и параметров. Кроме того, при возможности используйте символы нижнего регистра.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
</command:example>
</command:examples>
```

## <a name="adding-a-description"></a>Добавление описания

В следующем коде XML показано, как добавить описание для примера. PowerShell использует для описания один набор `<maml:para>` тегов, хотя `<maml:para>` можно использовать несколько тегов.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
    </dev:remarks>
</command:example>
</command:examples>
```

## <a name="adding-example-output"></a>Добавление выходных данных примера

В следующем коде XML показано, как добавить выходные данные команды. Сведения о результатах команды являются необязательными, но в некоторых случаях полезно продемонстрировать результат использования определенных параметров.
PowerShell использует два набора пустых `<maml:para>` тегов для отделения выходных данных команды от команды.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
      <maml:para></maml:para>
      <maml:para></maml:para>
      <maml:para> command output </maml:para>
</dev:remarks>
</command:example>
</command:examples>
```
