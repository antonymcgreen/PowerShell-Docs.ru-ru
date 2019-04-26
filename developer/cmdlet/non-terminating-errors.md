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
ms.openlocfilehash: 5f804756e0e3e867832f15f50967fd6987f160a5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067660"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="e8cdc-102">Непрерывающие ошибки</span><span class="sxs-lookup"><span data-stu-id="e8cdc-102">Non-Terminating Errors</span></span>

<span data-ttu-id="e8cdc-103">В этом разделе рассматривается метод, используемый при устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="e8cdc-104">Также описывается вызов метода в командлет.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="e8cdc-105">При возникновении неустранимой ошибки, командлет должен сообщить об этой ошибке, вызвав [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="e8cdc-106">Когда командлет сообщает о устранимую ошибку, командлет может продолжать работу этого объекта ввода и дальнейшей входящего в конвейер объектов.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="e8cdc-107">Если командлет вызывает [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) метод, этот командлет можно написать запись об ошибке, которое описывает условие, вызвавшее устранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="e8cdc-108">Дополнительные сведения о записи об ошибках, см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="e8cdc-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="e8cdc-109">Командлеты можно вызвать [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) при необходимости из свои методы обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-109">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="e8cdc-110">Тем не менее, можно вызывать командлеты [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) только из потока, который вызвал [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), или [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-110">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="e8cdc-111">Не вызывайте [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из другого потока.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-111">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="e8cdc-112">Вместо этого сообщения об ошибках, в основной поток.</span><span class="sxs-lookup"><span data-stu-id="e8cdc-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8cdc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e8cdc-113">See Also</span></span>

[<span data-ttu-id="e8cdc-114">System.Management.Automation.Cmdlet.WriteError</span><span class="sxs-lookup"><span data-stu-id="e8cdc-114">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="e8cdc-115">System.Management.Automation.Cmdlet.BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="e8cdc-115">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="e8cdc-116">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="e8cdc-116">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="e8cdc-117">System.Management.Automation.Cmdlet.EndProcessing</span><span class="sxs-lookup"><span data-stu-id="e8cdc-117">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="e8cdc-118">Записи об ошибках PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="e8cdc-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="e8cdc-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8cdc-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
