---
title: Как сообщить о проблеме с PowerShell-Docs
description: В этой статье описывается, как предоставить отзыв о документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: fa2c74d55cdcd779646c50d58f7705f7a4c33542
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060299"
---
# <a name="how-to-file-a-powershell-docs-issue"></a><span data-ttu-id="e03b3-103">Как сообщить о проблеме с PowerShell-Docs</span><span class="sxs-lookup"><span data-stu-id="e03b3-103">How to file a PowerShell-Docs issue</span></span>

<span data-ttu-id="e03b3-104">Сообщить о проблеме можно двумя способами.</span><span class="sxs-lookup"><span data-stu-id="e03b3-104">There are two ways to create an issue:</span></span>

1. <span data-ttu-id="e03b3-105">Используйте элементы управления для обратной связи в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="e03b3-105">Use the feedback controls at the bottom of the page.</span></span>
1. <span data-ttu-id="e03b3-106">Сообщите о проблеме непосредственно на GitHub.</span><span class="sxs-lookup"><span data-stu-id="e03b3-106">File an issue in GitHub directly</span></span>

## <a name="using-the-feedback-controls"></a><span data-ttu-id="e03b3-107">Элементы управления для обратной связи</span><span class="sxs-lookup"><span data-stu-id="e03b3-107">Using the feedback controls</span></span>

<span data-ttu-id="e03b3-108">Полное описание элементов управления для обратной связи см. в записи блога команды по разработке документации с объявлением о [выпуске этой функции][feedback].</span><span class="sxs-lookup"><span data-stu-id="e03b3-108">For a full description of the feedback controls, see the Docs Team blog announcing this [feature][feedback].</span></span>

<span data-ttu-id="e03b3-109">В нижней части большинства страниц на сайте `docs.microsoft.com` есть две кнопки обратной связи.</span><span class="sxs-lookup"><span data-stu-id="e03b3-109">At the bottom of most pages on `docs.microsoft.com`, you'll see two feedback buttons.</span></span> <span data-ttu-id="e03b3-110">Одна из них предназначена для отзыва о продукте, а другая — для отзыва о документации.</span><span class="sxs-lookup"><span data-stu-id="e03b3-110">One is a link for product feedback and one is for documentation feedback.</span></span> <span data-ttu-id="e03b3-111">Для отзыва о документации требуется учетная запись GitHub.</span><span class="sxs-lookup"><span data-stu-id="e03b3-111">The documentation feedback requires a GitHub account.</span></span> <span data-ttu-id="e03b3-112">При нажатии кнопки выполняется проверка подлинности в GitHub, а затем открывается простая форма для ввода отзыва.</span><span class="sxs-lookup"><span data-stu-id="e03b3-112">Clicking the button authenticates you in GitHub, then presents a simple form to enter your feedback.</span></span> <span data-ttu-id="e03b3-113">При отправке формы элемент управления обратной связи создает проблему в GitHub и связывает ее с текущей статьей.</span><span class="sxs-lookup"><span data-stu-id="e03b3-113">When you submit the form, the feedback control creates a new GitHub issue and links it to the current article.</span></span>

> [!NOTE]
> <span data-ttu-id="e03b3-114">Эта форма не является каналом поддержки.</span><span class="sxs-lookup"><span data-stu-id="e03b3-114">This is not a support channel.</span></span> <span data-ttu-id="e03b3-115">Она служит для задания уточняющих вопросов, касающихся документации, либо для сообщения об ошибках или недостающей информации.</span><span class="sxs-lookup"><span data-stu-id="e03b3-115">This is a way to ask clarifying questions about documentation or report errors and omissions.</span></span> <span data-ttu-id="e03b3-116">Если вам нужна техническая поддержка, обратитесь к [ресурсам сообщества](../community-support.md).</span><span class="sxs-lookup"><span data-stu-id="e03b3-116">If you need technical support, see [Community resources](../community-support.md).</span></span>

## <a name="filing-issues-on-github"></a><span data-ttu-id="e03b3-117">Сообщение о проблемах на GitHub</span><span class="sxs-lookup"><span data-stu-id="e03b3-117">Filing issues on GitHub</span></span>

<span data-ttu-id="e03b3-118">Чтобы сообщить о проблеме непосредственно на GitHub, можно нажать кнопку [New issue][new-issue] (Новая проблема) в репозитории [PowerShell-Docs][docs-issues].</span><span class="sxs-lookup"><span data-stu-id="e03b3-118">To file a GitHub issue directly, you can click on the [New issue][new-issue] button in the [PowerShell-Docs][docs-issues] repository.</span></span> <span data-ttu-id="e03b3-119">Нажмите кнопку **Get started** (Начать) для нужного типа проблемы.</span><span class="sxs-lookup"><span data-stu-id="e03b3-119">Click the **Get started** button for the type of issue you want to create.</span></span> <span data-ttu-id="e03b3-120">Новая проблема GitHub создается на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="e03b3-120">The new GitHub issue is prepopulated with a template.</span></span> <span data-ttu-id="e03b3-121">Шаблон помогает предоставить нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="e03b3-121">The template helps you provide the information needed to address the problem you're reporting.</span></span>

<span data-ttu-id="e03b3-122">Прежде чем сообщать о новой проблеме, просмотрите список существующих проблем, чтобы избежать повторения.</span><span class="sxs-lookup"><span data-stu-id="e03b3-122">Before you file a new issue, read through existing issues to see if your problem has already been reported.</span></span> <span data-ttu-id="e03b3-123">Возможно, о вашей проблеме уже сообщили и ответ был дан.</span><span class="sxs-lookup"><span data-stu-id="e03b3-123">This helps avoid duplication and your issue may have been answered already.</span></span> <span data-ttu-id="e03b3-124">Если вы нашли свою проблему в списке существующих, то можете добавить комментарии, задать дополнительные вопросы или дать ответы.</span><span class="sxs-lookup"><span data-stu-id="e03b3-124">If you find an existing issue, you can add your comments, related questions, or answers.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e03b3-125">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="e03b3-125">Next steps</span></span>

<span data-ttu-id="e03b3-126">См. статью [Участие в работе над документацией](get-started-writing.md).</span><span class="sxs-lookup"><span data-stu-id="e03b3-126">See [Get started writing](get-started-writing.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e03b3-127">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e03b3-127">Additional resources</span></span>

[<span data-ttu-id="e03b3-128">Рассмотрение сообщений о проблемах</span><span class="sxs-lookup"><span data-stu-id="e03b3-128">How we manage issues</span></span>](managing-issues.md)

<!-- reference links -->
[feedback]: /teamblog/a-new-feedback-system-is-coming-to-docs
[new-issue]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/new/choose
[docs-issues]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues
