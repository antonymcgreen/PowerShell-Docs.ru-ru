---
title: Добавление типов входных данных в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: 58b908be3149376547b075320b021421351b881e
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557075"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>Как добавить типы входных данных в раздел справки для командлета

В этом разделе описано, как добавить раздел ВХОДных данных в раздел справки по командлету Windows PowerShell®. В разделе ВХОДных данных перечислены классы .NET объектов, которые командлет принимает в качестве входных данных из конвейера: по значению или по имени свойства.

Количество классов, которые можно добавить в раздел ВХОДных данных, не ограничено. Входные типы заключаются в \< команду: инпуттипес> node с каждым классом, заключенным в \< команду: inputType> element.

Схема включает в себя два \< элемента MAML: description> в каждой \< команде: inputType> элемент. Однако `Get-Help` командлет отображает только содержимое \< команды: inputType>/ \< maml: Description>).

Начиная с Windows PowerShell 3,0, `Get-Help` командлет отображает содержимое \< элемента MAML: URI>. Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.

В следующем коде XML показан \< узел MAML: инпуттипес>.

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

В следующем коде XML показан пример использования \< узла MAML: инпуттипес> для документирования типа входных данных.

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
