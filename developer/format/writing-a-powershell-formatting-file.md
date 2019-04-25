---
title: Запись файла форматирования PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39acce45-5144-43ba-894d-a4ce782fa67d
caps.latest.revision: 13
ms.openlocfilehash: f89f0009972d5237d71cb8f0d1c53cd0ae614b67
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083581"
---
# <a name="writing-a-powershell-formatting-file"></a><span data-ttu-id="3ea31-102">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ea31-102">Writing a PowerShell Formatting File</span></span>

<span data-ttu-id="3ea31-103">«Запись файла форматирования PowerShell» предназначен для команды разработчиков, создающих командлеты или функции, которые выводят объекты в командную строку.</span><span class="sxs-lookup"><span data-stu-id="3ea31-103">"Writing a PowerShell Formatting File" is for command developers who are writing cmdlets or functions that output objects to the command line.</span></span> <span data-ttu-id="3ea31-104">Файлы форматирования определяют отображение этих объектов в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ea31-104">Formatting files define how PowerShell displays those objects at the command line.</span></span> <span data-ttu-id="3ea31-105">Эта документация Обзор форматирования файлы, объяснение того, основные понятия, которые следует понимать при написании эти файлы, примеры XML, используемых в эти файлы и справочник по элементам XML.</span><span class="sxs-lookup"><span data-stu-id="3ea31-105">This documentation provides an overview of formatting files, an explanation of the concepts that you should understand when writing these files, examples of XML used in these files, and a reference section for the XML elements.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3ea31-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="3ea31-106">In This Section</span></span>

<span data-ttu-id="3ea31-107">[Общие сведения о файлах форматирования](./formatting-file-overview.md) описывает, какой формат файла и общие компоненты форматирования файла, включая общие компоненты, которые могут быть определены в файле, различные типы формата представления, которые могут быть определены для объектов .NET и упрощенный пример того, XML, используемый для определения таблицы представления.</span><span class="sxs-lookup"><span data-stu-id="3ea31-107">[Formatting File Overview](./formatting-file-overview.md) Describes what a format file is and the general components of a formatting file, including common features that can be defined in the file, the different types of format views that can be defined for .NET objects, and a simplified example of the XML used to define a table view.</span></span>

<span data-ttu-id="3ea31-108">[Форматирование файла понятия](./formatting-file-concepts.md) включает сведения, которые необходимо знать при создании собственный формат файлов, таких как различные типы представлений, которые можно определить и специальные компоненты представления.</span><span class="sxs-lookup"><span data-stu-id="3ea31-108">[Formatting File Concepts](./formatting-file-concepts.md) Includes information that you might need to know when creating your own formatting files, such as the different types of views that you can define and special components of those views.</span></span>

<span data-ttu-id="3ea31-109">[Примеры файлов форматирования](./examples-of-formatting-files.md) XML предоставляет примеры из нескольких файлов форматирования, включая примеры представление таблицы, представления списка и широкое представление, а также примеры, которые показывают, как определить функции, такие как выбор наборов условий выборки и Стандартные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="3ea31-109">[Examples of Formatting Files](./examples-of-formatting-files.md) Provides XML examples of several formatting files, including examples of a table view, a list view, and a wide view, as well as examples that show how to define features such as selection sets, selection conditions, and common controls.</span></span>

<span data-ttu-id="3ea31-110">[Форматировать Справочник по XML](./format-schema-xml-reference.md) включает справочные разделы по элементы XML, используемые в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="3ea31-110">[Format XML Reference](./format-schema-xml-reference.md) Includes reference topics for the XML elements used in a formatting file.</span></span>
