---
title: Отправка запросов на вытягивание
description: В этой статье описывается, как отправлять запросы на вытягивание в репозиторий PowerShell-Docs.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 1a21c25e19189aec4f48ad034147b02f4f804f9d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "99602693"
---
# <a name="how-to-submit-pull-requests"></a><span data-ttu-id="db02b-103">Отправка запросов на вытягивание</span><span class="sxs-lookup"><span data-stu-id="db02b-103">How to submit pull requests</span></span>

<span data-ttu-id="db02b-104">Чтобы внести изменения в содержимое, отправьте запрос на вытягивание (PR) из своей вилки.</span><span class="sxs-lookup"><span data-stu-id="db02b-104">To make changes to content, submit a pull request (PR) from your fork.</span></span> <span data-ttu-id="db02b-105">Перед слиянием запрос на вытягивание должен быть проверен.</span><span class="sxs-lookup"><span data-stu-id="db02b-105">A pull request must be reviewed before it can be merged.</span></span> <span data-ttu-id="db02b-106">Для получения наилучших результатов перед отправкой запроса изучите [контрольный список для редактора](editorial-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="db02b-106">For best results, review the [editorial checklist](editorial-checklist.md) before submitting your pull request.</span></span>

## <a name="using-git-branches"></a><span data-ttu-id="db02b-107">Использование ветвей Git</span><span class="sxs-lookup"><span data-stu-id="db02b-107">Using git branches</span></span>

<span data-ttu-id="db02b-108">Ветвь по умолчанию для PowerShell-Docs является `staging` ветвью.</span><span class="sxs-lookup"><span data-stu-id="db02b-108">The default branch for PowerShell-Docs is the `staging` branch.</span></span> <span data-ttu-id="db02b-109">Изменения, внесенные в рабочие ветви, объединяются в `staging` ветвь перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="db02b-109">Changes made in working branches are merged into the `staging` branch before then being published.</span></span> <span data-ttu-id="db02b-110">`staging`Ветвь объединяется в `live` ветвь каждый рабочий день в 3:00 PM (Тихоокеанское время).</span><span class="sxs-lookup"><span data-stu-id="db02b-110">The `staging` branch is merged into the `live` branch every weekday at 3:00 PM (Pacific Time).</span></span> <span data-ttu-id="db02b-111">`live`Ветвь содержит содержимое, опубликованное в docs.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="db02b-111">The `live` branch contains the content that is published to docs.microsoft.com.</span></span>

<span data-ttu-id="db02b-112">Перед началом внесения изменений создайте рабочую ветвь в локальной копии репозитория PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="db02b-112">Before starting any changes, create a working branch in your local copy of the PowerShell-Docs repository.</span></span> <span data-ttu-id="db02b-113">При работе в локальной среде обязательно синхронизируйте локальный репозиторий перед созданием рабочей ветви.</span><span class="sxs-lookup"><span data-stu-id="db02b-113">When working locally, be sure to synchronize your local repository before creating your working branch.</span></span> <span data-ttu-id="db02b-114">Рабочая ветвь должна быть создана из обновленной копии `staging` ветви.</span><span class="sxs-lookup"><span data-stu-id="db02b-114">The working branch should be created from an update-to-date copy of the `staging` branch.</span></span>

<span data-ttu-id="db02b-115">Все запросы на вытягивание должны направляться в ветвь `staging`.</span><span class="sxs-lookup"><span data-stu-id="db02b-115">All pull requests should target the `staging` branch.</span></span> <span data-ttu-id="db02b-116">Не отправляйте изменения в `live` ветвь.</span><span class="sxs-lookup"><span data-stu-id="db02b-116">Don't submit change to the `live` branch.</span></span>
<span data-ttu-id="db02b-117">Изменения, внесенные в ветвь `staging`, подвергаются слиянию с ветвью `live`, причем изменения в `live` перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="db02b-117">Changes made in the `staging` branch get merged into `live`, overwriting any changes made to `live`.</span></span>

## <a name="make-the-pull-request-process-work-better-for-everyone"></a><span data-ttu-id="db02b-118">Упрощение процесса обработки запроса на вытягивание для всех участников</span><span class="sxs-lookup"><span data-stu-id="db02b-118">Make the pull request process work better for everyone</span></span>

<span data-ttu-id="db02b-119">Чем проще и конкретнее будет ваш запрос на вытягивание, тем быстрее он сможет пройти проверку и слияние.</span><span class="sxs-lookup"><span data-stu-id="db02b-119">The simpler and more focused you can make your PR, the faster it can be reviewed and merged.</span></span>

### <a name="avoid-pull-requests-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a><span data-ttu-id="db02b-120">Избегайте запросов на включение внесенных изменений, которые обновляют большое количество файлов или содержат несвязанные изменения</span><span class="sxs-lookup"><span data-stu-id="db02b-120">Avoid pull requests that update large numbers of files or contain unrelated changes</span></span>

<span data-ttu-id="db02b-121">Старайтесь не создавать запросы на вытягивание с несвязанными изменениями.</span><span class="sxs-lookup"><span data-stu-id="db02b-121">Avoid creating PRs that contain unrelated changes.</span></span> <span data-ttu-id="db02b-122">Отделяйте незначительные изменения в существующих статьях от новых статей или крупных переработок.</span><span class="sxs-lookup"><span data-stu-id="db02b-122">Separate minor updates to existing articles from new articles or major rewrites.</span></span> <span data-ttu-id="db02b-123">Работайте над этими изменениями в отдельных рабочих ветвях.</span><span class="sxs-lookup"><span data-stu-id="db02b-123">Work on these changes in separate working branches.</span></span>

<span data-ttu-id="db02b-124">При массовых изменениях создаются запросы на вытягивание с большим количеством измененных файлов.</span><span class="sxs-lookup"><span data-stu-id="db02b-124">Bulk changes create PRs with large numbers of changed files.</span></span> <span data-ttu-id="db02b-125">Запросы на вытягивание должны включать не более 50 измененных файлов.</span><span class="sxs-lookup"><span data-stu-id="db02b-125">Limit your PRs to a maximum of 50 changed files.</span></span> <span data-ttu-id="db02b-126">Большие запросы трудно проверять, и они более подвержены ошибкам.</span><span class="sxs-lookup"><span data-stu-id="db02b-126">Large PRs are difficult to review and are more prone to contain errors.</span></span>

### <a name="renaming-or-deleting-files"></a><span data-ttu-id="db02b-127">Переименование или удаление файлов</span><span class="sxs-lookup"><span data-stu-id="db02b-127">Renaming or deleting files</span></span>

<span data-ttu-id="db02b-128">При переименовании или удалении файлов необходима ошибка, связанная с запросом на вытягивание.</span><span class="sxs-lookup"><span data-stu-id="db02b-128">When renaming or deleting files, there must be an issue associated with the PR.</span></span> <span data-ttu-id="db02b-129">Она должна быть посвящена переименованию или удалению файлов.</span><span class="sxs-lookup"><span data-stu-id="db02b-129">That issue must discuss the need to rename or delete the files.</span></span>

<span data-ttu-id="db02b-130">Не сочетайте дополнения или изменения содержимого с переименованием и удалением файлов в одном запросе.</span><span class="sxs-lookup"><span data-stu-id="db02b-130">Avoid mixing content additions or change with file renames and deletes.</span></span> <span data-ttu-id="db02b-131">Любой файл, который переименовывается или удаляется, должен быть добавлен в глобальный файл перенаправления.</span><span class="sxs-lookup"><span data-stu-id="db02b-131">Any file that is renamed or deleted must be added to the global redirection file.</span></span> <span data-ttu-id="db02b-132">По возможности обновите все файлы, связанные с переименованным или удаленным содержимым, включая любые файлы ОГЛАВЛЕНИя.</span><span class="sxs-lookup"><span data-stu-id="db02b-132">When possible, update any files that link to the renamed or deleted content, including any TOC files.</span></span>

## <a name="docs-pr-validation-service"></a><span data-ttu-id="db02b-133">Служба проверки запросов на вытягивание для документации</span><span class="sxs-lookup"><span data-stu-id="db02b-133">Docs PR validation service</span></span>

<span data-ttu-id="db02b-134">Служба проверки документов по запросу — это приложение GitHub, которое выполняет правила проверки изменений.</span><span class="sxs-lookup"><span data-stu-id="db02b-134">The Docs PR validation service is a GitHub app that runs validation rules on your changes.</span></span> <span data-ttu-id="db02b-135">Необходимо исправить все ошибки или предупреждения, о которых сообщает служба проверки.</span><span class="sxs-lookup"><span data-stu-id="db02b-135">You must fix any errors or warnings reported by the validation service.</span></span>

<span data-ttu-id="db02b-136">Процесс происходит описанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="db02b-136">You'll see the following behavior:</span></span>

1. <span data-ttu-id="db02b-137">Вы отправляете запрос на вытягивание.</span><span class="sxs-lookup"><span data-stu-id="db02b-137">You submit a PR.</span></span>
1. <span data-ttu-id="db02b-138">В GitHub в комментарии, в котором указывается состояние запроса на вытягивание, вы увидите состояние checks (проверки) для репозитория.</span><span class="sxs-lookup"><span data-stu-id="db02b-138">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repository.</span></span> <span data-ttu-id="db02b-139">В этом примере включены две проверки: "фиксация проверки" и "OpenPublishing. Build".</span><span class="sxs-lookup"><span data-stu-id="db02b-139">In this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![состояние проверки — некоторые проверки не пройдены](media/pull-requests/validation-failed.png)

   <span data-ttu-id="db02b-141">Сборка может завершиться успешно, даже если проверка фиксации не пройдена.</span><span class="sxs-lookup"><span data-stu-id="db02b-141">The build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="db02b-142">Чтобы получить дополнительные сведения, щелкните ссылку **Details** (Сведения).</span><span class="sxs-lookup"><span data-stu-id="db02b-142">Click **Details** for more information.</span></span>
1. <span data-ttu-id="db02b-143">На странице сведений вы увидите все проверки, которые не были пройдены, и информацию об устранении проблем.</span><span class="sxs-lookup"><span data-stu-id="db02b-143">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues.</span></span>
1. <span data-ttu-id="db02b-144">Когда проверка пройдена, к запросу на вытягивание добавляется следующий комментарий:</span><span class="sxs-lookup"><span data-stu-id="db02b-144">When validation succeeds, the following comment is added to the PR:</span></span>

   ![Состояние проверки: успешно](media/pull-requests/build-validation.png)

> [!NOTE]
> <span data-ttu-id="db02b-146">Если вы являетесь внешним участником (не сотрудником корпорации Майкрософт), у вас нет доступа к подробным отчетам о сборке или ссылкам для предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="db02b-146">If you are an external (not a Microsoft employee) contributor you do not have access to the detailed build reports or preview links.</span></span>

<span data-ttu-id="db02b-147">При проверке запроса на вытягивание может появиться запрос на внесение изменений или исправление предупреждающих сообщений.</span><span class="sxs-lookup"><span data-stu-id="db02b-147">When the PR is reviewed, you may be asked to make changes or fix validation warning messages.</span></span> <span data-ttu-id="db02b-148">Команда PowerShell-Docs может помочь в понимании ошибок проверки и редакционных требований.</span><span class="sxs-lookup"><span data-stu-id="db02b-148">The PowerShell-Docs team can help you understand validation errors and editorial requirements.</span></span>

## <a name="next-steps"></a><span data-ttu-id="db02b-149">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="db02b-149">Next steps</span></span>

[<span data-ttu-id="db02b-150">Руководство по стилю для документации PowerShell</span><span class="sxs-lookup"><span data-stu-id="db02b-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

## <a name="additional-resources"></a><span data-ttu-id="db02b-151">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="db02b-151">Additional resources</span></span>

[<span data-ttu-id="db02b-152">Рассмотрение запросов на вытягивание</span><span class="sxs-lookup"><span data-stu-id="db02b-152">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[fork]: /contribute/get-started-setup-local#fork-the-repository
