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
ms.openlocfilehash: 833ff1c37ee025e9cd9d2760bc63695534dd69ff
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360383"
---
# <a name="getproc03-code-samples"></a><span data-ttu-id="0770d-102">Примеры кода GetProc03</span><span class="sxs-lookup"><span data-stu-id="0770d-102">GetProc03 Code Samples</span></span>

<span data-ttu-id="0770d-103">Ниже приведены примеры кода для командлета GetProc03 Sample.</span><span class="sxs-lookup"><span data-stu-id="0770d-103">Here are the code samples for the GetProc03 sample cmdlet.</span></span> <span data-ttu-id="0770d-104">Это пример командлета `Get-Process`, описанный в разделе [Добавление параметров, обрабатывающих входные данные конвейера](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="0770d-104">This is the `Get-Process` cmdlet sample described in [Adding Parameters that Process Pipeline Input](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="0770d-105">Этот командлет `Get-Process` использует параметр `Name`, который принимает входные данные из объекта конвейера, извлекает сведения о процессе с локального компьютера на основе заданных имен, а затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="0770d-105">This `Get-Process` cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="0770d-106">Вы можете скачать C# исходный файл (getprov03.cs) для этого командлета Get-proc с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="0770d-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="0770d-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="0770d-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="0770d-108">Скачанные исходные файлы доступны в каталоге **\<PowerShell samples >** Directory.</span><span class="sxs-lookup"><span data-stu-id="0770d-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="0770d-109">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="0770d-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="0770d-110">Language</span><span class="sxs-lookup"><span data-stu-id="0770d-110">Language</span></span>|<span data-ttu-id="0770d-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="0770d-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="0770d-112">C#</span><span class="sxs-lookup"><span data-stu-id="0770d-112">C#</span></span>|[<span data-ttu-id="0770d-113">Пример кодаC#GetProc03 ()</span><span class="sxs-lookup"><span data-stu-id="0770d-113">GetProc03 (C#) Sample Code</span></span>](./getproc03-csharp-sample-code.md)|
|<span data-ttu-id="0770d-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="0770d-114">VB.NET</span></span>|[<span data-ttu-id="0770d-115">Пример кода GetProc03 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="0770d-115">GetProc03 (VB.NET) Sample Code</span></span>](./getproc03-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="0770d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0770d-116">See Also</span></span>

[<span data-ttu-id="0770d-117">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0770d-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="0770d-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0770d-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)