---
title: Рассмотрение сообщений о проблемах
description: Эта статья описывает работу с проблемами в команде специалистов по PowerShell-Docs.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 72267137a2657f51e5f616113adf92d80647acad
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "99601076"
---
# <a name="how-we-manage-issues"></a><span data-ttu-id="6594c-103">Рассмотрение сообщений о проблемах</span><span class="sxs-lookup"><span data-stu-id="6594c-103">How we manage issues</span></span>

<span data-ttu-id="6594c-104">В этой статье описывается, как мы управляем проблемами в репозитории PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="6594c-104">This article documents how we manage issues in the PowerShell-Docs repo.</span></span> <span data-ttu-id="6594c-105">Изначально это памятка для участников команды PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="6594c-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="6594c-106">Он опубликован здесь, чтобы обеспечить прозрачность процесса для наших общедоступных участников.</span><span class="sxs-lookup"><span data-stu-id="6594c-106">It's published here to provide process transparency for our public contributors.</span></span>

## <a name="sources-of-issues"></a><span data-ttu-id="6594c-107">Источники проблем</span><span class="sxs-lookup"><span data-stu-id="6594c-107">Sources of issues</span></span>

- <span data-ttu-id="6594c-108">Участники из сообщества</span><span class="sxs-lookup"><span data-stu-id="6594c-108">Community contributors</span></span>
- <span data-ttu-id="6594c-109">Внутренние участники</span><span class="sxs-lookup"><span data-stu-id="6594c-109">Internal contributors</span></span>
- <span data-ttu-id="6594c-110">Расшифровка комментариев из каналов социальных сетей</span><span class="sxs-lookup"><span data-stu-id="6594c-110">Transcriptions of comments from social media channels</span></span>
- <span data-ttu-id="6594c-111">Комментарии, полученные через форму отзыва в документации</span><span class="sxs-lookup"><span data-stu-id="6594c-111">Feedback via the Docs feedback form</span></span>

## <a name="response-time-targets"></a><span data-ttu-id="6594c-112">Целевые показатели времени отклика</span><span class="sxs-lookup"><span data-stu-id="6594c-112">Response time targets</span></span>

<span data-ttu-id="6594c-113">80% новых проблем закрываются в течение 3 рабочих дней.</span><span class="sxs-lookup"><span data-stu-id="6594c-113">80% of new issues are closed within 3 business days.</span></span>

- <span data-ttu-id="6594c-114">Рассмотрено — 1 рабочие дни</span><span class="sxs-lookup"><span data-stu-id="6594c-114">Triaged - 1 business days</span></span>
- <span data-ttu-id="6594c-115">Исправление или изменение — 10 рабочих дней</span><span class="sxs-lookup"><span data-stu-id="6594c-115">Fix or change - 10 business days</span></span>

### <a name="labeling--milestones"></a><span data-ttu-id="6594c-116">Метки и вехи</span><span class="sxs-lookup"><span data-stu-id="6594c-116">Labeling & Milestones</span></span>

#### <a name="label-types"></a><span data-ttu-id="6594c-117">Типы меток</span><span class="sxs-lookup"><span data-stu-id="6594c-117">Label Types</span></span>

|   <span data-ttu-id="6594c-118">Тип</span><span class="sxs-lookup"><span data-stu-id="6594c-118">Type</span></span>   | <span data-ttu-id="6594c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6594c-119">Description</span></span>                                                         |
| -------- | ------------------------------------------------------------------- |
| <span data-ttu-id="6594c-120">Область</span><span class="sxs-lookup"><span data-stu-id="6594c-120">Area</span></span>     | <span data-ttu-id="6594c-121">Используется для указания того, к какой части PowerShell или документации относится проблема.</span><span class="sxs-lookup"><span data-stu-id="6594c-121">Used to indicate what part of PowerShell or the docs that the issue is discussing.</span></span><br><span data-ttu-id="6594c-122">Позволяет разработчикам функций легко находить проблемы, связанные с их функциями.</span><span class="sxs-lookup"><span data-stu-id="6594c-122">Useful for feature owners to find issues for their feature.</span></span> |
| <span data-ttu-id="6594c-123">Проблема</span><span class="sxs-lookup"><span data-stu-id="6594c-123">Issue</span></span>    | <span data-ttu-id="6594c-124">Указывает тип проблемы</span><span class="sxs-lookup"><span data-stu-id="6594c-124">Indicates the type of issue</span></span>                                         |
| <span data-ttu-id="6594c-125">Приоритет</span><span class="sxs-lookup"><span data-stu-id="6594c-125">Priority</span></span> | <span data-ttu-id="6594c-126">Указывает приоритет проблемы.</span><span class="sxs-lookup"><span data-stu-id="6594c-126">Indicates the priority of the issue.</span></span> <span data-ttu-id="6594c-127">Диапазон значений 0 (высокий) — 4 (низкий)</span><span class="sxs-lookup"><span data-stu-id="6594c-127">Value range 0 (high) -4 (low)</span></span>  |
| <span data-ttu-id="6594c-128">Состояние</span><span class="sxs-lookup"><span data-stu-id="6594c-128">Status</span></span>   | <span data-ttu-id="6594c-129">Указывает состояние рабочего элемента или причины его закрытия</span><span class="sxs-lookup"><span data-stu-id="6594c-129">Indicates the status of the work item or why it was closed</span></span>          |
| <span data-ttu-id="6594c-130">Тег</span><span class="sxs-lookup"><span data-stu-id="6594c-130">Tag</span></span>      | <span data-ttu-id="6594c-131">Метки, используемые для дополнительной классификации</span><span class="sxs-lookup"><span data-stu-id="6594c-131">Labels used to for additional classification</span></span>                        |
| <span data-ttu-id="6594c-132">Ожидание</span><span class="sxs-lookup"><span data-stu-id="6594c-132">Waiting</span></span>  | <span data-ttu-id="6594c-133">Указывает, что мы ожидаем какого-либо другого события</span><span class="sxs-lookup"><span data-stu-id="6594c-133">Indicates that we're waiting on someone or some other event</span></span>         |

#### <a name="milestones"></a><span data-ttu-id="6594c-134">Вехи</span><span class="sxs-lookup"><span data-stu-id="6594c-134">Milestones</span></span>

<span data-ttu-id="6594c-135">Проблемы и запросы на вытягивание должны помечаться соответствующими вехами.</span><span class="sxs-lookup"><span data-stu-id="6594c-135">Issues and PRs should be tagged with the appropriate milestone.</span></span> <span data-ttu-id="6594c-136">Если проблема не относится к определенной версии, то веха не используется.</span><span class="sxs-lookup"><span data-stu-id="6594c-136">If the issue doesn't apply to a specific version, then no milestone is used.</span></span> <span data-ttu-id="6594c-137">Вытягивание и связанные с ним проблемы с изменениями, которые еще необходимо объединить в базу кода PowerShell, должны быть назначены **будущей** вехе.</span><span class="sxs-lookup"><span data-stu-id="6594c-137">PRs and related issues for changes that have yet to be merged into the PowerShell code base should be assigned to the **Future** milestone.</span></span> <span data-ttu-id="6594c-138">После слияния изменения кода измените веху на соответствующую версию.</span><span class="sxs-lookup"><span data-stu-id="6594c-138">After the code change has been merged, change the milestone to the appropriate version.</span></span>

|    <span data-ttu-id="6594c-139">Веха</span><span class="sxs-lookup"><span data-stu-id="6594c-139">Milestone</span></span>     |                    <span data-ttu-id="6594c-140">Описание</span><span class="sxs-lookup"><span data-stu-id="6594c-140">Description</span></span>                     |
| ---------------- | -------------------------------------------------- |
| <span data-ttu-id="6594c-141">7.0.0</span><span class="sxs-lookup"><span data-stu-id="6594c-141">7.0.0</span></span>            | <span data-ttu-id="6594c-142">Рабочие элементы, связанные с PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="6594c-142">Work items related to PowerShell 7.0</span></span>               |
| <span data-ttu-id="6594c-143">7.1.0</span><span class="sxs-lookup"><span data-stu-id="6594c-143">7.1.0</span></span>            | <span data-ttu-id="6594c-144">Рабочие элементы, связанные с PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="6594c-144">Work items related to PowerShell 7.1</span></span>               |
| <span data-ttu-id="6594c-145">7.2.0</span><span class="sxs-lookup"><span data-stu-id="6594c-145">7.2.0</span></span>            | <span data-ttu-id="6594c-146">Рабочие элементы, связанные с PowerShell 7,2</span><span class="sxs-lookup"><span data-stu-id="6594c-146">Work items related to PowerShell 7.2</span></span>               |
| <span data-ttu-id="6594c-147">Планируется реализация.</span><span class="sxs-lookup"><span data-stu-id="6594c-147">Future</span></span>           | <span data-ttu-id="6594c-148">Рабочие элементы, связанные с будущей версией PowerShell</span><span class="sxs-lookup"><span data-stu-id="6594c-148">Work items a future version of PowerShell</span></span>          |

## <a name="triage-process"></a><span data-ttu-id="6594c-149">Процесс рассмотрения</span><span class="sxs-lookup"><span data-stu-id="6594c-149">Triage process</span></span>

<span data-ttu-id="6594c-150">Участники группы документации PowerShell могут просматривать проблемы ежедневно и рассматривать новые проблемы по мере их поступления.</span><span class="sxs-lookup"><span data-stu-id="6594c-150">PowerShell docs team members review the issues daily and triage new issues as they arrive.</span></span> <span data-ttu-id="6594c-151">Команда отвечает еженедельно, чтобы обсудить проблемы, которые требуют рассмотрения или остаются нерешенными.</span><span class="sxs-lookup"><span data-stu-id="6594c-151">The team meets weekly to discuss issues that need triage or remain unresolved.</span></span>

### <a name="misplaced-product-feedback"></a><span data-ttu-id="6594c-152">Ошибочно адресованный отзыв о продукте</span><span class="sxs-lookup"><span data-stu-id="6594c-152">Misplaced product feedback</span></span>

- <span data-ttu-id="6594c-153">Введите комментарий, перенаправляющий клиента на правильный канал обратной связи.</span><span class="sxs-lookup"><span data-stu-id="6594c-153">Enter a comment redirecting the customer to the correct feedback channel.</span></span>
- <span data-ttu-id="6594c-154">Необязательное действие: Скопируйте проблему в соответствующий канал обратной связи, добавьте ссылку на скопированный элемент и закройте проблему.</span><span class="sxs-lookup"><span data-stu-id="6594c-154">Optional: Copy the issue to the appropriate product feedback location, add a link to the copied item, and close the issue.</span></span> <span data-ttu-id="6594c-155">НЕ копируйте проблемы в UserVoice.</span><span class="sxs-lookup"><span data-stu-id="6594c-155">DO NOT copy issues to UserVoice.</span></span>

  <span data-ttu-id="6594c-156">По умолчанию для проблем с PowerShell используется расположение [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose) .</span><span class="sxs-lookup"><span data-stu-id="6594c-156">The default location for PowerShell issues is [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

  <span data-ttu-id="6594c-157">Следующие предметные области имеют различные расположения для проблем:</span><span class="sxs-lookup"><span data-stu-id="6594c-157">The following subject areas have different locations for issues:</span></span>

  | <span data-ttu-id="6594c-158">Субъекты</span><span class="sxs-lookup"><span data-stu-id="6594c-158">Subjects</span></span> |                                                     <span data-ttu-id="6594c-159">URL-адрес для отзыва о продукте</span><span class="sxs-lookup"><span data-stu-id="6594c-159">Product Feedback URL</span></span>                                                     |
  | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
  | <span data-ttu-id="6594c-160">DSC</span><span class="sxs-lookup"><span data-stu-id="6594c-160">dsc</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |
  | <span data-ttu-id="6594c-161">gallery</span><span class="sxs-lookup"><span data-stu-id="6594c-161">gallery</span></span>  | [https://github.com/powershell/powershellgallery/issues/new](https://github.com/powershell/powershellgallery/issues/new)     |
  | <span data-ttu-id="6594c-162">jea</span><span class="sxs-lookup"><span data-stu-id="6594c-162">jea</span></span>      | [https://github.com/powershell/jea/issues/new](https://github.com/powershell/jea/issues/new)                                 |
  | <span data-ttu-id="6594c-163">wmf</span><span class="sxs-lookup"><span data-stu-id="6594c-163">wmf</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |

### <a name="support-requests"></a><span data-ttu-id="6594c-164">Запросы в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="6594c-164">Support requests</span></span>

- <span data-ttu-id="6594c-165">Если вопрос в службу поддержки прост, ответьте на него и закройте проблему.</span><span class="sxs-lookup"><span data-stu-id="6594c-165">If the support question is simple, answer it politely and close the issue.</span></span>
- <span data-ttu-id="6594c-166">Если вопрос сложный или отправитель задает дополнительные вопросы, перенаправьте его на форумы и в каналы поддержки.</span><span class="sxs-lookup"><span data-stu-id="6594c-166">If the question is more complicated, or the submitter replies with more questions, redirect them to forums and support channels.</span></span> <span data-ttu-id="6594c-167">Вариант текста для перенаправления на форумы:</span><span class="sxs-lookup"><span data-stu-id="6594c-167">Suggested text for redirecting to forums:</span></span>

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a><span data-ttu-id="6594c-168">Нарушение кодекса поведения</span><span class="sxs-lookup"><span data-stu-id="6594c-168">Code of conduct violations</span></span>

- <span data-ttu-id="6594c-169">При необходимости отредактируйте проблему, чтобы удалить оскорбительное содержимое.</span><span class="sxs-lookup"><span data-stu-id="6594c-169">Edit the issue to remove any offensive content, if necessary.</span></span>
- <span data-ttu-id="6594c-170">Введите комментарий о том, что проблема является спамом, закройте проблему и заблокируйте ее, чтобы запретить добавление комментариев.</span><span class="sxs-lookup"><span data-stu-id="6594c-170">Enter a comment indicating the issue is spam, close the issue, and then lock it to prevent further comments.</span></span>
- <span data-ttu-id="6594c-171">Каждое нарушение следует обсудить при еженедельном рассмотрении, чтобы определить потребность в дальнейших действиях (отчет для GitHub или Microsoft Legal).</span><span class="sxs-lookup"><span data-stu-id="6594c-171">Each violation should be discussed in the weekly triage to determine the need for further action (report to GitHub or Microsoft Legal).</span></span>
