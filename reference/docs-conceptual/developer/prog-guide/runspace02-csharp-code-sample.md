---
title: Пример кодаC#Runspace02 () | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59a7b8b9-f72e-43fd-9a10-77404441a3f2
caps.latest.revision: 6
ms.openlocfilehash: 047d14d70853399bc262ac3f1541da38184c3ff8
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977885"
---
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="fc183-102">Пример кода Runspace02 (C#)</span><span class="sxs-lookup"><span data-stu-id="fc183-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="fc183-103">Ниже приведен C# исходный код для примера Runspace02.</span><span class="sxs-lookup"><span data-stu-id="fc183-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="fc183-104">В этом примере используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для синхронного выполнения командлета `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="fc183-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="fc183-105">Windows Forms и привязка данных используются для вывода результатов в элементе управления DataGridView.</span><span class="sxs-lookup"><span data-stu-id="fc183-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="fc183-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="fc183-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a><span data-ttu-id="fc183-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc183-107">See Also</span></span>

[<span data-ttu-id="fc183-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc183-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
