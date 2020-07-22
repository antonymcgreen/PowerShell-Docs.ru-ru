---
title: Как добавить связанные ссылки в раздел справки для командлета
ms.date: 09/12/2016
ms.openlocfilehash: 7557b3856d8470434070dd286cd7e30c9ba015c5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893379"
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
