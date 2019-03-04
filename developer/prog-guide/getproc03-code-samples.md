---
title: Примеры кода GetProc03 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad39c7d-2f64-49d1-9be0-d2295e4302b3
caps.latest.revision: 5
ms.openlocfilehash: 8cb02b9f2510b90f405651deaf551e9622f5a298
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857310"
---
# <a name="getproc03-code-samples"></a><span data-ttu-id="61ac6-102">Примеры кода GetProc03</span><span class="sxs-lookup"><span data-stu-id="61ac6-102">GetProc03 Code Samples</span></span>

<span data-ttu-id="61ac6-103">Ниже приведены примеры кода для командлета GetProc03 образца.</span><span class="sxs-lookup"><span data-stu-id="61ac6-103">Here are the code samples for the GetProc03 sample cmdlet.</span></span> <span data-ttu-id="61ac6-104">Это `Get-Process` командлетов, которые описаны в [Добавление параметров, входные данные конвейера процесс](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="61ac6-104">This is the `Get-Process` cmdlet sample described in [Adding Parameters that Process Pipeline Input](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="61ac6-105">Это `Get-Process` командлет использует `Name` параметр, который принимает входные данные из объекта конвейера, извлекает сведения о процессе на локальном компьютере, на основе предоставленных имен и затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="61ac6-105">This `Get-Process` cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="61ac6-106">Вы можете скачать C# исходный файл (getprov03.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="61ac6-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="61ac6-107">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="61ac6-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="61ac6-108">Вы можете скачать C# исходный файл (getprov03.cs) для этого командлета Get-Proc, с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="61ac6-108">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="61ac6-109">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="61ac6-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="61ac6-110">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="61ac6-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="61ac6-111">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="61ac6-111">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="61ac6-112">Language</span><span class="sxs-lookup"><span data-stu-id="61ac6-112">Language</span></span>|<span data-ttu-id="61ac6-113">Раздел</span><span class="sxs-lookup"><span data-stu-id="61ac6-113">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="61ac6-114">C#</span><span class="sxs-lookup"><span data-stu-id="61ac6-114">C#</span></span>|[<span data-ttu-id="61ac6-115">GetProc03 (C#) пример кода</span><span class="sxs-lookup"><span data-stu-id="61ac6-115">GetProc03 (C#) Sample Code</span></span>](./getproc03-csharp-sample-code.md)|
|<span data-ttu-id="61ac6-116">VB.NET</span><span class="sxs-lookup"><span data-stu-id="61ac6-116">VB.NET</span></span>|[<span data-ttu-id="61ac6-117">GetProc03 образец кода (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="61ac6-117">GetProc03 (VB.NET) Sample Code</span></span>](./getproc03-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="61ac6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="61ac6-118">See Also</span></span>

[<span data-ttu-id="61ac6-119">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ac6-119">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="61ac6-120">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ac6-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)