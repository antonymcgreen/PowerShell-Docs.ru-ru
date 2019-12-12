---
title: Пример кодаC#Runspace01 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 607113ed566fc1e08e5b1d7092c83da2a22366ca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74418020"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="a7427-102">Пример кода Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="a7427-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="a7427-103">Ниже приведены примеры кода для пространства выполнения, описанного в разделе [Создание консольного приложения, выполняющего указанную команду](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="a7427-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span> <span data-ttu-id="a7427-104">Для этого приложение вызывает пространство выполнения, а затем вызывает команду.</span><span class="sxs-lookup"><span data-stu-id="a7427-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="a7427-105">(Обратите внимание, что это приложение не указывает сведения о конфигурации пространства выполнения и не создает конвейер явным образом).</span><span class="sxs-lookup"><span data-stu-id="a7427-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="a7427-106">Вызываемая команда является командлетом `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="a7427-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a7427-107">Вы можете скачать C# исходный файл (runspace01.cs) для этого пространства выполнения с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="a7427-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a7427-108">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a7427-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="a7427-109">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="a7427-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a7427-110">Образец кода</span><span class="sxs-lookup"><span data-stu-id="a7427-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="a7427-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7427-111">See Also</span></span>

[<span data-ttu-id="a7427-112">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7427-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a7427-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7427-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
