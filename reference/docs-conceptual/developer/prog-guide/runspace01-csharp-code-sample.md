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
ms.openlocfilehash: 0978880a4294edb96fc6edb00f420cd0a9ad197b
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977987"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="9de8d-102">Пример кода Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="9de8d-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="9de8d-103">Ниже приведены примеры кода для пространства выполнения, описанного в разделе [Создание консольного приложения, выполняющего указанную команду](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="9de8d-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="9de8d-104">Для этого приложение вызывает пространство выполнения, а затем вызывает команду.</span><span class="sxs-lookup"><span data-stu-id="9de8d-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="9de8d-105">(Обратите внимание, что это приложение не указывает сведения о конфигурации пространства выполнения и не создает конвейер явным образом).</span><span class="sxs-lookup"><span data-stu-id="9de8d-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="9de8d-106">Вызываемая команда является командлетом `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="9de8d-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="9de8d-107">Вы можете скачать C# исходный файл (runspace01.cs) для этого пространства выполнения с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="9de8d-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="9de8d-108">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="9de8d-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="9de8d-109">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="9de8d-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="9de8d-110">Образец кода</span><span class="sxs-lookup"><span data-stu-id="9de8d-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="9de8d-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="9de8d-111">See Also</span></span>

[<span data-ttu-id="9de8d-112">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9de8d-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="9de8d-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9de8d-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
