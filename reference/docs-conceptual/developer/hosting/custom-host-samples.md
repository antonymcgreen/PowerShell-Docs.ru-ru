---
title: Примеры настраиваемого узла | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55aee25b-bbcb-4d41-a4c0-fb8e30c4cdc1
caps.latest.revision: 11
ms.openlocfilehash: 1e58b74cf1c37c70ebfb0f4970cfbf8a8263ec5c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367513"
---
# <a name="custom-host-samples"></a><span data-ttu-id="42dd3-102">Примеры пользовательских узлов</span><span class="sxs-lookup"><span data-stu-id="42dd3-102">Custom Host Samples</span></span>

<span data-ttu-id="42dd3-103">В этом разделе содержится пример кода для написания пользовательского узла.</span><span class="sxs-lookup"><span data-stu-id="42dd3-103">This section includes sample code for writing a custom host.</span></span> <span data-ttu-id="42dd3-104">С помощью Microsoft Visual Studio можно создать консольное приложение, а затем скопировать код из разделов этого раздела в ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="42dd3-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="42dd3-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="42dd3-105">In This Section</span></span>

 <span data-ttu-id="42dd3-106">[Пример Host01](./host01-sample.md) В этом примере показано, как реализовать ведущее приложение, которое использует базовый пользовательский узел.</span><span class="sxs-lookup"><span data-stu-id="42dd3-106">[Host01 Sample](./host01-sample.md) This sample shows how to implement a host application that uses a basic custom host.</span></span>

 <span data-ttu-id="42dd3-107">[Пример Host02](./host02-sample.md) В этом примере показано, как создать ведущее приложение, которое использует среду выполнения Windows PowerShell вместе с реализацией пользовательского узла.</span><span class="sxs-lookup"><span data-stu-id="42dd3-107">[Host02 Sample](./host02-sample.md) This sample shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span> <span data-ttu-id="42dd3-108">Ведущее приложение устанавливает немецкий язык и региональные параметры, запускает командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и отображает результаты, как это можно увидеть с помощью пврш. exe, а затем выводит текущие данные и время на немецком языке.</span><span class="sxs-lookup"><span data-stu-id="42dd3-108">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them using pwrsh.exe, and then prints out the current data and time in German.</span></span>

 <span data-ttu-id="42dd3-109">[Пример Host03](./host03-sample.md) В этом примере показано, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="42dd3-109">[Host03 Sample](./host03-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

 <span data-ttu-id="42dd3-110">[Пример Host04](./host04-sample.md) В этом примере показано, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="42dd3-110">[Host04 Sample](./host04-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="42dd3-111">Это приложение также поддерживает отображение запросов, позволяющих пользователю выбрать несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="42dd3-111">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

 <span data-ttu-id="42dd3-112">[Пример Host05](./host05-sample.md) В этом примере показано, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="42dd3-112">[Host05 Sample](./host05-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="42dd3-113">Это ведущее приложение также поддерживает вызовы удаленных компьютеров с помощью командлетов [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) и [Exit-PSSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) .</span><span class="sxs-lookup"><span data-stu-id="42dd3-113">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets</span></span>

 <span data-ttu-id="42dd3-114">[Пример Host06](./host06-sample.md) В этом примере показано, как создать консольное приложение на основе консоли, которое считывает команды из командной строки, выполняет команды и выводит результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="42dd3-114">[Host06 Sample](./host06-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="42dd3-115">Кроме того, в этом примере используются интерфейсы API создателя токенов для указания цвета текста, вводимого пользователем.</span><span class="sxs-lookup"><span data-stu-id="42dd3-115">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="42dd3-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="42dd3-116">See Also</span></span>
