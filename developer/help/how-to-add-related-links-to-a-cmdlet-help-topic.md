---
title: Добавление ссылки по теме раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5aadb730-4eb7-4936-b8df-3b0c0ca04fd5
caps.latest.revision: 5
ms.openlocfilehash: aa46cbc5bfcfdfec9fcf9d2581ff641baa532860
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083354"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="b0395-102">Как добавить связанные ссылки в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="b0395-102">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="b0395-103">В этом разделе описывается добавление ссылки на другие материалы, связанные с Windows PowerShell® раздела справки командлета.</span><span class="sxs-lookup"><span data-stu-id="b0395-103">This section describes how to add references to other content that is related to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="b0395-104">Поскольку эти ссылки отображаются в окне командной строки, они не создавать связь непосредственно к содержимому, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="b0395-104">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="b0395-105">В разделах справки командлетов, включенных в Windows PowerShell® ссылкам, ссылаться на другие командлеты, концептуальное содержимое («about_») и другие документы и файлы справки, которые не связаны с Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="b0395-105">In the cmdlet Help topics that are included in Windows PowerShell®, these links reference other cmdlets, conceptual content ("about_"), and other documents and Help files that are not related to Windows PowerShell®.</span></span>

<span data-ttu-id="b0395-106">Следующий код XML показано, как добавить узел RelatedLinks, который содержит две ссылки на связанные разделы.</span><span class="sxs-lookup"><span data-stu-id="b0395-106">The following XML shows how to add a RelatedLinks node that contains two references to related topics.</span></span>

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



