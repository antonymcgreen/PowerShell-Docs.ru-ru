---
title: Пример кода RunSpace10 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5337dc40-c56e-458b-aedc-5f5d401dfd28
caps.latest.revision: 6
ms.openlocfilehash: 95b25746a8e99deb871905734700aba51cd7765e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854610"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="e442c-102">Примеры кода RunSpace10</span><span class="sxs-lookup"><span data-stu-id="e442c-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="e442c-103">Ниже приведен исходный код для примера Runspace10.</span><span class="sxs-lookup"><span data-stu-id="e442c-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="e442c-104">В этом образце приложения добавляет командлету, чтобы [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) , а затем использует сведения о конфигурации, измененный на его создание.</span><span class="sxs-lookup"><span data-stu-id="e442c-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="e442c-105">Вы можете скачать C# исходный файл (runspace10.cs) с помощью Windows Software Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="e442c-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e442c-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="e442c-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="e442c-107">Вы можете скачать C# исходный файл (runspace10.cs) с помощью Windows Software Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="e442c-107">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e442c-108">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="e442c-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="e442c-109">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="e442c-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e442c-110">Пример кода</span><span class="sxs-lookup"><span data-stu-id="e442c-110">Code Sample</span></span>

[!code-csharp[Runspace10.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs#L11-L118 "Runspace10.cs")]

## <a name="see-also"></a><span data-ttu-id="e442c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e442c-111">See Also</span></span>

[<span data-ttu-id="e442c-112">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e442c-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e442c-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e442c-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)