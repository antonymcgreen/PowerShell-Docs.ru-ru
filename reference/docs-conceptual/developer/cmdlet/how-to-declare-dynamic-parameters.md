---
title: Объявление динамических параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db04f1df-def5-4456-8869-336024cda723
caps.latest.revision: 8
ms.openlocfilehash: d3c2c339ba9ac6ec4a1958fadbfe1c6d74e3d736
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561058"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="04161-102">Как объявить динамические параметры</span><span class="sxs-lookup"><span data-stu-id="04161-102">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="04161-103">В этом примере показано, как определить динамические параметры, добавляемые в командлет во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="04161-103">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="04161-104">В этом примере `Department` параметр добавляется в командлет каждый раз, когда пользователь указывает `Employee` параметр Switch.</span><span class="sxs-lookup"><span data-stu-id="04161-104">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="04161-105">Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета](./cmdlet-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="04161-105">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="04161-106">Определение динамических параметров</span><span class="sxs-lookup"><span data-stu-id="04161-106">To define dynamic parameters</span></span>

1. <span data-ttu-id="04161-107">В объявлении класса командлета добавьте интерфейс [System. Management. Automation. идинамикпараметерс](/dotnet/api/System.Management.Automation.IDynamicParameters) , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="04161-107">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="04161-108">Вызовите метод [System. Management. Automation. идинамикпараметерс. жетдинамикпараметерс \*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) , который возвращает объект, в котором определены динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="04161-108">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="04161-109">В этом примере метод вызывается при `Employee` указании параметра.</span><span class="sxs-lookup"><span data-stu-id="04161-109">In this example, the method is called when the `Employee` parameter is specified.</span></span>

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

3. <span data-ttu-id="04161-110">Объявите класс, который определяет динамические параметры для добавления.</span><span class="sxs-lookup"><span data-stu-id="04161-110">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="04161-111">Для объявления динамических параметров можно использовать атрибуты, которые использовались для объявления параметров статического командлета.</span><span class="sxs-lookup"><span data-stu-id="04161-111">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

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

## <a name="example"></a><span data-ttu-id="04161-112">Пример</span><span class="sxs-lookup"><span data-stu-id="04161-112">Example</span></span>

<span data-ttu-id="04161-113">В этом примере `Department` параметр добавляется каждый раз, когда пользователь указывает `Employee` параметр.</span><span class="sxs-lookup"><span data-stu-id="04161-113">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="04161-114">`Department`Параметр является необязательным параметром, и для указания допустимых аргументов используется атрибут Validate.</span><span class="sxs-lookup"><span data-stu-id="04161-114">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="04161-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="04161-115">See Also</span></span>

[<span data-ttu-id="04161-116">System. Management. Automation. Рунтимедефинедпараметердиктионари</span><span class="sxs-lookup"><span data-stu-id="04161-116">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="04161-117">System. Management. Automation. Идинамикпараметерс. Жетдинамикпараметерс \*</span><span class="sxs-lookup"><span data-stu-id="04161-117">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="04161-118">Динамические параметры командлетов</span><span class="sxs-lookup"><span data-stu-id="04161-118">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="04161-119">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04161-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
