---
title: Пример кода RunSpace08 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784696"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="fb14c-102">Примеры кода RunSpace08</span><span class="sxs-lookup"><span data-stu-id="fb14c-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="fb14c-103">Ниже приведен исходный код для примера Runspace08, описанного в разделе [Создание консольного приложения, добавляющего в команду Параметры](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span><span class="sxs-lookup"><span data-stu-id="fb14c-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="fb14c-104">Этот пример приложения создает пространство выполнения, создает конвейер, добавляет две команды в конвейер, добавляет два параметра во вторую команду, а затем выполняет конвейер.</span><span class="sxs-lookup"><span data-stu-id="fb14c-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="fb14c-105">Команды, добавляемые в конвейер, — это `Get-Process` `Sort-Object` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="fb14c-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="fb14c-106">Образец кода</span><span class="sxs-lookup"><span data-stu-id="fb14c-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="fb14c-107">См. также</span><span class="sxs-lookup"><span data-stu-id="fb14c-107">See Also</span></span>

[<span data-ttu-id="fb14c-108">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb14c-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
