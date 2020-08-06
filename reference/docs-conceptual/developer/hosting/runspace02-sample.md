---
title: Пример Runspace02 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7a2dce436aceb1d8744377c37671a66398614851
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784968"
---
# <a name="runspace02-sample"></a><span data-ttu-id="aebbf-102">Пример Runspace02</span><span class="sxs-lookup"><span data-stu-id="aebbf-102">Runspace02 Sample</span></span>

<span data-ttu-id="aebbf-103">В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения командлетов [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) .</span><span class="sxs-lookup"><span data-stu-id="aebbf-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span> <span data-ttu-id="aebbf-104">Командлет [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) возвращает объекты [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) для каждого процесса, выполняемого на локальном компьютере, и `Sort-Object` сортирует объекты на основе их свойства [System.Diagnostics.Process.ID \*](/dotnet/api/System.Diagnostics.Process.Id) .</span><span class="sxs-lookup"><span data-stu-id="aebbf-104">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer, and the `Sort-Object` sorts the objects based on their [System.Diagnostics.Process.Id\*](/dotnet/api/System.Diagnostics.Process.Id) property.</span></span> <span data-ttu-id="aebbf-105">Результаты этих команд отображаются с помощью элемента управления [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) .</span><span class="sxs-lookup"><span data-stu-id="aebbf-105">The results of these commands is displayed by using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

## <a name="requirements"></a><span data-ttu-id="aebbf-106">Требования</span><span class="sxs-lookup"><span data-stu-id="aebbf-106">Requirements</span></span>

<span data-ttu-id="aebbf-107">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="aebbf-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="aebbf-108">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="aebbf-108">Demonstrates</span></span>

<span data-ttu-id="aebbf-109">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="aebbf-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="aebbf-110">Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="aebbf-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run commands.</span></span>

- <span data-ttu-id="aebbf-111">Добавление команд в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="aebbf-111">Adding commands to the pipeline of [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="aebbf-112">Выполнение команд в синхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="aebbf-112">Running the commands synchronously.</span></span>

- <span data-ttu-id="aebbf-113">Использование элемента управления [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) для вывода выходных данных команд в Windows Forms приложении.</span><span class="sxs-lookup"><span data-stu-id="aebbf-113">Using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control to display the output of the commands in a Windows Forms application.</span></span>

## <a name="example"></a><span data-ttu-id="aebbf-114">Пример</span><span class="sxs-lookup"><span data-stu-id="aebbf-114">Example</span></span>

<span data-ttu-id="aebbf-115">В этом примере командлеты [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) и [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) синхронно выполняются в пространстве выполнения по умолчанию, предоставляемом Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aebbf-115">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="aebbf-116">Выходные данные отображаются в форме с помощью элемента управления [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) .</span><span class="sxs-lookup"><span data-stu-id="aebbf-116">The output is displayed in a form using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="aebbf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="aebbf-117">See Also</span></span>

[<span data-ttu-id="aebbf-118">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aebbf-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
