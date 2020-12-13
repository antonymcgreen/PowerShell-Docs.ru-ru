---
ms.date: 10/20/2020
ms.topic: reference
title: Как добавить примечания в раздел справки для командлета
description: Как добавить примечания в раздел справки для командлета
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659572"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Как добавить примечания в раздел справки для командлета

В этом разделе показано, как добавить раздел примечаний (**NOTES**) в раздел справки по командлету PowerShell. Раздел **NOTES** используется для предоставления сведений, которые не включаются в другие структурированные разделы, например более подробного описания параметра. Это содержимое может содержать комментарии о том, как командлет работает с конкретным поставщиком, некоторыми уникальные, но важные способы использования командлета, а также способы избежать возможных ошибок.

Раздел **NOTES** определяется с помощью одного узла `<maml:alertset>`. Количество примечаний, которые можно добавить в этот раздел, не ограничено. Для каждого примечания добавьте пару тегов `<maml:alert>` в узел `<maml:alertset>`. Содержимое каждого примечания добавляется в набор тегов `<maml:para>`. Используйте пустые теги `<maml:para>` для пробелов.

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```
