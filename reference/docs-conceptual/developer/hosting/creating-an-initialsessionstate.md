---
title: Создание InitialSessionState | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 946adf1006d1afcad2810c85e39f14514e837327
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779732"
---
# <a name="creating-an-initialsessionstate"></a>Создание InitialSessionState

Команды PowerShell выполняются в пространстве выполнения.
Чтобы разместить PowerShell в приложении, необходимо создать объект [System. Management. Automation. пространства. пространство](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .
С каждым пространством выполнения связано [System.Management.Automation.Runspaces.Iniобъект тиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .
InitialSessionState указывает характеристики пространства выполнения, например, какие команды, переменные и модули доступны для этого пространства выполнения.

## <a name="create-a-default-initialsessionstate"></a>Создание InitialSessionState по умолчанию

Методы [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) и [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) класса **InitialSessionState** можно использовать для создания объекта **InitialSessionState** .
Метод **CreateDefault** создает объект **InitialSessionState** со всеми загруженными встроенными командами, а метод **CreateDefault2** загружает только команды, необходимые для размещения PowerShell (команды из модуля Microsoft. PowerShell. Core).

Если вы хотите дополнительно ограничить команды, доступные в ведущем приложении, необходимо создать ограниченное пространство выполнения.
Дополнительные сведения см. [в разделе Создание ограниченного пространства выполнения](creating-a-constrained-runspace.md).

В следующем коде показано, как создать **InitialSessionState**, присвоить ему пространство выполнения, добавить команды в конвейер в этом пространстве выполнения и вызвать команды.
Дополнительные сведения о добавлении и вызове команд см. в разделе [Добавление и вызов команд](adding-and-invoking-commands.md).

```csharp
namespace SampleHost
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  class HostP4b
  {
    static void Main(string[] args)
    {
      // Call the InitialSessionState.CreateDefault method to create
      // an empty InitialSessionState object, and then add the
      // elements that will be available when the runspace is opened.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      SessionStateVariableEntry var1 = new
          SessionStateVariableEntry("test1",
                                    "MyVar1",
                                    "Initial session state MyVar1 test");
      iss.Variables.Add(var1);

      SessionStateVariableEntry var2 = new
          SessionStateVariableEntry("test2",
                                    "MyVar2",
                                    "Initial session state MyVar2 test");
      iss.Variables.Add(var2);

      // Call the RunspaceFactory.CreateRunspace(InitialSessionState)
      // method to create the runspace where the pipeline is run.
      Runspace rs = RunspaceFactory.CreateRunspace(iss);
      rs.Open();

      // Call the PowerShell.Create() method to create the PowerShell object,
      // and then specify the runspace and commands to the pipeline.
      // and create the command pipeline.
      PowerShell ps = PowerShell.Create();
      ps.Runspace = rs;
      ps.AddCommand("Get-Variable");
      ps.AddArgument("test*");

      Console.WriteLine("Variable             Value");
      Console.WriteLine("--------------------------");

      // Call the PowerShell.Invoke() method to run
      // the pipeline synchronously.
      foreach (PSObject result in ps.Invoke())
      {
        Console.WriteLine("{0,-20}{1}",
            result.Members["Name"].Value,
            result.Members["Value"].Value);
      } // End foreach.

      // Close the runspace to free resources.
      rs.Close();

    } // End Main.
  } // End SampleHost.
}
```

## <a name="see-also"></a>См. также

[Создание ограниченного пространства выполнения](creating-a-constrained-runspace.md)

[Добавление и вызов команд](adding-and-invoking-commands.md)
