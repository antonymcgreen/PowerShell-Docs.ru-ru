---
title: Отправка запросов на вытягивание
description: В этой статье описывается, как отправлять запросы на вытягивание в репозиторий PowerShell-Docs.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 2600049b06da5ad4869b6ff335f00bc40c2d1c22
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "79060239"
---
# <a name="how-to-submit-pull-requests"></a><span data-ttu-id="33312-103">Отправка запросов на вытягивание</span><span class="sxs-lookup"><span data-stu-id="33312-103">How to submit pull requests</span></span>

<span data-ttu-id="33312-104">Чтобы внести изменения в содержимое, отправьте запрос на вытягивание (PR) из своей вилки.</span><span class="sxs-lookup"><span data-stu-id="33312-104">To make changes to content, submit a pull request (PR) from your fork.</span></span> <span data-ttu-id="33312-105">Перед слиянием запрос на вытягивание должен быть проверен.</span><span class="sxs-lookup"><span data-stu-id="33312-105">A pull request must be reviewed before it can merged.</span></span> <span data-ttu-id="33312-106">Для получения наилучших результатов перед отправкой запроса изучите [контрольный список для редактора](editorial-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="33312-106">For best results, review the [editorial checklist](editorial-checklist.md) before submitting your pull request.</span></span>

## <a name="target-the-correct-branch"></a><span data-ttu-id="33312-107">Выбор правильной ветви</span><span class="sxs-lookup"><span data-stu-id="33312-107">Target the correct branch</span></span>

<span data-ttu-id="33312-108">Все запросы на вытягивание должны направляться в ветвь `staging`.</span><span class="sxs-lookup"><span data-stu-id="33312-108">All pull requests should target the `staging` branch.</span></span> <span data-ttu-id="33312-109">Отправлять изменения в ветвь `live` нельзя.</span><span class="sxs-lookup"><span data-stu-id="33312-109">Changes should never be submitted to the `live` branch.</span></span> <span data-ttu-id="33312-110">Изменения, внесенные в ветвь `staging`, подвергаются слиянию с ветвью `live`, причем изменения в `live` перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="33312-110">Changes made in the `staging` branch get merged into `live`, overwriting any changes made to `live`.</span></span>

<span data-ttu-id="33312-111">Если вы отправляете изменение, которое относится только к невыпущенной версии PowerShell, проверьте наличие ветви выпуска для этой версии.</span><span class="sxs-lookup"><span data-stu-id="33312-111">If you are submitting a change that only applies to an unreleased version of PowerShell, check for a release branch for that version.</span></span> <span data-ttu-id="33312-112">Ваш запрос на вытягивание должен направляться в ветвь выпуска.</span><span class="sxs-lookup"><span data-stu-id="33312-112">Your PR should be targeted at the release branch.</span></span> <span data-ttu-id="33312-113">Ветви выпусков имеют следующий шаблон имени: `release-<version>`.</span><span class="sxs-lookup"><span data-stu-id="33312-113">Release branches have the following name pattern: `release-<version>`.</span></span>

## <a name="make-the-pull-request-process-work-better-for-everyone"></a><span data-ttu-id="33312-114">Упрощение процесса обработки запроса на вытягивание для всех участников</span><span class="sxs-lookup"><span data-stu-id="33312-114">Make the pull request process work better for everyone</span></span>

<span data-ttu-id="33312-115">Чем проще и конкретнее будет ваш запрос на вытягивание, тем быстрее он сможет пройти проверку и слияние.</span><span class="sxs-lookup"><span data-stu-id="33312-115">The simpler and more focused you can make your PR, the faster it can be reviewed and merged.</span></span>

### <a name="avoid-branches-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a><span data-ttu-id="33312-116">Не создавайте ветви, которые обновляют большое количество файлов или содержат несвязанные изменения</span><span class="sxs-lookup"><span data-stu-id="33312-116">Avoid branches that update large numbers of files or contain unrelated changes</span></span>

<span data-ttu-id="33312-117">Старайтесь не создавать запросы на вытягивание с несвязанными изменениями.</span><span class="sxs-lookup"><span data-stu-id="33312-117">Avoid creating PRs that contain unrelated changes.</span></span> <span data-ttu-id="33312-118">Отделяйте незначительные изменения в существующих статьях от новых статей или крупных переработок.</span><span class="sxs-lookup"><span data-stu-id="33312-118">Separate minor updates to existing articles from new articles or major rewrites.</span></span> <span data-ttu-id="33312-119">Работайте над этими изменениями в отдельных рабочих ветвях.</span><span class="sxs-lookup"><span data-stu-id="33312-119">Work on these changes in separate working branches.</span></span>

<span data-ttu-id="33312-120">При массовых изменениях создаются запросы на вытягивание с большим количеством измененных файлов.</span><span class="sxs-lookup"><span data-stu-id="33312-120">Bulk changes create PRs with large numbers of changed files.</span></span> <span data-ttu-id="33312-121">Запросы на вытягивание должны включать не более 50 измененных файлов.</span><span class="sxs-lookup"><span data-stu-id="33312-121">Limit your PRs to a maximum of 50 changed files.</span></span> <span data-ttu-id="33312-122">Большие запросы трудно проверять, и они более подвержены ошибкам.</span><span class="sxs-lookup"><span data-stu-id="33312-122">Large PRs are difficult to review and are more prone to contain errors.</span></span>

### <a name="renaming-or-deleting-files"></a><span data-ttu-id="33312-123">Переименование или удаление файлов</span><span class="sxs-lookup"><span data-stu-id="33312-123">Renaming or deleting files</span></span>

<span data-ttu-id="33312-124">При переименовании или удалении файлов с запросом на вытягивание должна быть связана проблема.</span><span class="sxs-lookup"><span data-stu-id="33312-124">If you are renaming or deleting files, there must be an issue associated with the PR.</span></span> <span data-ttu-id="33312-125">Она должна быть посвящена переименованию или удалению файлов.</span><span class="sxs-lookup"><span data-stu-id="33312-125">That issue must discuss the need to rename or delete the files.</span></span>

<span data-ttu-id="33312-126">Не сочетайте дополнения или изменения содержимого с переименованием и удалением файлов в одном запросе.</span><span class="sxs-lookup"><span data-stu-id="33312-126">Avoid mixing content additions or change with file renames and deletes.</span></span> <span data-ttu-id="33312-127">Любой переименованный или удаленный файл должен быть добавлен в главный файл перенаправления.</span><span class="sxs-lookup"><span data-stu-id="33312-127">Any file that is renamed or deleted must be added to the master redirection file.</span></span> <span data-ttu-id="33312-128">По возможности следует также обновить все файлы, связанные с переименованным или удаленным содержимым.</span><span class="sxs-lookup"><span data-stu-id="33312-128">When possible, you should also update any files that link to the renamed or deleted content.</span></span> <span data-ttu-id="33312-129">К ним относятся в том числе файлы оглавления.</span><span class="sxs-lookup"><span data-stu-id="33312-129">This includes any TOC files.</span></span>

## <a name="docs-pr-validation-service"></a><span data-ttu-id="33312-130">Служба проверки запросов на вытягивание для документации</span><span class="sxs-lookup"><span data-stu-id="33312-130">Docs PR validation service</span></span>

<span data-ttu-id="33312-131">Служба проверки запросов на вытягивание для документации — это приложение GitHub, которое применяет правила проверки к файлам в запросе на вытягивание.</span><span class="sxs-lookup"><span data-stu-id="33312-131">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span> <span data-ttu-id="33312-132">Все ошибки и предупреждения, о которых сообщает служба проверки, необходимо исправить (см. исключения).</span><span class="sxs-lookup"><span data-stu-id="33312-132">You must fix any errors or warnings (see exceptions) reported by the validation service.</span></span>

<span data-ttu-id="33312-133">Представленные ниже предупреждения можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="33312-133">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="33312-134">Процесс происходит описанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="33312-134">You'll see the following behavior:</span></span>

1. <span data-ttu-id="33312-135">Вы отправляете запрос на вытягивание.</span><span class="sxs-lookup"><span data-stu-id="33312-135">You submit a PR.</span></span>
1. <span data-ttu-id="33312-136">В GitHub в комментарии, в котором указывается состояние запроса на вытягивание, вы увидите состояние "checks" (проверки) для репозитория.</span><span class="sxs-lookup"><span data-stu-id="33312-136">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="33312-137">Обратите внимание, что в этом примере включены две проверки: "Commit Validation" (Проверка фиксации) и OpenPublishing.Build:</span><span class="sxs-lookup"><span data-stu-id="33312-137">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![некоторые проверки не пройдены](media/pull-requests/validation-failed.png)

   <span data-ttu-id="33312-139">Сборка может завершиться успешно, даже если проверка фиксации не пройдена.</span><span class="sxs-lookup"><span data-stu-id="33312-139">The build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="33312-140">Чтобы получить дополнительные сведения, щелкните ссылку **Details** (Сведения).</span><span class="sxs-lookup"><span data-stu-id="33312-140">Click **Details** for more information.</span></span>
1. <span data-ttu-id="33312-141">На странице сведений вы увидите все проверки, которые не были пройдены, и информацию об устранении проблем.</span><span class="sxs-lookup"><span data-stu-id="33312-141">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues.</span></span>
1. <span data-ttu-id="33312-142">Когда проверка пройдена, к запросу на вытягивание добавляется следующий комментарий:</span><span class="sxs-lookup"><span data-stu-id="33312-142">When validation succeeds, the following comment is added to the PR:</span></span>

   ![проверка сборки](media/pull-requests/build-validation.png)

> [!NOTE]
> <span data-ttu-id="33312-144">Если вы являетесь внешним участником (не сотрудником корпорации Майкрософт), у вас нет доступа к подробным отчетам о сборке или ссылкам для предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="33312-144">If you are an external (not a Microsoft employee) contributor you do not have access to the detailed build reports or preview links.</span></span>

<span data-ttu-id="33312-145">Во время проверки запроса на вытягивание участником команды PowerShell-Docs вас могут попросить внести изменения или устранить проблемы, указанные в отчете о проверке.</span><span class="sxs-lookup"><span data-stu-id="33312-145">When the PR is reviewed by a member of the PowerShell-Docs team, you may be asked to make changes or fix problems flagged by the validation report.</span></span> <span data-ttu-id="33312-146">Обратитесь к команде PowerShell-Docs, чтобы узнать, как внести исправления и избежать подобной проблемы при отправке последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="33312-146">The PowerShell-Docs team can help you understand how to fix and avoid these problems for future submissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="33312-147">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="33312-147">Next steps</span></span>

[<span data-ttu-id="33312-148">Руководство по стилю для документации PowerShell</span><span class="sxs-lookup"><span data-stu-id="33312-148">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

## <a name="additional-resources"></a><span data-ttu-id="33312-149">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="33312-149">Additional resources</span></span>

[<span data-ttu-id="33312-150">Рассмотрение запросов на вытягивание</span><span class="sxs-lookup"><span data-stu-id="33312-150">How we manage pull requests</span></span>](managing-pull-requests.md)
