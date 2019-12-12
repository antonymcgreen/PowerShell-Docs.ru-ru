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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365943"
---
# <a name="cmdlet-output"></a><span data-ttu-id="199ff-102">Выходные данные командлета</span><span class="sxs-lookup"><span data-stu-id="199ff-102">Cmdlet Output</span></span>

<span data-ttu-id="199ff-103">В этом разделе обсуждаются типы выходных данных командлета и методы, которые могут вызываться командлетами для создания выходных данных, таких как сообщения об ошибках и объекты.</span><span class="sxs-lookup"><span data-stu-id="199ff-103">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="199ff-104">В этом разделе также описано, как определить типы .NET Framework, возвращаемые командлетами, и способ отображения этих объектов.</span><span class="sxs-lookup"><span data-stu-id="199ff-104">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="199ff-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="199ff-105">In This Section</span></span>

<span data-ttu-id="199ff-106">[Типы выходных данных командлета](./types-of-cmdlet-output.md) Описывает типы и выходные данные, которые могут быть созданы командлетами, и методы, которые вызываются командлетами для создания выходных данных.</span><span class="sxs-lookup"><span data-stu-id="199ff-106">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="199ff-107">[Отчеты об ошибках командлетов](./cmdlet-error-reporting.md) Описывает создание отчетов об ошибках командлетов, подмножество выходных данных командлетов.</span><span class="sxs-lookup"><span data-stu-id="199ff-107">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="199ff-108">[Расширение выходных объектов](./extending-output-objects.md) Описывает использование файлов типов (. ps1xml) для расширения объектов .NET Framework, возвращаемых командлетами, функциями и скриптами.</span><span class="sxs-lookup"><span data-stu-id="199ff-108">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="199ff-109">[Файлы форматирования PowerShell](../format/powershell-formatting-files.md) Описание файлов форматирования (. Format. ps1xml), определяющих отображение по умолчанию для определенного набора объектов .NET Framework в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="199ff-109">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="199ff-110">[Пользовательские файлы форматирования](./custom-formatting-files.md) Описание создания собственных файлов форматирования для перезаписи форматов отображения по умолчанию или для определения отображения объектов, возвращаемых собственными командами.</span><span class="sxs-lookup"><span data-stu-id="199ff-110">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="199ff-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="199ff-111">See Also</span></span>

[<span data-ttu-id="199ff-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="199ff-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
