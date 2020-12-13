---
ms.date: 09/13/2016
ms.topic: reference
title: Пример Windows PowerShell02
description: Пример Windows PowerShell02
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657356"
---
# <a name="windows-powershell02-sample"></a>Пример Windows PowerShell02

В этом образце показано, как асинхронно выполнять команды с помощью пространств выполнения пула. В примере создается список команд, а затем выполняется выполнение этих команд, когда подсистема Windows PowerShell открывает пространство выполнения из пула, когда оно требуется.

## <a name="requirements"></a>Требования

- Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Что демонстрирует

В этом образце демонстрируется следующее:

- Создание объекта Рунспацепул с минимальным и максимальным числом пространств выполнения, которые могут быть открыты одновременно.
- Создание списка команд.
- Асинхронное выполнение команд.
- Вызов метода [System. Management. Automation. пространства выполнения. рунспацепул. жетаваилаблерунспацес *](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) , чтобы узнать, сколько пространств выполнения свободно.
- Запись выходных данных команды с помощью метода [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .

## <a name="example"></a>Пример

В этом образце показано, как открыть пространства выполнения пула и как асинхронно выполнять команды в этих пространствах.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a>См. также:

[Написание ведущего приложения Windows PowerShell](./writing-a-windows-powershell-host-application.md)
