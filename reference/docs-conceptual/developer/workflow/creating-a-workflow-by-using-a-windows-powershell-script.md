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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366033"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a><span data-ttu-id="bd763-102">Создание рабочего процесса с помощью сценария Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd763-102">Creating a Workflow by Using a Windows PowerShell Script</span></span>

<span data-ttu-id="bd763-103">Рабочий процесс можно создать, написав сценарий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd763-103">You can create a workflow by writing a Windows PowerShell script.</span></span> <span data-ttu-id="bd763-104">Чтобы создать рабочий процесс, используйте ключевое слово Workflow, за которым следует имя рабочего процесса перед телом скрипта.</span><span class="sxs-lookup"><span data-stu-id="bd763-104">To create a workflow, use the workflow keyword followed by a name for the workflow before the body of the script.</span></span> <span data-ttu-id="bd763-105">Пример:</span><span class="sxs-lookup"><span data-stu-id="bd763-105">For example:</span></span>

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

<span data-ttu-id="bd763-106">Рабочий процесс можно найти так же, как и любую другую команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd763-106">You find the workflow in the same way you would any other Windows PowerShell command.</span></span>

## <a name="implementing-parallel-and-sequence"></a><span data-ttu-id="bd763-107">Реализация Parallel и Sequence</span><span class="sxs-lookup"><span data-stu-id="bd763-107">Implementing Parallel and Sequence</span></span>

<span data-ttu-id="bd763-108">[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) поддерживает параллельное выполнение действий.</span><span class="sxs-lookup"><span data-stu-id="bd763-108">[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) supports execution of activities in parallel.</span></span> <span data-ttu-id="bd763-109">Чтобы реализовать эту возможность в сценарии Windows PowerShell, используйте ключевое слово `parallel` перед блоком сценария.</span><span class="sxs-lookup"><span data-stu-id="bd763-109">To implement this capability in a Windows PowerShell script, use the `parallel` keyword in front of a script block.</span></span> <span data-ttu-id="bd763-110">Можно также использовать конструкцию `foreach -parallel` для параллельного прохода по коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="bd763-110">You can also use the `foreach -parallel` construction to iterate through a collection of objects in parallel.</span></span> <span data-ttu-id="bd763-111">Чтобы выполнить группу действий в последовательном порядке внутри параллельного блока, заключите эту группу действий в блок скрипта и перед блоком с помощью ключевого слова Sequence.</span><span class="sxs-lookup"><span data-stu-id="bd763-111">To execute a group of activities in sequential order within a parallel block, enclose that group of activities in a script block and precede the block with the sequence keyword.</span></span>

## <a name="joining-computers-to-a-domain"></a><span data-ttu-id="bd763-112">Присоединение компьютеров к домену</span><span class="sxs-lookup"><span data-stu-id="bd763-112">Joining Computers to a Domain</span></span>

<span data-ttu-id="bd763-113">Следующий скрипт создает рабочий процесс, который проверяет состояние домена указанных пользователем компьютеров, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние.</span><span class="sxs-lookup"><span data-stu-id="bd763-113">The following script creates a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span> <span data-ttu-id="bd763-114">Это версия скрипта рабочего процесса XAML, описанная в разделах [Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md).</span><span class="sxs-lookup"><span data-stu-id="bd763-114">This is a script version of the XAML workflow explained in [Creating a Workflow with Windows PowerShell Activities](./creating-a-workflow-with-windows-powershell-activities.md).</span></span>

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