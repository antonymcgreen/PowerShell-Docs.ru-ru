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
# <a name="cmdlet-sets"></a>Наборы командлетов

При проектировании командлетов могут возникнуть ситуации, в которых необходимо выполнить несколько действий с одним и тем же элементом данных. Например, может потребоваться получение и установка данных, а также запуск и завершение процесса. Хотя вам потребуется создать отдельные командлеты для выполнения каждого действия, структура командлетов должна включать базовый класс, из которого производятся классы для отдельных командлетов.

При реализации базового класса учитывайте следующие моменты.

- Объявите все общие параметры, используемые всеми производными командлетами в базовом классе.

- Добавьте параметры, относящиеся к командлету, к соответствующему классу командлета.

- Переопределите соответствующий метод обработки ввода в базовом классе.

- Объявите атрибут [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) для всех классов командлетов, но не объявляйте его в базовом классе.

- Реализуйте класс [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) или [System. Management. Automation. кустомпсснапин](/dotnet/api/System.Management.Automation.CustomPSSnapIn) , имя и описание которого отражают набор командлетов.

## <a name="example"></a>Пример

В следующем примере показана реализация базового класса, который используется Get-Proc и Stop-Proc командлета, производного от того же базового класса.

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

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
