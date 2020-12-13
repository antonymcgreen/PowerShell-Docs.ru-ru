---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры командлетов
description: Примеры командлетов
ms.openlocfilehash: 6ee149f611e5af5c45a62363e19e66bf200c0c0a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668258"
---
# <a name="cmdlet-samples"></a>Примеры командлетов

В этом разделе показан пример кода, предоставляемого в пакете SDK для Windows PowerShell 2.0. Вы можете скопировать код из статьи или открыть исходные файлы, установленные с пакетом SDK. [Пакет средств разработки программного обеспечения (пакет SDK) для Windows PowerShell 2.0](https://www.microsoft.com/download/details.aspx?id=2560) содержит файлы сведений, исходные файлы и файлы проектов Visual Studio для каждого примера. После установки пакета SDK примеры можно найти в папке `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.

## <a name="in-this-section"></a>в этом разделе

[Пример GetProcessSample01](./getprocesssample01-sample.md) Показано, как написать командлет, который будет получать сведения о процессах на локальном компьютере.

[Пример GetProcessSample02](./getprocesssample02-sample.md) Показано, как написать командлет, который будет получать сведения о процессах на локальном компьютере. Он поддерживает параметр Name, который можно использовать для определения процессов, которые необходимо получить.

[Пример GetProcessSample03](./getprocesssample03-sample.md) Показано, как написать командлет, который будет получать сведения о процессах на локальном компьютере. Он поддерживает параметр Name, который может принимать объект из конвейера или значение из свойства объекта, имя свойства которого совпадает с именем параметра.

[Пример GetProcessSample04](./getprocesssample04-sample.md) Показано, как написать командлет, который будет получать сведения о процессах на локальном компьютере. Он создает неустранимую ошибку, если при получении процесса возникает ошибка.

[Пример GetProcessSample05](./getprocesssample05-sample.md) Показано полную версию командлета Get-Proc.

[Пример StopProcessSample01](./stopprocesssample01-sample.md) Показано, как написать командлет, который обращается к пользователю перед попыткой завершить процесс, и как реализовать параметр `PassThru`, который указывает, что пользователь хочет, чтобы командлет возвращал объект.

[Пример StopProcessSample02](./stopprocesssample02-sample.md) Показано, как написать командлет, который будет записывать отладочные, подробные и предупреждающие сообщения при завершении процессов на локальном компьютере.

[Пример StopProcessSample03](./stopprocesssample03-sample.md) Показано, как написать командлет, параметры которого имеют псевдонимы и поддерживают подстановочные знаки.

[Пример StopProcessSample04](./stopprocesssample04-sample.md) Показано, как написать командлет, который объявляет наборы параметров и определяет набор параметров по умолчанию, а также может принимать входной объект.

[Пример Events01](./events01-sample.md) Показано, как создать командлет, который разрешает пользователю регистрировать события, вызванные [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher). С помощью этого командлета пользователи могут, например, зарегистрировать действие, выполняемое при создании файла в определенном каталоге. Этот пример является производным от базового класса [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase).

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
