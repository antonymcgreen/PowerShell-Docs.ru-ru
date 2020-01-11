---
title: Пример кода RunSpace07 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad306d9-45c2-4d55-8e64-fdcba43402c5
caps.latest.revision: 6
ms.openlocfilehash: f40b24951c44c228d85524845045aea58f680f2e
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870614"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="09240-102">Примеры кода RunSpace07</span><span class="sxs-lookup"><span data-stu-id="09240-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="09240-103">Ниже приведен исходный код для примера Runspace07, описанного в разделе [Создание консольного приложения, добавляющего команды в конвейер](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span><span class="sxs-lookup"><span data-stu-id="09240-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="09240-104">Этот пример приложения создает пространство выполнения, создает конвейер, добавляет в конвейер две команды, а затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="09240-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="09240-105">Команды, добавленные в конвейер, являются командлетами `Get-Process` и `Measure-Object`.</span><span class="sxs-lookup"><span data-stu-id="09240-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="09240-106">C# Исходный файл (runspace07.cs) можно загрузить с помощью пакета средств разработки программного обеспечения Microsoft Windows для компонентов среды выполнения Windows Vista и Microsoft .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="09240-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="09240-107">Инструкции по загрузке см. в статье [Установка Windows PowerShell и Загрузка пакета SDK для Windows PowerShell](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="09240-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="09240-108">Скачанные исходные файлы доступны в **\<примеров PowerShell >** Directory.</span><span class="sxs-lookup"><span data-stu-id="09240-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="09240-109">Образец кода</span><span class="sxs-lookup"><span data-stu-id="09240-109">Code Sample</span></span>

[!code-csharp[Runspace07.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a><span data-ttu-id="09240-110">См. также</span><span class="sxs-lookup"><span data-stu-id="09240-110">See Also</span></span>

[<span data-ttu-id="09240-111">Руководством программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09240-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="09240-112">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09240-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
