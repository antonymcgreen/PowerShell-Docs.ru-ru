---
title: Пример кода RunSpace06 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d71f86d5-eb62-4b16-aa95-5fd3f314ffd3
caps.latest.revision: 6
ms.openlocfilehash: d0330f082262b68486a582ed95c7a520be1e184c
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429539"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="b6f8c-102">Примеры кода RunSpace06</span><span class="sxs-lookup"><span data-stu-id="b6f8c-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="b6f8c-103">Ниже приведен исходный код для примера Runspace06, описанных в [Настройка пространство выполнения с помощью оснастки Windows PowerShell](http://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).</span><span class="sxs-lookup"><span data-stu-id="b6f8c-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](http://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span> <span data-ttu-id="b6f8c-104">Этот пример приложения создает пространства выполнения, зависимости от оснастки Windows PowerShell, который затем используется для запуска конвейера с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="b6f8c-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="b6f8c-105">Чтобы сделать это, приложение создает сведения о конфигурации пространства выполнения, создается пространство выполнения, создаст конвейер с помощью одной команды и затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="b6f8c-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="b6f8c-106">Вы можете скачать C# исходный файл (runspace06.cs) с помощью Windows Software Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6f8c-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b6f8c-107">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="b6f8c-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="b6f8c-108">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="b6f8c-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="b6f8c-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="b6f8c-109">Code Sample</span></span>

[!code-csharp[Runspace06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a><span data-ttu-id="b6f8c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b6f8c-110">See Also</span></span>

[<span data-ttu-id="b6f8c-111">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6f8c-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b6f8c-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6f8c-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)