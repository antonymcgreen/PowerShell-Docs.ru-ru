---
ms.date: 09/13/2016
ms.topic: reference
title: Руководства по написанию командлетов
description: Руководства по написанию командлетов
ms.openlocfilehash: 7ec20b845f8547d346c3777bd52984337d37b83a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646377"
---
# <a name="tutorials-for-writing-cmdlets"></a>Руководства по написанию командлетов

В этом разделе содержатся учебники по написанию командлетов. В эти учебники входит код, необходимый для написания командлетов, а также объясняется, зачем нужен код. Эти разделы будут очень полезны для тех, кто только начинает писать командлеты.

> [!IMPORTANT]
> Сведения о том, кому нужны примеры кода с меньшим описанием, см. в разделе [примеры командлетов](./cmdlet-samples.md).

## <a name="in-this-section"></a>в этом разделе

[Учебник по INPROC](./getproc-tutorial.md) . в этом учебнике описывается определение класса командлета и Добавление базовых функций, таких как добавление параметров и сообщения об ошибках. Командлет, описанный в этом руководстве, очень похож на командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) , предоставляемый Windows PowerShell.

[Учебник по стоппрок](./stopproc-tutorial.md) . в этом учебнике описывается, как определить командлет и добавить такие функции, как запросы пользователя, поддержка подстановочных знаков и использование наборов параметров. Описанный здесь командлет выполняет ту же задачу, что и командлет [-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) , предоставляемый Windows PowerShell.

[Учебник по селектстр](./selectstr-tutorial.md) . в этом учебнике описывается, как определить командлет, обращающийся к хранилищу данных. Описанный здесь командлет выполняет ту же задачу, что и командлет [Select-String](/powershell/module/microsoft.powershell.utility/select-string) , предоставляемый Windows PowerShell.

## <a name="see-also"></a>См. также:

[Руководство по GetProc](./getproc-tutorial.md)

[Руководство по StopProc](./stopproc-tutorial.md)

[Руководство по SelectStr](./selectstr-tutorial.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
