---
ms.date: 01/18/2019
ms.topic: reference
title: Типы выходных данных командлета
description: Типы выходных данных командлета
ms.openlocfilehash: 591b7699e951db9016e48d5ef623265e23791e11
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660506"
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

### <a name="verbose-output"></a>Подробные выходные данные

Командлеты могут предоставить вам полезную информацию, пока командлет правильно обрабатывает записи, вызвав метод [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) . Метод создает подробные сообщения, указывающие, как выполняется действие.

По умолчанию подробные сообщения не отображаются. При выполнении командлета для вывода этих сообщений можно указать параметр **verbose** . **Verbose** — это общий параметр, доступный для всех командлетов.

### <a name="progress-output"></a>Вывод хода выполнения

Командлеты могут предоставлять сведения о ходе выполнения, когда командлет выполняет задачи, выполнение которых занимает много времени, например рекурсивное копирование каталога. Чтобы отобразить сведения о ходе выполнения, командлет вызывает метод [System. Management. Automation. командлет. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .

### <a name="debug-output"></a>Выходные данные отладки

Командлеты могут предоставлять сообщения отладки, которые полезны при устранении неполадок с кодом командлета. Чтобы отобразить отладочную информацию, командлет вызывает метод [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) .

По умолчанию сообщения отладки не отображаются. При запуске командлета для вывода этих сообщений можно указать параметр **Debug** . **Debug** — это общий параметр, доступный для всех командлетов.

### <a name="warning-output"></a>Вывод предупреждений

Командлеты могут отображать предупреждающие сообщения, вызывая метод [System. Management. Automation. командлет. вритеварнинг](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) .

По умолчанию отображаются предупреждающие сообщения. Однако предупреждающие сообщения можно настроить с помощью `$WarningPreference` переменной или с помощью параметров **verbose** и **Debug** при вызове командлета.

## <a name="displaying-output"></a>Отображение выходных данных

Для всех вызовов метода Write отображение содержимого определяется определенными переменными среды выполнения. Исключением является метод [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . Используя эти переменные, можно сделать соответствующий вызов записи в правильном месте в коде и не беспокоиться о том, когда или когда должны отображаться выходные данные.

## <a name="accessing-the-output-functionality-of-a-host-application"></a>Доступ к функции вывода ведущего приложения

Можно также разработать командлет для прямого доступа к выходным функциям ведущего приложения с помощью среды выполнения PowerShell. Использование API хоста, предоставляемых PowerShell, а не [System. Console](/dotnet/api/System.Console) или [System. Windows. Forms](/dotnet/api/System.Windows.Forms) , гарантирует, что командлет будет работать с различными узлами. Например: узел консоли **powershell.exe** , **powershell_ise.exe** графический узел, узел удаленного взаимодействия PowerShell и сторонние узлы.

## <a name="see-also"></a>См. также раздел

[Основные понятия, связанные с отчетами об ошибках](./error-reporting-concepts.md)

[Общие сведения о командлетах](./cmdlet-overview.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
