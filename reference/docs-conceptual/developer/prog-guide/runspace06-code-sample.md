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
ms.openlocfilehash: 98b01a79474c58afc3ef1ae5b3761a8d651162f9
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870631"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="19dbd-102">Примеры кода RunSpace06</span><span class="sxs-lookup"><span data-stu-id="19dbd-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="19dbd-103">Ниже приведен исходный код для примера Runspace06, описанный в разделе [Настройка пространства выполнения с помощью оснастки Windows PowerShell](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span><span class="sxs-lookup"><span data-stu-id="19dbd-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="19dbd-104">Этот пример приложения создает пространство выполнения на основе оснастки Windows PowerShell, которая затем используется для запуска конвейера с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="19dbd-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="19dbd-105">Для этого приложение создает сведения о конфигурации пространства выполнения, создает пространство выполнения, создает конвейер с помощью одной команды, а затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="19dbd-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="19dbd-106">C# Исходный файл (runspace06.cs) можно скачать с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="19dbd-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="19dbd-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="19dbd-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="19dbd-108">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="19dbd-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="19dbd-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="19dbd-109">Code Sample</span></span>

[!code-csharp[Runspace06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a><span data-ttu-id="19dbd-110">См. также</span><span class="sxs-lookup"><span data-stu-id="19dbd-110">See Also</span></span>

[<span data-ttu-id="19dbd-111">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19dbd-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="19dbd-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19dbd-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
