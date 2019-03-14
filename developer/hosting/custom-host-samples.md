---
title: Примеры пользовательских узлов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55aee25b-bbcb-4d41-a4c0-fb8e30c4cdc1
caps.latest.revision: 11
ms.openlocfilehash: 1e58b74cf1c37c70ebfb0f4970cfbf8a8263ec5c
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794150"
---
# <a name="custom-host-samples"></a><span data-ttu-id="731eb-102">Примеры пользовательских узлов</span><span class="sxs-lookup"><span data-stu-id="731eb-102">Custom Host Samples</span></span>

<span data-ttu-id="731eb-103">Этот раздел содержит пример кода для написания пользовательского ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="731eb-103">This section includes sample code for writing a custom host.</span></span> <span data-ttu-id="731eb-104">Microsoft Visual Studio можно использовать для создания консольного приложения и затем скопируйте код из подразделы этого раздела в ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="731eb-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="731eb-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="731eb-105">In This Section</span></span>

 <span data-ttu-id="731eb-106">[Пример Host01](./host01-sample.md) в этом примере показано, как реализовать ведущее приложение, которое использует базовый пользовательский узел.</span><span class="sxs-lookup"><span data-stu-id="731eb-106">[Host01 Sample](./host01-sample.md) This sample shows how to implement a host application that uses a basic custom host.</span></span>

 <span data-ttu-id="731eb-107">[Пример Host02](./host02-sample.md) в этом примере показано, как написать ведущее приложение, использующее среду выполнения Windows PowerShell вместе с реализацией пользовательского узла.</span><span class="sxs-lookup"><span data-stu-id="731eb-107">[Host02 Sample](./host02-sample.md) This sample shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span> <span data-ttu-id="731eb-108">Ведущее приложение задает в качестве региональных параметров немецкий язык, запускает [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) командлета и отображает те результаты, что вы увидите их использовании pwrsh.exe, а затем выводит текущие дату и время на немецком языке.</span><span class="sxs-lookup"><span data-stu-id="731eb-108">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them using pwrsh.exe, and then prints out the current data and time in German.</span></span>

 <span data-ttu-id="731eb-109">[Пример Host03](./host03-sample.md) в этом примере показано, как сборку интерактивного консольного ведущего приложения, читает команды из командной строки, выполняет команды и затем отображает результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="731eb-109">[Host03 Sample](./host03-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

 <span data-ttu-id="731eb-110">[Пример Host04](./host04-sample.md) в этом примере показано, как сборку интерактивного консольного ведущего приложения, читает команды из командной строки, выполняет команды и затем отображает результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="731eb-110">[Host04 Sample](./host04-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="731eb-111">Это приложение также поддерживает отображение запросов, позволяющих пользователю выбрать несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="731eb-111">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

 <span data-ttu-id="731eb-112">[Пример узел05](./host05-sample.md) в этом примере показано, как сборку интерактивного консольного ведущего приложения, читает команды из командной строки, выполняет команды и затем отображает результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="731eb-112">[Host05 Sample](./host05-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="731eb-113">Это ведущее приложение также поддерживает вызовы удаленных компьютеров с помощью [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) и [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) командлетов</span><span class="sxs-lookup"><span data-stu-id="731eb-113">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets</span></span>

 <span data-ttu-id="731eb-114">[Пример Host06](./host06-sample.md) в этом примере показано, как сборку интерактивного консольного ведущего приложения, читает команды из командной строки, выполняет команды и затем отображает результаты на консоль.</span><span class="sxs-lookup"><span data-stu-id="731eb-114">[Host06 Sample](./host06-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="731eb-115">Кроме того, в этом примере используются интерфейсы API создателя токенов для указания цвета текста, вводимого пользователем.</span><span class="sxs-lookup"><span data-stu-id="731eb-115">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="731eb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="731eb-116">See Also</span></span>
