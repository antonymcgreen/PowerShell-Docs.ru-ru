---
ms.date: 09/13/2016
ms.topic: reference
title: Отчеты об ошибках Windows PowerShell
description: Отчеты об ошибках Windows PowerShell
ms.openlocfilehash: 438e3d96bf52d8ac1f770c0550ae49b356d616eb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650107"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="255d4-103">Отчеты об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="255d4-103">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="255d4-104">В подразделах этого раздела описывается, как командлеты сообщают об ошибках.</span><span class="sxs-lookup"><span data-stu-id="255d4-104">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="255d4-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="255d4-105">In This Section</span></span>

<span data-ttu-id="255d4-106">[Основные понятия отчетов об ошибках](./error-reporting-concepts.md) Описывает два механизма, которые командлеты могут использовать для сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="255d4-106">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="255d4-107">[Завершение ошибок](./terminating-errors.md) Описывает метод, используемый для сообщения о завершении ошибок, когда этот метод может быть вызван из командлета, и исключения, которые могут возвращаться средой выполнения Windows PowerShell при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="255d4-107">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="255d4-108">[Ошибки, не прерывающие](./non-terminating-errors.md) работу Описывает метод, используемый для сообщения об устранимых ошибках и в котором метод может быть вызван из командлета.</span><span class="sxs-lookup"><span data-stu-id="255d4-108">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="255d4-109">[Отображение сведений об ошибках по категориям](./displaying-error-information.md) Описывает способы, с помощью которых пользователи могут отображать ошибку.</span><span class="sxs-lookup"><span data-stu-id="255d4-109">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="255d4-110">[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md) Описывает компоненты записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="255d4-110">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="255d4-111">[Интерпретация объектов ерроррекорд](./interpreting-errorrecord-objects.md) Описывает, как обрабатываются объекты Ерроррекорд.</span><span class="sxs-lookup"><span data-stu-id="255d4-111">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="255d4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="255d4-112">See Also</span></span>

[<span data-ttu-id="255d4-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="255d4-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
