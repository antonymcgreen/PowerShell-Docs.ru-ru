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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369603"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="a0fa9-102">Непрерывающие ошибки</span><span class="sxs-lookup"><span data-stu-id="a0fa9-102">Non-Terminating Errors</span></span>

<span data-ttu-id="a0fa9-103">В этом разделе обсуждается метод, используемый для сообщения об устранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="a0fa9-104">В нем также обсуждается вызов метода из командлета.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="a0fa9-105">При возникновении неустранимой ошибки командлет должен сообщить об этой ошибке, вызвав метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) .</span><span class="sxs-lookup"><span data-stu-id="a0fa9-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="a0fa9-106">Когда командлет сообщает о неустранимой ошибке, командлет может продолжить работу с этим входным объектом и дальнейшими входящими объектами конвейера.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="a0fa9-107">Если командлет вызывает метод [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) , командлет может записать запись об ошибке, описывающую условие, вызвавшее неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="a0fa9-108">Дополнительные сведения о записях об ошибках см. в статье [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="a0fa9-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="a0fa9-109">Командлеты могут вызывать [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) в соответствии с их методами обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-109">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="a0fa9-110">Однако командлеты могут вызывать [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) только из потока, вызвавшего [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System. Management. Automation. командлет. ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)или метода обработки ввода [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="a0fa9-110">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="a0fa9-111">Не вызывайте [System. Management. Automation. командлет. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) из другого потока.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-111">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="a0fa9-112">Вместо этого следует сообщать об ошибках обратно в основной поток.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0fa9-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0fa9-113">See Also</span></span>

[<span data-ttu-id="a0fa9-114">System. Management. Automation. командлет. WriteError</span><span class="sxs-lookup"><span data-stu-id="a0fa9-114">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="a0fa9-115">System. Management. Automation. командлет. BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="a0fa9-115">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="a0fa9-116">System. Management. Automation. командлет. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="a0fa9-116">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="a0fa9-117">System. Management. Automation. командлет. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="a0fa9-117">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="a0fa9-118">Записи об ошибках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0fa9-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="a0fa9-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0fa9-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
