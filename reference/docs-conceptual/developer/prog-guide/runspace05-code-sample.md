---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры кода RunSpace05
description: Примеры кода RunSpace05
ms.openlocfilehash: f128e09522bdb05cba2c160bce4944c829a5c108
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654213"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="3f5e3-103">Примеры кода RunSpace05</span><span class="sxs-lookup"><span data-stu-id="3f5e3-103">RunSpace05 Code Sample</span></span>

<span data-ttu-id="3f5e3-104">Ниже приведен исходный код для примера Runspace05, описанный в разделе [Настройка пространства выполнения с помощью рунспацеконфигуратион](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span><span class="sxs-lookup"><span data-stu-id="3f5e3-104">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span></span>
<span data-ttu-id="3f5e3-105">В этом примере показано, как создать сведения о конфигурации пространства выполнения, создать пространство выполнения, создать конвейер с помощью одной команды, а затем выполнить конвейер.</span><span class="sxs-lookup"><span data-stu-id="3f5e3-105">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="3f5e3-106">Команда, которая выполняется, является `Get-Process` командлетом.</span><span class="sxs-lookup"><span data-stu-id="3f5e3-106">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3f5e3-107">Исходный файл C# (runspace05.cs) можно загрузить с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="3f5e3-107">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3f5e3-108">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="3f5e3-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="3f5e3-109">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="3f5e3-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3f5e3-110">Образец кода</span><span class="sxs-lookup"><span data-stu-id="3f5e3-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="3f5e3-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f5e3-111">See Also</span></span>

[<span data-ttu-id="3f5e3-112">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f5e3-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3f5e3-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f5e3-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
