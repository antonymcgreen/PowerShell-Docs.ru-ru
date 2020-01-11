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
ms.openlocfilehash: 2e9cd80f1869e0d859187eea89eca414a84cb4ab
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870594"
---
# <a name="runspace08-code-sample"></a>Примеры кода RunSpace08

Ниже приведен исходный код для примера Runspace08, описанного в разделе [Создание консольного приложения, добавляющего в команду Параметры](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).
Этот пример приложения создает пространство выполнения, создает конвейер, добавляет две команды в конвейер, добавляет два параметра во вторую команду, а затем выполняет конвейер. Команды, добавляемые в конвейер, являются командлетами `Get-Process` и `Sort-Object`.

## <a name="code-sample"></a>Образец кода

[!code-csharp[Runspace08.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
