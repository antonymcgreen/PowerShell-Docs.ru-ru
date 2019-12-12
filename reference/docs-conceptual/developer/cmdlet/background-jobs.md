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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363563"
---
# <a name="background-jobs"></a>Фоновые задания

Командлеты могут выполнять свои действия внутренним образом или в виде*фонового задания*Windows PowerShell. Если командлет выполняется как фоновое задание, работа выполняется асинхронно в собственном потоке отдельно от потока конвейера, который используется командлетом. С точки зрения пользователя, когда командлет выполняется как фоновое задание, Командная строка возвращается немедленно даже в том случае, если задание занимает длительное время, и пользователь может продолжить работу без прерывания во время выполнения задания.

## <a name="background-jobs-child-jobs-and-the-job-repository"></a>Фоновые задания, дочерние задания и репозиторий заданий

Объект задания, возвращаемый командлетами, поддерживающими фоновые задания, определяет задание. (Командлет [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) также возвращает объект задания.) Имя задания, идентификатор, который используется для указания задания, сведения о состоянии и дочерние задания включаются в это определение. Задание не выполняет никакой работы. Каждое фоновое задание имеет по крайней мере одно дочернее задание, поскольку дочернее задание выполняет фактическую работу. При запуске командлета для выполнения работы в качестве фонового задания командлет должен добавить задание и дочерние задания в общий репозиторий, который называется *репозиторием заданий*.

Дополнительные сведения об обработке фоновых заданий в командной строке см. в следующих статьях:

- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [about_Job_Details](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [about_Remote_Jobs](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a>Написание командлета, выполняемого как фоновое задание

Чтобы написать командлет, который можно запустить как фоновое задание, необходимо выполнить следующие задачи.

- Определите параметр `asJob` параметра, чтобы пользователь мог решить, следует ли запускать этот командлет как фоновое задание.

- Создайте объект, производный от класса [System. Management. Automation. job](/dotnet/api/System.Management.Automation.Job) . Этот объект может быть пользовательским объектом задания или объектом задания, предоставляемым Windows PowerShell, например объектом [System. Management. Automation. PSEventJob](/dotnet/api/System.Management.Automation.PSEventJob) .

- В методе обработки записи добавьте инструкцию `if`, которая определяет, должен ли командлет выполняться как фоновое задание.

- Для объектов пользовательских заданий Реализуйте класс Job.

- Возврат соответствующих объектов в зависимости от того, выполняется ли командлет в фоновом задании.

Пример кода см. в разделе [Поддержка заданий](./how-to-support-jobs.md).

## <a name="background-job-related-apis"></a>Интерфейсы API, связанные с фоновыми заданиями

Windows PowerShell предоставляет следующие интерфейсы API для управления фоновыми заданиями.

[System. Management. Automation. job](/dotnet/api/System.Management.Automation.Job) наследует пользовательские объекты задания. Этот класс является абстрактным.

[System. Management. Automation. жобрепоситори](/dotnet/api/System.Management.Automation.JobRepository) управляет и предоставляет сведения о текущих активных фоновых заданиях.

[System. Management. Automation. Jobstate](/dotnet/api/System.Management.Automation.JobState) определяет состояние фонового задания. Состояния включают запуск, запуск и остановку.

[System. Management. Automation. JobStateInfo](/dotnet/api/System.Management.Automation.JobStateInfo) предоставляет сведения о состоянии фонового задания и, если Последнее изменение состояния вызвало ошибку, причину, по которой задание перешло в текущее состояние.

[System. Management. Automation. жобстативентаргс](/dotnet/api/System.Management.Automation.JobStateEventArgs) предоставляет аргументы для события, которое возникает при изменении состояния фонового задания.

## <a name="windows-powershell-job-cmdlets"></a>Командлеты задания Windows PowerShell

Для управления фоновыми заданиями в Windows PowerShell предусмотрены следующие командлеты.

[Get-Job](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

Возвращает фоновые задания Windows PowerShell, запущенные в рамках текущего сеанса.

[Receive-Job](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

Получает результаты фоновых заданий Windows PowerShell в текущем сеансе.

[Remove-Job](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

Удаляет фоновое задание Windows PowerShell.

[Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

Запускает фоновое задание Windows PowerShell.

[Stop-Job](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

Останавливает фоновое задание Windows PowerShell.

[Wait-Job](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

Отключает командную строку до завершения выполнения одного или нескольких фоновых заданий Windows PowerShell, запущенных в этом сеансе.

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
