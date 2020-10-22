---
title: Как добавить примечания в раздел справки для командлета
ms.date: 10/20/2020
ms.openlocfilehash: 7f8be34a82de2c12cfd2a05deed139ddb30da95f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92298309"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="4b15b-102">Как добавить примечания в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="4b15b-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="4b15b-103">В этом разделе показано, как добавить раздел примечаний (**NOTES**) в раздел справки по командлету PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b15b-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="4b15b-104">Раздел **NOTES** используется для предоставления сведений, которые не включаются в другие структурированные разделы, например более подробного описания параметра.</span><span class="sxs-lookup"><span data-stu-id="4b15b-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="4b15b-105">Это содержимое может содержать комментарии о том, как командлет работает с конкретным поставщиком, некоторыми уникальные, но важные способы использования командлета, а также способы избежать возможных ошибок.</span><span class="sxs-lookup"><span data-stu-id="4b15b-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="4b15b-106">Раздел **NOTES** определяется с помощью одного узла `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="4b15b-106">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="4b15b-107">Количество примечаний, которые можно добавить в этот раздел, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="4b15b-107">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="4b15b-108">Для каждого примечания добавьте пару тегов `<maml:alert>` в узел `<maml:alertset>`.</span><span class="sxs-lookup"><span data-stu-id="4b15b-108">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="4b15b-109">Содержимое каждого примечания добавляется в набор тегов `<maml:para>`.</span><span class="sxs-lookup"><span data-stu-id="4b15b-109">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="4b15b-110">Используйте пустые теги `<maml:para>` для пробелов.</span><span class="sxs-lookup"><span data-stu-id="4b15b-110">Use blank `<maml:para>` tags for spacing.</span></span>

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
