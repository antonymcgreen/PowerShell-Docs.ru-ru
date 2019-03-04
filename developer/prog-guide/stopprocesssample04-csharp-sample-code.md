---
title: StopProcessSample04 (C#) пример кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 778ce1a2-e16d-4af5-b15b-77ca4326bdc4
caps.latest.revision: 5
ms.openlocfilehash: 5a9e7a9ea13c9a62440b7cd80285751c901bcdd4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862720"
---
# <a name="stopprocesssample04-c-sample-code"></a><span data-ttu-id="660ae-102">Пример кода StopProcessSample04 (C#)</span><span class="sxs-lookup"><span data-stu-id="660ae-102">StopProcessSample04 (C#) Sample Code</span></span>

<span data-ttu-id="660ae-103">Ниже приведен полный C# пример кода для командлета StopProc04 образца.</span><span class="sxs-lookup"><span data-stu-id="660ae-103">Here is the complete C# sample code for the StopProc04 sample cmdlet.</span></span> <span data-ttu-id="660ae-104">Это код для `Stop-Process` командлет описано в разделе [добавление наборов параметров для командлета](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="660ae-104">This is the code for the `Stop-Process` cmdlet described in [Adding Parameter Sets to a Cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span></span> <span data-ttu-id="660ae-105">`Stop-Process` Командлет предназначен для остановки процессов, которые можно получить с помощью командлета Get-Proc (описано в разделе [Создание свой первый командлет](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="660ae-105">The `Stop-Process` cmdlet is designed to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="660ae-106">Вы можете скачать C# (stopprocesssample04.cs) исходный файл для этого командлета Stop-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="660ae-106">You can download the C# (stopprocesssample04.cs) source file for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="660ae-107">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="660ae-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="660ae-108">Вы можете скачать C# (stopprocesssample04.cs) исходный файл для этого командлета Stop-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="660ae-108">You can download the C# (stopprocesssample04.cs) source file for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="660ae-109">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="660ae-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="660ae-110">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="660ae-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

[!code-csharp[StopProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L11-L435 "StopProcessSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="660ae-111">См. также</span><span class="sxs-lookup"><span data-stu-id="660ae-111">See Also</span></span>

[<span data-ttu-id="660ae-112">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="660ae-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="660ae-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="660ae-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)