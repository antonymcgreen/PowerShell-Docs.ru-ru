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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>Как добавить связанные ссылки в раздел справки для командлета

В этом разделе описывается добавление ссылки на другие материалы, связанные с Windows PowerShell® раздела справки командлета. Поскольку эти ссылки отображаются в окне командной строки, они не создавать связь непосредственно к содержимому, на которую указывает ссылка.

В разделах справки командлетов, включенных в Windows PowerShell® ссылкам, ссылаться на другие командлеты, концептуальное содержимое («about_») и другие документы и файлы справки, которые не связаны с Windows PowerShell®.

Следующий код XML показано, как добавить узел RelatedLinks, который содержит две ссылки на связанные разделы.

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



