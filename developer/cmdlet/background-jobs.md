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
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794711"
---
# <a name="background-jobs"></a><span data-ttu-id="6ce72-102">Фоновые задания</span><span class="sxs-lookup"><span data-stu-id="6ce72-102">Background Jobs</span></span>

<span data-ttu-id="6ce72-103">Командлеты действие можно выполнить их внутри, так и Windows PowerShell*фоновое задание*.</span><span class="sxs-lookup"><span data-stu-id="6ce72-103">Cmdlets can perform their action internally or as a Windows PowerShell*background job*.</span></span> <span data-ttu-id="6ce72-104">При выполнении командлета как фоновое задание работу асинхронно в отдельном потоке, отдельном от потока конвейер, используя командлет.</span><span class="sxs-lookup"><span data-stu-id="6ce72-104">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="6ce72-105">С точки зрения пользователя, при запуске командлета в качестве фонового задания, Командная строка возвращается немедленно даже в том случае, если задание занимает продолжительное время, и пользователь может продолжить работу без прерывания во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="6ce72-105">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="6ce72-106">Фоновые задания, дочерние задания и репозиторий заданий</span><span class="sxs-lookup"><span data-stu-id="6ce72-106">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="6ce72-107">Объект задания, который возвращается с помощью командлетов, которые поддерживают фоновые задания определяет задание.</span><span class="sxs-lookup"><span data-stu-id="6ce72-107">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="6ce72-108">( [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) командлет также возвращает объект задания.) Имя задания, идентификатор, который используется для указания задания, сведения о состоянии и дочерние задания, включаются в это определение.</span><span class="sxs-lookup"><span data-stu-id="6ce72-108">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="6ce72-109">Задание не выполнять часть работы.</span><span class="sxs-lookup"><span data-stu-id="6ce72-109">The job does not perform any of the work.</span></span> <span data-ttu-id="6ce72-110">Каждый фоновое задание имеет по крайней мере одно дочернее задание, так как дочернее задание выполняет фактическую работу.</span><span class="sxs-lookup"><span data-stu-id="6ce72-110">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="6ce72-111">При выполнении командлета, чтобы работа выполняется в качестве фонового задания, командлет необходимо добавить задание и дочерние задания общим хранилищем, называется *репозиторий заданий для*.</span><span class="sxs-lookup"><span data-stu-id="6ce72-111">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="6ce72-112">Дополнительные сведения об обработке фоновых заданий в командной строке см. в разделе ниже:</span><span class="sxs-lookup"><span data-stu-id="6ce72-112">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="6ce72-113">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="6ce72-113">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="6ce72-114">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="6ce72-114">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="6ce72-115">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="6ce72-115">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="6ce72-116">Написание командлетов, который запускается как фоновое задание</span><span class="sxs-lookup"><span data-stu-id="6ce72-116">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="6ce72-117">Чтобы написать командлет, который может выполняться как фоновое задание, необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="6ce72-117">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="6ce72-118">Определение `asJob` параметр-переключатель, чтобы пользователь может решить, следует ли выполнять командлет как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="6ce72-118">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="6ce72-119">Создайте объект, который является производным от [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) класса.</span><span class="sxs-lookup"><span data-stu-id="6ce72-119">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="6ce72-120">Этот объект может быть объект пользовательские задания или объект задания, предоставляемыми Windows PowerShell, такими как [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) объекта.</span><span class="sxs-lookup"><span data-stu-id="6ce72-120">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="6ce72-121">Добавьте в метод обработки записей, `if` инструкцию, которая определяет, следует ли запускать командлет как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="6ce72-121">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="6ce72-122">Для задания пользовательских объектов Реализуйте класс задания.</span><span class="sxs-lookup"><span data-stu-id="6ce72-122">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="6ce72-123">Возвращает соответствующие объекты, в зависимости от того, выполняется ли команда как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="6ce72-123">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="6ce72-124">Пример кода см. в разделе [как заданий поддержки](./how-to-support-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6ce72-124">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="6ce72-125">API-интерфейсов, связанных с заданием фона</span><span class="sxs-lookup"><span data-stu-id="6ce72-125">Background Job-Related APIs</span></span>

<span data-ttu-id="6ce72-126">Следующие API-интерфейсы, предоставляемые Windows PowerShell для управления фоновыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="6ce72-126">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="6ce72-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) производный объекты пользовательских заданий.</span><span class="sxs-lookup"><span data-stu-id="6ce72-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="6ce72-128">Это абстрактный класс.</span><span class="sxs-lookup"><span data-stu-id="6ce72-128">This is an abstract class.</span></span>

<span data-ttu-id="6ce72-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) управляет и предоставляет сведения о текущем active фоновые задания.</span><span class="sxs-lookup"><span data-stu-id="6ce72-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="6ce72-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) определяет состояние фонового задания.</span><span class="sxs-lookup"><span data-stu-id="6ce72-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="6ce72-131">Следующие состояния работы, запущена и остановлена.</span><span class="sxs-lookup"><span data-stu-id="6ce72-131">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="6ce72-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) предоставляет сведения о состоянии фонового задания и если изменить последнее состояние было вызвано сообщение об ошибке, а причина задание перешло в ее текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="6ce72-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="6ce72-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) предоставляет аргументы для события, которое возникает, когда фоновое задание меняет состояние.</span><span class="sxs-lookup"><span data-stu-id="6ce72-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="6ce72-134">Командлеты Windows PowerShell заданий</span><span class="sxs-lookup"><span data-stu-id="6ce72-134">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="6ce72-135">Имеются следующие командлеты Windows PowerShell для управления фоновыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="6ce72-135">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="6ce72-136">Get-Job</span><span class="sxs-lookup"><span data-stu-id="6ce72-136">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="6ce72-137">Возвращает фоновые задания Windows PowerShell, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="6ce72-137">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="6ce72-138">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="6ce72-138">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="6ce72-139">Получает результаты фоновых заданий Windows PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="6ce72-139">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="6ce72-140">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="6ce72-140">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="6ce72-141">Удаляет фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ce72-141">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="6ce72-142">Start-Job</span><span class="sxs-lookup"><span data-stu-id="6ce72-142">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="6ce72-143">Запускает фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ce72-143">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="6ce72-144">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="6ce72-144">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="6ce72-145">Останавливает фоновое задание Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ce72-145">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="6ce72-146">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="6ce72-146">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="6ce72-147">Отключает командную строку до завершения выполнения одного или нескольких фоновых заданий Windows PowerShell, запущенных в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="6ce72-147">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ce72-148">См. также</span><span class="sxs-lookup"><span data-stu-id="6ce72-148">See Also</span></span>

[<span data-ttu-id="6ce72-149">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ce72-149">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
