---
title: Windows PowerShell пример кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1106829a-8ddc-454e-bbdd-ade15d4bffb4
caps.latest.revision: 7
ms.openlocfilehash: 264e9f7538e13b48d899e87541239250eb88f14e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863360"
---
# <a name="windows-powershell-sample-code"></a>Пример кода Windows PowerShell

Примеры Windows PowerShell® доступны через пакет SDK Windows. Этот раздел содержит пример кода, который содержится в примеров из Windows SDK.

> [!NOTE]
> При установке пакета Windows SDK **примеры** создается каталог, в котором становятся доступными все примеры Windows PowerShell. Каталог установки стандартного — **C:\Program Files\Microsoft SDKs\Windows\v6.0**. Запустите Windows PowerShell и введите **«cd Samples\SysMgmt\PowerShell»** для поиска каталога, примеры Windows PowerShell. В этом документе каталоге Windows PowerShell Samples называется  **\<примеры PowerShell >**.

## <a name="sample-code-listing"></a>Пример кода

|Пример кода|Описание|
|-----------------|-----------------|
|[Пример кода AccessDbProviderSample01](./accessdbprovidersample01-code-sample.md)|Это описано в разделе поставщика [создание является базовым поставщиком Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).|
|[Пример кода AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md)|Это описано в разделе поставщика [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).|
|[Пример кода AccessDbProviderSample03](./accessdbprovidersample03-code-sample.md)|Это описано в разделе поставщика [Создание поставщика Windows PowerShell элемента](./creating-a-windows-powershell-item-provider.md).|
|[Пример кода AccessDbProviderSample04](./accessdbprovidersample04-code-sample.md)|Это описано в разделе поставщика [Создание поставщика Windows PowerShell контейнера](./creating-a-windows-powershell-container-provider.md).|
|[Пример кода AccessDbProviderSample05](./accessdbprovidersample05-code-sample.md)|Это описано в разделе поставщика [Создание поставщика Windows PowerShell навигации](./creating-a-windows-powershell-navigation-provider.md).|
|[Пример кода AccessDbProviderSample06](./accessdbprovidersample06-code-sample.md)|Это описано в разделе поставщика [Создание содержимого поставщика Windows PowerShell](./creating-a-windows-powershell-content-provider.md).|
|[Примеры кода GetProc01](./getproc01-code-samples.md)|Это базовый `Get-Process` командлетов, которые описаны в [Создание свой первый командлет](../cmdlet/creating-a-cmdlet-without-parameters.md).|
|[Примеры кода GetProc02](./getproc02-code-samples.md)|Это `Get-Process` командлетов, которые описаны в [Добавление параметров командной строки этого процесса входа](../cmdlet/adding-parameters-that-process-command-line-input.md).|
|[Примеры кода GetProc03](./getproc03-code-samples.md)|Это `Get-Process` командлетов, которые описаны в [Добавление параметров, входные данные конвейера процесс](../cmdlet/adding-parameters-that-process-pipeline-input.md).|
|[Примеры кода GetProc04](./getproc04-code-samples.md)|Это `Get-Process` командлетов, которые описаны в [Добавление устранимые отчеты об ошибках Your командлету](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).|
|[Примеры кода GetProc05](./getproc05-code-samples.md)|Это `Get-Process` командлет аналогичен командлету, описанные в [Добавление устранимые отчеты об ошибках Your командлету](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).|
|[Примеры кода StopProc01](./stopproc01-code-samples.md)|Это `Stop-Process` командлетов, которые описаны в [Создание командлет что изменяет система](../cmdlet/creating-a-cmdlet-that-modifies-the-system.md).|
|[Примеры кода StopProcessSample04](./stopprocesssample04-code-samples.md)|Это `Stop-Process` командлетов, которые описаны в [добавление наборов параметров для командлета](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).|
|[Примеры кода Runspace01](./runspace01-code-samples.md)|Ниже приведены примеры кода для пространства выполнения, описанных в [Создание консольного приложения, запускающегося команды указан](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).|
|[Примеры кода Runspace02](./runspace02-code-samples.md)|В этом примере используется [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) класс для выполнения `Get-Process` командлет синхронно.|
|[Примеры кода RunSpace03](./runspace03-code-samples.md)|Ниже приведены примеры кода для пространства выполнения, описанных в [Создание консольного приложения, запускающегося сценария указан](http://msdn.microsoft.com/en-us/a93e6006-36db-4bcc-b9da-c5bebf4ffd68).|
|[Примеры кода RunSpace04](./runspace04-code-samples.md)|Ниже приведен пример кода для пространства выполнения, который использует [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) класса, чтобы выполнить скрипт, который создает неустранимую ошибку.|
|[Пример кода RunSpace05](./runspace05-code-sample.md)|Это исходный код для примера Runspace05, описанных в [Настройка RunspaceConfiguration пространство выполнения с помощью](http://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2).|
|[Пример кода RunSpace06](./runspace06-code-sample.md)|Это исходный код для примера Runspace06, описанных в [Настройка пространство выполнения с помощью оснастки Windows PowerShell](http://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).|
|[Пример кода RunSpace07](./runspace07-code-sample.md)|Это исходный код для примера Runspace07, описанных в [Создание консольного приложения, добавляет команд в конвейер](http://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e).|
|[Пример кода RunSpace08](./runspace08-code-sample.md)|Это исходный код для примера Runspace08, описанных в [Создание консоли приложения, добавляет параметры в команду](http://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba).|
|[Пример кода RunSpace09](./runspace09-code-sample.md)|Это исходный код для примера Runspace09, описанных в [Создание консольного приложения, вызывает конвейер асинхронно](http://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47).|
|[Пример кода RunSpace10](./runspace10-code-sample.md)|Это исходный код для примера Runspace10, который добавляет командлету, чтобы [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) , а затем использует сведения о конфигурации, измененный на его создание.|

## <a name="see-also"></a>См. также

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)