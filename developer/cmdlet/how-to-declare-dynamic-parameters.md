---
title: Как объявить динамических параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db04f1df-def5-4456-8869-336024cda723
caps.latest.revision: 8
ms.openlocfilehash: a9c530cdc66302eb6b3d9d2b284eeb486c3b2ba9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067929"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="58965-102">Как объявить динамические параметры</span><span class="sxs-lookup"><span data-stu-id="58965-102">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="58965-103">В этом примере показано, как для определения динамических параметров, которые добавляются в командлет во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="58965-103">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="58965-104">В этом примере `Department` всякий раз, когда пользователь указывает командлету добавлен параметр `Employee` параметр-переключатель.</span><span class="sxs-lookup"><span data-stu-id="58965-104">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="58965-105">Дополнительные сведения о динамических параметров, см. в разделе [динамические параметры командлета](./cmdlet-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="58965-105">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="58965-106">Для определения динамических параметров</span><span class="sxs-lookup"><span data-stu-id="58965-106">To define dynamic parameters</span></span>

1. <span data-ttu-id="58965-107">Добавьте в объявление класса командлета, [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) интерфейс, как показано.</span><span class="sxs-lookup"><span data-stu-id="58965-107">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="58965-108">Вызовите [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) метод, который возвращает объект, в котором определены динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="58965-108">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="58965-109">В этом примере метод вызывается, когда `Employee` указан параметр.</span><span class="sxs-lookup"><span data-stu-id="58965-109">In this example, the method is called when the `Employee` parameter is specified.</span></span>

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

3. <span data-ttu-id="58965-110">Объявите класс, определяющий динамические параметры для добавления.</span><span class="sxs-lookup"><span data-stu-id="58965-110">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="58965-111">Можно использовать атрибуты, которые вы использовали для объявления параметры статического командлета для объявления динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="58965-111">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

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

## <a name="example"></a><span data-ttu-id="58965-112">Пример</span><span class="sxs-lookup"><span data-stu-id="58965-112">Example</span></span>

<span data-ttu-id="58965-113">В этом примере `Department` всякий раз, когда пользователь указывает, добавляется параметр `Employee` параметр.</span><span class="sxs-lookup"><span data-stu-id="58965-113">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="58965-114">`Department` Параметр является необязательным параметром, а атрибут ValidateSet используется для определения допустимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="58965-114">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="58965-115">См. также</span><span class="sxs-lookup"><span data-stu-id="58965-115">See Also</span></span>

[<span data-ttu-id="58965-116">System.Management.Automation.Runtimedefinedparameterdictionary</span><span class="sxs-lookup"><span data-stu-id="58965-116">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="58965-117">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span><span class="sxs-lookup"><span data-stu-id="58965-117">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="58965-118">Командлет динамических параметров</span><span class="sxs-lookup"><span data-stu-id="58965-118">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="58965-119">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58965-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)