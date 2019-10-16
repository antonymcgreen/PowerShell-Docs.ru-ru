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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>Как добавить связанные ссылки в раздел справки для командлета

В этом разделе описывается, как добавить ссылки на другое содержимое, связанное с разделом справки по командлету Windows PowerShell®. Так как эти ссылки отображаются в окне командной строки, они не связываются непосредственно с содержимым, на которое указывает ссылка.

В разделах справки по командлетам, которые включены в® Windows PowerShell, эти ссылки ссылаются на другие командлеты, концептуальное содержимое ("about_") и другие документы и файлы справки, не связанные с Windows PowerShell®.

В следующем коде XML показано, как добавить узел Релатедлинкс, содержащий две ссылки на связанные разделы.

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



