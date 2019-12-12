---
title: Прерывание ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b804e738-aefa-41bb-9649-f9ed897fd96c
caps.latest.revision: 8
ms.openlocfilehash: d1967fe7996f75ec5229920f7ec49aa5ff6bdbfd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369333"
---
# <a name="terminating-errors"></a>Прерывающие ошибки

В этом разделе обсуждается метод, используемый для сообщения о прекращении ошибок. В нем также обсуждается вызов метода из командлета и обсуждаются исключения, которые могут возвращаться средой выполнения Windows PowerShell при вызове метода.

При возникновении завершающей ошибки командлет должен сообщить об ошибке, вызвав метод [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) . Этот метод позволяет командлету отправить запись об ошибке, описывающую условие, вызвавшее завершающую ошибку. Дополнительные сведения о записях об ошибках см. в статье [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).

При вызове метода [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) среда выполнения Windows PowerShell безвозвратно останавливает выполнение конвейера и создает исключение [System. Management. Automation. пипелинестоппедексцептион](/dotnet/api/System.Management.Automation.PipelineStoppedException) . При последующих попытках вызова метода [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)или нескольких других API эти вызовы вызывают исключение [System. Management. Automation. пипелинестоппедексцептион](/dotnet/api/System.Management.Automation.PipelineStoppedException) .

Исключение [System. Management. Automation. пипелинестоппедексцептион](/dotnet/api/System.Management.Automation.PipelineStoppedException) также может возникать, если другой командлет в конвейере сообщает об завершающей ошибке, если пользователь попросил остановить конвейер, или если конвейер был остановлен до завершения по какой-либо причине. Командлету не требуется перехватывать исключение [System. Management. Automation. пипелинестоппедексцептион](/dotnet/api/System.Management.Automation.PipelineStoppedException) , если оно не должно очищать открытые ресурсы или его внутреннее состояние.

Командлеты могут записывать любое количество выходных объектов или неустранимых ошибок, прежде чем сообщать об завершающей ошибке. Тем не менее, завершающая ошибка окончательно останавливает конвейер, а дальнейшие выходные данные, завершающие ошибки или неустранимые ошибки могут быть переданы.

Командлеты могут вызывать [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) только из потока, который вызвал метод обработки входных данных [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)Management. Automation. командлет. ProcessRecord или [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Не пытайтесь вызвать [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) или [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из другого потока. Вместо этого ошибки должны быть переданы обратно в основной поток.

Командлет может вызвать исключение в реализации метода [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)или [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) . Любое исключение, вызванное этими методами (за исключением нескольких серьезных ошибок, которые останавливают узел Windows PowerShell), интерпретируется как завершающая ошибка, которая останавливает конвейер, но не Windows PowerShell в целом. (Это относится только к основному потоку командлета. Неперехваченные исключения в потоках, порожденных командлетом, в общем случае, приостановка работы узла Windows PowerShell.) Рекомендуется использовать [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) вместо создания исключения, поскольку запись об ошибке предоставляет дополнительные сведения о состоянии ошибки, что полезно для конечного пользователя. Командлеты должны учитывать рекомендации управляемого кода для перехвата и обработки всех исключений (`catch (Exception e)`). Преобразование исключений известных и ожидаемых типов в записи об ошибках.

## <a name="see-also"></a>См. также:

[System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. Пипелинестоппедексцептион](/dotnet/api/System.Management.Automation.PipelineStoppedException)

[System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
