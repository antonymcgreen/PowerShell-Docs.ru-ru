---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: ff2c2bd7369893d72db001ecabf63991ded0bfd5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058987"
---
# <a name="unified-and-consistent-state-and-status-representation"></a><span data-ttu-id="617c0-102">Единое и согласованное представление состояний</span><span class="sxs-lookup"><span data-stu-id="617c0-102">Unified and Consistent State and Status Representation</span></span>

<span data-ttu-id="617c0-103">В этот выпуск внесен ряд усовершенствований для служб автоматизации, отвечающих за состояние LCM и DSC.</span><span class="sxs-lookup"><span data-stu-id="617c0-103">A series of enhancements have been made in this release for automations built LCM state and DSC status.</span></span> <span data-ttu-id="617c0-104">Сюда входят единые и согласованные представления состояния, управляемое свойство datetime объектов состояния, возвращаемых командлетом `Get-DscConfigurationStatus`, и свойство расширенных сведений о состоянии LCM, возвращаемое командлетом `Get-DscLocalConfigurationManager`.</span><span class="sxs-lookup"><span data-stu-id="617c0-104">These include unified and consistent state and status representations, manageable datetime property of status objects returned by `Get-DscConfigurationStatus` cmdlet and enhanced LCM state details property returned by `Get-DscLocalConfigurationManager` cmdlet.</span></span>

<span data-ttu-id="617c0-105">Это представление состояния LCM и DSC пересмотрено и унифицировано согласно следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="617c0-105">The representation of LCM state and DSC operation status are revisited and unified according to following rules:</span></span>

1. <span data-ttu-id="617c0-106">Необработанный ресурс не влияет на состояние LCM и DSC.</span><span class="sxs-lookup"><span data-stu-id="617c0-106">Notprocessed resource does not impact LCM state and DSC status.</span></span>
2. <span data-ttu-id="617c0-107">LCM останавливает обработку дальнейших ресурсов, встретив ресурс, который требует перезагрузку.</span><span class="sxs-lookup"><span data-stu-id="617c0-107">LCM stop processing further resources once it encounters a resource that requests reboot.</span></span>
3. <span data-ttu-id="617c0-108">Ресурс, требующий перезагрузку, не находится в нужном состоянии до ее фактического выполнения.</span><span class="sxs-lookup"><span data-stu-id="617c0-108">A resource that requests reboot is not in desired state until reboot actually happens.</span></span>
4. <span data-ttu-id="617c0-109">После обнаружения ресурса, завершающегося сбоем, LCM продолжает обрабатывать дальнейшие ресурсы, если только они не зависят от ресурса со сбоем.</span><span class="sxs-lookup"><span data-stu-id="617c0-109">After encountering a resource that fails, LCM keeps processing further resources as long as they are not dependent on the failure one.</span></span>
5. <span data-ttu-id="617c0-110">Общее состояние, возвращаемое командлетом `Get-DscConfigurationStatus`, представляет собой супермножество состояния для всех ресурсов.</span><span class="sxs-lookup"><span data-stu-id="617c0-110">The overall status returned by `Get-DscConfigurationStatus` cmdlet is the super set of all resources' status.</span></span>
6. <span data-ttu-id="617c0-111">Состояние PendingReboot является супермножеством состояния PendingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="617c0-111">The PendingReboot state is a superset of PendingConfiguration state.</span></span>

<span data-ttu-id="617c0-112">В следующей таблице приведены итоговые свойства состояния в несколько типичных сценариях.</span><span class="sxs-lookup"><span data-stu-id="617c0-112">The table below illustrates the resultant state and status related properties under a few typical scenarios.</span></span>

| <span data-ttu-id="617c0-113">Сценарий</span><span class="sxs-lookup"><span data-stu-id="617c0-113">Scenario</span></span>                        | <span data-ttu-id="617c0-114">LCMState</span><span class="sxs-lookup"><span data-stu-id="617c0-114">LCMState</span></span>             | <span data-ttu-id="617c0-115">Состояние</span><span class="sxs-lookup"><span data-stu-id="617c0-115">Status</span></span>     | <span data-ttu-id="617c0-116">Запрошена перезагрузка</span><span class="sxs-lookup"><span data-stu-id="617c0-116">Reboot Requested</span></span> | <span data-ttu-id="617c0-117">ResourcesInDesiredState</span><span class="sxs-lookup"><span data-stu-id="617c0-117">ResourcesInDesiredState</span></span>   | <span data-ttu-id="617c0-118">ResourcesNotInDesiredState</span><span class="sxs-lookup"><span data-stu-id="617c0-118">ResourcesNotInDesiredState</span></span> |
|---------------------------------|----------------------|------------|---------------|------------------------------|--------------------------------|
| <span data-ttu-id="617c0-119">S<sub>i</sub></span><span class="sxs-lookup"><span data-stu-id="617c0-119">S<sub>i</sub></span></span>                   | <span data-ttu-id="617c0-120">Idle</span><span class="sxs-lookup"><span data-stu-id="617c0-120">Idle</span></span>                 | <span data-ttu-id="617c0-121">Успех</span><span class="sxs-lookup"><span data-stu-id="617c0-121">Success</span></span>    | <span data-ttu-id="617c0-122">$false</span><span class="sxs-lookup"><span data-stu-id="617c0-122">$false</span></span>        | <span data-ttu-id="617c0-123">S</span><span class="sxs-lookup"><span data-stu-id="617c0-123">S</span></span>                            | <span data-ttu-id="617c0-124">$null</span><span class="sxs-lookup"><span data-stu-id="617c0-124">$null</span></span>                          |
| <span data-ttu-id="617c0-125">F<sub>i</sub></span><span class="sxs-lookup"><span data-stu-id="617c0-125">F<sub>i</sub></span></span>                   | <span data-ttu-id="617c0-126">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="617c0-126">PendingConfiguration</span></span> | <span data-ttu-id="617c0-127">Отказ</span><span class="sxs-lookup"><span data-stu-id="617c0-127">Failure</span></span>    | <span data-ttu-id="617c0-128">$false</span><span class="sxs-lookup"><span data-stu-id="617c0-128">$false</span></span>        | <span data-ttu-id="617c0-129">$null</span><span class="sxs-lookup"><span data-stu-id="617c0-129">$null</span></span>                        | <span data-ttu-id="617c0-130">F</span><span class="sxs-lookup"><span data-stu-id="617c0-130">F</span></span>                              |
| <span data-ttu-id="617c0-131">S,F</span><span class="sxs-lookup"><span data-stu-id="617c0-131">S,F</span></span>                             | <span data-ttu-id="617c0-132">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="617c0-132">PendingConfiguration</span></span> | <span data-ttu-id="617c0-133">Отказ</span><span class="sxs-lookup"><span data-stu-id="617c0-133">Failure</span></span>    | <span data-ttu-id="617c0-134">$false</span><span class="sxs-lookup"><span data-stu-id="617c0-134">$false</span></span>        | <span data-ttu-id="617c0-135">S</span><span class="sxs-lookup"><span data-stu-id="617c0-135">S</span></span>                            | <span data-ttu-id="617c0-136">F</span><span class="sxs-lookup"><span data-stu-id="617c0-136">F</span></span>                              |
| <span data-ttu-id="617c0-137">F,S</span><span class="sxs-lookup"><span data-stu-id="617c0-137">F,S</span></span>                             | <span data-ttu-id="617c0-138">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="617c0-138">PendingConfiguration</span></span> | <span data-ttu-id="617c0-139">Отказ</span><span class="sxs-lookup"><span data-stu-id="617c0-139">Failure</span></span>    | <span data-ttu-id="617c0-140">$false</span><span class="sxs-lookup"><span data-stu-id="617c0-140">$false</span></span>        | <span data-ttu-id="617c0-141">S</span><span class="sxs-lookup"><span data-stu-id="617c0-141">S</span></span>                            | <span data-ttu-id="617c0-142">F</span><span class="sxs-lookup"><span data-stu-id="617c0-142">F</span></span>                              |
| <span data-ttu-id="617c0-143">S<sub>1</sub>, F, S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="617c0-143">S<sub>1</sub>, F, S<sub>2</sub></span></span> | <span data-ttu-id="617c0-144">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="617c0-144">PendingConfiguration</span></span> | <span data-ttu-id="617c0-145">Отказ</span><span class="sxs-lookup"><span data-stu-id="617c0-145">Failure</span></span>    | <span data-ttu-id="617c0-146">$false</span><span class="sxs-lookup"><span data-stu-id="617c0-146">$false</span></span>        | <span data-ttu-id="617c0-147">S<sub>1</sub>, S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="617c0-147">S<sub>1</sub>, S<sub>2</sub></span></span> | <span data-ttu-id="617c0-148">F</span><span class="sxs-lookup"><span data-stu-id="617c0-148">F</span></span>                              |
| <span data-ttu-id="617c0-149">F<sub>1</sub>, S, F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="617c0-149">F<sub>1</sub>, S, F<sub>2</sub></span></span> | <span data-ttu-id="617c0-150">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="617c0-150">PendingConfiguration</span></span> | <span data-ttu-id="617c0-151">Отказ</span><span class="sxs-lookup"><span data-stu-id="617c0-151">Failure</span></span>    | <span data-ttu-id="617c0-152">$false</span><span class="sxs-lookup"><span data-stu-id="617c0-152">$false</span></span>        | <span data-ttu-id="617c0-153">S</span><span class="sxs-lookup"><span data-stu-id="617c0-153">S</span></span>                            | <span data-ttu-id="617c0-154">F<sub>1</sub>, F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="617c0-154">F<sub>1</sub>, F<sub>2</sub></span></span>   |
| <span data-ttu-id="617c0-155">S, r</span><span class="sxs-lookup"><span data-stu-id="617c0-155">S, r</span></span>                            | <span data-ttu-id="617c0-156">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="617c0-156">PendingReboot</span></span>        | <span data-ttu-id="617c0-157">Успех</span><span class="sxs-lookup"><span data-stu-id="617c0-157">Success</span></span>    | <span data-ttu-id="617c0-158">$true</span><span class="sxs-lookup"><span data-stu-id="617c0-158">$true</span></span>         | <span data-ttu-id="617c0-159">S</span><span class="sxs-lookup"><span data-stu-id="617c0-159">S</span></span>                            | <span data-ttu-id="617c0-160">r</span><span class="sxs-lookup"><span data-stu-id="617c0-160">r</span></span>                              |
| <span data-ttu-id="617c0-161">F, r</span><span class="sxs-lookup"><span data-stu-id="617c0-161">F, r</span></span>                            | <span data-ttu-id="617c0-162">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="617c0-162">PendingReboot</span></span>        | <span data-ttu-id="617c0-163">Отказ</span><span class="sxs-lookup"><span data-stu-id="617c0-163">Failure</span></span>    | <span data-ttu-id="617c0-164">$true</span><span class="sxs-lookup"><span data-stu-id="617c0-164">$true</span></span>         | <span data-ttu-id="617c0-165">$null</span><span class="sxs-lookup"><span data-stu-id="617c0-165">$null</span></span>                        | <span data-ttu-id="617c0-166">F, r</span><span class="sxs-lookup"><span data-stu-id="617c0-166">F, r</span></span>                           |
| <span data-ttu-id="617c0-167">r, S</span><span class="sxs-lookup"><span data-stu-id="617c0-167">r, S</span></span>                            | <span data-ttu-id="617c0-168">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="617c0-168">PendingReboot</span></span>        | <span data-ttu-id="617c0-169">Успех</span><span class="sxs-lookup"><span data-stu-id="617c0-169">Success</span></span>    | <span data-ttu-id="617c0-170">$true</span><span class="sxs-lookup"><span data-stu-id="617c0-170">$true</span></span>         | <span data-ttu-id="617c0-171">$null</span><span class="sxs-lookup"><span data-stu-id="617c0-171">$null</span></span>                        | <span data-ttu-id="617c0-172">r</span><span class="sxs-lookup"><span data-stu-id="617c0-172">r</span></span>                              |
| <span data-ttu-id="617c0-173">r, F</span><span class="sxs-lookup"><span data-stu-id="617c0-173">r, F</span></span>                            | <span data-ttu-id="617c0-174">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="617c0-174">PendingReboot</span></span>        | <span data-ttu-id="617c0-175">Успех</span><span class="sxs-lookup"><span data-stu-id="617c0-175">Success</span></span>    | <span data-ttu-id="617c0-176">$true</span><span class="sxs-lookup"><span data-stu-id="617c0-176">$true</span></span>         | <span data-ttu-id="617c0-177">$null</span><span class="sxs-lookup"><span data-stu-id="617c0-177">$null</span></span>                        | <span data-ttu-id="617c0-178">r</span><span class="sxs-lookup"><span data-stu-id="617c0-178">r</span></span>                              |

- <span data-ttu-id="617c0-179">S<sub>i</sub>: ряд ресурсов, которые успешно применены.</span><span class="sxs-lookup"><span data-stu-id="617c0-179">S<sub>i</sub>: A series of resources that applied successfully</span></span>
- <span data-ttu-id="617c0-180">F<sub>i</sub>: ряд ресурсов, которые применены с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="617c0-180">F<sub>i</sub>: A series of resources that applied unsuccessfully</span></span>
- <span data-ttu-id="617c0-181">r: ресурс, который требует перезагрузку.</span><span class="sxs-lookup"><span data-stu-id="617c0-181">r: A resource that requires reboot</span></span>

```powershell
$LCMState = (Get-DscLocalConfigurationManager).LCMState
$Status = (Get-DscConfigurationStatus).Status

$RebootRequested = (Get-DscConfigurationStatus).RebootRequested

$ResourcesInDesiredState = (Get-DscConfigurationStatus).ResourcesInDesiredState

$ResourcesNotInDesiredState = (Get-DscConfigurationStatus).ResourcesNotInDesiredState
```

## <a name="enhancement-in-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="617c0-182">Улучшения в командлете Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="617c0-182">Enhancement in Get-DscConfigurationStatus cmdlet</span></span>

<span data-ttu-id="617c0-183">В этом выпуске в командлет `Get-DscConfigurationStatus` было внесено несколько улучшений.</span><span class="sxs-lookup"><span data-stu-id="617c0-183">A few enhancements have been made to `Get-DscConfigurationStatus` cmdlet in this release.</span></span> <span data-ttu-id="617c0-184">Ранее свойство StartDate объектов, возвращаемое командлетом StartDate, имело тип String.</span><span class="sxs-lookup"><span data-stu-id="617c0-184">Previously, the StartDate property of objects returned by the cmdlet is of String type.</span></span> <span data-ttu-id="617c0-185">Теперь оно имеет тип Datetime, что упрощает сложный выбор и фильтрацию благодаря встроенным свойствам объекта Datetime.</span><span class="sxs-lookup"><span data-stu-id="617c0-185">Now, it is of Datetime type, which enables complex selecting and filtering easier based on the intrinsic properties of a Datetime object.</span></span>

```powershell
(Get-DscConfigurationStatus).StartDate | Format-List *

DateTime    : Friday, November 13, 2015 1:39:44 PM
Date        : 11/13/2015 12:00:00 AM
Day         : 13
DayOfWeek   : Friday
DayOfYear   : 317
Hour        : 13
Kind        : Local
Millisecond : 886
Minute      : 39
Month       : 11
Second      : 44
Ticks       : 635830187848860000
TimeOfDay   : 13:39:44.8860000
Year        : 2015
```

<span data-ttu-id="617c0-186">Пример ниже возвращает все записи операций DSC, созданные в тот же день недели, что и сегодня.</span><span class="sxs-lookup"><span data-stu-id="617c0-186">The following example returns all DSC operation records that happened on the same day of week as the current day.</span></span>

```powershell
(Get-DscConfigurationStatus –All) | Where-Object { $_.startdate.dayofweek -eq (Get-Date).DayOfWeek }
```

<span data-ttu-id="617c0-187">Записи операций, которые не вносят изменения в конфигурацию узла (т. е. представлены операциями только для чтения), исключаются.</span><span class="sxs-lookup"><span data-stu-id="617c0-187">Records of operations that do not make changes to node’s configuration (i.e. read only operations) are eliminated.</span></span> <span data-ttu-id="617c0-188">Таким образом, операции `Test-DscConfiguration` и `Get-DscConfiguration` больше не имитируются в возвращаемых объектах из командлета `Get-DscConfigurationStatus`.</span><span class="sxs-lookup"><span data-stu-id="617c0-188">Therefore, `Test-DscConfiguration`, `Get-DscConfiguration` operations are no longer adulterated in returned objects from `Get-DscConfigurationStatus` cmdlet.</span></span> <span data-ttu-id="617c0-189">В выходные данные командлета `Get-DscConfigurationStatus`добавляются записи для операции настройки метаконфигурации.</span><span class="sxs-lookup"><span data-stu-id="617c0-189">Records of meta configuration setting operation is added to the return of `Get-DscConfigurationStatus` cmdlet.</span></span>

<span data-ttu-id="617c0-190">Ниже — пример результата, возвращаемого командлетом `Get-DscConfigurationStatus –All`.</span><span class="sxs-lookup"><span data-stu-id="617c0-190">Following is an example of result returned from `Get-DscConfigurationStatus –All` cmdlet.</span></span>

```output
All configuration operations:

Status StartDate Type RebootRequested
------ --------- ---- ---------------
Success 11/13/2015 11:38:16 AM Consistency False
Success 11/13/2015 11:23:16 AM Reboot False
Success 11/13/2015 11:21:43 AM Reboot True
Success 11/13/2015 11:20:44 AM Initial True
Success 11/13/2015 11:20:44 AM LocalConfigurationManager False
```

## <a name="enhancement-in-get-dsclocalconfigurationmanager-cmdlet"></a><span data-ttu-id="617c0-191">Улучшения в командлете Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="617c0-191">Enhancement in Get-DscLocalConfigurationManager cmdlet</span></span>

<span data-ttu-id="617c0-192">В объект, возвращаемый из командлета `Get-DscLocalConfigurationManager`, добавлено новое поле LCMStateDetail.</span><span class="sxs-lookup"><span data-stu-id="617c0-192">A new field of LCMStateDetail is added to the object returned from `Get-DscLocalConfigurationManager` cmdlet.</span></span> <span data-ttu-id="617c0-193">Оно заполняется в том случае, когда LCMState имеет значение Busy.</span><span class="sxs-lookup"><span data-stu-id="617c0-193">This field is populated when LCMState is "Busy".</span></span> <span data-ttu-id="617c0-194">Извлечь его можно с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="617c0-194">It can be retrieved by following cmdlet:</span></span>

```powershell
(Get-DscLocalConfigurationManager).LCMStateDetail
```

<span data-ttu-id="617c0-195">Ниже приведен пример выходных данных для постоянного мониторинга конфигурации, которая требует двух перезагрузок на удаленном узле.</span><span class="sxs-lookup"><span data-stu-id="617c0-195">Following is an example output of a continuous monitoring on a configuration that requires two reboots on a remote node.</span></span>

```output
Start a configuration that requires two reboots

Monitor LCM State:
LCM State: Busy, LCM is applying a new configuration.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: Idle,
LCM State: Busy, LCM is performing a consistency check.
LCM State: Idle,
```
