---
title: Отчеты об ошибках Windows PowerShell | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7f7afcf5186732734976304c8e58e4d940156e1e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783965"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="c5f9c-102">Отчеты об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5f9c-102">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="c5f9c-103">В подразделах этого раздела описывается, как командлеты сообщают об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-103">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c5f9c-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c5f9c-104">In This Section</span></span>

<span data-ttu-id="c5f9c-105">[Основные понятия отчетов об ошибках](./error-reporting-concepts.md) Описывает два механизма, которые командлеты могут использовать для сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-105">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="c5f9c-106">[Завершение ошибок](./terminating-errors.md) Описывает метод, используемый для сообщения о завершении ошибок, когда этот метод может быть вызван из командлета, и исключения, которые могут возвращаться средой выполнения Windows PowerShell при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-106">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="c5f9c-107">[Ошибки, не прерывающие](./non-terminating-errors.md) работу Описывает метод, используемый для сообщения об устранимых ошибках и в котором метод может быть вызван из командлета.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-107">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="c5f9c-108">[Отображение сведений об ошибках по категориям](./displaying-error-information.md) Описывает способы, с помощью которых пользователи могут отображать ошибку.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-108">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="c5f9c-109">[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md) Описывает компоненты записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-109">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="c5f9c-110">[Интерпретация объектов ерроррекорд](./interpreting-errorrecord-objects.md) Описывает, как обрабатываются объекты Ерроррекорд.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-110">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5f9c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c5f9c-111">See Also</span></span>

[<span data-ttu-id="c5f9c-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5f9c-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
