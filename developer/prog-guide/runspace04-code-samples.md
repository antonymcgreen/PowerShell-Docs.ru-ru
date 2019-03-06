---
title: Примеры кода RunSpace04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb6fcc47-cf89-43e7-b686-3d60934ce3e7
caps.latest.revision: 6
ms.openlocfilehash: 2a3e7598c433027fdd96343829c0606fc7b1c37c
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429471"
---
# <a name="runspace04-code-samples"></a><span data-ttu-id="dc76c-102">Примеры кода RunSpace04</span><span class="sxs-lookup"><span data-stu-id="dc76c-102">RunSpace04 Code Samples</span></span>

<span data-ttu-id="dc76c-103">Ниже приведен пример кода для пространства выполнения, который использует [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) класса, чтобы выполнить скрипт, который создает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="dc76c-103">Here is a code sample for a runspace that uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that generates a terminating error.</span></span> <span data-ttu-id="dc76c-104">Ведущее приложение отвечает за перехват ошибок и интерпретации запись об ошибке.</span><span class="sxs-lookup"><span data-stu-id="dc76c-104">The host application is responsible for catching the error and interpreting the error record.</span></span>

> [!NOTE]
> <span data-ttu-id="dc76c-105">Для этого пространства выполнения, используя Windows Software Development Kit для Windows Vista и компоненты среды выполнения Microsoft .NET Framework 3.0 можно загрузить исходный файл VB.NET (Runspace04.vb).</span><span class="sxs-lookup"><span data-stu-id="dc76c-105">You can download the VB.NET source file (Runspace04.vb) for this runspace using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="dc76c-106">Инструкции по загрузке см. в разделе [как установка Windows PowerShell и загрузки пакета SDK для Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="dc76c-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="dc76c-107">Скачанный исходные файлы доступны в  **\<примеры PowerShell >** каталога.</span><span class="sxs-lookup"><span data-stu-id="dc76c-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="dc76c-108">Полный пример кода см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="dc76c-108">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="dc76c-109">Language</span><span class="sxs-lookup"><span data-stu-id="dc76c-109">Language</span></span>|<span data-ttu-id="dc76c-110">Раздел</span><span class="sxs-lookup"><span data-stu-id="dc76c-110">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="dc76c-111">VB.NET</span><span class="sxs-lookup"><span data-stu-id="dc76c-111">VB.NET</span></span>|[<span data-ttu-id="dc76c-112">Runspace01 пример кода (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="dc76c-112">Runspace01 (VB.NET) Code Sample</span></span>](./runspace01-vb-net-code-sample.md)|

## <a name="see-also"></a><span data-ttu-id="dc76c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dc76c-113">See Also</span></span>

[<span data-ttu-id="dc76c-114">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc76c-114">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="dc76c-115">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc76c-115">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)