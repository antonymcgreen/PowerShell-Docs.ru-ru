---
title: Пример кодаC#GetProc02 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1eee3-316b-43a4-8a60-313391619be6
caps.latest.revision: 6
ms.openlocfilehash: c5e71ddacae1036164c5e8e579ddc8704d30670e
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978395"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="3c413-102">Пример кода GetProc02 (C#)</span><span class="sxs-lookup"><span data-stu-id="3c413-102">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="3c413-103">В следующем коде показана реализация командлета `Get-Process`, который принимает входные данные командной строки.</span><span class="sxs-lookup"><span data-stu-id="3c413-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="3c413-104">Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий вводить данные из командной строки, и в качестве механизма вывода для отправки выходных объектов в конвейер используется метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) .</span><span class="sxs-lookup"><span data-stu-id="3c413-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3c413-105">Образец кода</span><span class="sxs-lookup"><span data-stu-id="3c413-105">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="3c413-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c413-106">See Also</span></span>

[<span data-ttu-id="3c413-107">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c413-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
