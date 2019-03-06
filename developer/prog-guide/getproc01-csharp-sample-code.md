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
ms.openlocfilehash: 32c8214935a8c9f455426b76966d8c7fb33353d4
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57430083"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="999d5-102">Пример кода GetProc01 (C#)</span><span class="sxs-lookup"><span data-stu-id="999d5-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="999d5-103">Ниже показана реализация пример командлета GetProc01.</span><span class="sxs-lookup"><span data-stu-id="999d5-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="999d5-104">Обратите внимание на то, что командлет стало проще благодаря оставляя фактическую работу процесса извлечения, чтобы [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) метод.</span><span class="sxs-lookup"><span data-stu-id="999d5-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="999d5-105">Вы можете скачать C# исходный файл (getproc01.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="999d5-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="999d5-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="999d5-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="999d5-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="999d5-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="999d5-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="999d5-108">Code Sample</span></span>

[!code-csharp[GetProcessSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L11-L126 "GetProcessSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="999d5-109">См. также</span><span class="sxs-lookup"><span data-stu-id="999d5-109">See Also</span></span>

[<span data-ttu-id="999d5-110">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="999d5-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="999d5-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="999d5-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)