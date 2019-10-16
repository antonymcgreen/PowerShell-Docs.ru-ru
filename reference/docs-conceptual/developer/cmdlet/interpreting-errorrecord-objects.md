---
title: Интерпретация объектов Ерроррекорд | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a65b964-5bc6-4ade-a66b-b6afa7351ce7
caps.latest.revision: 9
ms.openlocfilehash: 32ebf2531237bfd1042310ccc4155193a58401fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365423"
---
# <a name="interpreting-errorrecord-objects"></a>Интерпретация объектов ErrorRecord

В большинстве случаев объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) представляет устранимую ошибку, созданную командой или сценарием. В случае прерывания ошибок можно также указать дополнительные сведения в Ерроррекорд через интерфейс [System. Management. Automation. иконтаинсерроррекорд](/dotnet/api/System.Management.Automation.IContainsErrorRecord) .

Если вы хотите написать обработчик ошибок в скрипте или на узле для обработки ошибок, происходящих во время выполнения команды или скрипта, необходимо интерпретировать объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) , чтобы определить, представляет ли он класс ошибка, которую требуется обработать.

Когда командлет обнаруживает неустранимую или устранимую ошибку, он должен создать запись об ошибке, которая описывает условие ошибки. Ведущее приложение должно исследовать эти записи об ошибках и выполнить любое действие, чтобы устранить ошибку. Ведущее приложение также должно исследовать записи об ошибках для неустранимых ошибок, которые не удалось обработать запись, но могли продолжать работу, и должны исследовать записи об ошибках для завершения процесса, вызвавшего остановку конвейера.

> [!NOTE]
> Для завершения ошибок командлет вызывает метод [System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) . Для неустранимых ошибок командлет вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) .

## <a name="error-record-design"></a>Структура записи ошибок

Записи об ошибках предназначены для предоставления дополнительных сведений об ошибках, недоступных в исключениях и гарантирующих уникальность Объединенных сведений в каждой записи об ошибке. Это уникальность позволяет ведущему приложению проверять различные части записи об ошибке, чтобы оно определяло условие ошибки и действие, которое должен выполнить узел.

## <a name="interpreting-error-records"></a>Интерпретация записей об ошибках

Для обнаружения ошибки можно изучить несколько частей записи об ошибке. В число этих частей входят следующие.

- Категория ошибки

- Исключение ошибки

- Полный идентификатор ошибки (ФКИД)

- Другие сведения

### <a name="the-error-category"></a>Категория ошибки

Категория ошибок записи об ошибке является одной из стандартных констант, предоставляемых перечислением [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory) . Эта информация доступна через свойство [System. Management. Automation. ерроррекорд. CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) объекта [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) .

Командлет может указывать категории Клосиррор, Опенеррор, Инвалидтипе, Реадеррор и WriteError, а также другие категории ошибок. Ведущее приложение может использовать категорию ошибок для записи групп ошибок.

### <a name="the-exception"></a>Исключение

Исключение, включенное в запись ошибки, предоставляется командлетом и доступно через свойство [System. Management. Automation. ерроррекорд. Exception *](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) объекта [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) .

Ведущие приложения могут использовать ключевое слово `is`, чтобы указать, что исключение относится к определенному классу или производному классу. Лучше создать ветвь для типа исключения, как показано в следующем примере.

`if (MyNonTerminatingError.Exception is AccessDeniedException)`

Таким образом, вы перехватываете производные классы. Однако при десериализации исключения возникают проблемы.

### <a name="the-fqid"></a>ФКИД

ФКИД — это наиболее специфичная информация, которую можно использовать для обнаружения ошибки. Это строка, которая включает определяемый командлетом идентификатор, имя класса командлета и источник, который сообщил об ошибке. Как правило, запись об ошибке аналогична записи события в журнале событий Windows. ФКИД является аналогом следующего кортежа, который определяет класс записи события: (*имя журнала*, *источник*, *идентификатор события*).

ФКИД предназначен для проверки в виде одной строки. Однако существуют случаи, в которых идентификатор ошибки предназначен для анализа ведущим приложением. Следующий пример представляет собой полный идентификатор ошибки с правильным форматом.

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand.`

В предыдущем примере первым маркером является идентификатор ошибки, за которым следует имя класса командлета. Идентификатор ошибки может быть одним токеном или идентификатором, разделенным точкой с запятой, который позволяет ветвление при проверке идентификатора. Не используйте пробелы или знаки препинания в идентификаторе ошибки. Особенно важно не использовать запятую; Запятая используется Windows PowerShell для разделения идентификатора и имени класса командлета.

### <a name="other-information"></a>Другие сведения

Объект [System. Management. Automation. ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord) также может предоставлять сведения, описывающие среду, в которой произошла ошибка. Эти сведения включают такие элементы, как сведения об ошибке, сведения о вызовах и целевой объект, который был обработан при возникновении ошибки. Хотя эта информация может быть полезной для ведущего приложения, она обычно не используется для обнаружения ошибки. Эти сведения доступны в следующих свойствах:

[System. Management. Automation. Ерроррекорд. ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails)

[System. Management. Automation. Ерроррекорд. Инвокатионинфо](/dotnet/api/System.Management.Automation.ErrorRecord.InvocationInfo)

[System. Management. Automation. Ерроррекорд. TargetObject](/dotnet/api/System.Management.Automation.ErrorRecord.TargetObject)

## <a name="see-also"></a>См. также:

[System. Management. Automation. Ерроррекорд](/dotnet/api/System.Management.Automation.ErrorRecord)

[System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory)

[System. Management. Automation. Ерроркатегоринфо](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System. Management. Automation. командлет. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[Добавление в командлет незавершающего сообщения об ошибках](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Отчеты об ошибках Windows PowerShell](./error-reporting-concepts.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
