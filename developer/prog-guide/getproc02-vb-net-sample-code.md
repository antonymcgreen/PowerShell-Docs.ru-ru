---
title: GetProc02 образец кода (VB.NET) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3497546-5b3a-4e29-84ba-cd9747be64b3
caps.latest.revision: 6
ms.openlocfilehash: 821d0dd327529614322e446bfb30d128d1b6a7f3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081600"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="16c0d-102">Пример кода GetProc02 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="16c0d-102">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="16c0d-103">Следующий код показывает реализацию `Get-Process` командлет, который принимает входные данные командной строки.</span><span class="sxs-lookup"><span data-stu-id="16c0d-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="16c0d-104">Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий входные данные командной строки и он использует [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) метода в качестве выходных данных механизм для отправки выходных данных объекты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="16c0d-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="16c0d-105">Пример кода</span><span class="sxs-lookup"><span data-stu-id="16c0d-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="16c0d-106">См. также</span><span class="sxs-lookup"><span data-stu-id="16c0d-106">See Also</span></span>

[<span data-ttu-id="16c0d-107">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16c0d-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)