---
title: Пример кода RunSpace05 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: b16ee45383059c52ce3433699c6b8d2120992431
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429573"
---
# <a name="runspace05-code-sample"></a>Примеры кода RunSpace05

Ниже приведен исходный код для примера Runspace05, описанный в [Настройка RunspaceConfiguration пространство выполнения с помощью](http://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2). В этом примере показано, как создать пространство выполнения сведения о конфигурации, создать пространство выполнения, создание конвейера с помощью одной команды и затем выполнить конвейер. — Команда, выполняемая `Get-Process` командлета.

> [!NOTE]
> Вы можете скачать C# исходный файл (runspace05.cs) с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a>См. также

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)