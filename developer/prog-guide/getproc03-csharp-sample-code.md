---
title: GetProc03 (C#) пример кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc0d538-69ac-43d5-837d-b6f47344fc6a
caps.latest.revision: 5
ms.openlocfilehash: 328f4eeea27243102679ab5d139181a878165ad6
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429760"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="916ed-102">Пример кода GetProc03 (C#)</span><span class="sxs-lookup"><span data-stu-id="916ed-102">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="916ed-103">Следующий код показывает реализацию `Get-Process` командлет, который может принять конвейерная входных данных.</span><span class="sxs-lookup"><span data-stu-id="916ed-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="916ed-104">Эта реализация определяет `Name` параметр, который принимает входные данные конвейера, извлекает сведения о процессе на локальном компьютере, на основе предоставленных имен, а затем использует [System.Management.Automation.Cmdlet.Writeobject% 28System.Object%2Csystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) метод в качестве механизма выходные данные для отправки объекты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="916ed-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [System.Management.Automation.Cmdlet.Writeobject%28System.Object%2Csystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="916ed-105">Вы можете скачать C# исходный файл (getprov03.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="916ed-105">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="916ed-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="916ed-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="916ed-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="916ed-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="916ed-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="916ed-108">Code Sample</span></span>

[!code-csharp[GetProcessSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L11-L78 "GetProcessSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="916ed-109">См. также</span><span class="sxs-lookup"><span data-stu-id="916ed-109">See Also</span></span>

[<span data-ttu-id="916ed-110">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="916ed-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="916ed-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="916ed-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)