---
title: GetProc01 (C#) пример кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65094bb7-1972-44b3-b8b0-5f639860b58c
caps.latest.revision: 5
ms.openlocfilehash: 56ce7080e24cc12de6d43ac607ffd5d3f0a3b17c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856890"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="a11a1-102">Пример кода GetProc01 (C#)</span><span class="sxs-lookup"><span data-stu-id="a11a1-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="a11a1-103">Ниже показана реализация пример командлета GetProc01.</span><span class="sxs-lookup"><span data-stu-id="a11a1-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="a11a1-104">Обратите внимание на то, что командлет стало проще благодаря оставляя фактическую работу процесса извлечения, чтобы [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) метод.</span><span class="sxs-lookup"><span data-stu-id="a11a1-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="a11a1-105">Вы можете скачать C# исходный файл (getproc01.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="a11a1-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a11a1-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a11a1-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="a11a1-107">Вы можете скачать C# исходный файл (getproc01.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="a11a1-107">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a11a1-108">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a11a1-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="a11a1-109">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="a11a1-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a11a1-110">Пример кода</span><span class="sxs-lookup"><span data-stu-id="a11a1-110">Code Sample</span></span>

[!code-csharp[GetProcessSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L11-L126 "GetProcessSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="a11a1-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a11a1-111">See Also</span></span>

[<span data-ttu-id="a11a1-112">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a11a1-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a11a1-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a11a1-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)