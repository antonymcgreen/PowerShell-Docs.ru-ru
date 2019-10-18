---
title: Фоновые задания | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0ef5ac9-8254-4832-ace8-84b356c10f08
caps.latest.revision: 13
ms.openlocfilehash: ff4fe159eedc47fc69f4d783cd90d2b0e888c0d5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363563"
---
# <a name="background-jobs"></a><span data-ttu-id="78300-102">Фоновые задания</span><span class="sxs-lookup"><span data-stu-id="78300-102">Background Jobs</span></span>

<span data-ttu-id="78300-103">Командлеты могут выполнять свои действия внутренним образом или в виде*фонового задания*Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78300-103">Cmdlets can perform their action internally or as a Windows PowerShell*background job*.</span></span> <span data-ttu-id="78300-104">Если командлет выполняется как фоновое задание, работа выполняется асинхронно в собственном потоке отдельно от потока конвейера, который используется командлетом.</span><span class="sxs-lookup"><span data-stu-id="78300-104">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="78300-105">С точки зрения пользователя, когда командлет выполняется как фоновое задание, Командная строка возвращается немедленно даже в том случае, если задание занимает длительное время, и пользователь может продолжить работу без прерывания во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="78300-105">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="78300-106">Фоновые задания, дочерние задания и репозиторий заданий</span><span class="sxs-lookup"><span data-stu-id="78300-106">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="78300-107">Объект задания, возвращаемый командлетами, поддерживающими фоновые задания, определяет задание.</span><span class="sxs-lookup"><span data-stu-id="78300-107">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="78300-108">(Командлет [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) также возвращает объект задания.) Имя задания, идентификатор, который используется для указания задания, сведения о состоянии и дочерние задания включаются в это определение.</span><span class="sxs-lookup"><span data-stu-id="78300-108">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="78300-109">Задание не выполняет никакой работы.</span><span class="sxs-lookup"><span data-stu-id="78300-109">The job does not perform any of the work.</span></span> <span data-ttu-id="78300-110">Каждое фоновое задание имеет по крайней мере одно дочернее задание, поскольку дочернее задание выполняет фактическую работу.</span><span class="sxs-lookup"><span data-stu-id="78300-110">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="78300-111">При запуске командлета для выполнения работы в качестве фонового задания командлет должен добавить задание и дочерние задания в общий репозиторий, который называется *репозиторием заданий*.</span><span class="sxs-lookup"><span data-stu-id="78300-111">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="78300-112">Дополнительные сведения об обработке фоновых заданий в командной строке см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="78300-112">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="78300-113">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="78300-113">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="78300-114">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="78300-114">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="78300-115">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="78300-115">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="78300-116">Написание командлета, выполняемого как фоновое задание</span><span class="sxs-lookup"><span data-stu-id="78300-116">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="78300-117">Чтобы написать командлет, который можно запустить как фоновое задание, необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="78300-117">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="78300-118">Определите параметр `asJob`, чтобы пользователь мог решить, следует ли запускать этот командлет как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="78300-118">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="78300-119">Создайте объект, производный от класса [System. Management. Automation. job](/dotnet/api/System.Management.Automation.Job) .</span><span class="sxs-lookup"><span data-stu-id="78300-119">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="78300-120">Этот объект может быть пользовательским объектом задания или объектом задания, предоставляемым Windows PowerShell, например объектом [System. Management. Automation. PSEventJob](/dotnet/api/System.Management.Automation.PSEventJob) .</span><span class="sxs-lookup"><span data-stu-id="78300-120">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="78300-121">В методе обработки записи добавьте инструкцию `if`, которая определяет, должен ли командлет выполняться как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="78300-121">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="78300-122">Для объектов пользовательских заданий Реализуйте класс Job.</span><span class="sxs-lookup"><span data-stu-id="78300-122">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="78300-123">Возврат соответствующих объектов в зависимости от того, выполняется ли командлет в фоновом задании.</span><span class="sxs-lookup"><span data-stu-id="78300-123">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="78300-124">Пример кода см. в разделе [Поддержка заданий](./how-to-support-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="78300-124">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="78300-125">Интерфейсы API, связанные с фоновыми заданиями</span><span class="sxs-lookup"><span data-stu-id="78300-125">Background Job-Related APIs</span></span>

<span data-ttu-id="78300-126">Windows PowerShell предоставляет следующие интерфейсы API для управления фоновыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="78300-126">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="78300-127">[System. Management. Automation. job](/dotnet/api/System.Management.Automation.Job) наследует пользовательские объекты задания.</span><span class="sxs-lookup"><span data-stu-id="78300-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="78300-128">Это абстрактный класс.</span><span class="sxs-lookup"><span data-stu-id="78300-128">This is an abstract class.</span></span>

<span data-ttu-id="78300-129">[System. Management. Automation. жобрепоситори](/dotnet/api/System.Management.Automation.JobRepository) управляет и предоставляет сведения о текущих активных фоновых заданиях.</span><span class="sxs-lookup"><span data-stu-id="78300-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="78300-130">[System. Management. Automation. Jobstate](/dotnet/api/System.Management.Automation.JobState) определяет состояние фонового задания.</span><span class="sxs-lookup"><span data-stu-id="78300-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="78300-131">Состояния включают запуск, запуск и остановку.</span><span class="sxs-lookup"><span data-stu-id="78300-131">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="78300-132">[System. Management. Automation. JobStateInfo](/dotnet/api/System.Management.Automation.JobStateInfo) предоставляет сведения о состоянии фонового задания и, если Последнее изменение состояния вызвало ошибку, причину, по которой задание перешло в текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="78300-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="78300-133">[System. Management. Automation. жобстативентаргс](/dotnet/api/System.Management.Automation.JobStateEventArgs) предоставляет аргументы для события, которое возникает при изменении состояния фонового задания.</span><span class="sxs-lookup"><span data-stu-id="78300-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="78300-134">Командлеты задания Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78300-134">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="78300-135">Для управления фоновыми заданиями в Windows PowerShell предусмотрены следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="78300-135">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="78300-136">Get-Job</span><span class="sxs-lookup"><span data-stu-id="78300-136">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="78300-137">Возвращает фоновые задания Windows PowerShell, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="78300-137">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="78300-138">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="78300-138">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="78300-139">Получает результаты фоновых заданий Windows PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="78300-139">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="78300-140">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="78300-140">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="78300-141">Удаляет фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78300-141">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="78300-142">Start-Job</span><span class="sxs-lookup"><span data-stu-id="78300-142">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="78300-143">Запускает фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78300-143">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="78300-144">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="78300-144">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="78300-145">Останавливает фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78300-145">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="78300-146">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="78300-146">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="78300-147">Отключает командную строку до завершения выполнения одного или нескольких фоновых заданий Windows PowerShell, запущенных в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="78300-147">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="78300-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="78300-148">See Also</span></span>

[<span data-ttu-id="78300-149">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78300-149">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
