---
title: Пример кодаC#GetProc01 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65094bb7-1972-44b3-b8b0-5f639860b58c
caps.latest.revision: 5
ms.openlocfilehash: 71ba68521ed8d26d0c85169d2b0d547cc6d2d5e3
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978429"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="2f573-102">Пример кода GetProc01 (C#)</span><span class="sxs-lookup"><span data-stu-id="2f573-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="2f573-103">В следующем коде показана реализация командлета Sample GetProc01.</span><span class="sxs-lookup"><span data-stu-id="2f573-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="2f573-104">Обратите внимание, что командлет упрощается за счет выполнения фактической работы по получению процесса к методу [System. Diagnostics. Process.-Processing \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) .</span><span class="sxs-lookup"><span data-stu-id="2f573-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="2f573-105">Вы можете скачать C# исходный файл (getproc01.cs) для этого командлета Get-proc с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="2f573-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="2f573-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="2f573-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="2f573-107">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="2f573-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="2f573-108">Образец кода</span><span class="sxs-lookup"><span data-stu-id="2f573-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a><span data-ttu-id="2f573-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f573-109">See Also</span></span>

[<span data-ttu-id="2f573-110">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f573-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="2f573-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f573-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
