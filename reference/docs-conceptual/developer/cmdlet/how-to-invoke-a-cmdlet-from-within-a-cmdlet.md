---
ms.date: 09/13/2016
ms.topic: reference
title: Как вызвать командлет из другого командлета
description: Как вызвать командлет из другого командлета
ms.openlocfilehash: d137ac895f66000329de76a2c16a74b02c0e82ca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667051"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="33bd9-103">Как вызвать командлет из другого командлета</span><span class="sxs-lookup"><span data-stu-id="33bd9-103">How to Invoke a Cmdlet from Within a Cmdlet</span></span>

<span data-ttu-id="33bd9-104">В этом примере показано, как вызвать командлет из другого командлета, который позволяет добавлять функциональные возможности вызванного командлета в разрабатываемый командлет.</span><span class="sxs-lookup"><span data-stu-id="33bd9-104">This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span> <span data-ttu-id="33bd9-105">В этом примере `Get-Process` вызывается командлет для получения процессов, выполняемых на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="33bd9-105">In this example, the `Get-Process` cmdlet is invoked to get the processes that are running on the local computer.</span></span> <span data-ttu-id="33bd9-106">Вызов `Get-Process` командлета эквивалентен следующей команде.</span><span class="sxs-lookup"><span data-stu-id="33bd9-106">The call to the `Get-Process` cmdlet is equivalent to the following command.</span></span> <span data-ttu-id="33bd9-107">Эта команда извлекает все процессы, имена которых начинаются с символов "a" и т. д.</span><span class="sxs-lookup"><span data-stu-id="33bd9-107">This command retrieves all the processes whose names start with the characters "a" through "t".</span></span>

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> <span data-ttu-id="33bd9-108">Можно вызывать только те командлеты, которые являются производными непосредственно от класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="33bd9-108">You can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="33bd9-109">Нельзя вызвать командлет, производный от класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="33bd9-109">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="33bd9-110">Вызов командлета из командлета</span><span class="sxs-lookup"><span data-stu-id="33bd9-110">To invoke a cmdlet from within a cmdlet</span></span>

1. <span data-ttu-id="33bd9-111">Убедитесь, что указана сборка, определяющая вызываемый командлет, и что `using` добавляется соответствующая инструкция.</span><span class="sxs-lookup"><span data-stu-id="33bd9-111">Ensure that the assembly that defines the cmdlet to be invoked is referenced and that the appropriate `using` statement is added.</span></span> <span data-ttu-id="33bd9-112">В этом примере добавляются следующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="33bd9-112">In this example, the following namespaces are added.</span></span>

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. <span data-ttu-id="33bd9-113">В методе обработки входных данных командлета создайте новый экземпляр вызываемого командлета.</span><span class="sxs-lookup"><span data-stu-id="33bd9-113">In the input processing method of the cmdlet, create a new instance of the cmdlet to be invoked.</span></span> <span data-ttu-id="33bd9-114">В этом примере создается объект типа [Microsoft. PowerShell. Commands. жетпроцесскомманд](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) вместе со строкой, содержащей аргументы, используемые при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="33bd9-114">In this example, an object of type [Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) is created along with the string that contains the arguments that are used when the cmdlet is invoked.</span></span>

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. <span data-ttu-id="33bd9-115">Вызовите метод [System. Management. Automation. командлет. Invoke \*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) , чтобы вызвать `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="33bd9-115">Call the [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method to invoke the `Get-Process` cmdlet.</span></span>

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a><span data-ttu-id="33bd9-116">Пример</span><span class="sxs-lookup"><span data-stu-id="33bd9-116">Example</span></span>

<span data-ttu-id="33bd9-117">В этом примере `Get-Process` командлет вызывается из метода [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) командлета.</span><span class="sxs-lookup"><span data-stu-id="33bd9-117">In this example, the `Get-Process` cmdlet is invoked from within the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method of a cmdlet.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;   // Windows PowerShell assembly.
using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify an
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "GreetingInvoke")]
  public class SendGreetingInvokeCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the BeginProcessing method to invoke
    // the Get-Process cmdlet.
    protected override void BeginProcessing()
    {
      GetProcessCommand gp = new GetProcessCommand();
      gp.Name = new string[] { "[a-t]*" };
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="33bd9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="33bd9-118">See Also</span></span>

[<span data-ttu-id="33bd9-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33bd9-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
