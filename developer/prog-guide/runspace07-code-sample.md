---
title: Пример кода RunSpace07 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad306d9-45c2-4d55-8e64-fdcba43402c5
caps.latest.revision: 6
ms.openlocfilehash: 064e7d7ea2ee173bbcdd75a9f3a6c12582afe17b
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429649"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="95813-102">Примеры кода RunSpace07</span><span class="sxs-lookup"><span data-stu-id="95813-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="95813-103">Ниже приведен исходный код для примера Runspace07, описанных в [Создание консольного приложения, добавляет команд в конвейер](http://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e).</span><span class="sxs-lookup"><span data-stu-id="95813-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](http://msdn.microsoft.com/en-us/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span> <span data-ttu-id="95813-104">В этом образце приложения создается пространство выполнения, создает конвейер, добавляет две команды в конвейер и затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="95813-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="95813-105">Команды, добавленные в конвейер, `Get-Process` и `Measure-Object` командлетов.</span><span class="sxs-lookup"><span data-stu-id="95813-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="95813-106">Вы можете скачать C# исходного файла (runspace07.cs) с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и Microsoft .NET Framework 3.0 Runtime компонентов.</span><span class="sxs-lookup"><span data-stu-id="95813-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="95813-107">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="95813-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="95813-108">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="95813-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="95813-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="95813-109">Code Sample</span></span>

[!code-csharp[Runspace07.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a><span data-ttu-id="95813-110">См. также</span><span class="sxs-lookup"><span data-stu-id="95813-110">See Also</span></span>

[<span data-ttu-id="95813-111">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95813-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="95813-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95813-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)