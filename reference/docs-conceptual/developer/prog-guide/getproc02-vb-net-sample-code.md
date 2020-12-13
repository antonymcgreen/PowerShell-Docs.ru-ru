---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода GetProc02 (VB.NET)
description: Пример кода GetProc02 (VB.NET)
ms.openlocfilehash: aefc3a4df5e0f29120916648ecdca41931a4c1c6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354547"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="76210-103">Пример кода GetProc02 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="76210-103">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="76210-104">В следующем коде показана реализация `Get-Process` командлета, который принимает входные данные командной строки.</span><span class="sxs-lookup"><span data-stu-id="76210-104">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="76210-105">Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий вводить данные из командной строки, и в качестве механизма вывода для отправки выходных объектов в конвейер используется метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) .</span><span class="sxs-lookup"><span data-stu-id="76210-105">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="76210-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="76210-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="76210-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="76210-107">See Also</span></span>

[<span data-ttu-id="76210-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76210-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
