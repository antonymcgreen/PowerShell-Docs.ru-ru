---
title: Пример кода RunSpace08 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: 21d7c4fe69e5026089676c43ad69a4263732cc34
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978259"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="cee22-102">Примеры кода RunSpace08</span><span class="sxs-lookup"><span data-stu-id="cee22-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="cee22-103">Ниже приведен исходный код для примера Runspace08, описанного в разделе [Создание консольного приложения, добавляющего в команду Параметры](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span><span class="sxs-lookup"><span data-stu-id="cee22-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="cee22-104">Этот пример приложения создает пространство выполнения, создает конвейер, добавляет две команды в конвейер, добавляет два параметра во вторую команду, а затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="cee22-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="cee22-105">Команды, добавляемые в конвейер, являются командлетами `Get-Process` и `Sort-Object`.</span><span class="sxs-lookup"><span data-stu-id="cee22-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="cee22-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="cee22-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="cee22-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="cee22-107">See Also</span></span>

[<span data-ttu-id="cee22-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cee22-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
