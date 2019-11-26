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
ms.openlocfilehash: 499a688ce5e8daa78baff58c454ad237836bbe48
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416159"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="b4dda-102">Пример кода GetProc01 (C#)</span><span class="sxs-lookup"><span data-stu-id="b4dda-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="b4dda-103">В следующем коде показана реализация командлета Sample GetProc01.</span><span class="sxs-lookup"><span data-stu-id="b4dda-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="b4dda-104">Обратите внимание, что командлет упрощается за счет выполнения фактической работы по получению процесса к методу [System. Diagnostics. Process.-Processing \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) .</span><span class="sxs-lookup"><span data-stu-id="b4dda-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="b4dda-105">Вы можете скачать C# исходный файл (getproc01.cs) для этого командлета Get-proc с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="b4dda-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b4dda-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b4dda-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="b4dda-107">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="b4dda-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b4dda-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="b4dda-108">Code Sample</span></span>

[!code-csharp[GetProcessSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L11-L126 "GetProcessSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="b4dda-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b4dda-109">See Also</span></span>

[<span data-ttu-id="b4dda-110">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4dda-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b4dda-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4dda-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
