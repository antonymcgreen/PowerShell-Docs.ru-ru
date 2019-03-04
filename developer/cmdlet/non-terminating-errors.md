---
title: Устранимые ошибки | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 468dabd6-bfeb-448d-8e09-0996db516edd
caps.latest.revision: 8
ms.openlocfilehash: 9d5c9b16fc5daf3d2f753eeeeedb0db925551a67
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853780"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="cde0b-102">Непрерывающие ошибки</span><span class="sxs-lookup"><span data-stu-id="cde0b-102">Non-Terminating Errors</span></span>

<span data-ttu-id="cde0b-103">В этом разделе рассматривается метод, используемый при устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="cde0b-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="cde0b-104">Также описывается вызов метода в командлет.</span><span class="sxs-lookup"><span data-stu-id="cde0b-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="cde0b-105">При возникновении неустранимой ошибки, командлет должен сообщить об этой ошибке, вызвав [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод.</span><span class="sxs-lookup"><span data-stu-id="cde0b-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="cde0b-106">Когда командлет сообщает о устранимую ошибку, командлет может продолжать работу этого объекта ввода и дальнейшей входящего в конвейер объектов.</span><span class="sxs-lookup"><span data-stu-id="cde0b-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="cde0b-107">Если командлет вызывает [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод, этот командлет можно написать запись об ошибке, которое описывает условие, вызвавшее устранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="cde0b-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="cde0b-108">Дополнительные сведения о записи об ошибках, см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="cde0b-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="cde0b-109">Командлеты можно вызвать [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) при необходимости из свои методы обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="cde0b-109">Cmdlets can call [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="cde0b-110">Тем не менее, можно вызывать командлеты [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) только из потока, который вызвал [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [ System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), или [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="cde0b-110">However, cmdlets can call [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="cde0b-111">Не вызывайте [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из другого потока.</span><span class="sxs-lookup"><span data-stu-id="cde0b-111">Do not call [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="cde0b-112">Вместо этого сообщения об ошибках, в основной поток.</span><span class="sxs-lookup"><span data-stu-id="cde0b-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="cde0b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cde0b-113">See Also</span></span>

[<span data-ttu-id="cde0b-114">System.Management.Automation.Cmdlet.Writeerror\*</span><span class="sxs-lookup"><span data-stu-id="cde0b-114">System.Management.Automation.Cmdlet.Writeerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="cde0b-115">System.Management.Automation.Cmdlet.Beginprocessing\*</span><span class="sxs-lookup"><span data-stu-id="cde0b-115">System.Management.Automation.Cmdlet.Beginprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="cde0b-116">System.Management.Automation.Cmdlet.Processrecord\*</span><span class="sxs-lookup"><span data-stu-id="cde0b-116">System.Management.Automation.Cmdlet.Processrecord\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="cde0b-117">System.Management.Automation.Cmdlet.Endprocessing\*</span><span class="sxs-lookup"><span data-stu-id="cde0b-117">System.Management.Automation.Cmdlet.Endprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="cde0b-118">Записи об ошибках PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="cde0b-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="cde0b-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cde0b-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
