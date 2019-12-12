---
title: Пример кода RunSpace09 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 136e451f-767b-42e0-bd6f-6486693abd5e
caps.latest.revision: 6
ms.openlocfilehash: 122a40dea93d874a7c131774e3d1abb148bcd4fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360133"
---
# <a name="runspace09-code-sample"></a>Примеры кода RunSpace09

Ниже приведен исходный код для примера Runspace09, описанного в разделе [Создание консольного приложения, которое вызывает конвейер асинхронно](https://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47). Этот пример приложения создает и открывает пространство выполнения, создает и асинхронно вызывает конвейер, а затем использует события конвейера для асинхронной обработки скрипта. Скрипт, выполняемый этим приложением, создает целые числа от 1 до 10 в 0,5-секундном интервале (500 мс).

## <a name="code-sample"></a>Образец кода

[!code-csharp[Runspace09.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a>См. также:

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
