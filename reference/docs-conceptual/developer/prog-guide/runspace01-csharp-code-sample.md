---
title: Пример кода Runspace01 (C#) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 418162731b4a98989642e1c61c655fdb0f002698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787068"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="d1933-102">Пример кода Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="d1933-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="d1933-103">Ниже приведены примеры кода для пространства выполнения, описанного в разделе [Создание консольного приложения, выполняющего указанную команду](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="d1933-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="d1933-104">Для этого приложение вызывает пространство выполнения, а затем вызывает команду.</span><span class="sxs-lookup"><span data-stu-id="d1933-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="d1933-105">(Обратите внимание, что это приложение не указывает сведения о конфигурации пространства выполнения и не создает конвейер явным образом).</span><span class="sxs-lookup"><span data-stu-id="d1933-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="d1933-106">Вызываемая команда является `Get-Process` командлетом.</span><span class="sxs-lookup"><span data-stu-id="d1933-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d1933-107">Вы можете скачать исходный файл C# (runspace01.cs) для этого пространства выполнения с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="d1933-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="d1933-108">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d1933-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="d1933-109">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="d1933-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d1933-110">Образец кода</span><span class="sxs-lookup"><span data-stu-id="d1933-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="d1933-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d1933-111">See Also</span></span>

[<span data-ttu-id="d1933-112">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1933-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d1933-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1933-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
