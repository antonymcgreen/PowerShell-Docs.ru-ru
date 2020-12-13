---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры кода GetProc04
description: Примеры кода GetProc04
ms.openlocfilehash: db94eda2b3aa5fc88a3054df66f54628e1482f56
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659235"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="b3e76-103">Примеры кода GetProc04</span><span class="sxs-lookup"><span data-stu-id="b3e76-103">GetProc04 Code Samples</span></span>

<span data-ttu-id="b3e76-104">Ниже приведены примеры кода для командлета GetProc04 Sample.</span><span class="sxs-lookup"><span data-stu-id="b3e76-104">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="b3e76-105">Это `Get-Process` Пример командлета, описанный в статье Добавление незавершенных [отчетов об ошибках в командлет](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="b3e76-105">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="b3e76-106">Этот `Get-Process` командлет вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) при возникновении исключения недопустимой операции во время получения сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="b3e76-106">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="b3e76-107">Вы можете скачать исходный файл C# (getprov04.cs) для этого командлета Get-Proc, используя пакет средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="b3e76-107">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b3e76-108">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b3e76-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="b3e76-109">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="b3e76-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="b3e76-110">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b3e76-110">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="b3e76-111">Язык</span><span class="sxs-lookup"><span data-stu-id="b3e76-111">Language</span></span>|<span data-ttu-id="b3e76-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="b3e76-112">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="b3e76-113">C#</span><span class="sxs-lookup"><span data-stu-id="b3e76-113">C#</span></span>|[<span data-ttu-id="b3e76-114">Пример кода GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="b3e76-114">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="b3e76-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="b3e76-115">VB.NET</span></span>|[<span data-ttu-id="b3e76-116">Пример кода GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="b3e76-116">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="b3e76-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3e76-117">See Also</span></span>

[<span data-ttu-id="b3e76-118">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3e76-118">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b3e76-119">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3e76-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
