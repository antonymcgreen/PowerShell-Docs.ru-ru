---
ms.date: 09/12/2016
ms.topic: reference
title: Как добавить связанные ссылки в раздел справки для командлета
description: Как добавить связанные ссылки в раздел справки для командлета
ms.openlocfilehash: 7f1baefea69310bdf835c52461f8d3f49c4d94e8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662001"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>Как добавить связанные ссылки в раздел справки для командлета

В этом разделе описывается, как добавить ссылки на другое содержимое, связанное с разделом справки по командлетам PowerShell. Так как эти ссылки отображаются в окне командной строки, они не связываются непосредственно с содержимым, на которое указывает ссылка.

В разделах справки по командлетам, которые включены в PowerShell, эти ссылки ссылаются на другие командлеты, концептуальное содержимое ( `about_` ) и другие документы и файлы справки, не связанные с PowerShell.

В следующем коде XML показано, как добавить узел **релатедлинкс** , содержащий две ссылки на связанные разделы.

```xml
<maml:relatedLinks>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
</ maml:relatedLinks >
```
