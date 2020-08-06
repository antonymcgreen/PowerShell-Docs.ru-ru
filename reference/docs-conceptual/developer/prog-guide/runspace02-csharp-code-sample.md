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
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="ffe40-102">Пример кода Runspace02 (C#)</span><span class="sxs-lookup"><span data-stu-id="ffe40-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="ffe40-103">Ниже приведен исходный код C# для примера Runspace02.</span><span class="sxs-lookup"><span data-stu-id="ffe40-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="ffe40-104">В этом примере используется класс [System. Management. Automation. рунспацеинвоке](/dotnet/api/System.Management.Automation.RunspaceInvoke) для `Get-Process` синхронного выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="ffe40-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="ffe40-105">Windows Forms и привязка данных используются для вывода результатов в элементе управления DataGridView.</span><span class="sxs-lookup"><span data-stu-id="ffe40-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="ffe40-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="ffe40-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a><span data-ttu-id="ffe40-107">См. также</span><span class="sxs-lookup"><span data-stu-id="ffe40-107">See Also</span></span>

[<span data-ttu-id="ffe40-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffe40-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
