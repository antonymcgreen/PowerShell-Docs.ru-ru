---
title: Пример PowerShell02 Windows | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: 89ad17257ebac56105a93672317a149515e80d32
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082521"
---
# <a name="windows-powershell02-sample"></a>Пример Windows PowerShell02

В этом примере показано, как выполнять команды асинхронно с помощью пространства выполнения пула пространства выполнения. В примере список команд и затем выполняет эти команды, пока подсистемы Windows PowerShell открывается пространство из пула, при необходимости.

## <a name="requirements"></a>Требования

- В этом примере требуется Windows PowerShell 2.0.

## <a name="demonstrates"></a>Демонстрирует

Этот образец демонстрирует следующее:

- Создание объекта RunspacePool с минимальным и максимальным количеством пространства выполнения может быть открыто одновременно.

- Создание списка команд.

- Асинхронное выполнение команды.

- Вызов [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) метод, чтобы увидеть, сколько пространства выполнения предоставляются бесплатно.

- Запись выходных данных команды с [System.Management.Automation.Powershell.Endinvoke*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) метод.

## <a name="example"></a>Пример

В этом примере показано, как открыть пространства выполнения пула пространство выполнения и асинхронное выполнение команд в пространства выполнения.

[!code-csharp[PowerShell02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a>См. также

[Создание приложения Windows PowerShell узла](./writing-a-windows-powershell-host-application.md)