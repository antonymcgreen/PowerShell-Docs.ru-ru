---
title: Примеры кода RunSpace04 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9a9b7e02358cdf9018199046c938c699aff8681c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787075"
---
# <a name="runspace04-code-samples"></a><span data-ttu-id="ee7d9-102">Примеры кода RunSpace04</span><span class="sxs-lookup"><span data-stu-id="ee7d9-102">RunSpace04 Code Samples</span></span>

<span data-ttu-id="ee7d9-103">Ниже приведен пример кода для пространства выполнения, в котором используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для выполнения скрипта, создающего завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="ee7d9-103">Here is a code sample for a runspace that uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that generates a terminating error.</span></span> <span data-ttu-id="ee7d9-104">Ведущее приложение отвечает за перехват ошибки и интерпретацию записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ee7d9-104">The host application is responsible for catching the error and interpreting the error record.</span></span>

> [!NOTE]
> <span data-ttu-id="ee7d9-105">Вы можете скачать исходный файл VB.NET (Runspace04. vb) для этого пространства выполнения с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="ee7d9-105">You can download the VB.NET source file (Runspace04.vb) for this runspace using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="ee7d9-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="ee7d9-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="ee7d9-107">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="ee7d9-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="ee7d9-108">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ee7d9-108">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="ee7d9-109">Язык</span><span class="sxs-lookup"><span data-stu-id="ee7d9-109">Language</span></span>|<span data-ttu-id="ee7d9-110">Раздел</span><span class="sxs-lookup"><span data-stu-id="ee7d9-110">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="ee7d9-111">VB.NET</span><span class="sxs-lookup"><span data-stu-id="ee7d9-111">VB.NET</span></span>|[<span data-ttu-id="ee7d9-112">Пример кода Runspace01 (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="ee7d9-112">Runspace01 (VB.NET) Code Sample</span></span>](./runspace01-vb-net-code-sample.md)|

## <a name="see-also"></a><span data-ttu-id="ee7d9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ee7d9-113">See Also</span></span>

[<span data-ttu-id="ee7d9-114">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee7d9-114">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="ee7d9-115">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee7d9-115">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
