---
title: GetProc04 (C#) пример кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 439ba3f3-91b1-46a4-8d07-9af6edb71bc4
caps.latest.revision: 5
ms.openlocfilehash: 1fc1ab58ae651239937e36c8bb08fda3d3272b2a
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429692"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="503d4-102">Пример кода GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="503d4-102">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="503d4-103">Следующий код показывает реализацию `Get-Process` командлет, который сообщает устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="503d4-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="503d4-104">Такая реализация вызывает [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="503d4-104">This implementation calls the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="503d4-105">Вы можете скачать C# исходный файл (getprov04.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="503d4-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="503d4-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="503d4-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="503d4-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="503d4-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="503d4-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="503d4-108">Code Sample</span></span>

[!code-csharp[GetProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs#L11-L98 "GetProcessSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="503d4-109">См. также</span><span class="sxs-lookup"><span data-stu-id="503d4-109">See Also</span></span>

[<span data-ttu-id="503d4-110">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="503d4-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="503d4-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="503d4-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)