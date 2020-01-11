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
ms.openlocfilehash: f40b24951c44c228d85524845045aea58f680f2e
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870614"
---
# <a name="runspace07-code-sample"></a>Примеры кода RunSpace07

Ниже приведен исходный код для примера Runspace07, описанного в разделе [Создание консольного приложения, добавляющего команды в конвейер](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).
Этот пример приложения создает пространство выполнения, создает конвейер, добавляет в конвейер две команды, а затем выполняет конвейер. Команды, добавленные в конвейер, являются командлетами `Get-Process` и `Measure-Object`.

> [!NOTE]
> C# Исходный файл (runspace07.cs) можно загрузить с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0. Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.

## <a name="code-sample"></a>Образец кода

[!code-csharp[Runspace07.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a>См. также

[Руководством программиста Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
