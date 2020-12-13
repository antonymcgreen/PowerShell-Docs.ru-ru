---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить типы входных данных в раздел справки для командлета
description: Как добавить типы входных данных в раздел справки для командлета
ms.openlocfilehash: f2ad87c54230bcdd7e0ea708e9a1869daef7495f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391108"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>Как добавить типы входных данных в раздел справки для командлета

В этом разделе описывается добавление раздела **входных данных** в раздел справки по командлетам PowerShell. В разделе **входных данных** перечислены классы .NET объектов, которые командлет принимает в качестве входных данных из конвейера: по значению или по имени свойства.

Количество классов, которые можно добавить в раздел **входных данных** , не ограничено. Входные типы заключаются в `<command:inputTypes>` узел с каждым классом, заключенным в `<command:inputType>` элемент.

Схема включает в себя два `<maml:description>` элемента в каждом `<command:inputType>` элементе.
Однако `Get-Help` командлет отображает только содержимое `<command:inputType>/<maml:description>` элемента.

Начиная с PowerShell 3,0, `Get-Help` командлет отображает содержимое `<maml:uri>` элемента.
Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.

В следующем коде XML показан `<maml:inputTypes>` узел.

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

В следующем коде XML показан пример использования `<maml:inputTypes>` узла для документирования типа входных данных.

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name>System.DateTime</maml:name>
      <maml:uri>https://docs.microsoft.com/dotnet/api/system.datetime</maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
