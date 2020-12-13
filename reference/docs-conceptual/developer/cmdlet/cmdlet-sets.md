---
ms.date: 09/13/2016
ms.topic: reference
title: Наборы командлетов
description: Наборы командлетов
ms.openlocfilehash: b4bcb6548f9d64a8cc5e3fc3a66c671a5566001d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668241"
---
# <a name="cmdlet-sets"></a><span data-ttu-id="c26f5-103">Наборы командлетов</span><span class="sxs-lookup"><span data-stu-id="c26f5-103">Cmdlet Sets</span></span>

<span data-ttu-id="c26f5-104">При проектировании командлетов могут возникнуть ситуации, в которых необходимо выполнить несколько действий с одним и тем же элементом данных.</span><span class="sxs-lookup"><span data-stu-id="c26f5-104">When you design your cmdlets, you might encounter cases in which you need to perform several actions on the same piece of data.</span></span> <span data-ttu-id="c26f5-105">Например, может потребоваться получение и установка данных, а также запуск и завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="c26f5-105">For example, you might need to get and set data or start and stop a process.</span></span> <span data-ttu-id="c26f5-106">Хотя вам потребуется создать отдельные командлеты для выполнения каждого действия, структура командлетов должна включать базовый класс, из которого производятся классы для отдельных командлетов.</span><span class="sxs-lookup"><span data-stu-id="c26f5-106">Although you will need to create separate cmdlets to perform each action, your cmdlet design should include a base class from which the classes for the individual cmdlets are derived.</span></span>

<span data-ttu-id="c26f5-107">При реализации базового класса учитывайте следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="c26f5-107">Keep the following things in mind when implementing a base class.</span></span>

- <span data-ttu-id="c26f5-108">Объявите все общие параметры, используемые всеми производными командлетами в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="c26f5-108">Declare any common parameters used by all the derived cmdlets in the base class.</span></span>

- <span data-ttu-id="c26f5-109">Добавьте параметры, относящиеся к командлету, к соответствующему классу командлета.</span><span class="sxs-lookup"><span data-stu-id="c26f5-109">Add cmdlet-specific parameters to the appropriate cmdlet class.</span></span>

- <span data-ttu-id="c26f5-110">Переопределите соответствующий метод обработки ввода в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="c26f5-110">Override the appropriate input processing method in the base class.</span></span>

- <span data-ttu-id="c26f5-111">Объявите атрибут [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) для всех классов командлетов, но не объявляйте его в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="c26f5-111">Declare the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute on all cmdlet classes, but do not declare it on the base class.</span></span>

- <span data-ttu-id="c26f5-112">Реализуйте класс [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) или [System. Management. Automation. кустомпсснапин](/dotnet/api/System.Management.Automation.CustomPSSnapIn) , имя и описание которого отражают набор командлетов.</span><span class="sxs-lookup"><span data-stu-id="c26f5-112">Implement a [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class whose name and description reflects the set of cmdlets.</span></span>

## <a name="example"></a><span data-ttu-id="c26f5-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c26f5-113">Example</span></span>

<span data-ttu-id="c26f5-114">В следующем примере показана реализация базового класса, который используется Get-Proc и Stop-Proc командлета, производного от того же базового класса.</span><span class="sxs-lookup"><span data-stu-id="c26f5-114">The following example shows the implementation of a base class that is used by Get-Proc and Stop-Proc cmdlet that derive from the same base class.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace.

namespace Microsoft.Samples.PowerShell.Commands
{

  #region ProcessCommands

  /// <summary>
  /// This class implements a Stop-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>
  [Cmdlet(VerbsLifecycle.Stop, "Proc", SupportsShouldProcess = true)]
  public class StopProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      if (ShouldProcess(process.ProcessName, "Stop-Proc"))
      {
        process.Kill();
      }
    }
  }

  /// <summary>
  /// This class implements a Get-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>

  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      WriteObject(process);
    }
  }

  /// <summary>
  /// This class is the base class that defines the common
  /// functionality used by the Get-Proc and Stop-Proc
  /// cmdlets.
  /// </summary>
  public class BaseProcCommand : Cmdlet
  {
    #region Parameters

    // Defines the Name parameter that is used to
    // specify a process by its name.
    [Parameter(
               Position = 0,
               Mandatory = true,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true
    )]
    public string[] Name
    {
      get { return processNames; }
      set { processNames = value; }
    }
    private string[] processNames;

    // Defines the Exclude parameter that is used to
    // specify which processes should be excluded when
    // the cmdlet performs its action.
    [Parameter()]
    public string[] Exclude
    {
      get { return excludeNames; }
      set { excludeNames = value; }
    }
    private string[] excludeNames = new string[0];
    #endregion Parameters

    public virtual void ProcessObject(Process process)
    {
      throw new NotImplementedException("This method should be overridden.");
    }

    #region Cmdlet Overrides
    // <summary>
    // For each of the requested process names, retrieve and write
    // the associated processes.
    // </summary>
    protected override void ProcessRecord()
    {
      // Set up the wildcard characters used in resolving
      // the process names.
      WildcardOptions options = WildcardOptions.IgnoreCase |
                                WildcardOptions.Compiled;

      WildcardPattern[] include = new WildcardPattern[Name.Length];
      for (int i = 0; i < Name.Length; i++)
      {
        include[i] = new WildcardPattern(Name[i], options);
      }

      WildcardPattern[] exclude = new WildcardPattern[Exclude.Length];
      for (int i = 0; i < Exclude.Length; i++)
      {
        exclude[i] = new WildcardPattern(Exclude[i], options);
      }

      foreach (Process p in Process.GetProcesses())
      {
        foreach (WildcardPattern wIn in include)
        {
          if (wIn.IsMatch(p.ProcessName))
          {
            bool processThisOne = true;
            foreach (WildcardPattern wOut in exclude)
            {
              if (wOut.IsMatch(p.ProcessName))
              {
                processThisOne = false;
                break;
              }
            }
            if (processThisOne)
            {
              ProcessObject(p);
            }
            break;
          }
        }
      }
    }
    #endregion Cmdlet Overrides
  }
    #endregion ProcessCommands
}
```

## <a name="see-also"></a><span data-ttu-id="c26f5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c26f5-115">See Also</span></span>

[<span data-ttu-id="c26f5-116">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c26f5-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
