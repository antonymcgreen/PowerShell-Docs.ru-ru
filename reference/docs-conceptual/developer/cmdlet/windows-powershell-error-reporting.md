---
title: Отчеты об ошибках Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61b7773a-c346-4835-a928-7212dc4c85bc
caps.latest.revision: 7
ms.openlocfilehash: 259de341fd2fcce2b0c4629f806b4348cba1ff2c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364273"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="8c868-102">Отчеты об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c868-102">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="8c868-103">В подразделах этого раздела описывается, как командлеты сообщают об ошибках.</span><span class="sxs-lookup"><span data-stu-id="8c868-103">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8c868-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="8c868-104">In This Section</span></span>

<span data-ttu-id="8c868-105">[Основные понятия отчетов об ошибках](./error-reporting-concepts.md) Описывает два механизма, которые командлеты могут использовать для сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="8c868-105">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="8c868-106">[Завершение ошибок](./terminating-errors.md) Описывает метод, используемый для сообщения о завершении ошибок, когда этот метод может быть вызван из командлета, и исключения, которые могут возвращаться средой выполнения Windows PowerShell при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="8c868-106">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="8c868-107">[Ошибки, не прерывающие](./non-terminating-errors.md) работу Описывает метод, используемый для сообщения об устранимых ошибках и в котором метод может быть вызван из командлета.</span><span class="sxs-lookup"><span data-stu-id="8c868-107">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="8c868-108">[Отображение сведений об ошибках по категориям](./displaying-error-information.md) Описывает способы, с помощью которых пользователи могут отображать ошибку.</span><span class="sxs-lookup"><span data-stu-id="8c868-108">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="8c868-109">[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md) Описывает компоненты записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="8c868-109">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="8c868-110">[Интерпретация объектов ерроррекорд](./interpreting-errorrecord-objects.md) Описывает, как обрабатываются объекты Ерроррекорд.</span><span class="sxs-lookup"><span data-stu-id="8c868-110">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c868-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="8c868-111">See Also</span></span>

[<span data-ttu-id="8c868-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c868-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
