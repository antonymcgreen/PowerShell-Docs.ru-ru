---
title: Создание рабочего процесса с помощью сценария Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70532e7e-9cac-43c3-9687-e77011ecc878
caps.latest.revision: 4
ms.openlocfilehash: cc613240e056e8443b075019cbff6dd15da3716f
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557454"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a><span data-ttu-id="0ec80-102">Создание рабочего процесса с помощью сценария Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ec80-102">Creating a Workflow by Using a Windows PowerShell Script</span></span>

<span data-ttu-id="0ec80-103">Рабочий процесс можно создать, написав сценарий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ec80-103">You can create a workflow by writing a Windows PowerShell script.</span></span> <span data-ttu-id="0ec80-104">Чтобы создать рабочий процесс, используйте ключевое слово Workflow, за которым следует имя рабочего процесса перед телом скрипта.</span><span class="sxs-lookup"><span data-stu-id="0ec80-104">To create a workflow, use the workflow keyword followed by a name for the workflow before the body of the script.</span></span> <span data-ttu-id="0ec80-105">Пример:</span><span class="sxs-lookup"><span data-stu-id="0ec80-105">For example:</span></span>

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

<span data-ttu-id="0ec80-106">Рабочий процесс можно найти так же, как и любую другую команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ec80-106">You find the workflow in the same way you would any other Windows PowerShell command.</span></span>

## <a name="implementing-parallel-and-sequence"></a><span data-ttu-id="0ec80-107">Реализация Parallel и Sequence</span><span class="sxs-lookup"><span data-stu-id="0ec80-107">Implementing Parallel and Sequence</span></span>

<span data-ttu-id="0ec80-108">[Windows Workflow Foundation](/previous-versions/dotnet/netframework-3.5/ms735967(v=vs.90)) поддерживает параллельное выполнение действий.</span><span class="sxs-lookup"><span data-stu-id="0ec80-108">[Windows Workflow Foundation](/previous-versions/dotnet/netframework-3.5/ms735967(v=vs.90)) supports execution of activities in parallel.</span></span> <span data-ttu-id="0ec80-109">Чтобы реализовать эту возможность в сценарии Windows PowerShell, используйте `parallel` ключевое слово перед блоком сценария.</span><span class="sxs-lookup"><span data-stu-id="0ec80-109">To implement this capability in a Windows PowerShell script, use the `parallel` keyword in front of a script block.</span></span> <span data-ttu-id="0ec80-110">Можно также использовать `foreach -parallel` конструкцию для параллельного прохода по коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="0ec80-110">You can also use the `foreach -parallel` construction to iterate through a collection of objects in parallel.</span></span> <span data-ttu-id="0ec80-111">Чтобы выполнить группу действий в последовательном порядке внутри параллельного блока, заключите эту группу действий в блок скрипта и перед блоком с помощью ключевого слова Sequence.</span><span class="sxs-lookup"><span data-stu-id="0ec80-111">To execute a group of activities in sequential order within a parallel block, enclose that group of activities in a script block and precede the block with the sequence keyword.</span></span>

## <a name="joining-computers-to-a-domain"></a><span data-ttu-id="0ec80-112">Присоединение компьютеров к домену</span><span class="sxs-lookup"><span data-stu-id="0ec80-112">Joining Computers to a Domain</span></span>

<span data-ttu-id="0ec80-113">Следующий скрипт создает рабочий процесс, который проверяет состояние домена указанных пользователем компьютеров, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние.</span><span class="sxs-lookup"><span data-stu-id="0ec80-113">The following script creates a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span>
<span data-ttu-id="0ec80-114">Это версия скрипта рабочего процесса XAML, описанная в разделах [Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md).</span><span class="sxs-lookup"><span data-stu-id="0ec80-114">This is a script version of the XAML workflow explained in [Creating a Workflow with Windows PowerShell Activities](./creating-a-workflow-with-windows-powershell-activities.md).</span></span>

```powershell
workflow Join-Domain
{
    param([string[]] $ComputerName, [PSCredential] $DomainCred, [PsCredential] $MachineCred)

    foreach -parallel($Computer in $ComputerName)
    {
        sequence {
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        Add-Computer -PSComputerName $Computer -PSCredential $DomainCred
        Restart-Computer -ComputerName $Computer -Credential $MachineCred -For PowerShell -Force -Wait -PSComputerName ""
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        }
    }
}
```
