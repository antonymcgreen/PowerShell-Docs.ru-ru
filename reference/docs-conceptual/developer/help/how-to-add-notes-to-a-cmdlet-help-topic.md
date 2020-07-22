---
title: Как добавить примечания в раздел справки для командлета
ms.date: 09/12/2016
ms.openlocfilehash: d3679126ea34d7e86bcda700d0d050d8312a7aa2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893413"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="a1f21-102">Как добавить примечания в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="a1f21-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="a1f21-103">В этом разделе описывается добавление раздела **примечаний** в раздел справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1f21-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="a1f21-104">В разделе **Notes** содержатся сведения, которые не помещаются в другие структурированные разделы, например более подробное описание параметра.</span><span class="sxs-lookup"><span data-stu-id="a1f21-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="a1f21-105">Это содержимое может содержать комментарии о том, как командлет работает с конкретным поставщиком, некоторыми уникальными, но важными, использованием командлета или способами избежать возможных ошибок.</span><span class="sxs-lookup"><span data-stu-id="a1f21-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="a1f21-106">Количество примечаний, которые можно добавить в раздел примечаний, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="a1f21-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="a1f21-107">Для каждой заметки добавьте пару `<maml:alert>` тегов в `<maml:alertset>` узел.</span><span class="sxs-lookup"><span data-stu-id="a1f21-107">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="a1f21-108">Содержимое каждой заметки добавляется в набор `<maml:para>` тегов.</span><span class="sxs-lookup"><span data-stu-id="a1f21-108">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="a1f21-109">Используйте пустые `<maml:para>` теги для пробелов.</span><span class="sxs-lookup"><span data-stu-id="a1f21-109">Use blank `<maml:para>` tags for spacing.</span></span>

<span data-ttu-id="a1f21-110">В следующем коде XML показан `<maml:alertset>` узел с двумя заметками.</span><span class="sxs-lookup"><span data-stu-id="a1f21-110">The following XML shows an `<maml:alertset>` node with two notes.</span></span> <span data-ttu-id="a1f21-111">Обратите внимание, что каждая заметка имеет необязательный `<maml:title>` тег (заголовки можно использовать для группирования любого набора `<maml:alert>` тегов), и каждая заметка содержит пустую строку, следующую за содержимым для пробелов.</span><span class="sxs-lookup"><span data-stu-id="a1f21-111">Notice that each note has an optional `<maml:title>` tag (titles can be used to group any set of `<maml:alert>` tags), and that each note has a blank line following the content for spacing.</span></span>

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
