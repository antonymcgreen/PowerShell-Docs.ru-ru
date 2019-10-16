---
title: Сообщения подтверждения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a886a26d-7730-4586-aeac-fd3f0bc60b88
caps.latest.revision: 8
ms.openlocfilehash: 229725b5b9f1f0082592dcebe11564fd2f630ce1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365733"
---
# <a name="confirmation-messages"></a><span data-ttu-id="f406f-102">Сообщения подтверждения</span><span class="sxs-lookup"><span data-stu-id="f406f-102">Confirmation Messages</span></span>

<span data-ttu-id="f406f-103">Ниже приведены различные сообщения с подтверждением, которые могут отображаться в зависимости от того, какие методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызываются.</span><span class="sxs-lookup"><span data-stu-id="f406f-103">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f406f-104">Пример кода, демонстрирующий запрос подтверждений, см. [в разделе как запросить подтверждения](./how-to-request-confirmations.md).</span><span class="sxs-lookup"><span data-stu-id="f406f-104">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="f406f-105">Указание ресурса</span><span class="sxs-lookup"><span data-stu-id="f406f-105">Specifying the Resource</span></span>

<span data-ttu-id="f406f-106">Вы можете указать ресурс, который собираетесь изменить, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) .</span><span class="sxs-lookup"><span data-stu-id="f406f-106">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="f406f-107">В этом случае ресурс предоставляется с помощью параметра `target` метода, и эта операция добавляется Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f406f-107">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="f406f-108">В следующем сообщении текст "MyResource" — это ресурс, на котором выполняется операция, а в качестве операции используется имя команды, выполняющей вызов.</span><span class="sxs-lookup"><span data-stu-id="f406f-108">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="f406f-109">Если пользователь выбирает **Да** или **Да для всех** запросов подтверждения (как показано в следующем примере), вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , который вызывает второе сообщение с подтверждением. отображаем.</span><span class="sxs-lookup"><span data-stu-id="f406f-109">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="f406f-110">Указание операции и ресурса</span><span class="sxs-lookup"><span data-stu-id="f406f-110">Specifying the Operation and Resource</span></span>

<span data-ttu-id="f406f-111">Можно указать ресурс, который будет изменен, и операцию, которую должна выполнить команда, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) .</span><span class="sxs-lookup"><span data-stu-id="f406f-111">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="f406f-112">В этом случае ресурс предоставляется с помощью параметра `target` и операции с помощью параметра `target`.</span><span class="sxs-lookup"><span data-stu-id="f406f-112">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="f406f-113">В следующем сообщении текст "MyResource" — это работающий с ресурсом, а "Мяктион" — выполняемая операция.</span><span class="sxs-lookup"><span data-stu-id="f406f-113">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="f406f-114">Если пользователь выбирает **Да** или **Да для всех** предыдущих сообщений, вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , что приводит к отображению второго сообщения подтверждения.</span><span class="sxs-lookup"><span data-stu-id="f406f-114">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="f406f-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="f406f-115">See Also</span></span>

[<span data-ttu-id="f406f-116">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f406f-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
