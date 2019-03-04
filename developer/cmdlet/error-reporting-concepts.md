---
title: Основные понятия отчетов об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.assetid: 0dce97c0-bd9a-4691-8ca3-e8d5dea902c5
caps.latest.revision: 11
ms.openlocfilehash: aac6b7b6ac8a0fad15194b6d3f92c434524fabdb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855080"
---
# <a name="error-reporting-concepts"></a><span data-ttu-id="fe98e-102">Основные понятия, связанные с отчетами об ошибках</span><span class="sxs-lookup"><span data-stu-id="fe98e-102">Error Reporting Concepts</span></span>

<span data-ttu-id="fe98e-103">Windows PowerShell предоставляет два механизма для сообщений об ошибках: один механизм для *завершение ошибки* и еще один механизм *устранимые ошибки*.</span><span class="sxs-lookup"><span data-stu-id="fe98e-103">Windows PowerShell provides two mechanisms for reporting errors: one mechanism for *terminating errors* and another mechanism for *non-terminating errors*.</span></span> <span data-ttu-id="fe98e-104">Очень важно для командлета для сообщения об ошибках правильно, чтобы ведущее приложение, на котором выполняется командлетов может реагировать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="fe98e-104">It is important for your cmdlet to report errors correctly so that the host application that is running your cmdlets can react in an appropriate manner.</span></span>

<span data-ttu-id="fe98e-105">Необходимо вызвать командлет [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) метод при возникновении ошибки, который не поддерживает или не должен разрешать командлет, чтобы продолжить обработку входные объекты.</span><span class="sxs-lookup"><span data-stu-id="fe98e-105">Your cmdlet should call the [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method when an error occurs that does not or should not allow the cmdlet to continue to process its input objects.</span></span> <span data-ttu-id="fe98e-106">Необходимо вызвать командлет [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод, позволяющий сообщить устранимые ошибки, когда командлет может продолжить обработку входных объектов.</span><span class="sxs-lookup"><span data-stu-id="fe98e-106">Your cmdlet should call the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report non-terminating errors when the cmdlet can continue processing the input objects.</span></span> <span data-ttu-id="fe98e-107">Оба метода обеспечивают запись об ошибке, ведущее приложение можно использовать, чтобы установить причину ошибки.</span><span class="sxs-lookup"><span data-stu-id="fe98e-107">Both methods provide an error record that the host application can use to investigate the cause of the error.</span></span>

<span data-ttu-id="fe98e-108">Чтобы определить, является ли ошибка точки в конце или устранимую ошибку, следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="fe98e-108">Use the following guidelines to determine whether an error is a terminating or non-terminating error.</span></span>

- <span data-ttu-id="fe98e-109">Ошибка является неустранимую ошибку, если он предотвращает командлета продолжение для обработки текущего объекта или успешно обрабатывать любые дополнительные входные объекты, независимо от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="fe98e-109">An error is a terminating error if it prevents your cmdlet from continuing to process the current object or from successfully processing any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="fe98e-110">Ошибка является неустранимую ошибку, если вы не хотите командлета для продолжения обработки текущего объекта или дальнейшей входных объектов, независимо от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="fe98e-110">An error is a terminating error if you do not want your cmdlet to continue processing the current object or any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="fe98e-111">Ошибка является неустранимую ошибку, если оно присутствует в командлет, который не принимают или возвращают объект, или если оно присутствует в командлет, который принимает или возвращает только один объект.</span><span class="sxs-lookup"><span data-stu-id="fe98e-111">An error is a terminating error if it occurs in a cmdlet that does not accept or return an object or if it occurs in a cmdlet that accepts or returns only one object.</span></span>

- <span data-ttu-id="fe98e-112">Ошибка является неустранимой ошибки, если вы хотите продолжить обработку текущий объект и все дополнительные входные объекты в командлет.</span><span class="sxs-lookup"><span data-stu-id="fe98e-112">An error is a non-terminating error if you want your cmdlet to continue processing the current object and any further input objects.</span></span>

- <span data-ttu-id="fe98e-113">Ошибка является неустранимой ошибки, если она связана с отдельный входной объект или подмножество входных объектов.</span><span class="sxs-lookup"><span data-stu-id="fe98e-113">An error is a non-terminating error if it is related to a specific input object or subset of input objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe98e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fe98e-114">See Also</span></span>

[<span data-ttu-id="fe98e-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span><span class="sxs-lookup"><span data-stu-id="fe98e-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[<span data-ttu-id="fe98e-116">System.Management.Automation.Cmdlet.Writeerror\*</span><span class="sxs-lookup"><span data-stu-id="fe98e-116">System.Management.Automation.Cmdlet.Writeerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="fe98e-117">Записи об ошибках PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="fe98e-117">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="fe98e-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe98e-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
