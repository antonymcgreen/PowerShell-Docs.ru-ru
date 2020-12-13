---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода GetProc02 (C#)
description: Пример кода GetProc02 (C#)
ms.openlocfilehash: 17fd0d0c0829ed21ef955fd2e62e9ee089d62190
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355618"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="3bdac-103">Пример кода GetProc02 (C#)</span><span class="sxs-lookup"><span data-stu-id="3bdac-103">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="3bdac-104">В следующем коде показана реализация `Get-Process` командлета, который принимает входные данные командной строки.</span><span class="sxs-lookup"><span data-stu-id="3bdac-104">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="3bdac-105">Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий вводить данные из командной строки, и в качестве механизма вывода для отправки выходных объектов в конвейер используется метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) .</span><span class="sxs-lookup"><span data-stu-id="3bdac-105">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3bdac-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="3bdac-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="3bdac-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="3bdac-107">See Also</span></span>

[<span data-ttu-id="3bdac-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bdac-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
