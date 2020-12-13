---
ms.date: 09/13/2016
ms.topic: reference
title: Выходные данные командлета
description: Выходные данные командлета
ms.openlocfilehash: 37606e57d9dff3ed9fa25b2b99eb07efa0147127
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653265"
---
# <a name="cmdlet-output"></a><span data-ttu-id="e77c9-103">Выходные данные командлета</span><span class="sxs-lookup"><span data-stu-id="e77c9-103">Cmdlet Output</span></span>

<span data-ttu-id="e77c9-104">В этом разделе обсуждаются типы выходных данных командлета и методы, которые могут вызываться командлетами для создания выходных данных, таких как сообщения об ошибках и объекты.</span><span class="sxs-lookup"><span data-stu-id="e77c9-104">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="e77c9-105">В этом разделе также описано, как определить типы .NET Framework, возвращаемые командлетами, и способ отображения этих объектов.</span><span class="sxs-lookup"><span data-stu-id="e77c9-105">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e77c9-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e77c9-106">In This Section</span></span>

<span data-ttu-id="e77c9-107">[Типы выходных данных командлета](./types-of-cmdlet-output.md) Описывает типы и выходные данные, которые могут быть созданы командлетами, и методы, которые вызываются командлетами для создания выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e77c9-107">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="e77c9-108">[Отчеты об ошибках командлетов](./cmdlet-error-reporting.md) Описывает создание отчетов об ошибках командлетов, подмножество выходных данных командлетов.</span><span class="sxs-lookup"><span data-stu-id="e77c9-108">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="e77c9-109">[Расширение выходных объектов](./extending-output-objects.md) Описывает использование файлов типов (. ps1xml) для расширения объектов .NET Framework, возвращаемых командлетами, функциями и скриптами.</span><span class="sxs-lookup"><span data-stu-id="e77c9-109">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="e77c9-110">[Файлы форматирования PowerShell](../format/powershell-formatting-files.md) Описывает файлы форматирования (.format.ps1XML), определяющие отображение по умолчанию для определенного набора .NET Framework объектов в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e77c9-110">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="e77c9-111">[Пользовательские файлы форматирования](./custom-formatting-files.md) Описание создания собственных файлов форматирования для перезаписи форматов отображения по умолчанию или для определения отображения объектов, возвращаемых собственными командами.</span><span class="sxs-lookup"><span data-stu-id="e77c9-111">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="e77c9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e77c9-112">See Also</span></span>

[<span data-ttu-id="e77c9-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e77c9-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
