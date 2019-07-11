---
title: Пример кода RunSpace07 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad306d9-45c2-4d55-8e64-fdcba43402c5
caps.latest.revision: 6
ms.openlocfilehash: 232b282e366c9fad167686337696ef2ccd8b30d8
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734945"
---
# <a name="runspace07-code-sample"></a>Примеры кода RunSpace07

Ниже приведен исходный код для примера Runspace07, описанных в [Создание консольного приложения, добавляет команд в конвейер](https://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e). В этом образце приложения создается пространство выполнения, создает конвейер, добавляет две команды в конвейер и затем выполняет конвейер. Команды, добавленные в конвейер, `Get-Process` и `Measure-Object` командлетов.

> [!NOTE]
> Вы можете скачать C# исходного файла (runspace07.cs) с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и Microsoft .NET Framework 3.0 Runtime компонентов. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace07.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a>См. также

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)