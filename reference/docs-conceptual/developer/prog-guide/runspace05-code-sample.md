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
ms.openlocfilehash: 8802e308712be93992ead5ef77b97d8c21b137f7
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870648"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="0a114-102">Примеры кода RunSpace05</span><span class="sxs-lookup"><span data-stu-id="0a114-102">RunSpace05 Code Sample</span></span>

<span data-ttu-id="0a114-103">Ниже приведен исходный код для примера Runspace05, описанный в разделе [Настройка пространства выполнения с помощью рунспацеконфигуратион](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span><span class="sxs-lookup"><span data-stu-id="0a114-103">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span></span>
<span data-ttu-id="0a114-104">В этом примере показано, как создать сведения о конфигурации пространства выполнения, создать пространство выполнения, создать конвейер с помощью одной команды, а затем выполнить конвейер.</span><span class="sxs-lookup"><span data-stu-id="0a114-104">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="0a114-105">Выполняемая команда является командлетом `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="0a114-105">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="0a114-106">C# Исходный файл (runspace05.cs) можно загрузить с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="0a114-106">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="0a114-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="0a114-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="0a114-108">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="0a114-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="0a114-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="0a114-109">Code Sample</span></span>

[!code-csharp[Runspace05.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a><span data-ttu-id="0a114-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0a114-110">See Also</span></span>

[<span data-ttu-id="0a114-111">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a114-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="0a114-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a114-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
