---
title: Примеры кода, командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fed2f68-ce6d-4a8f-bf21-f94f27a155c2
caps.latest.revision: 9
ms.openlocfilehash: 39c0814faf72cdb4b24730acb2ae429a2f465b32
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863130"
---
# <a name="examples-of-cmdlet-code"></a>Примеры кода командлетов

В этом разделе содержатся примеры кода командлет, который можно использовать для написания собственных командлетов.

> [!IMPORTANT]
> Пошаговые инструкции для написания командлетов, см. в разделе [учебники для написания командлетов](./tutorials-for-writing-cmdlets.md).

## <a name="in-this-section"></a>Содержание

[Как написать простой командлет](./how-to-write-a-simple-cmdlet.md) в этом примере показана базовая структура кода командлета.

[Как объявить параметры командлета](./how-to-declare-cmdlet-parameters.md) в этом примере показан способ объявления различных типов параметров.

[Как объявить наборы параметров](./how-to-declare-parameter-sets.md) в этом примере показано, как объявить наборы параметров, которые могут изменяться командлет выполняет действие.

[Как проверить входной параметр](./how-to-validate-parameter-input.md) этих примерах показано, как для проверки входных параметров.

[Как объявить динамических параметров](./how-to-declare-dynamic-parameters.md) в этом примере показано, как объявить параметр, который добавляется во время выполнения.

[Как вызывать скрипты в командлет](./how-to-invoke-scripts-within-a-cmdlet.md) в этом примере показано, как вызвать скрипт, который передается в командлет.

[Как переопределить методы обработки ввода](./how-to-override-input-processing-methods.md) в следующих примерах используется для переопределения методов BeginProcessing, ProcessRecord и EndProcessing базовую структуру.

[Как обращений в службу поддержки ShouldProcess](./how-to-request-confirmations.md) в этом примере показано, как [System.Management.Automation.Cmdlet.Shouldprocess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.Shouldcontinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)методы должны вызываться из командлета.

[Как для поддержки транзакций](./how-to-support-transactions.md) в этом примере показано, как указать, что командлет поддерживает транзакции и как реализовать действие, выполняемое при использовании с командлетом в рамках транзакции.

[Как задания поддерживают](./how-to-support-jobs.md) в этом примере показано, как для поддержки задания при написании командлетов.

[Как вызвать командлет из в командлет](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) в этом примере показано, как для вызова командлета из в другой командлет, который позволяет добавлять функциональные возможности вызванного командлета в командлет, вы разрабатываете.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
