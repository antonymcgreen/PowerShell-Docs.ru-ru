---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода GetProc01 (C#)
description: Пример кода GetProc01 (C#)
ms.openlocfilehash: 79509ff12afb32c907058f4ddb0c707f3823857a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654482"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="d247b-103">Пример кода GetProc01 (C#)</span><span class="sxs-lookup"><span data-stu-id="d247b-103">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="d247b-104">В следующем коде показана реализация командлета Sample GetProc01.</span><span class="sxs-lookup"><span data-stu-id="d247b-104">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="d247b-105">Обратите внимание, что командлет упрощается за счет выполнения фактической работы по получению процесса к методу [System. Diagnostics. Process.-Processing \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) .</span><span class="sxs-lookup"><span data-stu-id="d247b-105">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="d247b-106">Вы можете скачать исходный файл C# (getproc01.cs) для этого командлета Get-Proc, используя пакет средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="d247b-106">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="d247b-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d247b-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="d247b-108">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="d247b-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d247b-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="d247b-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a><span data-ttu-id="d247b-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="d247b-110">See Also</span></span>

[<span data-ttu-id="d247b-111">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d247b-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d247b-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d247b-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
