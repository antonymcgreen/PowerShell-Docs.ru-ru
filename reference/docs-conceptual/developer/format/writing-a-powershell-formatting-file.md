---
title: Написание файла форматирования PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39acce45-5144-43ba-894d-a4ce782fa67d
caps.latest.revision: 13
ms.openlocfilehash: f89f0009972d5237d71cb8f0d1c53cd0ae614b67
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361413"
---
# <a name="writing-a-powershell-formatting-file"></a><span data-ttu-id="e0178-102">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0178-102">Writing a PowerShell Formatting File</span></span>

<span data-ttu-id="e0178-103">"Написание файла форматирования PowerShell" предназначен для разработчиков команд, создающих командлеты или функции, которые выводят объекты в командную строку.</span><span class="sxs-lookup"><span data-stu-id="e0178-103">"Writing a PowerShell Formatting File" is for command developers who are writing cmdlets or functions that output objects to the command line.</span></span> <span data-ttu-id="e0178-104">Файлы форматирования определяют, как PowerShell отображает эти объекты в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e0178-104">Formatting files define how PowerShell displays those objects at the command line.</span></span> <span data-ttu-id="e0178-105">Эта документация содержит общие сведения о файлах форматирования, объяснение понятий, которые следует понимать при написании этих файлов, примеры XML-файлов, используемых в этих файлах, и справочный раздел для XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="e0178-105">This documentation provides an overview of formatting files, an explanation of the concepts that you should understand when writing these files, examples of XML used in these files, and a reference section for the XML elements.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e0178-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="e0178-106">In This Section</span></span>

<span data-ttu-id="e0178-107">[Общие сведения о файле форматирования](./formatting-file-overview.md) Описывает, что такое файл форматирования и общие компоненты файла форматирования, включая общие функции, которые могут быть определены в файле, различные типы представлений формата, которые могут быть определены для объектов .NET, и упрощенный пример XML-кода, используемого для определения таблицы v. рейти.</span><span class="sxs-lookup"><span data-stu-id="e0178-107">[Formatting File Overview](./formatting-file-overview.md) Describes what a format file is and the general components of a formatting file, including common features that can be defined in the file, the different types of format views that can be defined for .NET objects, and a simplified example of the XML used to define a table view.</span></span>

<span data-ttu-id="e0178-108">[Основные понятия файла форматирования](./formatting-file-concepts.md) Содержит сведения, которые может потребоваться знать при создании собственных файлов форматирования, таких как различные типы представлений, которые можно определить и специальные компоненты этих представлений.</span><span class="sxs-lookup"><span data-stu-id="e0178-108">[Formatting File Concepts](./formatting-file-concepts.md) Includes information that you might need to know when creating your own formatting files, such as the different types of views that you can define and special components of those views.</span></span>

<span data-ttu-id="e0178-109">[Примеры файлов форматирования](./examples-of-formatting-files.md) Содержит XML-примеры нескольких файлов форматирования, включая примеры табличного представления, представления списка и расширенного представления, а также примеры, демонстрирующие определение таких функций, как наборы выбора, условия выбора и общие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="e0178-109">[Examples of Formatting Files](./examples-of-formatting-files.md) Provides XML examples of several formatting files, including examples of a table view, a list view, and a wide view, as well as examples that show how to define features such as selection sets, selection conditions, and common controls.</span></span>

<span data-ttu-id="e0178-110">[Формат XML-ссылки](./format-schema-xml-reference.md) Содержит справочные разделы по XML-элементам, используемым в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="e0178-110">[Format XML Reference](./format-schema-xml-reference.md) Includes reference topics for the XML elements used in a formatting file.</span></span>
