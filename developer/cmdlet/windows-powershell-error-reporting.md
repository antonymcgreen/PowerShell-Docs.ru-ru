---
title: Отчетов об ошибках Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61b7773a-c346-4835-a928-7212dc4c85bc
caps.latest.revision: 7
ms.openlocfilehash: 259de341fd2fcce2b0c4629f806b4348cba1ff2c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067099"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="32bd5-102">Отчеты об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32bd5-102">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="32bd5-103">В этом разделе рассматриваются, как командлеты сообщать об ошибках.</span><span class="sxs-lookup"><span data-stu-id="32bd5-103">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="32bd5-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="32bd5-104">In This Section</span></span>

<span data-ttu-id="32bd5-105">[Основные понятия служб Reporting ошибка](./error-reporting-concepts.md) описывает два механизма, которые можно использовать командлеты для сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="32bd5-105">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="32bd5-106">[Завершение ошибки](./terminating-errors.md) описывает метод, используемый для отчетов, завершение ошибок, где этот метод может вызываться из командлета и исключения, которые могут быть возвращены средой выполнения Windows PowerShell, при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="32bd5-106">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="32bd5-107">[Устранимые ошибки](./non-terminating-errors.md) описывает метод, используемый для отчетов устранимые ошибки и где этот метод можно вызвать из командлета.</span><span class="sxs-lookup"><span data-stu-id="32bd5-107">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="32bd5-108">[Отображение сведений об ошибках по категориям](./displaying-error-information.md) обсуждаются способы, что пользователи могут отображать ошибки.</span><span class="sxs-lookup"><span data-stu-id="32bd5-108">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="32bd5-109">[Записи об ошибках Windows PowerShell](./windows-powershell-error-records.md) описание компонентов записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="32bd5-109">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="32bd5-110">[Интерпретация объекты ErrorRecord](./interpreting-errorrecord-objects.md) описывает способ интерпретации ErrorRecord объектов.</span><span class="sxs-lookup"><span data-stu-id="32bd5-110">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="32bd5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="32bd5-111">See Also</span></span>

[<span data-ttu-id="32bd5-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32bd5-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
