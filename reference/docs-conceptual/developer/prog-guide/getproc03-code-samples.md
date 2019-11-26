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
ms.openlocfilehash: bd6d26cb830bcd6706c88548956e5358b2fddf41
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416155"
---
# <a name="getproc03-code-samples"></a><span data-ttu-id="840db-102">Примеры кода GetProc03</span><span class="sxs-lookup"><span data-stu-id="840db-102">GetProc03 Code Samples</span></span>

<span data-ttu-id="840db-103">Ниже приведены примеры кода для командлета GetProc03 Sample.</span><span class="sxs-lookup"><span data-stu-id="840db-103">Here are the code samples for the GetProc03 sample cmdlet.</span></span> <span data-ttu-id="840db-104">Это пример командлета `Get-Process`, описанный в разделе [Добавление параметров, обрабатывающих входные данные конвейера](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="840db-104">This is the `Get-Process` cmdlet sample described in [Adding Parameters that Process Pipeline Input](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="840db-105">Этот командлет `Get-Process` использует параметр `Name`, который принимает входные данные из объекта конвейера, извлекает сведения о процессе с локального компьютера на основе заданных имен, а затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="840db-105">This `Get-Process` cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="840db-106">Вы можете скачать C# исходный файл (getprov03.cs) для этого командлета Get-proc с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="840db-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="840db-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="840db-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="840db-108">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="840db-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="840db-109">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="840db-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="840db-110">Язык</span><span class="sxs-lookup"><span data-stu-id="840db-110">Language</span></span>|<span data-ttu-id="840db-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="840db-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="840db-112">C#</span><span class="sxs-lookup"><span data-stu-id="840db-112">C#</span></span>|[<span data-ttu-id="840db-113">Пример кодаC#GetProc03 ()</span><span class="sxs-lookup"><span data-stu-id="840db-113">GetProc03 (C#) Sample Code</span></span>](./getproc03-csharp-sample-code.md)|
|<span data-ttu-id="840db-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="840db-114">VB.NET</span></span>|[<span data-ttu-id="840db-115">Пример кода GetProc03 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="840db-115">GetProc03 (VB.NET) Sample Code</span></span>](./getproc03-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="840db-116">См. также</span><span class="sxs-lookup"><span data-stu-id="840db-116">See Also</span></span>

[<span data-ttu-id="840db-117">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="840db-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="840db-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="840db-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
