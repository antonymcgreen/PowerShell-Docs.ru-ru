---
title: Добавление заметок в раздел справки по командлетам | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361273"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="331ea-102">Как добавить примечания в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="331ea-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="331ea-103">В этом разделе описано, как добавить раздел "Примечания" в раздел справки по командлету® Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="331ea-103">This section describes how to add a Notes section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="331ea-104">В разделе Notes содержатся сведения, которые не помещаются в другие структурированные разделы, например более подробное описание параметра.</span><span class="sxs-lookup"><span data-stu-id="331ea-104">The Notes section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="331ea-105">Это содержимое может содержать комментарии о том, как командлет работает с конкретным поставщиком, некоторыми уникальными, но важными, использованием командлета или способами избежать возможных ошибок.</span><span class="sxs-lookup"><span data-stu-id="331ea-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="331ea-106">Количество примечаний, которые можно добавить в раздел примечаний, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="331ea-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="331ea-107">Для каждой заметки добавьте пару тегов \<maml: Alert > в узел \<maml: Alert >.</span><span class="sxs-lookup"><span data-stu-id="331ea-107">For each note, add a pair of \<maml:alert> tags to the \<maml:alertset> node.</span></span> <span data-ttu-id="331ea-108">Содержимое каждой заметки добавляется в набор тегов \<maml: para >.</span><span class="sxs-lookup"><span data-stu-id="331ea-108">The content of each note is added within a set of \<maml:para> tags.</span></span> <span data-ttu-id="331ea-109">Используйте пустой \<maml: para > Теги для интервала.</span><span class="sxs-lookup"><span data-stu-id="331ea-109">Use blank \<maml:para> tags for spacing.</span></span>

<span data-ttu-id="331ea-110">В следующем XML-коде показан узел \<maml: Alerting > с двумя заметками.</span><span class="sxs-lookup"><span data-stu-id="331ea-110">The following XML shows an \<maml:alertset> node with two notes.</span></span> <span data-ttu-id="331ea-111">Обратите внимание, что каждая заметка содержит необязательный тег \<maml: Title > (заголовки можно использовать для группирования любого набора тегов \<maml: Alert >), и каждая заметка содержит пустую строку после содержимого для пробелов.</span><span class="sxs-lookup"><span data-stu-id="331ea-111">Notice that each note has an optional \<maml:title> tag (titles can be used to group any set of \<maml:alert> tags), and that each note has a blank line following the content for spacing.</span></span>

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



