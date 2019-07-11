---
title: Пример кода RunSpace05 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: abf19d848f6150d005c63bb0fc2ffbe1de405e2a
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734970"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="7c40d-102">Примеры кода RunSpace05</span><span class="sxs-lookup"><span data-stu-id="7c40d-102">RunSpace05 Code Sample</span></span>

<span data-ttu-id="7c40d-103">Ниже приведен исходный код для примера Runspace05, описанный в [Настройка RunspaceConfiguration пространство выполнения с помощью](https://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2).</span><span class="sxs-lookup"><span data-stu-id="7c40d-103">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2).</span></span> <span data-ttu-id="7c40d-104">В этом примере показано, как создать пространство выполнения сведения о конфигурации, создать пространство выполнения, создание конвейера с помощью одной команды и затем выполнить конвейер.</span><span class="sxs-lookup"><span data-stu-id="7c40d-104">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="7c40d-105">— Команда, выполняемая `Get-Process` командлета.</span><span class="sxs-lookup"><span data-stu-id="7c40d-105">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="7c40d-106">Вы можете скачать C# исходный файл (runspace05.cs) с помощью Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="7c40d-106">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="7c40d-107">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="7c40d-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="7c40d-108">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="7c40d-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="7c40d-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="7c40d-109">Code Sample</span></span>

[!code-csharp[Runspace05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a><span data-ttu-id="7c40d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7c40d-110">See Also</span></span>

[<span data-ttu-id="7c40d-111">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c40d-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="7c40d-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c40d-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)