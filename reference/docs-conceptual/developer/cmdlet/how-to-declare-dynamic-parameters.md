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
# <a name="how-to-declare-dynamic-parameters"></a>Как объявить динамические параметры

В этом примере показано, как определить динамические параметры, добавляемые в командлет во время выполнения. В этом примере `Department` параметр добавляется в командлет каждый раз, когда пользователь указывает `Employee` параметр Switch. Дополнительные сведения о динамических параметрах см. в разделе [динамические параметры командлета](./cmdlet-dynamic-parameters.md).

## <a name="to-define-dynamic-parameters"></a>Определение динамических параметров

1. В объявлении класса командлета добавьте интерфейс [System. Management. Automation. идинамикпараметерс](/dotnet/api/System.Management.Automation.IDynamicParameters) , как показано ниже.

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. Вызовите метод [System. Management. Automation. идинамикпараметерс. жетдинамикпараметерс *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) , который возвращает объект, в котором определены динамические параметры. В этом примере метод вызывается при `Employee` указании параметра.

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

3. Объявите класс, который определяет динамические параметры для добавления. Для объявления динамических параметров можно использовать атрибуты, которые использовались для объявления параметров статического командлета.

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

## <a name="example"></a>Пример

В этом примере `Department` параметр добавляется каждый раз, когда пользователь указывает `Employee` параметр. `Department`Параметр является необязательным параметром, и для указания допустимых аргументов используется атрибут Validate.

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

## <a name="see-also"></a>См. также:

[System. Management. Automation. Рунтимедефинедпараметердиктионари](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[System. Management. Automation. Идинамикпараметерс. Жетдинамикпараметерс *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[Динамические параметры командлетов](./cmdlet-dynamic-parameters.md)

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
