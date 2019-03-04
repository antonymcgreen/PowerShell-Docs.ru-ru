---
title: Пример кода RunSpace05 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: 2b5ac097e8a52832b0f8cfb93b84eef56fc64858
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854600"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="d69f7-102">Примеры кода RunSpace05</span><span class="sxs-lookup"><span data-stu-id="d69f7-102">RunSpace05 Code Sample</span></span>

<span data-ttu-id="d69f7-103">Ниже приведен исходный код для примера Runspace05, описанный в [Настройка RunspaceConfiguration пространство выполнения с помощью](http://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2).</span><span class="sxs-lookup"><span data-stu-id="d69f7-103">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](http://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2).</span></span> <span data-ttu-id="d69f7-104">В этом примере показано, как создать пространство выполнения сведения о конфигурации, создать пространство выполнения, создание конвейера с помощью одной команды и затем выполнить конвейер.</span><span class="sxs-lookup"><span data-stu-id="d69f7-104">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="d69f7-105">— Команда, выполняемая `Get-Process` командлета.</span><span class="sxs-lookup"><span data-stu-id="d69f7-105">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d69f7-106">Вы можете скачать C# исходный файл (runspace05.cs) с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="d69f7-106">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="d69f7-107">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d69f7-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="d69f7-108">Вы можете скачать C# исходный файл (runspace05.cs) с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="d69f7-108">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="d69f7-109">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d69f7-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="d69f7-110">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="d69f7-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d69f7-111">Пример кода</span><span class="sxs-lookup"><span data-stu-id="d69f7-111">Code Sample</span></span>

[!code-csharp[Runspace05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a><span data-ttu-id="d69f7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d69f7-112">See Also</span></span>

[<span data-ttu-id="d69f7-113">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d69f7-113">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d69f7-114">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d69f7-114">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)