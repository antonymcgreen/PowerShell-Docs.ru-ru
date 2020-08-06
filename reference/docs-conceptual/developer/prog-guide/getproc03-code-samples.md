---
title: Примеры кода GetProc03 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a31b17968c3a6066d2304f3029853c8d4e35e3f3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787144"
---
# <a name="getproc03-code-samples"></a><span data-ttu-id="987fa-102">Примеры кода GetProc03</span><span class="sxs-lookup"><span data-stu-id="987fa-102">GetProc03 Code Samples</span></span>

<span data-ttu-id="987fa-103">Ниже приведены примеры кода для командлета GetProc03 Sample.</span><span class="sxs-lookup"><span data-stu-id="987fa-103">Here are the code samples for the GetProc03 sample cmdlet.</span></span> <span data-ttu-id="987fa-104">Это `Get-Process` Пример командлета, описанный в разделе [Добавление параметров, обрабатывающих входные данные конвейера](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="987fa-104">This is the `Get-Process` cmdlet sample described in [Adding Parameters that Process Pipeline Input](../cmdlet/adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="987fa-105">Этот `Get-Process` командлет использует `Name` параметр, который принимает входные данные из объекта конвейера, извлекает сведения о процессе с локального компьютера на основе заданных имен, а затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="987fa-105">This `Get-Process` cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="987fa-106">Исходный файл C# (getprov03.cs) для этого командлета Get-proc можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="987fa-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="987fa-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="987fa-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="987fa-108">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="987fa-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="987fa-109">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="987fa-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="987fa-110">Язык</span><span class="sxs-lookup"><span data-stu-id="987fa-110">Language</span></span>|<span data-ttu-id="987fa-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="987fa-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="987fa-112">C#</span><span class="sxs-lookup"><span data-stu-id="987fa-112">C#</span></span>|[<span data-ttu-id="987fa-113">Пример кода GetProc03 (C#)</span><span class="sxs-lookup"><span data-stu-id="987fa-113">GetProc03 (C#) Sample Code</span></span>](./getproc03-csharp-sample-code.md)|
|<span data-ttu-id="987fa-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="987fa-114">VB.NET</span></span>|[<span data-ttu-id="987fa-115">Пример кода GetProc03 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="987fa-115">GetProc03 (VB.NET) Sample Code</span></span>](./getproc03-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="987fa-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="987fa-116">See Also</span></span>

[<span data-ttu-id="987fa-117">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="987fa-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="987fa-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="987fa-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
