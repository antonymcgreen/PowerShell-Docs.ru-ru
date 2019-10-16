---
title: Примеры кода GetProc04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: 67081528ebe14fbb082091c1b9500de82069b48f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360323"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="33cfd-102">Примеры кода GetProc04</span><span class="sxs-lookup"><span data-stu-id="33cfd-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="33cfd-103">Ниже приведены примеры кода для командлета GetProc04 Sample.</span><span class="sxs-lookup"><span data-stu-id="33cfd-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="33cfd-104">Это пример командлета `Get-Process`, описанный в статье Добавление незавершенных [отчетов об ошибках в командлет](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="33cfd-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="33cfd-105">Этот командлет `Get-Process` вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) при возникновении исключения недопустимой операции во время получения сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="33cfd-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="33cfd-106">Вы можете скачать C# исходный файл (getprov04.cs) для этого командлета Get-proc с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="33cfd-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="33cfd-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="33cfd-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="33cfd-108">Скачанные исходные файлы доступны в каталоге **\<PowerShell samples >** Directory.</span><span class="sxs-lookup"><span data-stu-id="33cfd-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="33cfd-109">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="33cfd-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="33cfd-110">Language</span><span class="sxs-lookup"><span data-stu-id="33cfd-110">Language</span></span>|<span data-ttu-id="33cfd-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="33cfd-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="33cfd-112">C#</span><span class="sxs-lookup"><span data-stu-id="33cfd-112">C#</span></span>|[<span data-ttu-id="33cfd-113">Пример кодаC#GetProc04 ()</span><span class="sxs-lookup"><span data-stu-id="33cfd-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="33cfd-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="33cfd-114">VB.NET</span></span>|[<span data-ttu-id="33cfd-115">Пример кода GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="33cfd-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="33cfd-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="33cfd-116">See Also</span></span>

[<span data-ttu-id="33cfd-117">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33cfd-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="33cfd-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33cfd-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)