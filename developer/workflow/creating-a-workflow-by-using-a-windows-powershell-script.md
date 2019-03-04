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
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a>Создание рабочего процесса с помощью сценария Windows PowerShell

Можно создать рабочий процесс с помощью сценариев Windows PowerShell. Чтобы создать рабочий процесс, используйте ключевое слово workflow, за которым следует имя рабочего процесса до основной части скрипта. Например:

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

Рабочий процесс находится в так же, как любые другие команды Windows PowerShell.

## <a name="implementing-parallel-and-sequence"></a>Реализация Parallel и Sequence

[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) поддерживает выполнение операций в параллельном режиме. Чтобы реализовать эту возможность в сценарий Windows PowerShell, используйте `parallel` ключевое слово перед блок сценария. Можно также использовать `foreach -parallel` конструкции для выполнения итерации по коллекции объектов в параллельном режиме. Чтобы выполнить группу действий в последовательном порядке в пределах параллельного блока, заключите этой группы действий в блоке скрипта и перед блоком с ключевым словом последовательности.

## <a name="joining-computers-to-a-domain"></a>Присоединение компьютеров к домену

Следующий скрипт создает рабочий процесс, который проверяет состояние домена для группы компьютеров, определяемое пользователем, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние. Это версия сценария рабочего процесса XAML, как описано в [Создание рабочего процесса с помощью Windows PowerShell действий](./creating-a-workflow-with-windows-powershell-activities.md).

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