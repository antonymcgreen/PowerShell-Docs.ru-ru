---
ms.date: 09/12/2016
ms.topic: reference
title: Пример кода GetProc03 (VB.NET)
description: Пример кода GetProc03 (VB.NET)
ms.openlocfilehash: fc70496178c85e101b380e68aacd64c8d1f350e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355567"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="26a30-103">Пример кода GetProc03 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="26a30-103">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="26a30-104">В следующем коде показана реализация `Get-Process` командлета, который может принимать конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="26a30-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="26a30-105">Эта реализация определяет `Name` параметр, который принимает входные данные конвейера, извлекает сведения о процессе с локального компьютера на основе предоставляемых имен, а затем использует метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) в качестве механизма вывода для отправки объектов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="26a30-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="26a30-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="26a30-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
