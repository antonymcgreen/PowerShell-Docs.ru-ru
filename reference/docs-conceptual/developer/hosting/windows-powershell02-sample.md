---
title: Пример PowerShell02 для Windows | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: db7ff3a2dbd92f562379d206db494ab92ef08736
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367303"
---
# <a name="windows-powershell02-sample"></a>Пример Windows PowerShell02

В этом примере показано, как асинхронно выполнять команды с помощью пространств выполнения пула. В примере создается список команд, а затем выполняется выполнение этих команд, когда подсистема Windows PowerShell открывает пространство выполнения из пула, когда оно требуется.

## <a name="requirements"></a>Требования

- Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Демонстрация

В этом образце демонстрируется следующее:

- Создание объекта Рунспацепул с минимальным и максимальным числом пространств выполнения, которые могут быть открыты одновременно.

- Создание списка команд.

- Асинхронное выполнение команд.

- Вызов метода [System. Management. Automation. пространства выполнения. рунспацепул. жетаваилаблерунспацес *](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) , чтобы узнать, сколько пространств выполнения свободно.

- Запись выходных данных команды с помощью метода [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .

## <a name="example"></a>Пример

В этом образце показано, как открыть пространства выполнения пула и как асинхронно выполнять команды в этих пространствах.

[!code-csharp[PowerShell02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a>См. также:

[Написание ведущего приложения Windows PowerShell](./writing-a-windows-powershell-host-application.md)
