---
title: Основные понятия отчетов об ошибках | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.openlocfilehash: ff010bbe1a87daa351ec13ed249ffc899781a8c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774513"
---
# <a name="error-reporting-concepts"></a><span data-ttu-id="a6841-102">Основные понятия, связанные с отчетами об ошибках</span><span class="sxs-lookup"><span data-stu-id="a6841-102">Error Reporting Concepts</span></span>

<span data-ttu-id="a6841-103">Windows PowerShell предоставляет два механизма для создания отчетов об ошибках: один механизм для *завершения ошибок* и другой механизм *неустранимых ошибок*.</span><span class="sxs-lookup"><span data-stu-id="a6841-103">Windows PowerShell provides two mechanisms for reporting errors: one mechanism for *terminating errors* and another mechanism for *non-terminating errors*.</span></span> <span data-ttu-id="a6841-104">Для правильной работы командлета необходимо правильно сообщать об ошибках, чтобы ведущее приложение, выполняющее командлеты, мог реагировать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6841-104">It is important for your cmdlet to report errors correctly so that the host application that is running your cmdlets can react in an appropriate manner.</span></span>

<span data-ttu-id="a6841-105">Командлет должен вызвать метод [System. Management. Automation. командлет. ThrowTerminatingError \*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) при возникновении ошибки, которая не позволяет командлету продолжить обработку своих входных объектов.</span><span class="sxs-lookup"><span data-stu-id="a6841-105">Your cmdlet should call the [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method when an error occurs that does not or should not allow the cmdlet to continue to process its input objects.</span></span> <span data-ttu-id="a6841-106">Командлет должен вызвать метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) для сообщения об устранимых ошибках, когда командлет может продолжить обработку входных объектов.</span><span class="sxs-lookup"><span data-stu-id="a6841-106">Your cmdlet should call the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report non-terminating errors when the cmdlet can continue processing the input objects.</span></span> <span data-ttu-id="a6841-107">Оба метода предоставляют запись об ошибке, которую ведущее приложение может использовать для исследования причины ошибки.</span><span class="sxs-lookup"><span data-stu-id="a6841-107">Both methods provide an error record that the host application can use to investigate the cause of the error.</span></span>

<span data-ttu-id="a6841-108">Используйте следующие рекомендации, чтобы определить, является ли ошибка завершающей или устранимой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a6841-108">Use the following guidelines to determine whether an error is a terminating or non-terminating error.</span></span>

- <span data-ttu-id="a6841-109">Ошибка является завершающей ошибкой, если она не позволяет командлету продолжить обработку текущего объекта или успешно обработать все последующие входные объекты, независимо от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="a6841-109">An error is a terminating error if it prevents your cmdlet from continuing to process the current object or from successfully processing any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="a6841-110">Ошибка является завершающей ошибкой, если не нужно, чтобы командлет продолжал обрабатывать текущий объект или любые последующие входные объекты, независимо от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="a6841-110">An error is a terminating error if you do not want your cmdlet to continue processing the current object or any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="a6841-111">Ошибка — это завершающая ошибка, если она возникает в командлете, который не принимает или не возвращает объект, или если он происходит в командлете, который принимает или возвращает только один объект.</span><span class="sxs-lookup"><span data-stu-id="a6841-111">An error is a terminating error if it occurs in a cmdlet that does not accept or return an object or if it occurs in a cmdlet that accepts or returns only one object.</span></span>

- <span data-ttu-id="a6841-112">Ошибка — это Неустранимая ошибка, если необходимо, чтобы командлет продолжал обрабатывать текущий объект и все последующие входные объекты.</span><span class="sxs-lookup"><span data-stu-id="a6841-112">An error is a non-terminating error if you want your cmdlet to continue processing the current object and any further input objects.</span></span>

- <span data-ttu-id="a6841-113">Ошибка — это Неустранимая ошибка, если она связана с определенным входным объектом или подмножеством входных объектов.</span><span class="sxs-lookup"><span data-stu-id="a6841-113">An error is a non-terminating error if it is related to a specific input object or subset of input objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6841-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a6841-114">See Also</span></span>

[<span data-ttu-id="a6841-115">System. Management. Automation. командлет. ThrowTerminatingError \*</span><span class="sxs-lookup"><span data-stu-id="a6841-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[<span data-ttu-id="a6841-116">System. Management. Automation. командлет. WriteError</span><span class="sxs-lookup"><span data-stu-id="a6841-116">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="a6841-117">Записи об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6841-117">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="a6841-118">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6841-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
