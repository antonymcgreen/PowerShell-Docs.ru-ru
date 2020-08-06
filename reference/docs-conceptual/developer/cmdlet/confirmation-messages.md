---
title: Сообщения подтверждения | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 8f8192f6ed96b1eeb22e3b28ce1366eee8e7c16a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782197"
---
# <a name="confirmation-messages"></a><span data-ttu-id="1a23c-102">Сообщения подтверждения</span><span class="sxs-lookup"><span data-stu-id="1a23c-102">Confirmation Messages</span></span>

<span data-ttu-id="1a23c-103">Ниже приведены различные сообщения с подтверждением, которые могут отображаться в зависимости от того, какие методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызываются.</span><span class="sxs-lookup"><span data-stu-id="1a23c-103">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a23c-104">Пример кода, демонстрирующий запрос подтверждений, см. [в разделе как запросить подтверждения](./how-to-request-confirmations.md).</span><span class="sxs-lookup"><span data-stu-id="1a23c-104">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="1a23c-105">Указание ресурса</span><span class="sxs-lookup"><span data-stu-id="1a23c-105">Specifying the Resource</span></span>

<span data-ttu-id="1a23c-106">Вы можете указать ресурс, который собираетесь изменить, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) .</span><span class="sxs-lookup"><span data-stu-id="1a23c-106">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="1a23c-107">В этом случае вы предоставляете ресурс с помощью `target` параметра метода, и эта операция добавляется Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a23c-107">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="1a23c-108">В следующем сообщении текст "MyResource" — это ресурс, на котором выполняется операция, а в качестве операции используется имя команды, выполняющей вызов.</span><span class="sxs-lookup"><span data-stu-id="1a23c-108">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="1a23c-109">Если пользователь выбирает **Да** или **Да для всех** запросов подтверждения (как показано в следующем примере), вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , что приводит к отображению второго сообщения с подтверждением.</span><span class="sxs-lookup"><span data-stu-id="1a23c-109">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="1a23c-110">Указание операции и ресурса</span><span class="sxs-lookup"><span data-stu-id="1a23c-110">Specifying the Operation and Resource</span></span>

<span data-ttu-id="1a23c-111">Можно указать ресурс, который будет изменен, и операцию, которую должна выполнить команда, вызвав метод [System. Management. Automation. командлет. ShouldProcess% 2A? DisplayProperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) .</span><span class="sxs-lookup"><span data-stu-id="1a23c-111">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="1a23c-112">В этом случае вы предоставляете ресурс с помощью `target` параметра и операции с помощью `target` параметра.</span><span class="sxs-lookup"><span data-stu-id="1a23c-112">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="1a23c-113">В следующем сообщении текст "MyResource" — это работающий с ресурсом, а "Мяктион" — выполняемая операция.</span><span class="sxs-lookup"><span data-stu-id="1a23c-113">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="1a23c-114">Если пользователь выбирает **Да** или **Да для всех** предыдущих сообщений, вызывается метод [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , что приводит к отображению второго сообщения подтверждения.</span><span class="sxs-lookup"><span data-stu-id="1a23c-114">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="1a23c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1a23c-115">See Also</span></span>

[<span data-ttu-id="1a23c-116">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a23c-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
