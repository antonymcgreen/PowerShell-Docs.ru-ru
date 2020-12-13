---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода Windows PowerShell
description: Пример кода Windows PowerShell
ms.openlocfilehash: da916fa3557f44ecc9126ecef38235109aa391ec
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390139"
---
# <a name="windows-powershell-sample-code"></a>Пример кода Windows PowerShell

Примеры Windows PowerShell &reg; доступны в Windows SDK. В этом разделе содержится пример кода, который содержится в примерах Windows SDK.

> [!NOTE]
> При установке Windows SDK создается каталог **Samples** , в котором все примеры Windows PowerShell становятся доступными. Типичный каталог установки — **C:\Program Files\Microsoft SDKs\Windows\v6.0**. Запустите Windows PowerShell и введите **"CD самплес\сисмгмт\повершелл"** , чтобы перейти к каталогу примеров Windows PowerShell. В этом документе каталог примеров Windows PowerShell называется **\<PowerShell Samples>** .

## <a name="sample-code-listing"></a>Пример листинга кода

|                                    Пример кода                                    |                                                                                                                                           Описание                                                                                                                                           |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Пример кода AccessDbProviderSample01](./accessdbprovidersample01-code-sample.md) | Это поставщик, описанный в статье [Создание базового поставщика Windows PowerShell](./creating-a-basic-windows-powershell-provider.md).                                                                                                                                                            |
| [Пример кода AccessDbProviderSample02](./accessdbprovidersample02-code-sample.md) | Это поставщик, описанный в разделе [Создание поставщика диска Windows PowerShell](./creating-a-windows-powershell-drive-provider.md).                                                                                                                                                            |
| [Пример кода AccessDbProviderSample03](./accessdbprovidersample03-code-sample.md) | Это поставщик, описанный в разделе [Создание поставщика элементов Windows PowerShell](./creating-a-windows-powershell-item-provider.md).                                                                                                                                                              |
| [Пример кода AccessDbProviderSample04](./accessdbprovidersample04-code-sample.md) | Это поставщик, описанный в разделе [Создание поставщика контейнера Windows PowerShell](./creating-a-windows-powershell-container-provider.md).                                                                                                                                                    |
| [Пример кода AccessDbProviderSample05](./accessdbprovidersample05-code-sample.md) | Это поставщик, описанный в разделе [Создание поставщика навигации Windows PowerShell](./creating-a-windows-powershell-navigation-provider.md).                                                                                                                                                  |
| [Пример кода AccessDbProviderSample06](./accessdbprovidersample06-code-sample.md) | Это поставщик, описанный в разделе [Создание поставщика содержимого Windows PowerShell](./creating-a-windows-powershell-content-provider.md).                                                                                                                                                        |
| [Примеры кода GetProc01](./getproc01-code-samples.md)                             | Это базовый `Get-Process` Пример командлета, описанный в разделе [Создание первого командлета](../cmdlet/creating-a-cmdlet-without-parameters.md).                                                                                                                                                     |
| [Примеры кода GetProc02](./getproc02-code-samples.md)                             | Это `Get-Process` Пример командлета, описанный в разделе [Добавление параметров, которые обрабатывают Command-Line входе](../cmdlet/adding-parameters-that-process-command-line-input.md).                                                                                                                       |
| [Примеры кода GetProc03](./getproc03-code-samples.md)                             | Это `Get-Process` Пример командлета, описанный в разделе [Добавление параметров, обрабатывающих входные данные конвейера](../cmdlet/adding-parameters-that-process-pipeline-input.md).                                                                                                                               |
| [Примеры кода GetProc04](./getproc04-code-samples.md)                             | Это `Get-Process` Пример командлета, описанный в статье Добавление незавершенных [отчетов об ошибках в командлет](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).                                                                                                                |
| [Примеры кода GetProc05](./getproc05-code-samples.md)                             | Этот `Get-Process` командлет аналогичен командлету, описанному в статье Добавление незавершенных [отчетов об ошибках в командлет](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).                                                                                                     |
| [Примеры кода StopProc01](./stopproc01-code-samples.md)                           | Это `Stop-Process` Пример командлета, описанный в разделе [Создание командлета, изменяющего систему](../cmdlet/creating-a-cmdlet-that-modifies-the-system.md).                                                                                                                                    |
| [Примеры кода StopProcessSample04](./stopprocesssample04-code-samples.md)         | Это `Stop-Process` Пример командлета, описанный в разделе [Добавление наборов параметров в командлет](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).                                                                                                                                                      |
| [Примеры кода Runspace01](./runspace01-code-samples.md)                           | Ниже приведены примеры кода для пространства выполнения, описанного в разделе [Создание консольного приложения, выполняющего указанную команду](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).                                                                                      |
| [Примеры кода Runspace02](./runspace02-code-samples.md)                           | В этом примере используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для `Get-Process` синхронного выполнения командлета.                                                                                                            |
| [Примеры кода RunSpace03](./runspace03-code-samples.md)                           | Ниже приведены примеры кода для пространства выполнения, описанного в разделе "Создание консольного приложения, запускающего указанный скрипт".                                                                                                                                                                         |
| [Примеры кода RunSpace04](./runspace04-code-samples.md)                           | Это пример кода для пространства выполнения, в котором используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для выполнения скрипта, который создает завершающую ошибку.                                                                         |
| [Примеры кода RunSpace05](./runspace05-code-sample.md)                             |                                                                                                            |
| [Примеры кода RunSpace06](./runspace06-code-sample.md)                             |                                                                                                     |
| [Примеры кода RunSpace07](./runspace07-code-sample.md)                             |                                                                                               |
| [Примеры кода RunSpace08](./runspace08-code-sample.md)                             |                                                                                              |
| [Примеры кода RunSpace09](./runspace09-code-sample.md)                             |                                                                                       |
| [Примеры кода RunSpace10](./runspace10-code-sample.md)                             | Это исходный код для образца Runspace10, который добавляет командлет в [System. Management. Automation. пространства. рунспацеконфигуратион](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) , а затем использует измененные сведения о конфигурации для создания пространства выполнения. |

## <a name="see-also"></a>См. также:

[Руководство программиста по Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
