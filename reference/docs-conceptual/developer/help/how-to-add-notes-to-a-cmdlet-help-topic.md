---
ms.date: 10/20/2020
ms.topic: reference
title: Как добавить примечания в раздел справки для командлета
description: Как добавить примечания в раздел справки для командлета
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659572"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="8a380-103">Как добавить примечания в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="8a380-103">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="8a380-104">В этом разделе показано, как добавить раздел примечаний (**NOTES**) в раздел справки по командлету PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a380-104">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="8a380-105">Раздел **NOTES** используется для предоставления сведений, которые не включаются в другие структурированные разделы, например более подробного описания параметра.</span><span class="sxs-lookup"><span data-stu-id="8a380-105">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="8a380-106">Это содержимое может содержать комментарии о том, как командлет работает с конкретным поставщиком, некоторыми уникальные, но важные способы использования командлета, а также способы избежать возможных ошибок.</span><span class="sxs-lookup"><span data-stu-id="8a380-106">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="8a380-107">Раздел **NOTES** определяется с помощью одного узла `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="8a380-107">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="8a380-108">Количество примечаний, которые можно добавить в этот раздел, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="8a380-108">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="8a380-109">Для каждого примечания добавьте пару тегов `<maml:alert>` в узел `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="8a380-109">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="8a380-110">Содержимое каждого примечания добавляется в набор тегов `<maml:para>`.</span><span class="sxs-lookup"><span data-stu-id="8a380-110">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="8a380-111">Используйте пустые теги `<maml:para>` для пробелов.</span><span class="sxs-lookup"><span data-stu-id="8a380-111">Use blank `<maml:para>` tags for spacing.</span></span>

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```
