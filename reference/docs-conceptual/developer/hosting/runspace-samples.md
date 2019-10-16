---
title: Примеры пространства выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c92a6d3d-8d34-4a76-bdc3-dea923d9858e
caps.latest.revision: 17
ms.openlocfilehash: e24d40746da91f60aaf2af655ddcadc88ab6a4db
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361003"
---
# <a name="runspace-samples"></a>Примеры пространств выполнения

В этом разделе содержится пример кода, демонстрирующий использование различных типов пространств выполнения для синхронного и асинхронного запуска команд. С помощью Microsoft Visual Studio можно создать консольное приложение, а затем скопировать код из разделов этого раздела в ведущее приложение.

## <a name="in-this-section"></a>Содержание

> [!NOTE]
> Примеры ведущих приложений, которые создают пользовательские интерфейсы узлов, см. в разделе [примеры пользовательских узлов](./custom-host-samples.md).

 [Пример Runspace01](./runspace01-sample.md) В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения командлета [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и вывода его выходных данных в окне консоли.

 [Пример Runspace02](./runspace02-sample.md) В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения командлетов [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) . Результаты этих команд отображаются с помощью элемента управления [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) .

 [Пример Runspace03](./runspace03-sample.md) В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения скрипта и для решения неустранимых ошибок. Скрипт получает список имен процессов, а затем извлекает эти процессы. Результаты выполнения скрипта, включая вызванные им устранимые ошибки, отображаются в окне консоли.

 [Пример Runspace04](./runspace04-sample.md) В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения команд и перехвата ошибок, возникающих при выполнении команд. Выполняются две команды, и последняя получает недопустимый аргумент параметра. В результате объекты не возвращаются, и возникает ошибка завершения.

 [Пример Runspace05](./runspace05-sample.md) В этом примере показано, как добавить оснастку в объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) , чтобы командлет оснастки был доступен при открытии пространства выполнения. Оснастка предоставляет командлет Get-proc (определяемый [образцом GetProcessSample01](../cmdlet/getprocesssample01-sample.md)), который выполняется синхронно с помощью объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Пример Runspace06](./runspace06-sample.md) В этом примере показано, как добавить модуль в объект [System. Management. Automation. пространства. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) , чтобы модуль загружался при открытии пространства выполнения. Модуль предоставляет командлет Get-proc (определяемый [образцом GetProcessSample02](../cmdlet/getprocesssample02-sample.md)), который выполняется синхронно с помощью объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Пример Runspace07](./runspace07-sample.md) В этом примере показано, как создать пространство выполнения, а затем использовать это пространство выполнения для синхронного выполнения двух командлетов с помощью объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Пример Runspace08](./runspace08-sample.md) В этом примере показано, как добавить команды и аргументы в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) и как выполнять команды синхронно.

 [Пример Runspace09](./runspace09-sample.md) В этом примере показано, как добавить скрипт в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) и как запустить скрипт в асинхронном режиме. События используются для обработки выходных данных скрипта.

 [Пример Runspace10](./runspace10-sample.md) В этом примере показано, как создать начальное состояние сеанса по умолчанию, как добавить командлет в [System. Management. Automation. пространства выполнения. Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), как создать пространство выполнение, использующее исходное состояние сеанса, и как выполнить команду с помощью Объект [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

 [Пример Runspace11](./runspace11-sample.md) В этом примере показано, как использовать класс [System. Management. Automation. проксикомманд](/dotnet/api/System.Management.Automation.ProxyCommand) для создания команды прокси, которая вызывает существующий командлет, но ограничит набор доступных параметров. Прокси-команда затем добавляется в начальное состояние сеанса, который используется для создания ограниченного пространства выполнения. Это означает, что пользователь может получить доступ к функциям командлета только с помощью прокси-команды.

## <a name="see-also"></a>См. также:
