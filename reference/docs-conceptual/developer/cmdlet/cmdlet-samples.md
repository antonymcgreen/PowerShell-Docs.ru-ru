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
ms.openlocfilehash: 0fa4a5f804586c51ae6a36121f9aab041b0989cc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365883"
---
# <a name="cmdlet-samples"></a>Примеры командлетов

В этом разделе описывается пример кода, предоставляемого в пакете SDK для Windows PowerShell 2,0. Вы можете скопировать код из подразделов этого раздела или открыть исходные файлы, установленные с помощью пакета SDK. [Пакет средств разработки программного обеспечения (SDK) для Windows PowerShell 2,0](https://www.microsoft.com/en-us/download/details.aspx?id=2560) предоставляет файлы Readme, исходные файлы и файлы проектов Visual Studio для каждого примера. После установки пакета SDK можно найти образцы в папке `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.

## <a name="in-this-section"></a>Содержание

[Пример GetProcessSample01](./getprocesssample01-sample.md) В этом примере показано, как написать командлет, который получает процессы на локальном компьютере.

[Пример GetProcessSample02](./getprocesssample02-sample.md) В этом примере показано, как написать командлет, который получает процессы на локальном компьютере. Он предоставляет параметр name, который можно использовать для указания процессов, которые необходимо получить.

[Пример GetProcessSample03](./getprocesssample03-sample.md) В этом примере показано, как написать командлет, который получает процессы на локальном компьютере. Он предоставляет параметр name, который может принимать объект из конвейера или значение свойства объекта, имя свойства которого совпадает с именем параметра.

[Пример GetProcessSample04](./getprocesssample04-sample.md) В этом примере показано, как написать командлет, который получает процессы на локальном компьютере. Она создает неустранимую ошибку в случае возникновения ошибки при получении процесса.

[Пример GetProcessSample05](./getprocesssample05-sample.md) В этом примере показана полная версия командлета Get-proc.

[Пример StopProcessSample01](./stopprocesssample01-sample.md) В этом примере показано, как написать командлет, запрашивающий отзыв от пользователя перед попыткой его завершения, и как реализовать параметр `PassThru`, который указывает, что пользователь хочет, чтобы командлет возвращал объект.

[Пример StopProcessSample02](./stopprocesssample02-sample.md) В этом примере показано, как написать командлет, записывающий отладку, подробные и предупреждающие сообщения при остановке процессов на локальном компьютере.

[Пример StopProcessSample03](./stopprocesssample03-sample.md) В этом примере показано, как написать командлет, параметры которого имеют псевдонимы и которые поддерживают символы-шаблоны.

[Пример StopProcessSample04](./stopprocesssample04-sample.md) В этом примере показано, как написать командлет, который объявляет наборы параметров, задает набор параметров по умолчанию и может принимать входной объект.

[Пример Events01](./events01-sample.md) В этом примере показано, как создать командлет, позволяющий пользователю регистрировать события, вызванные [System. IO. FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher). С помощью этого командлета пользователи могут, например, зарегистрировать действие, выполняемое при создании файла в определенном каталоге. Этот пример является производным от базового класса [Microsoft. PowerShell. Commands. Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) .

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
