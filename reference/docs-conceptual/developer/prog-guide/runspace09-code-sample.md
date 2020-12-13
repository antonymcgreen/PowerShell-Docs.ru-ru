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
# <a name="runspace09-code-sample"></a><span data-ttu-id="ea28c-103">Примеры кода RunSpace09</span><span class="sxs-lookup"><span data-stu-id="ea28c-103">RunSpace09 Code Sample</span></span>

<span data-ttu-id="ea28c-104">Ниже приведен исходный код для примера Runspace09, описанного в разделе [Создание консольного приложения, которое вызывает конвейер асинхронно](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span><span class="sxs-lookup"><span data-stu-id="ea28c-104">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="ea28c-105">Этот пример приложения создает и открывает пространство выполнения, создает и асинхронно вызывает конвейер, а затем использует события конвейера для асинхронной обработки скрипта.</span><span class="sxs-lookup"><span data-stu-id="ea28c-105">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="ea28c-106">Скрипт, выполняемый этим приложением, создает целые числа от 1 до 10 в 0,5-секундном интервале (500 мс).</span><span class="sxs-lookup"><span data-stu-id="ea28c-106">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="ea28c-107">Образец кода</span><span class="sxs-lookup"><span data-stu-id="ea28c-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="ea28c-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea28c-108">See Also</span></span>

[<span data-ttu-id="ea28c-109">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea28c-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
