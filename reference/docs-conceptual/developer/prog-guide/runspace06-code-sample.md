---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры кода RunSpace06
description: Примеры кода RunSpace06
ms.openlocfilehash: 627fa2be51721dd8bfdd63fabdd2e6f286d593be
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667489"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="20c1d-103">Примеры кода RunSpace06</span><span class="sxs-lookup"><span data-stu-id="20c1d-103">RunSpace06 Code Sample</span></span>

<span data-ttu-id="20c1d-104">Ниже приведен исходный код для примера Runspace06, описанный в разделе [Настройка пространства выполнения с помощью оснастки Windows PowerShell](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span><span class="sxs-lookup"><span data-stu-id="20c1d-104">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="20c1d-105">Этот пример приложения создает пространство выполнения на основе оснастки Windows PowerShell, которая затем используется для запуска конвейера с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="20c1d-105">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="20c1d-106">Для этого приложение создает сведения о конфигурации пространства выполнения, создает пространство выполнения, создает конвейер с помощью одной команды, а затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="20c1d-106">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="20c1d-107">Исходный файл C# (runspace06.cs) можно скачать с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="20c1d-107">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="20c1d-108">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="20c1d-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="20c1d-109">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="20c1d-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="20c1d-110">Образец кода</span><span class="sxs-lookup"><span data-stu-id="20c1d-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a><span data-ttu-id="20c1d-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="20c1d-111">See Also</span></span>

[<span data-ttu-id="20c1d-112">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20c1d-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="20c1d-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20c1d-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
