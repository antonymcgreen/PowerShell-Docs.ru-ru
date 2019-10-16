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
ms.openlocfilehash: da8455a72f6a50b8ab17650541cde8cc9c98a8fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366473"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="e2718-102">Примеры кода RunSpace10</span><span class="sxs-lookup"><span data-stu-id="e2718-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="e2718-103">Ниже приведен исходный код для примера Runspace10.</span><span class="sxs-lookup"><span data-stu-id="e2718-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="e2718-104">Этот пример приложения добавляет командлет в [System. Management. Automation. пространства. рунспацеконфигуратион](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) , а затем использует измененные сведения о конфигурации для создания пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="e2718-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="e2718-105">C# Исходный файл (runspace10.cs) можно скачать с помощью пакета средств разработки программного обеспечения Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="e2718-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="e2718-106">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="e2718-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="e2718-107">Скачанные исходные файлы доступны в каталоге **\<PowerShell samples >** Directory.</span><span class="sxs-lookup"><span data-stu-id="e2718-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e2718-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="e2718-108">Code Sample</span></span>

[!code-csharp[Runspace10.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs#L11-L118 "Runspace10.cs")]

## <a name="see-also"></a><span data-ttu-id="e2718-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2718-109">See Also</span></span>

[<span data-ttu-id="e2718-110">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2718-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e2718-111">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2718-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
