---
ms.date: 09/13/2016
ms.topic: reference
title: Как объявить динамические параметры
description: Как объявить динамические параметры
ms.openlocfilehash: 0f5a8f249b414663aa9702a908ea5c8ca24755ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667085"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="c572a-103">Как объявить динамические параметры</span><span class="sxs-lookup"><span data-stu-id="c572a-103">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="c572a-104">В этом примере показано, как определить динамические параметры, добавляемые в командлет во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c572a-104">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="c572a-105">В этом примере `Department` параметр добавляется в командлет каждый раз, когда пользователь указывает `Employee` параметр Switch.</span><span class="sxs-lookup"><span data-stu-id="c572a-105">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="c572a-106">Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета](./cmdlet-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c572a-106">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="c572a-107">Определение динамических параметров</span><span class="sxs-lookup"><span data-stu-id="c572a-107">To define dynamic parameters</span></span>

1. <span data-ttu-id="c572a-108">В объявлении класса командлета добавьте интерфейс [System. Management. Automation. идинамикпараметерс](/dotnet/api/System.Management.Automation.IDynamicParameters) , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="c572a-108">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="c572a-109">Вызовите метод [System. Management. Automation. идинамикпараметерс. жетдинамикпараметерс \*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) , который возвращает объект, в котором определены динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="c572a-109">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="c572a-110">В этом примере метод вызывается при `Employee` указании параметра.</span><span class="sxs-lookup"><span data-stu-id="c572a-110">In this example, the method is called when the `Employee` parameter is specified.</span></span>

   ```csharp
   public object GetDynamicParameters()
   {
       if (employee)
       {
         context= new SendGreetingCommandDynamicParameters();
         return context;
       }
       return null;
   }
   private SendGreetingCommandDynamicParameters context;
   ```

3. <span data-ttu-id="c572a-111">Объявите класс, который определяет динамические параметры для добавления.</span><span class="sxs-lookup"><span data-stu-id="c572a-111">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="c572a-112">Для объявления динамических параметров можно использовать атрибуты, которые использовались для объявления параметров статического командлета.</span><span class="sxs-lookup"><span data-stu-id="c572a-112">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

   ```csharp
   public class SendGreetingCommandDynamicParameters
   {
     [Parameter]
     [ValidateSet ("Marketing", "Sales", "Development")]
     public string Department
     {
       get { return department; }
       set { department = value; }
     }
     private string department;
   }
   ```

## <a name="example"></a><span data-ttu-id="c572a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c572a-113">Example</span></span>

<span data-ttu-id="c572a-114">В этом примере `Department` параметр добавляется каждый раз, когда пользователь указывает `Employee` параметр.</span><span class="sxs-lookup"><span data-stu-id="c572a-114">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="c572a-115">`Department`Параметр является необязательным параметром, и для указания допустимых аргументов используется атрибут Validate.</span><span class="sxs-lookup"><span data-stu-id="c572a-115">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;     // PowerShell assembly.

namespace SendGreeting
{
  // Declare the cmdlet class that supports the
  // IDynamicParameters interface.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet, IDynamicParameters
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    [Parameter]
    [Alias ("FTE")]
    public SwitchParameter Employee
    {
      get { return employee; }
      set { employee = value; }
    }
    private Boolean employee;

    // Implement GetDynamicParameters to
    // retrieve the dynamic parameter.
    public object GetDynamicParameters()
    {
      if (employee)
      {
        context= new SendGreetingCommandDynamicParameters();
        return context;
      }
      return null;
   }
   private SendGreetingCommandDynamicParameters context;

    // Overide the ProcessRecord method to process the
    // supplied user name and write out a greeting to
    // the user by calling the WriteObject method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "! ");
      if (employee)
      {
        WriteObject("Department: " + context.Department);
      }
    }
  }

  // Define the dynamic parameters to be added
  public class SendGreetingCommandDynamicParameters
  {
    [Parameter]
    [ValidateSet ("Marketing", "Sales", "Development")]
    public string Department
    {
      get { return department; }
      set { department = value; }
    }
    private string department;
  }
}
```

## <a name="see-also"></a><span data-ttu-id="c572a-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="c572a-116">See Also</span></span>

[<span data-ttu-id="c572a-117">System. Management. Automation. Рунтимедефинедпараметердиктионари</span><span class="sxs-lookup"><span data-stu-id="c572a-117">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="c572a-118">System. Management. Automation. Идинамикпараметерс. Жетдинамикпараметерс \*</span><span class="sxs-lookup"><span data-stu-id="c572a-118">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="c572a-119">Динамические параметры командлетов</span><span class="sxs-lookup"><span data-stu-id="c572a-119">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="c572a-120">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c572a-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
