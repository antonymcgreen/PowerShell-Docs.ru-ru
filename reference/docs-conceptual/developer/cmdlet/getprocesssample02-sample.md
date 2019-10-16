---
title: Пример GetProcessSample02 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 481f557d-3344-4d33-b2da-4736a0165181
caps.latest.revision: 7
ms.openlocfilehash: fa4cd8a724793e71b615c84a5c5a833aa92c93fc
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364573"
---
# <a name="getprocesssample02-sample"></a>Пример командлета GetProcessSample02

В этом примере показано, как написать командлет, который получает процессы на локальном компьютере. Он предоставляет параметр `Name`, который можно использовать для указания процессов, которые требуется получить. Этот командлет является упрощенной версией командлета `Get-Process`, предоставляемого Windows PowerShell 2,0.

## <a name="how-to-build-the-sample-using-visual-studio"></a>Как создать пример с помощью Visual Studio.

1. С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку GetProcessSample02 Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.

2. Дважды щелкните значок файла решения (SLN). Откроется пример проекта в Visual Studio.

3. В меню **Сборка** выберите пункт **построить решение**.

    Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.

### <a name="how-to-run-the-sample"></a>Запуск примера

1. Создайте следующую папку модуля:

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. Скопируйте пример сборки в папку Module.

3. Запустите Windows PowerShell.

4. Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:

    `import-module getprossessample02`

5. Выполните следующую команду, чтобы запустить командлет:

    `get-proc`

## <a name="requirements"></a>Требования

Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Демонстрирующее

В этом образце демонстрируется следующее.

- Объявление класса командлета с помощью атрибута командлета.

- Объявление параметра командлета с помощью атрибута Parameter.

- Указание расположения параметра.

- Объявление атрибута проверки для входных параметров.

## <a name="example"></a>Пример

В этом примере показана реализация командлета Get-proc, который включает параметр `Name`.

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;     // Windows PowerShell namespace

  #region GetProcCommand

  /// <summary>
  /// This class implements the get-proc cmdlet.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Parameters

    /// <summary>
    /// The names of the processes retrieved by the cmdlet.
    /// </summary>
    private string[] processNames;

    /// <summary>
    /// Gets or sets the list of process names on which
    /// the Get-Proc cmdlet will work.
    /// </summary>
    [Parameter(Position = 0)]
    [ValidateNotNullOrEmpty]
    public string[] Name
    {
      get { return this.processNames; }
      set { this.processNames = value; }
    }

    #endregion Parameters

    #region Cmdlet Overrides

    /// <summary>
    /// The ProcessRecord method calls the Process.GetProcesses
    /// method to retrieve the processes specified by the Name
    /// parameter. Then, the WriteObject method writes the
    /// associated process objects to the pipeline.
    /// </summary>
    protected override void ProcessRecord()
    {
      // If no process names are passed to the cmdlet, get all
      // processes.
      if (this.processNames == null)
      {
        WriteObject(Process.GetProcesses(), true);
      }
      else
      {
        // If process names are passed to cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames...).
    } // End ProcessRecord.
    #endregion Cmdlet Overrides
  } // End GetProcCommand class.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
