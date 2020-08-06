---
title: Пример кода GetProc02 (VB.NET) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 98261f2d6678e24bb8e8df6d2c8a405b25203364
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787178"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="13611-102">Пример кода GetProc02 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="13611-102">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="13611-103">В следующем коде показана реализация `Get-Process` командлета, который принимает входные данные командной строки.</span><span class="sxs-lookup"><span data-stu-id="13611-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="13611-104">Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий вводить данные из командной строки, и в качестве механизма вывода для отправки выходных объектов в конвейер используется метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) .</span><span class="sxs-lookup"><span data-stu-id="13611-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="13611-105">Образец кода</span><span class="sxs-lookup"><span data-stu-id="13611-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="13611-106">См. также</span><span class="sxs-lookup"><span data-stu-id="13611-106">See Also</span></span>

[<span data-ttu-id="13611-107">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13611-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
