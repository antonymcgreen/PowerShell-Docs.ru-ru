---
title: Создание InitialSessionState | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ae707db-52e0-408c-87fa-b35c42eaaab1
caps.latest.revision: 5
ms.openlocfilehash: 9140d03e046def2fbbcc2a842b9ea1b9e1fa2985
ms.sourcegitcommit: 13f24786ed39ca1c07eff2b73a1974c366e31cb8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2019
ms.locfileid: "67263829"
---
# <a name="creating-an-initialsessionstate"></a>Создание InitialSessionState

Команды PowerShell, выполняются в пространстве выполнения.
Чтобы разместить PowerShell в вашем приложении, необходимо создать [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) объекта.
Каждый пространства выполнения имеет [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объект, связанный с ним.
InitialSessionState указывает характеристики пространства выполнения, например, какие команды, переменные и модули доступны для этого пространства выполнения.

## <a name="create-a-default-initialsessionstate"></a>Создание InitialSessionState по умолчанию

[CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) и [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) методы **InitialSessionState** класс может использоваться для создания **InitialSessionState**объекта.
**CreateDefault** метод создает **InitialSessionState** со всеми встроенные команды, загруженных во время **CreateDefault2** метод загружает только те команды требуется для узла PowerShell (команды из модуля Microsoft.PowerShell.Core).

Если вы хотите ограничить команды, доступные в своем хост-приложении необходимо создать ограниченное пространство выполнения.
Сведения см. в разделе [Создание ограниченное пространство выполнения](creating-a-constrained-runspace.md).

Ниже показано, как создать **InitialSessionState**, назначьте его к пространству выполнения, как добавить команды в конвейер в это пространство выполнения и вызывать команды.
Дополнительные сведения о добавлении и вызова команд см. в разделе [Добавление и вызова команд](adding-and-invoking-commands.md).

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

[Создание ограниченное пространство выполнения](creating-a-constrained-runspace.md)

[Добавление и вызова команд](adding-and-invoking-commands.md)
