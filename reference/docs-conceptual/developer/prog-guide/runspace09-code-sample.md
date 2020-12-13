---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры кода RunSpace09
description: Примеры кода RunSpace09
ms.openlocfilehash: 52ebfa5dcfd6c12d2ded78a41a6090caa5087149
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654192"
---
# <a name="runspace09-code-sample"></a>Примеры кода RunSpace09

Ниже приведен исходный код для примера Runspace09, описанного в разделе [Создание консольного приложения, которое вызывает конвейер асинхронно](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).
Этот пример приложения создает и открывает пространство выполнения, создает и асинхронно вызывает конвейер, а затем использует события конвейера для асинхронной обработки скрипта. Скрипт, выполняемый этим приложением, создает целые числа от 1 до 10 в 0,5-секундном интервале (500 мс).

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a>См. также:

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
