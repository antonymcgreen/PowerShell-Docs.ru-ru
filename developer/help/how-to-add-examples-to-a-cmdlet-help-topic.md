---
title: Как добавить примеры для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: 5e8d1df6b423bfd2cd6b0a64a8875dea9c3fb4ef
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083473"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>Как добавить примеры в раздел справки для командлета

- [Что нужно знать о примерах справки по командлетам](#Things-to-Know-about-Examples-in-Cmdlet-Help)

- [Справка представлений, которые отображают примеры](#Help-Views-that-Display-Examples)

- [Добавление узла примеры](#Adding-an-Examples-Node)

- [Добавление предшествующих символов](#Adding-Preceding-Characters)

- [Добавление команды](#Adding-the-Command)

- [Добавление описания](#Adding-a-Description)

- [Добавление выходных данных примера](#Adding-Example-Output)

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>Что нужно знать о примерах справки по командлетам

- Список всех имен параметров в команде, даже в том случае, если имена параметров являются необязательными. Это позволяет пользователю легко интерпретировать команду.

- Избегайте псевдонимы и частичные имена параметров, несмотря на то, что они работают в Windows PowerShell®.

- В описании примера объясните rational для создания команды. Объясните предложениями определенного параметры и значения, и как использовать переменные.

- Если команда использует выражения, их также подробно объясняется.

- Если команда использует свойства и методы объектов, особенно те свойства, которые не отображаются в представление по умолчанию, используйте приведенный пример, как возможность сообщить пользователю об объекте.

## <a name="help-views-that-display-examples"></a>Справка представлений, которые отображают примеры

Примеры приведены только в подробный и полного представления справки по командлетам.

## <a name="adding-an-examples-node"></a>Добавление узла примеры

Следующий код XML показано, как добавить узел примерах, содержит один узел пример. Добавьте дополнительный пример узлы для каждого примеры, которые вы хотите включить в разделе.

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>Добавление название примера

Следующий код XML показано, как добавить заголовок для примера. Заголовок, используемый для задания в примере, помимо других примеров. Windows PowerShell® использует стандартный заголовок, который включает несколько последовательном примере.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>Добавление предшествующих символов

Следующий код XML показано, как добавить символы, такие как командной строке Windows PowerShell, которые отображаются непосредственно перед пример команды (без пробелов промежуточных). Windows PowerShell® используется в командной строке Windows PowerShell: C:\PS>.

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

Следующий код XML показано, как добавить команду фактическое примера. При добавлении команды, введите полное имя (не используйте псевдоним) командлетов и параметров. Кроме того можно используйте строчные буквы, когда это возможно.

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

Следующий код XML показано, как добавить описание для примера. Windows PowerShell® использует один набор \<MAML: para > теги для описания, даже если несколько \<MAML: para > теги можно использовать.

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

Следующий XML-код демонстрирует добавление выходных данных команды. Сведения о командах результатов является необязательным, но в некоторых случаях полезно демонстрации эффекта с помощью определенных параметров. Windows PowerShell® использует два набора пустым \<MAML: para > теги для разделения выходных данных команды из команды.

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