---
ms.date: 09/13/2016
ms.topic: reference
title: Пример командлета GetProcessSample04
description: Пример командлета GetProcessSample04
ms.openlocfilehash: 4b2b7f7ed5fd87711d0d7872caaf75d453de4832
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652728"
---
# <a name="getprocesssample04-sample"></a>Пример командлета GetProcessSample04

В этом примере показано, как реализовать командлет, который получает процессы на локальном компьютере. Он создает неустранимую ошибку, если при получении процесса возникает ошибка. Этот командлет является упрощенной версией `Get-Process` командлета, предоставляемого Windows PowerShell 2,0.

## <a name="how-to-build-the-sample-using-visual-studio"></a>Как создать пример с помощью Visual Studio.

1. С установленным пакетом SDK для Windows PowerShell 2,0 перейдите в папку GetProcessSample04 Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.

2. Дважды щелкните значок файла решения (SLN). Откроется пример проекта в Visual Studio.

3. В меню **Построение** выберите команду **Построить решение**.

    Библиотека для образца будет построена в папках \bin или \bin\Debug по умолчанию.

### <a name="how-to-run-the-sample"></a>Запуск примера

1. Создайте следующую папку модуля:

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. Скопируйте пример сборки в папку Module.

3. Запустите Windows PowerShell.

4. Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:

    `Import-module getprossessample04`

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

- Перехват незавершающей ошибки и запись сообщения об ошибке в поток ошибок.

## <a name="example"></a>Пример

В этом примере показано, как создать командлет, который обрабатывает неустранимые ошибки и записывает сообщения об ошибках в поток ошибок.

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
    using System;
    using System.Diagnostics;
    using System.Management.Automation;      // Windows PowerShell namespace.
   #region GetProcCommand

   /// <summary>
   /// This class implements the get-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Parameters

       /// <summary>
       /// The names of the processes to act on.
       /// </summary>
       private string[] processNames;

      /// <summary>
      /// Gets or sets the list of process names on
      /// which the Get-Proc cmdlet will work.
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
          // If no process names are passed to cmdlet, get all
          // processes.
          if (this.processNames == null)
          {
              WriteObject(Process.GetProcesses(), true);
          }
          else
          {
              // If process names are passed to the cmdlet, get and write
              // the associated processes.
              // If a nonterminating error occurs while retrieving processes,
              // call the WriteError method to send an error record to the
              // error stream.
              foreach (string name in this.processNames)
              {
                  Process[] processes;

                  try
                  {
                      processes = Process.GetProcessesByName(name);
                  }
                  catch (InvalidOperationException ex)
                  {
                      WriteError(new ErrorRecord(
                         ex,
                         "UnableToAccessProcessByName",
                         ErrorCategory.InvalidOperation,
                         name));
                      continue;
                  }

                  WriteObject(processes, true);
              } // foreach (string name...
          } // else
      } // ProcessRecord

      #endregion Overrides
    } // End GetProcCommand class.

   #endregion GetProcCommand
}
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
