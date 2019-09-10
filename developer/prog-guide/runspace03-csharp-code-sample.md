---
title: Пример кодаC#RunSpace03 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 9afdb97b8ae2919f091ca5bacccedbe37c2e1584
ms.sourcegitcommit: 00083f07b13c73b86936e7d7307397df27c63c04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848023"
---
# <a name="runspace03-c-code-sample"></a>Пример кода RunSpace03 (C#)

Ниже приведен C# исходный код для консольного приложения, описанного в разделе «Создание консольного приложения, запускающего указанный скрипт». В этом примере класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) используется для выполнения скрипта, который получает сведения о процессе, используя список имен процессов, переданных в скрипт. В нем показано, как передавать входные объекты в скрипт и как получать объекты ошибок, а также выходные объекты.

> [!NOTE]
> C# Исходный файл (runspace03.cs) для этого примера можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в  **\<примерах PowerShell >** Directory.

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a>См. также

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)