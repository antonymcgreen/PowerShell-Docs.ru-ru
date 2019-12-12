---
title: Добавление заметок в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361273"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Как добавить примечания в раздел справки для командлета

В этом разделе описано, как добавить раздел "Примечания" в раздел справки по командлету® Windows PowerShell. В разделе Notes содержатся сведения, которые не помещаются в другие структурированные разделы, например более подробное описание параметра. Это содержимое может содержать комментарии о том, как командлет работает с конкретным поставщиком, некоторыми уникальными, но важными, использованием командлета или способами избежать возможных ошибок.

Количество примечаний, которые можно добавить в раздел примечаний, не ограничено. Для каждой заметки добавьте пару тегов \<MAML: Alert > в узел \<MAML: Alert >. Содержимое каждой заметки добавляется в набор тегов \<MAML: para >. Используйте пустой \<MAML: para > Теги для интервала.

В следующем XML-коде показан \<MAML: Alerting > node с двумя заметками. Обратите внимание, что каждая заметка содержит необязательный тег \<MAML: Title > (заголовки можно использовать для группирования любого набора \<MAML: Alert >), и каждая заметка содержит пустую строку после содержимого для пробелов.

```xml
<maml:alertSet>
  <maml:title>title for Note 1</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
  <maml:title>title for Note 2</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
</maml:alertSet>
```



