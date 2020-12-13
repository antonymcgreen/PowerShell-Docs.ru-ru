---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить возвращаемые значения в раздел справки для командлета
description: Как добавить возвращаемые значения в раздел справки для командлета
ms.openlocfilehash: 8c556821a257451a320916231cb20fc82e75ebb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "94389748"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>Как добавить возвращаемые значения в раздел справки для командлета

В этом разделе описывается добавление раздела OUTPUTs в раздел справки по командлетам PowerShell. В разделе **Outputs** перечислены классы .NET объектов, которые командлет возвращает или передает по конвейеру.

Количество классов, которые можно добавить в раздел **Outputs** , не ограничено. Типы возвращаемых данных командлета заключаются в `<command:returnValues>` узел с каждым классом, заключенным в `<command:returnValue>` элемент.

Если командлет не создает никаких выходных данных, используйте этот раздел, чтобы указать, что выходные данные отсутствуют. Например, вместо имени класса напишите **None** и укажите краткое объяснение. Если командлет создает выходные условия, используйте этот узел для объяснения условий и описания условного вывода.

Схема включает в себя два `<maml:description>` элемента в каждом `<command:returnValue>` элементе.
Однако `Get-Help` командлет отображает только содержимое `<command:returnValue>/<maml:description>` элемента.

Начиная с PowerShell 3,0, `Get-Help` командлет отображает содержимое `<maml:uri>` элемента.
Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.

В следующем коде XML показан `<maml:returnValues>` узел.

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

В следующем коде XML показан пример использования `<maml:returnValues>` узла для документирования типа выходных данных.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://docs.microsoft.com/dotnet/api/system.datetime </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
