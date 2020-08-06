---
title: Пример PowerShell02 для Windows | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a82366a88addb08e186eede79e621d90d915c50f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779392"
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

## <a name="see-also"></a>См. также

[Написание ведущего приложения Windows PowerShell](./writing-a-windows-powershell-host-application.md)
