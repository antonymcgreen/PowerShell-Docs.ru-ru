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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="b4f1b-102">Как добавить связанные ссылки в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="b4f1b-102">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="b4f1b-103">В этом разделе описывается, как добавить ссылки на другое содержимое, связанное с разделом справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4f1b-103">This section describes how to add references to other content that is related to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="b4f1b-104">Так как эти ссылки отображаются в окне командной строки, они не связываются непосредственно с содержимым, на которое указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="b4f1b-104">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="b4f1b-105">В разделах справки по командлетам, которые включены в PowerShell, эти ссылки ссылаются на другие командлеты, концептуальное содержимое ( `about_` ) и другие документы и файлы справки, не связанные с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4f1b-105">In the cmdlet Help topics that are included in PowerShell, these links reference other cmdlets, conceptual content (`about_`), and other documents and Help files that are not related to PowerShell.</span></span>

<span data-ttu-id="b4f1b-106">В следующем коде XML показано, как добавить узел **релатедлинкс** , содержащий две ссылки на связанные разделы.</span><span class="sxs-lookup"><span data-stu-id="b4f1b-106">The following XML shows how to add a **RelatedLinks** node that contains two references to related topics.</span></span>

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
