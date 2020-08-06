---
title: GetProc02 (C#) образец кода | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d9afa8fff23d99661987c067e8082a9294c12717
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787161"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="f488c-102">Пример кода GetProc02 (C#)</span><span class="sxs-lookup"><span data-stu-id="f488c-102">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="f488c-103">В следующем коде показана реализация `Get-Process` командлета, который принимает входные данные командной строки.</span><span class="sxs-lookup"><span data-stu-id="f488c-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="f488c-104">Обратите внимание, что эта реализация определяет `Name` параметр, позволяющий вводить данные из командной строки, и в качестве механизма вывода для отправки выходных объектов в конвейер используется метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) .</span><span class="sxs-lookup"><span data-stu-id="f488c-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f488c-105">Образец кода</span><span class="sxs-lookup"><span data-stu-id="f488c-105">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="f488c-106">См. также</span><span class="sxs-lookup"><span data-stu-id="f488c-106">See Also</span></span>

[<span data-ttu-id="f488c-107">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f488c-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
