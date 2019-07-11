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
ms.openlocfilehash: 1a21af4b48a414d9c9fee57871eacb0a39c9ab11
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734893"
---
# <a name="runspace09-code-sample"></a>Примеры кода RunSpace09

Ниже приведен исходный код для примера Runspace09, описанных в [Создание консольного приложения, вызывает конвейер асинхронно](https://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47). Этот пример приложения создает и открывает пространство выполнения, создает и асинхронно вызывает конвейер, и затем использует конвейер событий для асинхронной обработки скрипта. Скрипт, который запускается в это приложение создает целые числа от 1 до 10 в интервалах, кратных 0,5 секунды (500 мс).

## <a name="code-sample"></a>Пример кода

[!code-csharp[Runspace09.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)