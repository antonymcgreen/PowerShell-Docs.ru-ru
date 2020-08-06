---
title: Пример GetProcessSample03 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 09df93792ab611e167279bc35755d8d6c28e7cf3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784220"
---
# <a name="getprocesssample03-sample"></a>Пример командлета GetProcessSample03

В этом примере показано, как реализовать командлет, который получает процессы на локальном компьютере. Он предоставляет `Name` параметр, который может принимать объект из конвейера или значение свойства объекта, имя свойства которого совпадает с именем параметра. Этот командлет является упрощенной версией `Get-Process` командлета, предоставляемого Windows PowerShell 2,0.

## <a name="how-to-build-the-sample-using-visual-studio"></a>Как создать пример с помощью Visual Studio.

1. С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку GetProcessSample03 Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03.

2. Дважды щелкните значок файла решения (SLN). Откроется пример проекта в Visual Studio.

3. В меню **Построение** выберите команду **Построить решение**.

    Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.

### <a name="how-to-run-the-sample"></a>Запуск примера

1. Создайте следующую папку модуля:

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. Скопируйте пример сборки в папку Module.

3. Запустите Windows PowerShell.

4. Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:

    `Import-module getprossessample03`

5. Выполните следующую команду, чтобы запустить командлет:

    `get-proc`

## <a name="requirements"></a>Требования

Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Что демонстрирует

В этом образце демонстрируется следующее.

- Объявление класса командлета с помощью атрибута командлета.

- Объявление параметра командлета с помощью атрибута Parameter.

- Указание расположения параметра.

- Указание того, что параметр принимает входные данные из конвейера. Входные данные могут быть взяты из объекта или значения из свойства объекта, имя свойства которого совпадает с именем параметра.

- Объявление атрибута проверки для входных параметров.

## <a name="example"></a>Пример

В этом примере показана реализация командлета Get-proc, который содержит `Name` параметр, который принимает входные данные из конвейера.

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;           // Windows PowerShell namespace
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
    /// Gets or sets the names of the
    /// process that the cmdlet will retrieve.
    /// </summary>
    [Parameter(
               Position = 0,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true)]
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
    /// associated processes to the pipeline.
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
        // If process names are passed to the cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames ...)
    } // End ProcessRecord.

    #endregion Overrides
  } // End GetProcCommand.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
