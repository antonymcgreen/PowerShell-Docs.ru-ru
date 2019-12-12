---
title: Пример кода RunSpace08 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: 20032913969606f722f3768b0433775aeaa8c3a8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366483"
---
# <a name="runspace08-code-sample"></a>Примеры кода RunSpace08

Ниже приведен исходный код для примера Runspace08, описанного в разделе [Создание консольного приложения, добавляющего в команду Параметры](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba). Этот пример приложения создает пространство выполнения, создает конвейер, добавляет две команды в конвейер, добавляет два параметра во вторую команду, а затем выполняет конвейер. Команды, добавляемые в конвейер, являются командлетами `Get-Process` и `Sort-Object`.

## <a name="code-sample"></a>Образец кода

[!code-csharp[Runspace08.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a>См. также:

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
