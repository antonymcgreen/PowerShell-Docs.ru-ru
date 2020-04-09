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
ms.openlocfilehash: d7fa39485eea833483682c91c96417a76e5d770f
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977545"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="c3163-102">Примеры кода RunSpace09</span><span class="sxs-lookup"><span data-stu-id="c3163-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="c3163-103">Ниже приведен исходный код для примера Runspace09, описанного в разделе [Создание консольного приложения, которое вызывает конвейер асинхронно](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span><span class="sxs-lookup"><span data-stu-id="c3163-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="c3163-104">Этот пример приложения создает и открывает пространство выполнения, создает и асинхронно вызывает конвейер, а затем использует события конвейера для асинхронной обработки скрипта.</span><span class="sxs-lookup"><span data-stu-id="c3163-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="c3163-105">Скрипт, выполняемый этим приложением, создает целые числа от 1 до 10 в 0,5-секундном интервале (500 мс).</span><span class="sxs-lookup"><span data-stu-id="c3163-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="c3163-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="c3163-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="c3163-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3163-107">See Also</span></span>

[<span data-ttu-id="c3163-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3163-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
