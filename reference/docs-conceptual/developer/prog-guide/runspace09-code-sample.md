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
ms.openlocfilehash: 2f447fd0ce21c5bca8abe1fddb4e3c7025b70ef1
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870593"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="2d84d-102">Примеры кода RunSpace09</span><span class="sxs-lookup"><span data-stu-id="2d84d-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="2d84d-103">Ниже приведен исходный код для примера Runspace09, описанного в разделе [Создание консольного приложения, которое вызывает конвейер асинхронно](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span><span class="sxs-lookup"><span data-stu-id="2d84d-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="2d84d-104">Этот пример приложения создает и открывает пространство выполнения, создает и асинхронно вызывает конвейер, а затем использует события конвейера для асинхронной обработки скрипта.</span><span class="sxs-lookup"><span data-stu-id="2d84d-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="2d84d-105">Скрипт, выполняемый этим приложением, создает целые числа от 1 до 10 в 0,5-секундном интервале (500 мс).</span><span class="sxs-lookup"><span data-stu-id="2d84d-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="2d84d-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="2d84d-106">Code Sample</span></span>

[!code-csharp[Runspace09.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a><span data-ttu-id="2d84d-107">См. также</span><span class="sxs-lookup"><span data-stu-id="2d84d-107">See Also</span></span>

[<span data-ttu-id="2d84d-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d84d-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
