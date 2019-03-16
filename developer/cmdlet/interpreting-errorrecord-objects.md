---
title: Интерпретация объекты ErrorRecord | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a65b964-5bc6-4ade-a66b-b6afa7351ce7
caps.latest.revision: 9
ms.openlocfilehash: 32ebf2531237bfd1042310ccc4155193a58401fd
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058782"
---
# <a name="interpreting-errorrecord-objects"></a>Интерпретация объектов ErrorRecord

В большинстве случаев [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) представляет устранимую ошибку, созданные команды или сценария. Завершение ошибки можно также указать дополнительные сведения в ErrorRecord через [System.Management.Automation.Icontainserrorrecord](/dotnet/api/System.Management.Automation.IContainsErrorRecord) интерфейс.

Если вы хотите написать обработчик ошибок в скрипте или узла для обработки определенных ошибок, возникающих во время выполнения команды или сценария, необходимо интерпретировать [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объектом, чтобы определить ли он Представляет класс ошибки, необходимо обработать.

Когда командлет встречает точки в конце или устранимую ошибку, оно должно создавать записи об ошибке, которое описывает условие ошибки. Ведущее приложение необходимо изучить эти записи об ошибках и выполните действие позволит устранить ошибки. Ведущее приложение также необходимо изучить записи об ошибках для устранимые ошибки, которые не удалось обработать запись, но смогли продолжить, и она должна изучить записи об ошибках для неустранимых ошибок, вызвавшего конвейер остановить.

> [!NOTE]
> Для прерывающие ошибки вызывает командлет [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) метод. Устранимые ошибки вызывает командлет [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод.

## <a name="error-record-design"></a>Ошибка записи разработки

Записи об ошибках призваны обеспечить Дополнительные сведения об ошибке, но недоступный в исключениях гарантией того, что обобщенную информацию в каждой записи ошибка уникальна. Эта уникальность позволяет ведущему приложению для проверки различных частей запись об ошибке, чтобы его можно определить условие ошибки, и необходимо выполнить действие узла.

## <a name="interpreting-error-records"></a>Интерпретация записей ошибок

Можно просмотреть отдельные части запись об ошибке, чтобы определить ошибку. Ниже приведены эти части:

- Категория ошибки

- Ошибка исключения

- Идентификатор ошибки полное (FQID)

- Другие сведения

### <a name="the-error-category"></a>Категория ошибки

Категория ошибки записи об ошибке является одним из предопределенных констант, предоставляемые [System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory) перечисления. Эти сведения можно получить через [System.Management.Automation.ErrorRecord.CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) свойство [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объекта.

Командлет можно указать категории CloseError, OpenError, InvalidType, ошибка чтения и WriteError и другие категории ошибок. Ведущее приложение может использовать категорию ошибки для записи группы ошибок.

### <a name="the-exception"></a>Исключение

Исключение, включенных в запись об ошибке предоставляется с помощью командлета и может осуществляться через [System.Management.Automation.ErrorRecord.Exception*](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) свойство [ System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объекта.

Ведущие приложения могут использовать `is` ключевое слово, чтобы определить, что исключение определенного класса или производного класса. Лучше Branch на тип исключения, как показано в следующем примере.

`if (MyNonTerminatingError.Exception is AccessDeniedException)`

Таким образом, можно перехватить производных классов. Тем не менее существуют проблемы, если исключение десериализуется.

### <a name="the-fqid"></a>FQID

FQID является наиболее подходящим сведения, которые можно использовать для определения ошибки. Это строка, которая включает в себя определенный идентификатор командлет, имя класса cmdlet и источник, сообщила об ошибке. В общем случае запись об ошибке аналогично записи события в журнал событий Windows. FQID является аналогом следующий кортеж, который идентифицирует класс записи события: (*имя журнала*, *источника*, *событие с Идентификатором*).

FQID предназначен для проверяться в виде одной строки. Тем не менее случаях существуют, в которых идентификатор ошибки предназначен для синтаксического анализа, ведущим приложением. Следующий пример — это идентификатор правильный формат полных ошибки.

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand.`

В предыдущем примере первый токен — ошибка идентификатора, который следует имя класса командлета. Идентификатор ошибки может быть один токен, или он может быть идентификатор с разделителями точками, который позволяет для ветвления для проверки идентификатора. Не используйте пробелы или знаки препинания в идентификатор ошибки. Это особенно важно, не следует использовать запятую; для разделения идентификатор и имя класса командлета по Windows PowerShell используется запятая.

### <a name="other-information"></a>Другие сведения

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) объект также может предоставлять сведения, описывающие среду, в которой произошла ошибка. Эта информация включает сведения об ошибке, сведения о вызове и целевой объект, который обрабатывался во время возникновения ошибки. Несмотря на то, что эти сведения могут пригодиться ведущему приложению, он обычно не используется для идентификации ошибки. Эти сведения можно получить через следующие свойства:

[System.Management.Automation.ErrorRecord.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails)

[System.Management.Automation.ErrorRecord.InvocationInfo](/dotnet/api/System.Management.Automation.ErrorRecord.InvocationInfo)

[System.Management.Automation.ErrorRecord.TargetObject](/dotnet/api/System.Management.Automation.ErrorRecord.TargetObject)

## <a name="see-also"></a>См. также

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)

[System.Management.Automation.Errorcategory](/dotnet/api/System.Management.Automation.ErrorCategory)

[System.Management.Automation.Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[Добавление устранимую командлета отчетов об ошибках](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Отчетов об ошибках Windows PowerShell](./error-reporting-concepts.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
