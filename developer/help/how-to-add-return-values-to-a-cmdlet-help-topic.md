---
title: Добавление возвращаемого значения для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52ab737-753c-4d04-8af7-758d5c805e18
caps.latest.revision: 7
ms.openlocfilehash: b21811e5a5a819c3d5c4a55fcbe685a84819b71d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859440"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>Как добавить возвращаемые значения в раздел справки для командлета

В этом разделе описывается добавление раздел OUTPUTS для раздела справки командлета Windows PowerShell®. В разделе выходных данных перечислены классы .NET объектов, которые возвращает командлет, или передает по конвейеру.

Нет ограничений на число классов, которые можно добавить в раздел выходных данных. Типы возвращаемого значения командлета заключаются в \<команда: returnValues > узел, в которой каждый класс, заключенный в \<команда: returnValue > элемента.

Если командлет не создает никаких выходных данных, используйте этот раздел, чтобы о том, что выходные данные. Например вместо имени класса, написать «None» и Дайте краткое описание. Если командлет создает выходные данные по условию, используйте этот узел, чтобы объяснить условия и описание условным выводом.

Эта схема включает два \<maml:description > элементов в каждом \<команда: returnValue > элемента. Тем не менее `Get-Help` командлет отображает только содержимое \<команда: returnValue > /\<maml:description > элемента.

Начиная с Windows PowerShell 3.0, `Get-Help` командлет отображает содержимое элемента \<MAML: URI > элемента. Этот элемент позволяет направлять пользователей на разделы, описывающие класс .NET.

Следующий код XML показывает \<maml:returnValues > узла.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

Следующий код XML показывает пример использования \<maml:returnValues > узел для документирования тип выходных данных.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```



