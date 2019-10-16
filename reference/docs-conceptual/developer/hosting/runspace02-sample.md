---
title: Пример Runspace02 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7630bb63-ef39-4abd-b795-8000f984c1e5
caps.latest.revision: 9
ms.openlocfilehash: 6352169cffbb8a8bf59a42f79979f5003c150fa4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360983"
---
# <a name="runspace02-sample"></a>Пример Runspace02

В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения командлетов [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) . Командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) возвращает объекты [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) для каждого процесса, выполняемого на локальном компьютере, а `Sort-Object` сортирует объекты на основе их свойства [System.Diagnostics.Process.ID *](/dotnet/api/System.Diagnostics.Process.Id) . Результаты этих команд отображаются с помощью элемента управления [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) .

## <a name="requirements"></a>Требования

Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Демонстрирующее

В этом образце демонстрируется следующее.

- Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения команд.

- Добавление команд в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

- Выполнение команд в синхронном режиме.

- Использование элемента управления [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) для вывода выходных данных команд в Windows Forms приложении.

## <a name="example"></a>Пример

В этом примере командлеты [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) синхронно выполняются в пространстве выполнения по умолчанию, предоставляемом Windows PowerShell. Выходные данные отображаются в форме с помощью элемента управления [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) .

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using System.Windows.Forms;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace02
  {
    /// <summary>
    /// This method creates the form where the output is displayed.
    /// </summary>
    private static void CreateForm()
    {
      Form form = new Form();
      DataGridView grid = new DataGridView();
      form.Controls.Add(grid);
      grid.Dock = DockStyle.Fill;

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddCommand("get-process").AddCommand("sort-object").AddArgument("ID");
        if (Runspace.DefaultRunspace == null)
        {
          Runspace.DefaultRunspace = powershell.Runspace;
        }

        Collection<PSObject> results = powershell.Invoke();

        // The generic collection needs to be re-wrapped in an ArrayList
        // for data-binding to work.
        ArrayList objects = new ArrayList();
        objects.AddRange(results);

        // The DataGridView will use the PSObjectTypeDescriptor type
        // to retrieve the properties.
        grid.DataSource = objects;
      }

      form.ShowDialog();
    }

    /// <summary>
    /// This sample uses a PowerShell object to run the Get-Process
    /// and Sort-Object cmdlets synchronously. Windows Forms and
    /// data binding are then used to display the results in a
    /// DataGridView control.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object.
    /// 2. Adding commands and arguments to the pipeline of
    ///    the PowerShell object.
    /// 3. Running the commands synchronously.
    /// 4. Using a DataGridView control to display the output
    ///    of the commands in a Windows Forms application.
    /// </remarks>
    private static void Main(string[] args)
    {
      Runspace02.CreateForm();
    }
  }
}
```

## <a name="see-also"></a>См. также:

[Написание ведущего приложения Windows PowerShell](./writing-a-windows-powershell-host-application.md)