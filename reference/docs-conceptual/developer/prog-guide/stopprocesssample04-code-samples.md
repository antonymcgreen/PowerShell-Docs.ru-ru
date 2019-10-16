---
title: Примеры кода StopProcessSample04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc68af2b-f622-47c4-964f-b07f3d5bdf14
caps.latest.revision: 5
ms.openlocfilehash: 367fecfe5417e0e4cc41b076bac6fefbe185624f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360113"
---
# <a name="stopprocesssample04-code-samples"></a><span data-ttu-id="2b10c-102">Примеры кода StopProcessSample04</span><span class="sxs-lookup"><span data-stu-id="2b10c-102">StopProcessSample04 Code Samples</span></span>

<span data-ttu-id="2b10c-103">Ниже приведены примеры кода для командлета StopProc00 Sample.</span><span class="sxs-lookup"><span data-stu-id="2b10c-103">Here are the code samples for the StopProc00 sample cmdlet.</span></span> <span data-ttu-id="2b10c-104">Это пример командлета `Stop-Process`, описанный в разделе [Добавление наборов параметров в командлет](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="2b10c-104">This is the `Stop-Process` cmdlet sample described in [Adding Parameter Sets to a Cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md).</span></span> <span data-ttu-id="2b10c-105">Командлет `Stop-Process` предназначен для завершения процессов, которые извлекаются с помощью командлета Get-proc (описывается в разделе [Создание первого командлета](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="2b10c-105">The `Stop-Process` cmdlet is designed to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="2b10c-106">Вы можете скачать C# (stopprocesssample04.cs) и VB.NET (stopprocesssample04. vb) для этого командлета "прекращать-proc" с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="2b10c-106">You can download the C# (stopprocesssample04.cs) and VB.NET (stopprocesssample04.vb) for this Stop-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="2b10c-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="2b10c-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="2b10c-108">Скачанные исходные файлы доступны в каталоге **\<PowerShell samples >** Directory.</span><span class="sxs-lookup"><span data-stu-id="2b10c-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="2b10c-109">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="2b10c-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="2b10c-110">Language</span><span class="sxs-lookup"><span data-stu-id="2b10c-110">Language</span></span>|<span data-ttu-id="2b10c-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="2b10c-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="2b10c-112">C#</span><span class="sxs-lookup"><span data-stu-id="2b10c-112">C#</span></span>|[<span data-ttu-id="2b10c-113">Пример кодаC#StopProc04 ()</span><span class="sxs-lookup"><span data-stu-id="2b10c-113">StopProc04 (C#) Sample Code</span></span>](./stopprocesssample04-csharp-sample-code.md)|
|<span data-ttu-id="2b10c-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="2b10c-114">VB.NET</span></span>|[<span data-ttu-id="2b10c-115">Пример кода StopProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="2b10c-115">StopProc04 (VB.NET) Sample Code</span></span>](./stopprocesssample04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="2b10c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b10c-116">See Also</span></span>

[<span data-ttu-id="2b10c-117">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b10c-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="2b10c-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b10c-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)