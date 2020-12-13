---
ms.date: 09/13/2016
ms.topic: reference
title: Фоновые задания
description: Фоновые задания
ms.openlocfilehash: 5478789a2ee1f2eabc71a46673e3a707643cdba8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648614"
---
# <a name="background-jobs"></a><span data-ttu-id="b1b96-103">Фоновые задания</span><span class="sxs-lookup"><span data-stu-id="b1b96-103">Background Jobs</span></span>

<span data-ttu-id="b1b96-104">Командлеты могут выполнять свои действия внутренним образом или в виде *фонового задания* Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1b96-104">Cmdlets can perform their action internally or as a Windows PowerShell *background job*.</span></span> <span data-ttu-id="b1b96-105">Если командлет выполняется как фоновое задание, работа выполняется асинхронно в собственном потоке отдельно от потока конвейера, который используется командлетом.</span><span class="sxs-lookup"><span data-stu-id="b1b96-105">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="b1b96-106">С точки зрения пользователя, когда командлет выполняется как фоновое задание, Командная строка возвращается немедленно даже в том случае, если задание занимает длительное время, и пользователь может продолжить работу без прерывания во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="b1b96-106">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="b1b96-107">Фоновые задания, дочерние задания и репозиторий заданий</span><span class="sxs-lookup"><span data-stu-id="b1b96-107">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="b1b96-108">Объект задания, возвращаемый командлетами, поддерживающими фоновые задания, определяет задание.</span><span class="sxs-lookup"><span data-stu-id="b1b96-108">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="b1b96-109">(Командлет [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) также возвращает объект задания.) Имя задания, идентификатор, который используется для указания задания, сведения о состоянии и дочерние задания включаются в это определение.</span><span class="sxs-lookup"><span data-stu-id="b1b96-109">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="b1b96-110">Задание не выполняет никакой работы.</span><span class="sxs-lookup"><span data-stu-id="b1b96-110">The job does not perform any of the work.</span></span> <span data-ttu-id="b1b96-111">Каждое фоновое задание имеет по крайней мере одно дочернее задание, поскольку дочернее задание выполняет фактическую работу.</span><span class="sxs-lookup"><span data-stu-id="b1b96-111">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="b1b96-112">При запуске командлета для выполнения работы в качестве фонового задания командлет должен добавить задание и дочерние задания в общий репозиторий, который называется *репозиторием заданий*.</span><span class="sxs-lookup"><span data-stu-id="b1b96-112">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="b1b96-113">Дополнительные сведения об обработке фоновых заданий в командной строке см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="b1b96-113">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="b1b96-114">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="b1b96-114">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="b1b96-115">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="b1b96-115">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="b1b96-116">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="b1b96-116">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="b1b96-117">Написание командлета, выполняемого как фоновое задание</span><span class="sxs-lookup"><span data-stu-id="b1b96-117">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="b1b96-118">Чтобы написать командлет, который можно запустить как фоновое задание, необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="b1b96-118">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="b1b96-119">Определите `asJob` параметр переключателя, чтобы пользователь мог решить, следует ли запускать этот командлет как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="b1b96-119">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="b1b96-120">Создайте объект, производный от класса [System. Management. Automation. job](/dotnet/api/System.Management.Automation.Job) .</span><span class="sxs-lookup"><span data-stu-id="b1b96-120">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="b1b96-121">Этот объект может быть пользовательским объектом задания или объектом задания, предоставляемым Windows PowerShell, например объектом [System. Management. Automation. PSEventJob](/dotnet/api/System.Management.Automation.PSEventJob) .</span><span class="sxs-lookup"><span data-stu-id="b1b96-121">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="b1b96-122">В методе обработки записи добавьте `if` инструкцию, которая определяет, должен ли командлет выполняться как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="b1b96-122">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="b1b96-123">Для объектов пользовательских заданий Реализуйте класс Job.</span><span class="sxs-lookup"><span data-stu-id="b1b96-123">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="b1b96-124">Возврат соответствующих объектов в зависимости от того, выполняется ли командлет в фоновом задании.</span><span class="sxs-lookup"><span data-stu-id="b1b96-124">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="b1b96-125">Пример кода см. в разделе [Поддержка заданий](./how-to-support-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="b1b96-125">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="b1b96-126">Фоновые Job-Related интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="b1b96-126">Background Job-Related APIs</span></span>

<span data-ttu-id="b1b96-127">Windows PowerShell предоставляет следующие интерфейсы API для управления фоновыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="b1b96-127">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="b1b96-128">[System. Management. Automation. job](/dotnet/api/System.Management.Automation.Job) наследует пользовательские объекты задания.</span><span class="sxs-lookup"><span data-stu-id="b1b96-128">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="b1b96-129">Этот класс является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="b1b96-129">This is an abstract class.</span></span>

<span data-ttu-id="b1b96-130">[System. Management. Automation. жобрепоситори](/dotnet/api/System.Management.Automation.JobRepository) управляет и предоставляет сведения о текущих активных фоновых заданиях.</span><span class="sxs-lookup"><span data-stu-id="b1b96-130">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="b1b96-131">[System. Management. Automation. Jobstate](/dotnet/api/System.Management.Automation.JobState) определяет состояние фонового задания.</span><span class="sxs-lookup"><span data-stu-id="b1b96-131">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="b1b96-132">Состояния включают запуск, запуск и остановку.</span><span class="sxs-lookup"><span data-stu-id="b1b96-132">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="b1b96-133">[System. Management. Automation. JobStateInfo](/dotnet/api/System.Management.Automation.JobStateInfo) предоставляет сведения о состоянии фонового задания и, если Последнее изменение состояния вызвало ошибку, причину, по которой задание перешло в текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="b1b96-133">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="b1b96-134">[System. Management. Automation. жобстативентаргс](/dotnet/api/System.Management.Automation.JobStateEventArgs) предоставляет аргументы для события, которое возникает при изменении состояния фонового задания.</span><span class="sxs-lookup"><span data-stu-id="b1b96-134">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="b1b96-135">Командлеты задания Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1b96-135">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="b1b96-136">Для управления фоновыми заданиями в Windows PowerShell предусмотрены следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="b1b96-136">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="b1b96-137">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="b1b96-137">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="b1b96-138">Возвращает фоновые задания Windows PowerShell, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="b1b96-138">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="b1b96-139">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="b1b96-139">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="b1b96-140">Получает результаты фоновых заданий Windows PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b1b96-140">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="b1b96-141">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="b1b96-141">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="b1b96-142">Удаляет фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1b96-142">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="b1b96-143">Start-Job</span><span class="sxs-lookup"><span data-stu-id="b1b96-143">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="b1b96-144">Запускает фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1b96-144">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="b1b96-145">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="b1b96-145">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="b1b96-146">Останавливает фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1b96-146">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="b1b96-147">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="b1b96-147">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="b1b96-148">Отключает командную строку до завершения выполнения одного или нескольких фоновых заданий Windows PowerShell, запущенных в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="b1b96-148">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1b96-149">См. также</span><span class="sxs-lookup"><span data-stu-id="b1b96-149">See Also</span></span>

[<span data-ttu-id="b1b96-150">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1b96-150">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
