---
title: Пример кодаC#RunSpace03 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 28cef037f56f2a101f631d3a234974a8868b4ef9
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978327"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="06b53-102">Пример кода RunSpace03 (C#)</span><span class="sxs-lookup"><span data-stu-id="06b53-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="06b53-103">Ниже приведен C# исходный код для консольного приложения, описанного в разделе «Создание консольного приложения, запускающего указанный скрипт».</span><span class="sxs-lookup"><span data-stu-id="06b53-103">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="06b53-104">В этом примере класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) используется для выполнения скрипта, который получает сведения о процессе, используя список имен процессов, переданных в скрипт.</span><span class="sxs-lookup"><span data-stu-id="06b53-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="06b53-105">В нем показано, как передавать входные объекты в скрипт и как получать объекты ошибок, а также выходные объекты.</span><span class="sxs-lookup"><span data-stu-id="06b53-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="06b53-106">C# Исходный файл (runspace03.cs) для этого примера можно скачать с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="06b53-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="06b53-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="06b53-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="06b53-108">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="06b53-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="06b53-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="06b53-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="06b53-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="06b53-110">See Also</span></span>

[<span data-ttu-id="06b53-111">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06b53-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="06b53-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06b53-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
