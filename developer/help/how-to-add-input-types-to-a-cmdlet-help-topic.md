---
title: Добавление типов входных данных для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: f213605dda0132051d983f8608515325e815c455
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083439"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>Как добавить типы входных данных в раздел справки для командлета

В этом разделе описывается добавление раздел входных данных для раздела справки командлета Windows PowerShell®. В разделе входных данных перечислены классы .NET объектов, командлет принимает в качестве входных данных из конвейера, по значению или по имени свойства.

Нет ограничений на число классов, которые можно добавить раздел входных данных. Типы входных данных заключаются в \<команда: inputTypes > узел, в которой каждый класс, заключенный в \<команда: inputType > элемента.

Эта схема включает два \<maml:description > элементов в каждом \<команда: inputType > элемента. Тем не менее `Get-Help` командлет отображает только содержимое \<команда: inputType > /\<maml:description >) элемента.

Начиная с Windows PowerShell 3.0, `Get-Help` командлет отображает содержимое элемента \<MAML: URI > элемента. Этот элемент позволяет направлять пользователей на разделы, описывающие класс .NET.

Следующий код XML показывает \<maml:inputTypes > узла.

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> Class name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Brief description </maml:para>
    </maml:description>
  </command:inputType>
</command:inputTypes>
```

Следующий код XML показывает пример использования \<maml:inputTypes > узел для документирования тип входных данных.

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```