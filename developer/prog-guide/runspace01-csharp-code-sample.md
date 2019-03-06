---
title: Runspace01 (C#) образец кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 59320365c4a35c3d71af10273eb21b1ce01e5c0c
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429709"
---
# <a name="runspace01-c-code-sample"></a>Пример кода Runspace01 (C#)

Ниже приведены примеры кода для пространства выполнения, описанных в [Создание консольного приложения, запускающегося команды указан](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e). Чтобы сделать это, приложение вызывает пространство выполнения и затем вызывает команду. (Обратите внимание, что это приложение не содержит сведения о конфигурации пространства выполнения, а также ли его явным образом создать конвейер). Команда, вызываемая `Get-Process` командлета.

> [!NOTE]
> Вы можете скачать C# исходный файл (runspace01.cs) для этого пространства выполнения, используя Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0. Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a>См. также

[Руководство программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)