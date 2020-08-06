---
title: Пример кода Runspace02 (C#) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1e58f035f20baa7443d9031499062a45beae01b9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778450"
---
# <a name="runspace02-c-code-sample"></a>Пример кода Runspace02 (C#)

Ниже приведен исходный код C# для примера Runspace02. В этом примере используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для `Get-Process` синхронного выполнения командлета. Windows Forms и привязка данных используются для вывода результатов в элементе управления DataGridView.

## <a name="code-sample"></a>Образец кода

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
