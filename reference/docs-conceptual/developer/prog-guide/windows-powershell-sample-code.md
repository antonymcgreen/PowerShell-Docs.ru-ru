---
title: Пример кода Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1106829a-8ddc-454e-bbdd-ade15d4bffb4
caps.latest.revision: 7
ms.openlocfilehash: e9df44b17453e9f73f6eb388d9cbc8a69fce4ba2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366423"
---
# <a name="windows-powershell-sample-code"></a>Пример кода Windows PowerShell

Примеры® Windows PowerShell доступны в Windows SDK. В этом разделе содержится пример кода, который содержится в примерах Windows SDK.

> [!NOTE]
> При установке Windows SDK создается каталог **Samples** , в котором все примеры Windows PowerShell становятся доступными. Типичный каталог установки — **C:\Program Files\Microsoft SDKs\Windows\v6.0**.
> Запустите Windows PowerShell и введите **"CD самплес\сисмгмт\повершелл"** , чтобы перейти к каталогу примеров Windows PowerShell. В этом документе каталог примеров Windows PowerShell называется **\<PowerShell samples >** .

## <a name="sample-code-listing"></a>Пример листинга кода

|Пример кода|Описание|
|-----------------|-----------------|
|[Пример кода AccessDbProviderSample01](./accessdbprovidersample01-code-sample.md)|Это поставщик, описанный в статье [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).|
|[Пример кода AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md)|Это поставщик, описанный в разделе [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).|
|[Пример кода AccessDbProviderSample03](./accessdbprovidersample03-code-sample.md)|Это поставщик, описанный в разделе [Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md).|
|[Пример кода AccessDbProviderSample04](./accessdbprovidersample04-code-sample.md)|Это поставщик, описанный в разделе [Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).|
|[Пример кода AccessDbProviderSample05](./accessdbprovidersample05-code-sample.md)|Это поставщик, описанный в разделе [Создание поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).|
|[Пример кода AccessDbProviderSample06](./accessdbprovidersample06-code-sample.md)|Это поставщик, описанный в разделе [Создание поставщика содержимого Windows PowerShell](./creating-a-windows-powershell-content-provider.md).|
|[Примеры кода GetProc01](./getproc01-code-samples.md)|Это базовый пример командлета `Get-Process`, описанный в разделе [Создание первого командлета](../cmdlet/creating-a-cmdlet-without-parameters.md).|
|[Примеры кода GetProc02](./getproc02-code-samples.md)|Это пример командлета `Get-Process`, описанный в разделе [Добавление параметров, обрабатывающих входные данные командной строки](../cmdlet/adding-parameters-that-process-command-line-input.md).|
|[Примеры кода GetProc03](./getproc03-code-samples.md)|Это пример командлета `Get-Process`, описанный в разделе [Добавление параметров, обрабатывающих входные данные конвейера](../cmdlet/adding-parameters-that-process-pipeline-input.md).|
|[Примеры кода GetProc04](./getproc04-code-samples.md)|Это пример командлета `Get-Process`, описанный в статье Добавление незавершенных [отчетов об ошибках в командлет](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).|
|[Примеры кода GetProc05](./getproc05-code-samples.md)|Этот командлет `Get-Process` аналогичен командлету, описанному в статье Добавление незавершенных [отчетов об ошибках в командлет](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).|
|[Примеры кода StopProc01](./stopproc01-code-samples.md)|Это пример командлета `Stop-Process`, описанный в разделе [Создание командлета, изменяющего систему](../cmdlet/creating-a-cmdlet-that-modifies-the-system.md).|
|[Примеры кода StopProcessSample04](./stopprocesssample04-code-samples.md)|Это пример командлета `Stop-Process`, описанный в разделе [Добавление наборов параметров в командлет](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).|
|[Примеры кода Runspace01](./runspace01-code-samples.md)|Ниже приведены примеры кода для пространства выполнения, описанного в разделе [Создание консольного приложения, выполняющего указанную команду](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).|
|[Примеры кода Runspace02](./runspace02-code-samples.md)|В этом примере используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для синхронного выполнения командлета `Get-Process`.|
|[Примеры кода RunSpace03](./runspace03-code-samples.md)|Ниже приведены примеры кода для пространства выполнения, описанного в разделе "Создание консольного приложения, запускающего указанный скрипт".|
|[Примеры кода RunSpace04](./runspace04-code-samples.md)|Это пример кода для пространства выполнения, в котором используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для выполнения скрипта, который создает завершающую ошибку.|
|[Пример кода RunSpace05](./runspace05-code-sample.md)|Это исходный код для примера Runspace05, описанный в разделе [Настройка пространства выполнения с помощью рунспацеконфигуратион](https://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2).|
|[Пример кода RunSpace06](./runspace06-code-sample.md)|Это исходный код для примера Runspace06, описанный в разделе [Настройка пространства выполнения с помощью оснастки Windows PowerShell](https://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).|
|[Пример кода RunSpace07](./runspace07-code-sample.md)|Это исходный код для образца Runspace07, описанный в разделе [Создание консольного приложения, добавляющего команды в конвейер](https://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e).|
|[Пример кода RunSpace08](./runspace08-code-sample.md)|Это исходный код для образца Runspace08, описанный в разделе [Создание консольного приложения, добавляющего параметры в команду](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba).|
|[Пример кода RunSpace09](./runspace09-code-sample.md)|Это исходный код для образца Runspace09, описанный в разделе [Создание консольного приложения, которое вызывает конвейер асинхронно](https://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47).|
|[Пример кода RunSpace10](./runspace10-code-sample.md)|Это исходный код для образца Runspace10, который добавляет командлет в [System. Management. Automation. пространства. рунспацеконфигуратион](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) , а затем использует измененные сведения о конфигурации для создания пространства выполнения.|

## <a name="see-also"></a>См. также:

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)