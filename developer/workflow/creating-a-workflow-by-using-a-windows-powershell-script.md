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
ms.openlocfilehash: 5eb2186cbceee21f8b4a8c88b812e9c71f15e0af
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853050"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a><span data-ttu-id="9891c-102">Создание рабочего процесса с помощью сценария Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9891c-102">Creating a Workflow by Using a Windows PowerShell Script</span></span>

<span data-ttu-id="9891c-103">Можно создать рабочий процесс с помощью сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9891c-103">You can create a workflow by writing a Windows PowerShell script.</span></span> <span data-ttu-id="9891c-104">Чтобы создать рабочий процесс, используйте ключевое слово workflow, за которым следует имя рабочего процесса до основной части скрипта.</span><span class="sxs-lookup"><span data-stu-id="9891c-104">To create a workflow, use the workflow keyword followed by a name for the workflow before the body of the script.</span></span> <span data-ttu-id="9891c-105">Например:</span><span class="sxs-lookup"><span data-stu-id="9891c-105">For example:</span></span>

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

<span data-ttu-id="9891c-106">Рабочий процесс находится в так же, как любые другие команды Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9891c-106">You find the workflow in the same way you would any other Windows PowerShell command.</span></span>

## <a name="implementing-parallel-and-sequence"></a><span data-ttu-id="9891c-107">Реализация Parallel и Sequence</span><span class="sxs-lookup"><span data-stu-id="9891c-107">Implementing Parallel and Sequence</span></span>

<span data-ttu-id="9891c-108">[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) поддерживает выполнение операций в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="9891c-108">[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) supports execution of activities in parallel.</span></span> <span data-ttu-id="9891c-109">Чтобы реализовать эту возможность в сценарий Windows PowerShell, используйте `parallel` ключевое слово перед блок сценария.</span><span class="sxs-lookup"><span data-stu-id="9891c-109">To implement this capability in a Windows PowerShell script, use the `parallel` keyword in front of a script block.</span></span> <span data-ttu-id="9891c-110">Можно также использовать `foreach -parallel` конструкции для выполнения итерации по коллекции объектов в параллельном режиме.</span><span class="sxs-lookup"><span data-stu-id="9891c-110">You can also use the `foreach -parallel` construction to iterate through a collection of objects in parallel.</span></span> <span data-ttu-id="9891c-111">Чтобы выполнить группу действий в последовательном порядке в пределах параллельного блока, заключите этой группы действий в блоке скрипта и перед блоком с ключевым словом последовательности.</span><span class="sxs-lookup"><span data-stu-id="9891c-111">To execute a group of activities in sequential order within a parallel block, enclose that group of activities in a script block and precede the block with the sequence keyword.</span></span>

## <a name="joining-computers-to-a-domain"></a><span data-ttu-id="9891c-112">Присоединение компьютеров к домену</span><span class="sxs-lookup"><span data-stu-id="9891c-112">Joining Computers to a Domain</span></span>

<span data-ttu-id="9891c-113">Следующий скрипт создает рабочий процесс, который проверяет состояние домена для группы компьютеров, определяемое пользователем, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние.</span><span class="sxs-lookup"><span data-stu-id="9891c-113">The following script creates a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span> <span data-ttu-id="9891c-114">Это версия сценария рабочего процесса XAML, как описано в [Создание рабочего процесса с помощью Windows PowerShell действий](./creating-a-workflow-with-windows-powershell-activities.md).</span><span class="sxs-lookup"><span data-stu-id="9891c-114">This is a script version of the XAML workflow explained in [Creating a Workflow with Windows PowerShell Activities](./creating-a-workflow-with-windows-powershell-activities.md).</span></span>

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