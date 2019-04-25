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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068693"
---
# <a name="background-jobs"></a>Фоновые задания

Командлеты действие можно выполнить их внутри, так и Windows PowerShell*фоновое задание*. При выполнении командлета как фоновое задание работу асинхронно в отдельном потоке, отдельном от потока конвейер, используя командлет. С точки зрения пользователя, при запуске командлета в качестве фонового задания, Командная строка возвращается немедленно даже в том случае, если задание занимает продолжительное время, и пользователь может продолжить работу без прерывания во время выполнения задания.

## <a name="background-jobs-child-jobs-and-the-job-repository"></a>Фоновые задания, дочерние задания и репозиторий заданий

Объект задания, который возвращается с помощью командлетов, которые поддерживают фоновые задания определяет задание. ( [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) командлет также возвращает объект задания.) Имя задания, идентификатор, который используется для указания задания, сведения о состоянии и дочерние задания, включаются в это определение. Задание не выполнять часть работы. Каждый фоновое задание имеет по крайней мере одно дочернее задание, так как дочернее задание выполняет фактическую работу. При выполнении командлета, чтобы работа выполняется в качестве фонового задания, командлет необходимо добавить задание и дочерние задания общим хранилищем, называется *репозиторий заданий для*.

Дополнительные сведения об обработке фоновых заданий в командной строке см. в разделе ниже:

- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [about_Job_Details](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [about_Remote_Jobs](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a>Написание командлетов, который запускается как фоновое задание

Чтобы написать командлет, который может выполняться как фоновое задание, необходимо выполнить следующие задачи:

- Определение `asJob` параметр-переключатель, чтобы пользователь может решить, следует ли выполнять командлет как фоновое задание.

- Создайте объект, который является производным от [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) класса. Этот объект может быть объект пользовательские задания или объект задания, предоставляемыми Windows PowerShell, такими как [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) объекта.

- Добавьте в метод обработки записей, `if` инструкцию, которая определяет, следует ли запускать командлет как фоновое задание.

- Для задания пользовательских объектов Реализуйте класс задания.

- Возвращает соответствующие объекты, в зависимости от того, выполняется ли команда как фоновое задание.

Пример кода см. в разделе [как заданий поддержки](./how-to-support-jobs.md).

## <a name="background-job-related-apis"></a>API-интерфейсов, связанных с заданием фона

Следующие API-интерфейсы, предоставляемые Windows PowerShell для управления фоновыми заданиями.

[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) производный объекты пользовательских заданий. Это абстрактный класс.

[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) управляет и предоставляет сведения о текущем active фоновые задания.

[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) определяет состояние фонового задания. Следующие состояния работы, запущена и остановлена.

[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) предоставляет сведения о состоянии фонового задания и если изменить последнее состояние было вызвано сообщение об ошибке, а причина задание перешло в ее текущем состоянии.

[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) предоставляет аргументы для события, которое возникает, когда фоновое задание меняет состояние.

## <a name="windows-powershell-job-cmdlets"></a>Командлеты Windows PowerShell заданий

Имеются следующие командлеты Windows PowerShell для управления фоновыми заданиями.

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

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
