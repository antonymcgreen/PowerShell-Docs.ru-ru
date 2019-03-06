---
title: GetProc01 образец кода (VB.NET) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ee87f67-6d2c-48cc-b300-3ae917c6dc88
caps.latest.revision: 5
ms.openlocfilehash: 2411642c39737e7dc03bd0bb4ea753ed27783732
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429794"
---
# <a name="getproc01-vbnet-sample-code"></a><span data-ttu-id="3af08-102">Пример кода GetProc01 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="3af08-102">GetProc01 (VB.NET) Sample Code</span></span>

<span data-ttu-id="3af08-103">Ниже показана реализация пример командлета GetProc01.</span><span class="sxs-lookup"><span data-stu-id="3af08-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="3af08-104">Обратите внимание на то, что командлет стало проще благодаря оставляя фактическую работу процесса извлечения, чтобы [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) метод.</span><span class="sxs-lookup"><span data-stu-id="3af08-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="3af08-105">Вы можете скачать C# исходный файл (getproc01.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="3af08-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3af08-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="3af08-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="3af08-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="3af08-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3af08-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="3af08-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [msh_samplesgetproc01#getproc01vball](msh_samplesgetproc01#getproc01vball)]  -->

## <a name="see-also"></a><span data-ttu-id="3af08-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3af08-109">See Also</span></span>

[<span data-ttu-id="3af08-110">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3af08-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3af08-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3af08-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)