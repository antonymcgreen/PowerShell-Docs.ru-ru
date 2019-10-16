---
title: Типы выходных данных командлета | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK], output
ms.assetid: 547e6695-e936-4cac-a90b-417d0dab393d
caps.latest.revision: 12
ms.openlocfilehash: 3efa98c7aa22fdaee8042bae99282aea0618ef5f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369293"
---
# <a name="types-of-cmdlet-output"></a>Типы выходных данных командлета

PowerShell предоставляет несколько методов, которые могут вызываться командлетами для создания выходных данных. Эти методы используют определенную операцию для записи выходных данных в конкретный поток данных, например поток данных об успешном выполнении или поток данных ошибок. В этой статье описываются типы выходных данных и методы, используемые для их создания.

## <a name="types-of-output"></a>Типы выходных данных

### <a name="success-output"></a>Выходные данные успешного выполнения

Командлеты могут сообщать об успешном выполнении, возвращая объект, который может быть обработан следующей командой в конвейере. После успешного выполнения командлета Командлет вызывает метод [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . Рекомендуется вызывать этот метод вместо методов [System. Console. WriteLine](/dotnet/api/System.Console.WriteLine) или [System. Management. Automation. host. пшостусеринтерфаце. WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine) .

Можно указать параметр **PassThru** для командлетов, которые обычно не возвращают объекты.
Если в командной строке указан параметр **PassThru** , то командлету будет предложено вернуть объект. Пример командлета с параметром **PassThru** см. в разделе [Add-History](/powershell/module/Microsoft.PowerShell.Core/Add-History).

### <a name="error-output"></a>Вывод ошибок

Командлеты могут сообщать об ошибках. При возникновении неустранимой ошибки командлет создает исключение. При возникновении неустранимой ошибки командлет вызывает метод [System. Management. Automation. Provider. кмдлетпровидер. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) , чтобы отправить запись об ошибке в поток данных об ошибке. Дополнительные сведения об отчетах об ошибках см. в разделе [Основные понятия отчетов об ошибках](./error-reporting-concepts.md).

### <a name="verbose-output"></a>Подробный вывод

Командлеты могут предоставить вам полезную информацию, пока командлет правильно обрабатывает записи, вызвав метод [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) . Метод создает подробные сообщения, указывающие, как выполняется действие.

По умолчанию подробные сообщения не отображаются. При выполнении командлета для вывода этих сообщений можно указать параметр **verbose** . **Verbose** — это общий параметр, доступный для всех командлетов.

### <a name="progress-output"></a>Вывод хода выполнения

Командлеты могут предоставлять сведения о ходе выполнения, когда командлет выполняет задачи, выполнение которых занимает много времени, например рекурсивное копирование каталога. Чтобы отобразить сведения о ходе выполнения, командлет вызывает метод [System. Management. Automation. командлет. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .

### <a name="debug-output"></a>Выходные данные отладки

Командлеты могут предоставлять сообщения отладки, которые полезны при устранении неполадок с кодом командлета. Чтобы отобразить отладочную информацию, командлет вызывает метод [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) .

По умолчанию сообщения отладки не отображаются. При запуске командлета для вывода этих сообщений можно указать параметр **Debug** . **Debug** — это общий параметр, доступный для всех командлетов.

### <a name="warning-output"></a>Вывод предупреждений

Командлеты могут отображать предупреждающие сообщения, вызывая метод [System. Management. Automation. командлет. вритеварнинг](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) .

По умолчанию отображаются предупреждающие сообщения. Однако предупреждающие сообщения можно настроить с помощью переменной `$WarningPreference` или с помощью параметров **verbose** и **Debug** при вызове командлета.

## <a name="displaying-output"></a>Отображение выходных данных

Для всех вызовов метода Write отображение содержимого определяется определенными переменными среды выполнения. Исключением является метод [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . Используя эти переменные, можно сделать соответствующий вызов записи в правильном месте в коде и не беспокоиться о том, когда или когда должны отображаться выходные данные.

## <a name="accessing-the-output-functionality-of-a-host-application"></a>Доступ к функции вывода ведущего приложения

Можно также разработать командлет для прямого доступа к выходным функциям ведущего приложения с помощью среды выполнения PowerShell. Использование API хоста, предоставляемых PowerShell, а не [System. Console](/dotnet/api/System.Console) или [System. Windows. Forms](/dotnet/api/System.Windows.Forms) , гарантирует, что командлет будет работать с различными узлами. Например: узел консоли **PowerShell. exe** , графический узел **Powershell_ise. exe** , узел удаленного взаимодействия PowerShell и узлы сторонних производителей.

## <a name="see-also"></a>См. также статью

[Основные понятия отчетов об ошибках](./error-reporting-concepts.md)

[Обзор командлетов](./cmdlet-overview.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)