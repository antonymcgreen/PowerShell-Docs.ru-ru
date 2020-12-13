---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода RunSpace03 (C#)
description: Пример кода RunSpace03 (C#)
ms.openlocfilehash: cdb08811de13f8bbf5cd91fcbef552c78594b788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653843"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="84d60-103">Пример кода RunSpace03 (C#)</span><span class="sxs-lookup"><span data-stu-id="84d60-103">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="84d60-104">Ниже приведен исходный код C# для консольного приложения, описанного в разделе «Создание консольного приложения, запускающего указанный скрипт».</span><span class="sxs-lookup"><span data-stu-id="84d60-104">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="84d60-105">В этом примере класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) используется для выполнения скрипта, который получает сведения о процессе, используя список имен процессов, переданных в скрипт.</span><span class="sxs-lookup"><span data-stu-id="84d60-105">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="84d60-106">В нем показано, как передавать входные объекты в скрипт и как получать объекты ошибок, а также выходные объекты.</span><span class="sxs-lookup"><span data-stu-id="84d60-106">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="84d60-107">Исходный файл C# (runspace03.cs) для этого примера можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="84d60-107">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="84d60-108">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="84d60-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="84d60-109">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="84d60-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="84d60-110">Образец кода</span><span class="sxs-lookup"><span data-stu-id="84d60-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="84d60-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="84d60-111">See Also</span></span>

[<span data-ttu-id="84d60-112">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="84d60-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="84d60-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="84d60-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
