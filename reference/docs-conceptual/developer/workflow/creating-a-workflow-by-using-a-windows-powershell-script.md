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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366033"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a>Создание рабочего процесса с помощью сценария Windows PowerShell

Рабочий процесс можно создать, написав сценарий Windows PowerShell. Чтобы создать рабочий процесс, используйте ключевое слово Workflow, за которым следует имя рабочего процесса перед телом скрипта. Пример:

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

Рабочий процесс можно найти так же, как и любую другую команду Windows PowerShell.

## <a name="implementing-parallel-and-sequence"></a>Реализация Parallel и Sequence

[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) поддерживает параллельное выполнение действий. Чтобы реализовать эту возможность в сценарии Windows PowerShell, используйте ключевое слово `parallel` перед блоком сценария. Можно также использовать конструкцию `foreach -parallel` для параллельного прохода по коллекции объектов. Чтобы выполнить группу действий в последовательном порядке внутри параллельного блока, заключите эту группу действий в блок скрипта и перед блоком с помощью ключевого слова Sequence.

## <a name="joining-computers-to-a-domain"></a>Присоединение компьютеров к домену

Следующий скрипт создает рабочий процесс, который проверяет состояние домена указанных пользователем компьютеров, присоединяет их к домену, если они еще не присоединены, а затем снова проверяет состояние. Это версия скрипта рабочего процесса XAML, описанная в разделах [Создание рабочего процесса с помощью действий Windows PowerShell](./creating-a-workflow-with-windows-powershell-activities.md).

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