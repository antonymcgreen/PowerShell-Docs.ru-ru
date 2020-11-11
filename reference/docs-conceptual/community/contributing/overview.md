---
title: Участие в работе над документацией по PowerShell
description: В статье приведены необходимые действия для участия в создании документации по PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 255b74a75b8412ed509f6da930eb722d54233711
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354411"
---
# <a name="contributing-to-powershell-documentation"></a><span data-ttu-id="20711-103">Участие в работе над документацией по PowerShell</span><span class="sxs-lookup"><span data-stu-id="20711-103">Contributing to PowerShell documentation</span></span>

<span data-ttu-id="20711-104">Благодарим за поддержку PowerShell!</span><span class="sxs-lookup"><span data-stu-id="20711-104">Thank you for your support of PowerShell!</span></span>

<span data-ttu-id="20711-105">Руководство для соавторов представляет собой набор статей, в которых объясняются средства и процессы, используемые для создания документации в корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="20711-105">The Contributor's Guide is a collection of articles that explain the tools and processes we use to create documentation at Microsoft.</span></span> <span data-ttu-id="20711-106">Некоторые из этих руководств содержат сведения, общие для всех наборов документации, опубликованных на сайте [docs.microsoft.com][docs].</span><span class="sxs-lookup"><span data-stu-id="20711-106">Some of these guides cover information that is common to any documentation set published to [docs.microsoft.com][docs].</span></span> <span data-ttu-id="20711-107">Некоторые руководства относятся к написанию документации по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20711-107">Some of the guides are specific to how we write documentation for PowerShell.</span></span>

<span data-ttu-id="20711-108">Общие статьи доступны в централизованном [Руководстве для соавторов][contribute].</span><span class="sxs-lookup"><span data-stu-id="20711-108">The common articles are available in our centralized [Contributor's Guide][contribute].</span></span> <span data-ttu-id="20711-109">Руководства для PowerShell доступны здесь.</span><span class="sxs-lookup"><span data-stu-id="20711-109">The PowerShell-specific guides are available here.</span></span>

## <a name="ways-to-contribute"></a><span data-ttu-id="20711-110">Варианты участия в наполнении документации</span><span class="sxs-lookup"><span data-stu-id="20711-110">Ways to contribute</span></span>

<span data-ttu-id="20711-111">Существует два способа участия в создании документации.</span><span class="sxs-lookup"><span data-stu-id="20711-111">There are two ways to contribute.</span></span> <span data-ttu-id="20711-112">Оба варианта участия являются ценными для нас.</span><span class="sxs-lookup"><span data-stu-id="20711-112">Both contributions are valuable to us.</span></span>

- <span data-ttu-id="20711-113">[Отправка сообщений о проблемах][file-an-issue] помогает нам выявлять ошибки и пробелы в нашей документации.</span><span class="sxs-lookup"><span data-stu-id="20711-113">[Filing issues][file-an-issue] helps us identify problems and gaps in our documentation.</span></span> <span data-ttu-id="20711-114">Иногда проблемы трудно устранить, при этом требуется дополнительное изучение и исследование.</span><span class="sxs-lookup"><span data-stu-id="20711-114">Sometimes the issues are difficult to resolve, requiring more investigation and research.</span></span> <span data-ttu-id="20711-115">Процесс работы над проблемой позволяет нам обсудить проблему и найти удовлетворительное решение.</span><span class="sxs-lookup"><span data-stu-id="20711-115">The issue process allows us to have a conversation about the problem and develop a satisfactory resolution.</span></span>

- <span data-ttu-id="20711-116">Отправка нового содержимого или внесение изменений в существующие статьи является более сложным процессом.</span><span class="sxs-lookup"><span data-stu-id="20711-116">Submitting new content or changes to existing articles is a more involved process.</span></span> <span data-ttu-id="20711-117">Ниже описаны средства, процессы и стандарты для отправки содержимого в документацию.</span><span class="sxs-lookup"><span data-stu-id="20711-117">The following information outlines the tools, processes, and standards for submitting content to the documentation.</span></span>

## <a name="prepare-to-make-a-contribution"></a><span data-ttu-id="20711-118">Подготовка к внесению дополнений в документацию</span><span class="sxs-lookup"><span data-stu-id="20711-118">Prepare to make a contribution</span></span>

<span data-ttu-id="20711-119">Для внесения дополнений в документацию вам потребуется учетная запись GitHub.</span><span class="sxs-lookup"><span data-stu-id="20711-119">Contributing to the documentation requires a GitHub account.</span></span> <span data-ttu-id="20711-120">Используйте следующий контрольный список, чтобы получить средства и понять процессы, используемые для внесения изменений в документацию.</span><span class="sxs-lookup"><span data-stu-id="20711-120">Use the following checklist to get the tools and understand the processes we use for making contributions.</span></span>

1. [<span data-ttu-id="20711-121">Регистрация в GitHub</span><span class="sxs-lookup"><span data-stu-id="20711-121">Sign up for GitHub</span></span>](/contribute/get-started-setup-github)
1. [<span data-ttu-id="20711-122">Установка средств Git и Markdown</span><span class="sxs-lookup"><span data-stu-id="20711-122">Install Git and Markdown tools</span></span>](/contribute/get-started-setup-tools)
1. [<span data-ttu-id="20711-123">Установка пакета создания документации</span><span class="sxs-lookup"><span data-stu-id="20711-123">Install the Docs Authoring Pack</span></span>](/contribute/how-to-write-docs-auth-pack)
1. <span data-ttu-id="20711-124">[Установка Posh-Git][posh-git] — не требуется, но рекомендуется</span><span class="sxs-lookup"><span data-stu-id="20711-124">[Install Posh-Git][posh-git] - not required but recommended</span></span>
1. [<span data-ttu-id="20711-125">Настройка локального репозитория Git</span><span class="sxs-lookup"><span data-stu-id="20711-125">Set up a local Git repository</span></span>](/contribute/get-started-setup-local)
1. [<span data-ttu-id="20711-126">Обзор основных сведений о Git и GitHub</span><span class="sxs-lookup"><span data-stu-id="20711-126">Review Git and GitHub fundamentals</span></span>](/contribute/git-github-fundamentals)

## <a name="get-started-writing-docs"></a><span data-ttu-id="20711-127">Приступая к работе с документацией</span><span class="sxs-lookup"><span data-stu-id="20711-127">Get started writing docs</span></span>

<span data-ttu-id="20711-128">Внести изменения в документацию можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="20711-128">There are two ways to contribute changes to the documentation:</span></span>

1. [<span data-ttu-id="20711-129">Быстрые изменения в существующих документах</span><span class="sxs-lookup"><span data-stu-id="20711-129">Quick edits to existing docs</span></span>](/contribute/#quick-edits-to-existing-documents)
   - <span data-ttu-id="20711-130">Небольшие исправления, исправление опечаток или небольшие дополнения</span><span class="sxs-lookup"><span data-stu-id="20711-130">Minor corrections, fixing typos, or small additions</span></span>
1. [<span data-ttu-id="20711-131">Полный рабочий процесс GitHub для документов</span><span class="sxs-lookup"><span data-stu-id="20711-131">Full GitHub workflow for docs</span></span>](/contribute/how-to-write-workflows-major)
   - <span data-ttu-id="20711-132">большие изменения, несколько версий, добавление или изменение изображений или участие в написании новых статей</span><span class="sxs-lookup"><span data-stu-id="20711-132">large changes, multiple versions, adding or changing images, or contributing new articles</span></span>

<span data-ttu-id="20711-133">Также ознакомьтесь с разделом [Важнейшие инструменты для создания документов](/contribute/style-quick-start) в централизованном Руководстве для соавторов.</span><span class="sxs-lookup"><span data-stu-id="20711-133">Also, read the [Writing essentials](/contribute/style-quick-start) section of the centralized Contributor's Guide.</span></span> <span data-ttu-id="20711-134">Другим отличным ресурсом является [руководство по стилю написания материалов Майкрософт][style-guide].</span><span class="sxs-lookup"><span data-stu-id="20711-134">Another excellent resource is the [Microsoft Writing Style Guide][style-guide].</span></span> <span data-ttu-id="20711-135">Цель руководства по стилю написания материалов Майкрософт состоит в том, чтобы помочь редакторам, техническим специалистам, разработчикам, маркетологам и другим сотрудникам в сфере ИТ добиться наилучшего качества содержимого.</span><span class="sxs-lookup"><span data-stu-id="20711-135">The goal of the Microsoft Writing Style Guide is to help editors, technical writers, developers, marketers, and anyone else in IT write better content.</span></span>

<span data-ttu-id="20711-136">Порядок внесения незначительных исправлений или уточнений в документацию и примеры кода в общедоступных репозиториях описаны в [Условиях использования][terms-of-use] сайта docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="20711-136">Minor corrections or clarifications to documentation and code examples in public repositories are covered by the docs.microsoft.com [Terms of Use][terms-of-use].</span></span>

<span data-ttu-id="20711-137">При внесении значительных изменений используйте полный рабочий процесс GitHub.</span><span class="sxs-lookup"><span data-stu-id="20711-137">Use the full GitHub workflow when you're making significant changes.</span></span> <span data-ttu-id="20711-138">Если вы не являетесь сотрудником корпорации Майкрософт, то при внесении значительных изменений создается комментарий в запросе на внесение изменений, который предлагает подтвердить принятие [Соглашения о лицензировании участия (CLA)][cla] в Интернете.</span><span class="sxs-lookup"><span data-stu-id="20711-138">If you're not an employee of Microsoft, significant changes generate a comment in the pull request that asks you to submit an online [Contribution Licensing Agreement (CLA)][cla].</span></span> <span data-ttu-id="20711-139">Вам нужно заполнить онлайн-форму, после чего мы сможем проверить и принять ваш запрос на внесение изменений.</span><span class="sxs-lookup"><span data-stu-id="20711-139">We need you to complete the online form before we can review or accept your pull request.</span></span>

## <a name="code-of-conduct"></a><span data-ttu-id="20711-140">Правила поведения</span><span class="sxs-lookup"><span data-stu-id="20711-140">Code of conduct</span></span>

<span data-ttu-id="20711-141">Для всех репозиториев, используемых для публикации на сайте docs.microsoft.com, установлены [Правила поведения для управляемых Майкрософт сообществ разработки ПО с открытым исходным кодом](https://opensource.microsoft.com/codeofconduct/) и [Правила поведения для .NET Foundation](https://dotnetfoundation.org/code-of-conduct).</span><span class="sxs-lookup"><span data-stu-id="20711-141">All repositories that publish to docs.microsoft.com have adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/) or the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct).</span></span> <span data-ttu-id="20711-142">Дополнительные сведения см. в разделе [Часто задаваемые вопросы по правилам поведения](https://opensource.microsoft.com/codeofconduct/faq/).</span><span class="sxs-lookup"><span data-stu-id="20711-142">For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="20711-143">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="20711-143">Next steps</span></span>

<span data-ttu-id="20711-144">В следующих статьях рассматриваются сведения, относящиеся к документации по PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20711-144">The following articles cover information specific to PowerShell documentation.</span></span> <span data-ttu-id="20711-145">Если эти сведения перекрываются инструкциями, приведенными в Руководстве для соавторов, мы уточним, в чем заключается отличие этих правил для содержимого PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20711-145">Where there's overlap with the guidance in the centralized Contributor's Guide, we call out how those rules differ for the PowerShell content.</span></span>

<span data-ttu-id="20711-146">Ознакомьтесь со следующими документами:</span><span class="sxs-lookup"><span data-stu-id="20711-146">Review the following documents:</span></span>

- [<span data-ttu-id="20711-147">Как отправить сообщение о проблеме</span><span class="sxs-lookup"><span data-stu-id="20711-147">How to file an issue</span></span>](file-an-issue.md)
- [<span data-ttu-id="20711-148">Приступая к работе с документацией</span><span class="sxs-lookup"><span data-stu-id="20711-148">Get started writing docs</span></span>](get-started-writing.md)
- [<span data-ttu-id="20711-149">Отправка запроса на внесение изменений</span><span class="sxs-lookup"><span data-stu-id="20711-149">Submitting a pull request</span></span>](pull-requests.md)
- [<span data-ttu-id="20711-150">Руководство по стилю для документации PowerShell</span><span class="sxs-lookup"><span data-stu-id="20711-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)
- [<span data-ttu-id="20711-151">Редактирование справки по командлетам</span><span class="sxs-lookup"><span data-stu-id="20711-151">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<span data-ttu-id="20711-152">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="20711-152">Additional resources</span></span>

- [<span data-ttu-id="20711-153">Контрольный список редактора</span><span class="sxs-lookup"><span data-stu-id="20711-153">Editorial checklist</span></span>](editorial-checklist.md)
- [<span data-ttu-id="20711-154">Рассмотрение сообщений о проблемах</span><span class="sxs-lookup"><span data-stu-id="20711-154">How we manage issues</span></span>](managing-issues.md)
- [<span data-ttu-id="20711-155">Рассмотрение запросов на внесение изменений</span><span class="sxs-lookup"><span data-stu-id="20711-155">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[cla]: https://cla.microsoft.com/
[contribute]: /contribute/
[docs]: https://docs.microsoft.com/
[file-an-issue]: file-an-issue.md
[posh-git]: https://www.powershellgallery.com/packages/posh-git
[psdocs]: /powershell
[style-guide]: /style-guide/welcome/
[terms-of-use]: /legal/termsofuse
