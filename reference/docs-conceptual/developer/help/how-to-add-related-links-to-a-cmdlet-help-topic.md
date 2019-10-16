---
title: Добавление связанных ссылок в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5aadb730-4eb7-4936-b8df-3b0c0ca04fd5
caps.latest.revision: 5
ms.openlocfilehash: aa46cbc5bfcfdfec9fcf9d2581ff641baa532860
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361223"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="2c3be-102">Как добавить связанные ссылки в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="2c3be-102">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="2c3be-103">В этом разделе описывается, как добавить ссылки на другое содержимое, связанное с разделом справки по командлету Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="2c3be-103">This section describes how to add references to other content that is related to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="2c3be-104">Так как эти ссылки отображаются в окне командной строки, они не связываются непосредственно с содержимым, на которое указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="2c3be-104">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="2c3be-105">В разделах справки по командлетам, которые включены в® Windows PowerShell, эти ссылки ссылаются на другие командлеты, концептуальное содержимое ("about_") и другие документы и файлы справки, не связанные с Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="2c3be-105">In the cmdlet Help topics that are included in Windows PowerShell®, these links reference other cmdlets, conceptual content ("about_"), and other documents and Help files that are not related to Windows PowerShell®.</span></span>

<span data-ttu-id="2c3be-106">В следующем коде XML показано, как добавить узел Релатедлинкс, содержащий две ссылки на связанные разделы.</span><span class="sxs-lookup"><span data-stu-id="2c3be-106">The following XML shows how to add a RelatedLinks node that contains two references to related topics.</span></span>

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



