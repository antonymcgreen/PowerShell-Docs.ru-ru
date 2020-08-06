---
title: Пример кода RunSpace03 (C#) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: df34652f60ed85b13739a04485cf6622cf924872
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784798"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="c65b3-102">Пример кода RunSpace03 (C#)</span><span class="sxs-lookup"><span data-stu-id="c65b3-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="c65b3-103">Ниже приведен исходный код C# для консольного приложения, описанного в разделе «Создание консольного приложения, запускающего указанный скрипт».</span><span class="sxs-lookup"><span data-stu-id="c65b3-103">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="c65b3-104">В этом примере класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) используется для выполнения скрипта, который получает сведения о процессе, используя список имен процессов, переданных в скрипт.</span><span class="sxs-lookup"><span data-stu-id="c65b3-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="c65b3-105">В нем показано, как передавать входные объекты в скрипт и как получать объекты ошибок, а также выходные объекты.</span><span class="sxs-lookup"><span data-stu-id="c65b3-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="c65b3-106">Исходный файл C# (runspace03.cs) для этого примера можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="c65b3-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="c65b3-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="c65b3-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="c65b3-108">Скачанные исходные файлы доступны в **\<PowerShell Samples>** каталоге.</span><span class="sxs-lookup"><span data-stu-id="c65b3-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c65b3-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="c65b3-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="c65b3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c65b3-110">See Also</span></span>

[<span data-ttu-id="c65b3-111">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c65b3-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="c65b3-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c65b3-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
