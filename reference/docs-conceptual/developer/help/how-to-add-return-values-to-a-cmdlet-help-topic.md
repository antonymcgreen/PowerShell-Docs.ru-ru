---
title: Добавление возвращаемых значений в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52ab737-753c-4d04-8af7-758d5c805e18
caps.latest.revision: 7
ms.openlocfilehash: b21811e5a5a819c3d5c4a55fcbe685a84819b71d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367803"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>Как добавить возвращаемые значения в раздел справки для командлета

В этом разделе описывается добавление раздела OUTPUTs в раздел справки Windows PowerShell®. В разделе OUTPUTs перечислены классы .NET объектов, которые командлет возвращает или передает по конвейеру.

Количество классов, которые можно добавить в раздел OUTPUTs, не ограничено. Типы возвращаемых данных командлета заключаются в \<команду: Ретурнвалуес > node с каждым классом, заключенным в \<ную команду: returnValue > элемент.

Если командлет не создает никаких выходных данных, используйте этот раздел, чтобы указать, что выходные данные отсутствуют. Например, вместо имени класса напишите «None» и укажите краткое объяснение. Если командлет создает выходные условия, используйте этот узел для объяснения условий и описания условного вывода.

Схема включает в себя два \<MAML: Description > элементов в каждой команде \<: returnValue > элемент. Однако командлет `Get-Help` отображает только содержимое команды \<: returnValue >/\<MAML: Description > элемент.

Начиная с Windows PowerShell 3,0, командлет `Get-Help` отображает содержимое элемента > \<MAML: URI. Этот элемент позволяет направить пользователей в разделы, описывающие класс .NET.

В следующем коде XML показан узел \<MAML: Ретурнвалуес >.

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

В следующем коде XML показан пример использования узла \<MAML: Ретурнвалуес > для документирования типа выходных данных.

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



