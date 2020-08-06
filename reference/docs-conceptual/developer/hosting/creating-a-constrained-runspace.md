---
title: Создание ограниченного пространства выполнения | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 30ecb80dbd96278ee9aa5a609d27bfc4eaa423e9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779817"
---
# <a name="creating-a-constrained-runspace"></a>Создание ограниченного пространства выполнения

В целях повышения производительности или безопасности может потребоваться ограничить команды Windows PowerShell, доступные для ведущего приложения. Чтобы сделать это, создайте пустую [System.Management.Automation.Runspaces.Iniтиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) , вызвав [System.Management.Automation.Runspaces.Iniтиалсессионстате. Создайте метод *](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) , а затем добавьте только те команды, которые должны быть доступны.

 Использование пространства выполнения, которое загружает только указанные команды, обеспечивает значительно повышенную производительность.

 Методы класса [System. Management. Automation. пространства выполнения. сессионстатекмдлетентри](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) используются для определения командлетов для начального состояния сеанса.

 Команды также можно сделать закрытыми. Частные команды могут использоваться ведущим приложением, но не пользователями приложения.

## <a name="adding-commands-to-an-empty-runspace"></a>Добавление команд в пустое пространство выполнения

 В следующем примере показано, как создать пустой InitialSessionState и добавить в него команды.

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using Microsoft.PowerShell.Commands;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class Runspace10b
  {
    /// <summary>
    /// This sample shows how to create an empty initial session state,
    /// how to add commands to the session state, and then how to create a
    /// runspace that has only those two commands. A PowerShell object
    /// is used to run the Get-Command cmdlet to show that only two commands
    /// are available.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create an empty InitialSessionState and then add two commands.
      InitialSessionState iss = InitialSessionState.Create();

      // Add the Get-Process and Get-Command cmdlets to the session state.
      SessionStateCmdletEntry ssce1 = new SessionStateCmdletEntry(
                                                            "get-process",
                                                            typeof(GetProcessCommand),
                                                            null);
      iss.Commands.Add(ssce1);

      SessionStateCmdletEntry ssce2 = new SessionStateCmdletEntry(
                                                            "get-command",
                                                            typeof(GetCommandCommand),
                                                            null);
      iss.Commands.Add(ssce2);

      // Create a runspace.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Create a pipeline with the Get-Command command.
          powershell.AddCommand("get-command");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Verb                 Noun");
          Console.WriteLine("----------------------------");

          // Display each result object.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                             "{0,-20} {1}",
                             result.Members["verb"].Value,
                             result.Members["Noun"].Value);
          }
        }

        // Close the runspace and release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="making-commands-private"></a>Создание закрытых команд

 Можно также сделать команду закрытой, установив свойство [System. Management. Automation. Commandinfo. Visibility](/dotnet/api/System.Management.Automation.CommandInfo.Visibility) в значение [System. Management. Automation. сессионстатинтривисибилити](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility) **Private**. Ведущее приложение и другие команды могут вызывать эту команду, но пользователь приложения не может. В следующем примере команда [Get-ChildItem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) является закрытой.

```csharp
defaultSessionState = InitialSessionState.CreateDefault();
commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;

this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
this.runspace.Open();
```

## <a name="see-also"></a>См. также

 [Создание InitialSessionState](./creating-an-initialsessionstate.md)
