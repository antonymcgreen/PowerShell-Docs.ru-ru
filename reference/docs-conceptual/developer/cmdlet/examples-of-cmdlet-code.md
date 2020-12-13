---
ms.date: 09/13/2016
ms.topic: reference
title: Примеры кода командлетов
description: Примеры кода командлетов
ms.openlocfilehash: 91dd2019300504697ad9a7a0c155a04600d09c58
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652920"
---
# <a name="examples-of-cmdlet-code"></a>Примеры кода командлетов

В этом разделе приводятся примеры кода командлетов, которые можно использовать для написания собственных командлетов.

> [!IMPORTANT]
> Пошаговые инструкции по написанию командлетов см. в [руководствах по написанию командлетов](./tutorials-for-writing-cmdlets.md).

## <a name="in-this-section"></a>в этом разделе

[Написание простого командлета](./how-to-write-a-simple-cmdlet.md) В этом примере показана базовая структура кода командлета.

[Как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md) В этом примере показано, как объявить различные типы параметров.

[Объявление наборов параметров](./how-to-declare-parameter-sets.md) В этом примере показано, как объявить наборы параметров, которые могут изменить действие, выполняемое командлетом.

[Проверка входных параметров](./how-to-validate-parameter-input.md) В этих примерах показано, как проверить входные данные параметра.

[Объявление динамических параметров](./how-to-declare-dynamic-parameters.md) В этом примере показано, как объявить параметр, добавляемый во время выполнения.

[Как вызывать скрипты в командлете](./how-to-invoke-scripts-within-a-cmdlet.md) В этом примере показано, как вызвать скрипт, передаваемый в командлет.

[Переопределение методов обработки входных данных](./how-to-override-input-processing-methods.md) В этих примерах показана базовая структура, используемая для переопределения методов BeginProcessing, ProcessRecord и EndProcessing.

[Поддержка вызовов ShouldProcess](./how-to-request-confirmations.md) В этом примере показано, как вызывать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) из командлета.

[Поддержка транзакций](./how-to-support-transactions.md) В этом примере показано, как указать, что командлет поддерживает транзакции и как реализовать действие, выполняемое при использовании командлета в транзакции.

[Поддержка заданий](./how-to-support-jobs.md) В этом примере показано, как поддерживать задания при записи командлетов.

[Вызов командлета из командлета](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) В этом примере показано, как вызвать командлет из другого командлета, который позволяет добавлять функциональные возможности вызванного командлета в разрабатываемый командлет.

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
