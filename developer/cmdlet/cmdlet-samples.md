---
title: Примеры командлетов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b99d53fc-0af9-426b-82ce-09955e031d4b
caps.latest.revision: 13
ms.openlocfilehash: d919d4ad8554e762230c1448d81b50e27c38ba99
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863370"
---
# <a name="cmdlet-samples"></a>Примеры командлетов

В этом разделе описан пример кода, который предоставляется в пакете SDK для Windows PowerShell 2.0. Можно скопировать код из подразделы этого раздела, или открыть исходные файлы установки с пакетом SDK. [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560) предоставляет файлы ReadMe, исходные файлы и файлы проекта Visual Studio для каждого примера. С пакетом SDK установлен, можно найти примеры в разделе `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` папки.

## <a name="in-this-section"></a>Содержание

[Пример GetProcessSample01](./getprocesssample01-sample.md) в этом примере показано, как написать командлет, который извлекает процессы на локальном компьютере.

[Пример GetProcessSample02](./getprocesssample02-sample.md) в этом примере показано, как написать командлет, который извлекает процессы на локальном компьютере. Он предоставляет параметр Name, который может использоваться для указания процессов, которые требуется получить.

[Пример GetProcessSample03](./getprocesssample03-sample.md) в этом примере показано, как написать командлет, который извлекает процессы на локальном компьютере. Он предоставляет параметр Name, которое может принять объект из конвейера или значения из свойства объекта, имя свойства совпадает с именем параметра.

[Пример GetProcessSample04](./getprocesssample04-sample.md) в этом примере показано, как написать командлет, который извлекает процессы на локальном компьютере. Устранимые ошибки возникает в том случае, если произошла ошибка при получении процесса.

[Пример GetProcessSample05](./getprocesssample05-sample.md) в этом примере показано полную версию командлет Get-Proc.

[Пример StopProcessSample01](./stopprocesssample01-sample.md) в этом примере показано, как создать командлет, который запрашивает отзывы от пользователя, прежде чем она пытается остановить процесс, а также способы реализации `PassThru` параметр, указывающий, что пользователю командлет для возвращения объект.

[Пример StopProcessSample02](./stopprocesssample02-sample.md) в этом примере показано, как написать командлет, который записывает отладки, verbose, сообщения и предупреждения во время остановки процессов на локальном компьютере.

[Пример StopProcessSample03](./stopprocesssample03-sample.md) в этом примере показано, как написать, параметры которых имеют псевдонимы, командлет поддерживает символы-шаблоны.

[Пример StopProcessSample04](./stopprocesssample04-sample.md) в этом примере показано, как написать командлет, который объявляет наборов параметров, указывает параметр по умолчанию значение и может принимать входной объект.

[Пример Events01](./events01-sample.md) в этом примере показано, как создать командлет, который позволяет пользователю для регистрации событий, вызываемых [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher). С помощью этого командлета пользователи могут например, зарегистрировать действие для выполнения при создании файла в конкретном каталоге. В этом примере является производным от [Microsoft.Powershell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) базового класса.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
