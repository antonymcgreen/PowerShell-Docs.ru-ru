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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853930"
---
# <a name="types-of-cmdlet-output"></a>Типы выходных данных командлета

PowerShell предоставляет несколько методов, которые могут быть вызваны командлеты для создания выходных данных. Эти методы используют какой-либо операции записывать выходные данные в поток данных, например поток данных успеха или ошибки потока данных. В этой статье описываются типы выходных данных и методы, используемые для их создания.

## <a name="types-of-output"></a>Типы вывода.

### <a name="success-output"></a>Выходные данные

Командлеты можно сообщать об успехе, возвращая объект, который может быть обработан с помощью следующей команды в конвейере. После командлета успешно выполнил действие, командлет вызывает [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) метод. Мы рекомендуем использовать этот метод вместо [System.Console.WriteLine](/dotnet/api/System.Console.WriteLine) или [System.Management.Automation.Host.PSHostUserInterface.WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine) методы.

Вы можете предоставить **PassThru** параметр для командлетов, которые обычно не возвращают объекты-переключатель.
Когда **PassThru** в командной строке указан параметр-переключатель, командлет получает запрос для возврата объекта. Например, командлет, который имеет **PassThru** параметр, см. в разделе [Add-History](/powershell/module/Microsoft.PowerShell.Core/Add-History).

### <a name="error-output"></a>Вывод ошибок

Командлеты можно сообщать об ошибках. Если происходит неустранимая ошибка, командлет создает исключение. При возникновении неустранимой ошибки вызывает командлет [System.Management.Automation.Provider.CmdletProvider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) метод для отправки записи об ошибке в поток данных ошибок. Дополнительные сведения об отчетах об ошибках см. в разделе [основные понятия служб Reporting ошибка](./error-reporting-concepts.md).

### <a name="verbose-output"></a>Подробный вывод

Командлеты могут сообщить полезные сведения для вас, хотя командлет правильно обрабатывает записи путем вызова [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) метод. Метод создает подробные сообщения, которые указывают, как действие будет продолжена.

По умолчанию подробные сообщения не отображаются. Можно указать **Verbose** параметра при запуске командлета для отображения этих сообщений. **Verbose** — это общий параметр, которая доступна для всех командлетов.

### <a name="progress-output"></a>Выходные данные о ходе выполнения

Командлеты можно предоставлять сведения о ходе выполнения вам при выполнении задач, которые занять много времени для завершения, например каталог рекурсивное копирование командлет. Чтобы отобразить сведения о ходе выполнения командлета вызывает [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) метод.

### <a name="debug-output"></a>Выходные данные отладки

Командлеты можно предоставить отладочные сообщения, которые могут быть полезны при устранении неполадок код командлета. Чтобы отобразить сведения об отладке командлет вызывает [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) метод.

По умолчанию сообщения отладки не отображаются. Можно указать **Отладка** параметра при запуске командлета для отображения этих сообщений. **Отладка** — это общий параметр, которая доступна для всех командлетов.

### <a name="warning-output"></a>Вывод предупреждения

Командлеты можно отображать предупреждающие сообщения путем вызова [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) метод.

По умолчанию отображаются предупреждающие сообщения. Тем не менее, можно настроить предупреждения с помощью `$WarningPreference` переменных или с помощью **Verbose** и **Отладка** параметров при вызове командлета.

## <a name="displaying-output"></a>Отображение выходных данных

Отображение содержимого для всех вызовов метода записи определяется переменные конкретную среду выполнения. Исключением является [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) метод. С помощью этих переменных, можно внести соответствующие записи вызовов в верном месте в коде, не беспокоясь о, когда или если выходные данные должны отображаться.

## <a name="accessing-the-output-functionality-of-a-host-application"></a>Доступ к функциональным возможностям выходных данных, ведущего приложения

Можно также создать командлет для прямого доступа к функциональные возможности вывода ведущего приложения через среду выполнения PowerShell. С помощью API, предоставляемые PowerShell вместо узла [System.Console](/dotnet/api/System.Console) или [System.Windows.Forms](/dotnet/api/System.Windows.Forms) гарантирует, что командлет будет работать с множеством узлов. Например: **powershell.exe** консольное размещение **powershell_ise.exe** графический узла, узла удаленного взаимодействия PowerShell и узлы независимых производителей.

## <a name="see-also"></a>См. также:

[Основные понятия служб Reporting ошибки](./error-reporting-concepts.md)

[Обзор командлетов](./cmdlet-overview.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)