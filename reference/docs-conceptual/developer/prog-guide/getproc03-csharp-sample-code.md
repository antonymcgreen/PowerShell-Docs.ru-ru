---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода GetProc03 (C#)
description: Пример кода GetProc03 (C#)
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355584"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="51df8-103">Пример кода GetProc03 (C#)</span><span class="sxs-lookup"><span data-stu-id="51df8-103">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="51df8-104">В следующем коде показана реализация `Get-Process` командлета, который может принимать конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="51df8-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="51df8-105">Эта реализация определяет `Name` параметр, который принимает входные данные конвейера, извлекает сведения о процессе с локального компьютера на основе предоставляемых имен, а затем использует метод [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) в качестве механизма вывода для отправки объектов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="51df8-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="51df8-106">Вы можете скачать исходный файл C# (getprov03.cs) для этого командлета Get-Proc, используя пакет средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="51df8-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="51df8-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="51df8-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="51df8-108">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="51df8-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="51df8-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="51df8-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a><span data-ttu-id="51df8-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="51df8-110">See Also</span></span>

[<span data-ttu-id="51df8-111">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51df8-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="51df8-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51df8-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
