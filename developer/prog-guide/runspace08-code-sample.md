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
ms.openlocfilehash: ec6aae544eafea1dedc1379dab00beeed2c7c436
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734914"
---
# <a name="runspace08-code-sample"></a>Примеры кода RunSpace08

Ниже приведен исходный код для примера Runspace08, описанных в [Создание консоли приложения, добавляет параметры в команду](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba). В этом образце приложения создается пространство выполнения, создает конвейер, добавляет две команды в конвейер, вторая команда добавляет два параметра и затем выполняет конвейер. Команды, которые добавляются в конвейер, `Get-Process` и `Sort-Object` командлетов.

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace08.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)