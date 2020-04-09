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
ms.openlocfilehash: d1d5e7f4096288ed09dada8eb8a61773921dc1ce
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978241"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="2795e-102">Примеры кода RunSpace06</span><span class="sxs-lookup"><span data-stu-id="2795e-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="2795e-103">Ниже приведен исходный код для примера Runspace06, описанный в разделе [Настройка пространства выполнения с помощью оснастки Windows PowerShell](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span><span class="sxs-lookup"><span data-stu-id="2795e-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="2795e-104">Этот пример приложения создает пространство выполнения на основе оснастки Windows PowerShell, которая затем используется для запуска конвейера с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="2795e-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="2795e-105">Для этого приложение создает сведения о конфигурации пространства выполнения, создает пространство выполнения, создает конвейер с помощью одной команды, а затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="2795e-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="2795e-106">C# Исходный файл (runspace06.cs) можно скачать с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="2795e-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="2795e-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="2795e-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="2795e-108">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="2795e-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="2795e-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="2795e-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a><span data-ttu-id="2795e-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="2795e-110">See Also</span></span>

[<span data-ttu-id="2795e-111">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2795e-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="2795e-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2795e-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
