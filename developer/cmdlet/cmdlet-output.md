---
title: Выходные данные командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1362f4cd-4e05-4ace-ade6-7128da8ad86c
caps.latest.revision: 10
ms.openlocfilehash: 4c6aacd49b0a87bca6806ba5f08a1b4d48a90959
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853820"
---
# <a name="cmdlet-output"></a><span data-ttu-id="ff852-102">Выходные данные командлета</span><span class="sxs-lookup"><span data-stu-id="ff852-102">Cmdlet Output</span></span>

<span data-ttu-id="ff852-103">В этом разделе рассматриваются типы выходных данных командлета и методы, которые могут вызывать командлеты для создания выходных данных, таких как сообщения об ошибках и объекты.</span><span class="sxs-lookup"><span data-stu-id="ff852-103">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="ff852-104">В этом разделе также описывается, как определить типы .NET Framework, возвращаемые командлетов и отображения этих объектов.</span><span class="sxs-lookup"><span data-stu-id="ff852-104">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff852-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="ff852-105">In This Section</span></span>

<span data-ttu-id="ff852-106">[Типы выходных данных командлета](./types-of-cmdlet-output.md) описывает типы и выходные данные, которые можно создавать командлеты и методы, которые вызывают командлеты для создания выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ff852-106">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="ff852-107">[Отчеты об ошибках командлет](./cmdlet-error-reporting.md) рассматриваются командлет об ошибках, подмножество выходные данные командлета.</span><span class="sxs-lookup"><span data-stu-id="ff852-107">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="ff852-108">[Расширение выходных объектов](./extending-output-objects.md) описывает, как использовать файлы типов (ps1xml) для расширения объектов .NET Framework, которые возвращаются, командлеты, функции и сценарии.</span><span class="sxs-lookup"><span data-stu-id="ff852-108">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="ff852-109">[Файлы форматирования PowerShell](../format/powershell-formatting-files.md) описывает файлы форматирования (. format.ps1xml) отображать файлы, которые определяют значение по умолчанию для определенного набора объектов .NET Framework в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff852-109">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="ff852-110">[Пользовательские файлы форматирования](./custom-formatting-files.md) описывает, как создать собственный пользовательский формат файлов для перезаписи по умолчанию форматы отображения, или для определения отображения объектов, возвращенных собственные команды.</span><span class="sxs-lookup"><span data-stu-id="ff852-110">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff852-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ff852-111">See Also</span></span>

[<span data-ttu-id="ff852-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff852-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
