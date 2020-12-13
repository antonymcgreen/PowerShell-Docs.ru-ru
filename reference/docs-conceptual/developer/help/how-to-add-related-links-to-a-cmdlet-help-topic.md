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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="77ef4-103">Как добавить связанные ссылки в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="77ef4-103">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="77ef4-104">В этом разделе описывается, как добавить ссылки на другое содержимое, связанное с разделом справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77ef4-104">This section describes how to add references to other content that is related to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="77ef4-105">Так как эти ссылки отображаются в окне командной строки, они не связываются непосредственно с содержимым, на которое указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="77ef4-105">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="77ef4-106">В разделах справки по командлетам, которые включены в PowerShell, эти ссылки ссылаются на другие командлеты, концептуальное содержимое ( `about_` ) и другие документы и файлы справки, не связанные с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77ef4-106">In the cmdlet Help topics that are included in PowerShell, these links reference other cmdlets, conceptual content (`about_`), and other documents and Help files that are not related to PowerShell.</span></span>

<span data-ttu-id="77ef4-107">В следующем коде XML показано, как добавить узел **релатедлинкс** , содержащий две ссылки на связанные разделы.</span><span class="sxs-lookup"><span data-stu-id="77ef4-107">The following XML shows how to add a **RelatedLinks** node that contains two references to related topics.</span></span>

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
