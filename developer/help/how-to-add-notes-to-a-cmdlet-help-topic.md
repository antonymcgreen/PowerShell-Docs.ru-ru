---
title: Добавление заметки для раздела справки командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862270"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="ec9d2-102">Как добавить примечания в раздел справки для командлета</span><span class="sxs-lookup"><span data-stu-id="ec9d2-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="ec9d2-103">В этом разделе описывается добавление разделе "Примечания" раздела справки командлета Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-103">This section describes how to add a Notes section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="ec9d2-104">В разделе "Примечания" используется для сведения, которые не укладывающиеся в других структурированных подразделах, таких как более подробное описание параметра.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-104">The Notes section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="ec9d2-105">Это содержимое может включать комментарии в как командлет работает с конкретного поставщика, некоторые уникальный, но важно, примеры использования командлета, то есть способы избежания возможные ошибки.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="ec9d2-106">Отсутствуют ограничения на число примечания, которые добавляются в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="ec9d2-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="ec9d2-107">Для каждого класса note, добавьте пару \<maml:alert > теги \<maml:alertset > узла.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-107">For each note, add a pair of \<maml:alert> tags to the \<maml:alertset> node.</span></span> <span data-ttu-id="ec9d2-108">Содержание каждого класса note добавляется в набор \<MAML: para > теги.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-108">The content of each note is added within a set of \<maml:para> tags.</span></span> <span data-ttu-id="ec9d2-109">Используйте пустой \<MAML: para > теги для интервала.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-109">Use blank \<maml:para> tags for spacing.</span></span>

<span data-ttu-id="ec9d2-110">Следующий код XML показывает \<maml:alertset > узла с двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-110">The following XML shows an \<maml:alertset> node with two notes.</span></span> <span data-ttu-id="ec9d2-111">Обратите внимание на то, что каждое Примечание имеет необязательный \<MAML: title > тег (заголовки можно использовать для группирования любой набор \<maml:alert > теги), и что каждое Примечание имеет пустую строку после содержимого для интервала.</span><span class="sxs-lookup"><span data-stu-id="ec9d2-111">Notice that each note has an optional \<maml:title> tag (titles can be used to group any set of \<maml:alert> tags), and that each note has a blank line following the content for spacing.</span></span>

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



