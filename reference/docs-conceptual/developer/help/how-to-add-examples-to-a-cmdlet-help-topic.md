---
title: Добавление примеров в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: 82bee7b7bb0ef49203636f2a293075f3db924ce4
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557096"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>Как добавить примеры в раздел справки для командлета

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>Что нужно узнать о примерах в справке по командлетам

- Список всех имен параметров в команде, даже если имена параметров являются необязательными. Это позволяет пользователю легко интерпретировать команду.

- Не рекомендуется использовать псевдонимы и имена частичных параметров, даже если они работают в Windows PowerShell®.

- В описании примера объясните рациональное построение команды. Объясните, почему вы выбрали определенные параметры и значения и как использовать переменные.

- Если команда использует выражения, объясните их подробно.

- Если команда использует свойства и методы объектов, особенно свойства, которые не отображаются в отображении по умолчанию, используйте пример как возможность, чтобы сообщить пользователю об объекте.

## <a name="help-views-that-display-examples"></a>Представления справки, в которых отображаются примеры

Примеры отображаются только в подробных и полных представлениях справки по командлетам.

## <a name="adding-an-examples-node"></a>Добавление узла примеров

В следующем коде XML показано, как добавить узел примеров, содержащий один узел примера. Добавьте дополнительные примеры узлов для каждого из примеров, которые необходимо включить в раздел.

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>Добавление примера заголовка

В следующем коде XML показано, как добавить заголовок для примера. Заголовок используется для задания примера отдельно от других примеров. ® Windows PowerShell использует стандартный заголовок, который содержит последовательный пример.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>Добавление предшествующих символов

В следующем коде XML показано, как добавить символы, такие как Командная строка Windows PowerShell, которые отображаются непосредственно перед командой example (без каких-либо промежуточных пробелов). ® Windows PowerShell использует командную строку Windows PowerShell: К:\ПС>.

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

В следующем коде XML показано, как добавить описание для примера. ® Windows PowerShell использует один набор \< тегов MAML: para> для описания, хотя \< можно использовать несколько тегов MAML: para>.

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

В следующем коде XML показано, как добавить выходные данные команды. Сведения о результатах команды являются необязательными, но в некоторых случаях полезно продемонстрировать результат использования определенных параметров. ® Windows PowerShell использует два набора пустых \< тегов MAML: para>, чтобы отделить выходные данные команды от команды.

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
