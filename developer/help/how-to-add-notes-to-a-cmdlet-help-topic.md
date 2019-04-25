---
title: Добавление заметки для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083422"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Как добавить примечания в раздел справки для командлета

В этом разделе описывается добавление разделе "Примечания" раздела справки командлета Windows PowerShell®. В разделе "Примечания" используется для сведения, которые не укладывающиеся в других структурированных подразделах, таких как более подробное описание параметра. Это содержимое может включать комментарии в как командлет работает с конкретного поставщика, некоторые уникальный, но важно, примеры использования командлета, то есть способы избежания возможные ошибки.

Отсутствуют ограничения на число примечания, которые добавляются в разделе "Примечания". Для каждого класса note, добавьте пару \<maml:alert > теги \<maml:alertset > узла. Содержание каждого класса note добавляется в набор \<MAML: para > теги. Используйте пустой \<MAML: para > теги для интервала.

Следующий код XML показывает \<maml:alertset > узла с двумя узлами. Обратите внимание на то, что каждое Примечание имеет необязательный \<MAML: title > тег (заголовки можно использовать для группирования любой набор \<maml:alert > теги), и что каждое Примечание имеет пустую строку после содержимого для интервала.

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



