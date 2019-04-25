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
ms.openlocfilehash: 77c0675b45bf4ff6f8c6a85ff9a090c13c199c6d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081246"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="f8256-102">Примеры кода RunSpace10</span><span class="sxs-lookup"><span data-stu-id="f8256-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="f8256-103">Ниже приведен исходный код для примера Runspace10.</span><span class="sxs-lookup"><span data-stu-id="f8256-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="f8256-104">В этом образце приложения добавляет командлету, чтобы [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) , а затем использует сведения о конфигурации, измененный на его создание.</span><span class="sxs-lookup"><span data-stu-id="f8256-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="f8256-105">Вы можете скачать C# исходный файл (runspace10.cs) с помощью Windows Software Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="f8256-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="f8256-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="f8256-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="f8256-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="f8256-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f8256-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="f8256-108">Code Sample</span></span>

[!code-csharp[Runspace10.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs#L11-L118 "Runspace10.cs")]

## <a name="see-also"></a><span data-ttu-id="f8256-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f8256-109">See Also</span></span>

[<span data-ttu-id="f8256-110">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8256-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="f8256-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8256-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)