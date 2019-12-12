---
title: Учебники по написанию командлетов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0b548aa-febf-45dd-bf71-2077730b9b73
caps.latest.revision: 6
ms.openlocfilehash: 767b392bd1603e83d80bad5b3fd9cb42ff142ce6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369323"
---
# <a name="tutorials-for-writing-cmdlets"></a>Руководства по написанию командлетов

В этом разделе содержатся учебники по написанию командлетов. В эти учебники входит код, необходимый для написания командлетов, а также объясняется, зачем нужен код. Эти разделы будут очень полезны для тех, кто только начинает писать командлеты.

> [!IMPORTANT]
> Сведения о том, кому нужны примеры кода с меньшим описанием, см. в разделе [примеры командлетов](./cmdlet-samples.md).

## <a name="in-this-section"></a>Содержание

[Учебник по INPROC](./getproc-tutorial.md) . в этом учебнике описывается определение класса командлета и Добавление базовых функций, таких как добавление параметров и сообщения об ошибках. Командлет, описанный в этом руководстве, очень похож на командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) , предоставляемый Windows PowerShell.

[Учебник по стоппрок](./stopproc-tutorial.md) . в этом учебнике описывается, как определить командлет и добавить такие функции, как запросы пользователя, поддержка подстановочных знаков и использование наборов параметров. Описанный здесь командлет выполняет ту же задачу, что и командлет [-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) , предоставляемый Windows PowerShell.

[Учебник по селектстр](./selectstr-tutorial.md) . в этом учебнике описывается, как определить командлет, обращающийся к хранилищу данных. Описанный здесь командлет выполняет ту же задачу, что и командлет [Select-String](/powershell/module/microsoft.powershell.utility/select-string) , предоставляемый Windows PowerShell.

## <a name="see-also"></a>См. также:

[Учебник по процедурам INPROC](./getproc-tutorial.md)

[Руководство по Стоппрок](./stopproc-tutorial.md)

[Руководство по Селектстр](./selectstr-tutorial.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
