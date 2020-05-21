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
ms.openlocfilehash: 1a365a167c245006bb882a542aedb5c43cfc4c96
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557113"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Как добавить примечания в раздел справки для командлета

В этом разделе описано, как добавить раздел "Примечания" в раздел справки по командлету® Windows PowerShell. В разделе Notes содержатся сведения, которые не помещаются в другие структурированные разделы, например более подробное описание параметра. Это содержимое может содержать комментарии о том, как командлет работает с конкретным поставщиком, некоторыми уникальными, но важными, использованием командлета или способами избежать возможных ошибок.

Количество примечаний, которые можно добавить в раздел примечаний, не ограничено. Для каждой заметки добавьте пару \< тегов MAML: alert> в \< узел MAML: alerting>. Содержимое каждой заметки добавляется в набор \< тегов MAML: para>. Используйте пустой \< MAML: para> теги для интервала.

В приведенном ниже коде XML показан \< узел MAML: alerting> с двумя заметками. Обратите внимание, что каждая заметка содержит необязательный \< тег MAML: title> (заголовки можно использовать для группирования любого набора \< MAML: Alert> Tags), и каждая заметка содержит пустую строку после содержимого для пробелов.

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
