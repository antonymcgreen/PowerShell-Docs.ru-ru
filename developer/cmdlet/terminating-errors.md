---
title: Завершение ошибки | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b804e738-aefa-41bb-9649-f9ed897fd96c
caps.latest.revision: 8
ms.openlocfilehash: d1967fe7996f75ec5229920f7ec49aa5ff6bdbfd
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059241"
---
# <a name="terminating-errors"></a>Прерывающие ошибки

В этом разделе рассматривается метод, используемый для отчетов, завершение ошибки. Также описывается вызов метода в командлет, и в нем рассматриваются исключения, которые могут быть возвращены средой выполнения Windows PowerShell, при вызове метода.

При прекращении возникает ошибка, командлет должен сообщить об ошибке, вызвав [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) метод. Этот метод позволяет командлету отправлять запись об ошибке, которое описывает условие, вызвавшее Неустранимая ошибка. Дополнительные сведения о записи об ошибках, см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

Когда [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) вызывается метод, среда выполнения Windows PowerShell останавливает выполнение конвейера и без возможности восстановления создает [ System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) исключение. Все последующие попытки вызова [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError), или несколько других интерфейсов API вызывает исключение вызовы[ System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) исключение.

[System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) исключение также может возникнуть, если другому командлету в конвейере выдает неустранимую ошибку, если пользователь запросил остановить конвейера или конвейер остановлен до завершения по любой причине. Командлет не требуется перехватывать [System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) исключение, если необходимо открыть очистку ресурсов или внутреннего состояния.

Командлеты можно создать любое количество выходных объектов или устранимые ошибки до появления неустранимую ошибку. Тем не менее Неустранимая ошибка без возможности восстановления останавливается конвейера, а не Дополнительные выходные данные, завершение ошибки, или устранимые ошибки может быть включено в отчет.

Командлеты можно вызвать [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) только из потока, который вызвал [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), или [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод обработки ввода. Не пытайтесь вызвать [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) или [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из другого потока. Вместо этого ошибки необходимо передать обратно в основной поток.

Это возможно для командлета, для создания исключения в своей реализации [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), или [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод. Любое исключение, возникшее из этих методов (за исключением нескольких серьезные ошибки, которые остановить узел Windows PowerShell) интерпретируется как неустранимую ошибку, которая останавливает конвейера, но не в Windows PowerShell в целом. (Это относится только к командлет основной поток. Неперехваченных исключений в потоков, созданных с помощью командлета в общем случае остановка узлов Windows PowerShell.) Мы рекомендуем использовать [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) вместо создания исключения, так как запись об ошибке дополнительная информация об ошибке, что полезно для конечному пользователю. Командлеты должны учитываться в случае управляемого кода, рекомендуется от перехват и обработка всех исключений (`catch (Exception e)`). Преобразуйте только исключения известного и ожидаемого типов в записи об ошибках.

## <a name="see-also"></a>См. также

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Записи об ошибках PowerShell Windows](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
