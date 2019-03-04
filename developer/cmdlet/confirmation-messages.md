---
title: Подтверждение | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a886a26d-7730-4586-aeac-fd3f0bc60b88
caps.latest.revision: 8
ms.openlocfilehash: 75214a3fe4bc019836f75db19fb873bd081f200f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861420"
---
# <a name="confirmation-messages"></a><span data-ttu-id="28a66-102">Сообщения подтверждения</span><span class="sxs-lookup"><span data-stu-id="28a66-102">Confirmation Messages</span></span>

<span data-ttu-id="28a66-103">Ниже приведены различные подтверждающих сообщений, которые могут отображаться в зависимости от того, варианты [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [ System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы, вызываемые.</span><span class="sxs-lookup"><span data-stu-id="28a66-103">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28a66-104">Пример кода, показывающий, как для запроса подтверждения, см. в разделе [как подтверждения](./how-to-request-confirmations.md).</span><span class="sxs-lookup"><span data-stu-id="28a66-104">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="28a66-105">Указание ресурса</span><span class="sxs-lookup"><span data-stu-id="28a66-105">Specifying the Resource</span></span>

<span data-ttu-id="28a66-106">Можно указать ресурс, который собираетесь изменить, вызвав [System.Management.Automation.Cmdlet.Shouldprocess%2A? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) метод.</span><span class="sxs-lookup"><span data-stu-id="28a66-106">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="28a66-107">В этом случае указать ресурс с помощью `target` добавлен параметр метода, и операции с Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28a66-107">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="28a66-108">В следующее сообщение: текст «MyResource» — это ресурс, обрабатываемого и операции является имя команды, которая выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="28a66-108">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="28a66-109">Если пользователь выбирает **Да** или **Да для всех** для подтверждения запроса (как показано в следующем примере), вызов [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод будет установлено, что вызывает второе сообщение с подтверждением для отображения.</span><span class="sxs-lookup"><span data-stu-id="28a66-109">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="28a66-110">Задание операции и ресурсов</span><span class="sxs-lookup"><span data-stu-id="28a66-110">Specifying the Operation and Resource</span></span>

<span data-ttu-id="28a66-111">Можно указать ресурс должен быть изменен и операцию, команда должна выполнить путем вызова [System.Management.Automation.Cmdlet.Shouldprocess%2A? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) метод.</span><span class="sxs-lookup"><span data-stu-id="28a66-111">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="28a66-112">В этом случае указать ресурс с помощью `target` параметр и операцию, используя `target` параметра.</span><span class="sxs-lookup"><span data-stu-id="28a66-112">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="28a66-113">В следующее сообщение: текст «MyResource» — это ресурс, обрабатываемого, а «MyAction» — операцию для выполнения.</span><span class="sxs-lookup"><span data-stu-id="28a66-113">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="28a66-114">Если пользователь выбирает **Да** или **Да для всех** к предыдущему сообщению, вызов [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод будет установлено, что приводит второе сообщение с подтверждением для отображения.</span><span class="sxs-lookup"><span data-stu-id="28a66-114">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="28a66-115">См. также</span><span class="sxs-lookup"><span data-stu-id="28a66-115">See Also</span></span>

[<span data-ttu-id="28a66-116">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28a66-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
