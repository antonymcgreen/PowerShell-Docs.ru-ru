---
title: RunSpace03 (C#) образец кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 0e80f4d850a7c6dc044526a56b92f16eea4040b5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081382"
---
# <a name="runspace03-c-code-sample"></a>Пример кода RunSpace03 (C#)

Вот C# исходный код для консольного приложения, описанные в [Создание консольного приложения, запускающегося сценария указан](http://msdn.microsoft.com/en-us/a93e6006-36db-4bcc-b9da-c5bebf4ffd68). В этом примере используется [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) класса, чтобы выполнить скрипт, который извлекает обработки информации, используя список имен процессов передачи в сценарий. Он показывает, как для передачи входных объектов скрипта и как получить объекты ошибок, а также выходных объектов.

> [!NOTE]
> Вы можете скачать C# исходный файл (runspace03.cs) для этого образца, используя Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a>См. также

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)