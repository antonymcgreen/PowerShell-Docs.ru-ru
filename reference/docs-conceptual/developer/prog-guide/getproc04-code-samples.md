---
title: Примеры кода GetProc04 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b90b7e96c1454e57df93863b526758f25d9be690
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771963"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="4f922-102">Примеры кода GetProc04</span><span class="sxs-lookup"><span data-stu-id="4f922-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="4f922-103">Ниже приведены примеры кода для командлета GetProc04 Sample.</span><span class="sxs-lookup"><span data-stu-id="4f922-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="4f922-104">Это `Get-Process` Пример командлета, описанный в статье Добавление незавершенных [отчетов об ошибках в командлет](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="4f922-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="4f922-105">Этот `Get-Process` командлет вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) при возникновении исключения недопустимой операции во время получения сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="4f922-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="4f922-106">Исходный файл C# (getprov04.cs) для этого командлета Get-proc можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="4f922-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="4f922-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="4f922-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="4f922-108">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="4f922-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="4f922-109">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="4f922-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="4f922-110">Язык</span><span class="sxs-lookup"><span data-stu-id="4f922-110">Language</span></span>|<span data-ttu-id="4f922-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="4f922-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="4f922-112">C#</span><span class="sxs-lookup"><span data-stu-id="4f922-112">C#</span></span>|[<span data-ttu-id="4f922-113">Пример кода GetProc04 (C#)</span><span class="sxs-lookup"><span data-stu-id="4f922-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="4f922-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="4f922-114">VB.NET</span></span>|[<span data-ttu-id="4f922-115">Пример кода GetProc04 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="4f922-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="4f922-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4f922-116">See Also</span></span>

[<span data-ttu-id="4f922-117">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f922-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="4f922-118">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f922-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
