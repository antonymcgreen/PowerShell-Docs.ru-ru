---
title: Runspace01 (C#) образец кода | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 59320365c4a35c3d71af10273eb21b1ce01e5c0c
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429709"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="0e625-102">Пример кода Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="0e625-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="0e625-103">Ниже приведены примеры кода для пространства выполнения, описанных в [Создание консольного приложения, запускающегося команды указан](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span><span class="sxs-lookup"><span data-stu-id="0e625-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span></span> <span data-ttu-id="0e625-104">Чтобы сделать это, приложение вызывает пространство выполнения и затем вызывает команду.</span><span class="sxs-lookup"><span data-stu-id="0e625-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="0e625-105">(Обратите внимание, что это приложение не содержит сведения о конфигурации пространства выполнения, а также ли его явным образом создать конвейер).</span><span class="sxs-lookup"><span data-stu-id="0e625-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="0e625-106">Команда, вызываемая `Get-Process` командлета.</span><span class="sxs-lookup"><span data-stu-id="0e625-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="0e625-107">Вы можете скачать C# исходный файл (runspace01.cs) для этого пространства выполнения, используя Microsoft Windows программное обеспечение Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="0e625-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="0e625-108">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="0e625-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="0e625-109">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="0e625-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="0e625-110">Пример кода</span><span class="sxs-lookup"><span data-stu-id="0e625-110">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="0e625-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0e625-111">See Also</span></span>

[<span data-ttu-id="0e625-112">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e625-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="0e625-113">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e625-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)