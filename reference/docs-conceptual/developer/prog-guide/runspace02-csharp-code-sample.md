---
ms.date: 09/13/2016
ms.topic: reference
title: Пример кода Runspace02 (C#)
description: Пример кода Runspace02 (C#)
ms.openlocfilehash: 9e2c0cf37d1bf12a92f4fbf781928c0241202915
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647446"
---
# <a name="runspace02-c-code-sample"></a>Пример кода Runspace02 (C#)

Ниже приведен исходный код C# для примера Runspace02. В этом примере используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для `Get-Process` синхронного выполнения командлета. Windows Forms и привязка данных используются для вывода результатов в элементе управления DataGridView.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a>См. также:

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
