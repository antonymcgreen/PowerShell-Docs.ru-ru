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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082742"
---
# <a name="runspace-samples"></a>Примеры пространств выполнения

Этот раздел содержит пример кода, показывающий, как использовать различные виды пространств выполнения для выполнения команд, синхронно и асинхронно. Microsoft Visual Studio можно использовать для создания консольного приложения и затем скопируйте код из подразделы этого раздела в ведущее приложение.

## <a name="in-this-section"></a>Содержание

> [!NOTE]
> Примеры размещения приложений, которые создают интерфейсы пользовательского ведущего приложения, см. в разделе [нестандартные образцы узла](./custom-host-samples.md).

 [Пример Runspace01](./runspace01-sample.md) в этом примере показано, как использовать [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) класс запустить [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) командлет синхронно и отобразить ее выходные данные в консоли окно.

 [Пример Runspace02](./runspace02-sample.md) в этом примере показано, как использовать [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) класс запустить [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) командлеты синхронно. Результаты этих команд отображаются с помощью [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) элемента управления.

 [Пример Runspace03](./runspace03-sample.md) в этом примере показано, как использовать [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) класса для синхронного запуска скрипта и как обрабатывать устранимые ошибки. Скрипт получает список имен процессов, а затем извлекает эти процессы. Результаты выполнения скрипта, включая вызванные им устранимые ошибки, отображаются в окне консоли.

 [Пример Runspace04](./runspace04-sample.md) в этом примере показано, как использовать [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) класса для выполнения команд и как фиксации неустранимых ошибок, которые вызываются при выполнении команды. Выполняются две команды, и последняя получает недопустимый аргумент параметра. В результате объекты не возвращаются и возникает неустранимая ошибка.

 [Пример Runspace05](./runspace05-sample.md) в этом примере показано, как добавить оснастку в [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта, чтобы командлет оснастки был доступен при открытии пространства выполнения. Оснастка предоставляет командлет Get-Proc (определяется [пример GetProcessSample01](../cmdlet/getprocesssample01-sample.md)) который запускается синхронно с помощью [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.

 [Пример Runspace06](./runspace06-sample.md) в этом примере показано, как добавить модуль в [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) таким образом, чтобы модуль был загружен при открытии пространства выполнения. Модуль предоставляет командлет Get-Proc (определяется [пример GetProcessSample02](../cmdlet/getprocesssample02-sample.md)) который запускается синхронно с помощью [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.

 [Пример Runspace07](./runspace07-sample.md) в этом примере показано, как создать пространство выполнения, а затем использовать его для синхронного запуска двух командлетов с помощью [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.

 [Пример Runspace08](./runspace08-sample.md) в этом примере показано, как добавить команды и аргументы в конвейер объекта [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) и запустить команды синхронно.

 [Пример Runspace09](./runspace09-sample.md) в этом примере показано, как добавить скрипт в конвейер объекта [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта и как запустить скрипт асинхронно. События используются для обработки выходных данных скрипта.

 [Пример Runspace10](./runspace10-sample.md) в этом примере показано, как создать состояние исходного сеанса по умолчанию, как командлет, чтобы добавить [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), как создать пространство выполнения, с использованием Начальное состояние сеанса и как выполнять команды с помощью [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.

 [Пример Runspace11](./runspace11-sample.md) это демонстрируется использование [System.Management.Automation.Proxycommand](/dotnet/api/System.Management.Automation.ProxyCommand) класса для создания прокси-команды, которая вызывает существующий командлет, но ограничивает набор доступных параметров. Прокси-команда затем добавляется в начальное состояние сеанса, который используется для создания ограниченного пространства выполнения. Это означает, что пользователь может получить доступ к функциям командлета только с помощью прокси-команды.

## <a name="see-also"></a>См. также
