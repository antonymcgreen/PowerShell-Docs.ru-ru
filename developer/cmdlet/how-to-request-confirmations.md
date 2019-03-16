---
title: Как запросить подтверждения | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f24f77d5-e224-4b62-b128-535e045d333e
caps.latest.revision: 9
ms.openlocfilehash: 19e96b612a8778d82cdbafb528a7ffeb01f15f99
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058833"
---
# <a name="how-to-request-confirmations"></a><span data-ttu-id="9388d-102">Как запросить подтверждение</span><span class="sxs-lookup"><span data-stu-id="9388d-102">How to Request Confirmations</span></span>

<span data-ttu-id="9388d-103">В этом примере показан способ вызова [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы для запроса подтверждения из пользователь, прежде чем произойдет.</span><span class="sxs-lookup"><span data-stu-id="9388d-103">This example shows how to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to request confirmations from the user before an action is taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9388d-104">Дополнительные сведения о том, как Windows PowerShell обрабатывает эти запросы, см. в разделе [запрашивает подтверждение](./requesting-confirmation-from-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="9388d-104">For more information about how Windows PowerShell handles these requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

## <a name="to-request-confirmation"></a><span data-ttu-id="9388d-105">Чтобы запросить подтверждение</span><span class="sxs-lookup"><span data-stu-id="9388d-105">To request confirmation</span></span>

1. <span data-ttu-id="9388d-106">Убедитесь, что `SupportsShouldProcess` командлет атрибута установлено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="9388d-106">Ensure that the `SupportsShouldProcess` parameter of the Cmdlet attribute is set to `true`.</span></span> <span data-ttu-id="9388d-107">(Для функций это параметр атрибута CmdletBinding.)</span><span class="sxs-lookup"><span data-stu-id="9388d-107">(For functions this is a parameter of the CmdletBinding attribute.)</span></span>

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. <span data-ttu-id="9388d-108">Добавление `Force` параметра командлета, чтобы пользователь может отменить запрос на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="9388d-108">Add a `Force` parameter to your cmdlet so that the user can override a confirmation request.</span></span>

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. <span data-ttu-id="9388d-109">Добавить `if` инструкцию, которая использует возвращаемое значение [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) метод на предмет [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="9388d-109">Add an `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to determine if the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is called.</span></span>

4. <span data-ttu-id="9388d-110">Добавьте второй `if` инструкцию, которая использует возвращаемое значение [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) метод и значения `Force` параметр, чтобы определить, следует ли операции выполнить.</span><span class="sxs-lookup"><span data-stu-id="9388d-110">Add a second `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method and the value of the `Force` parameter to determine whether the operation should be performed.</span></span>

## <a name="example"></a><span data-ttu-id="9388d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="9388d-111">Example</span></span>

<span data-ttu-id="9388d-112">В следующем примере кода [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы вызываются из в рамках переопределения из [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="9388d-112">In the following code example, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods are called from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="9388d-113">Тем не менее эти методы можно вызывать другие методы обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="9388d-113">However, you can also call these methods from the other input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="9388d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9388d-114">See Also</span></span>

[<span data-ttu-id="9388d-115">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9388d-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
