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
ms.openlocfilehash: 4ec63ed32bd2906f5b027523aa0f253b51a5d873
ms.sourcegitcommit: f60fa420bdc81db174e6168d3aeb11371e483162
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2019
ms.locfileid: "67301350"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="10587-102">Пример кода GetProc02 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="10587-102">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="10587-103">Следующий код показывает реализацию `Get-Process` командлет, который принимает входные данные командной строки.</span><span class="sxs-lookup"><span data-stu-id="10587-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="10587-104">Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий входные данные командной строки и он использует [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) метод как механизм выходные данные для отправки выходных данных в объекты конвейер.</span><span class="sxs-lookup"><span data-stu-id="10587-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="10587-105">Пример кода</span><span class="sxs-lookup"><span data-stu-id="10587-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="10587-106">См. также</span><span class="sxs-lookup"><span data-stu-id="10587-106">See Also</span></span>

[<span data-ttu-id="10587-107">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10587-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
