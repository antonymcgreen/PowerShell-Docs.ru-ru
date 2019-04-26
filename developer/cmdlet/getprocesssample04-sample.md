---
title: Пример GetProcessSample04 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa2aa4c4-3457-4601-806a-801afe3dcc80
caps.latest.revision: 6
ms.openlocfilehash: 095bebf868efd00f8eeaec979a5606f140714cb1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068034"
---
# <a name="getprocesssample04-sample"></a>Пример командлета GetProcessSample04

В этом примере показано, как выполнить командлет, который извлекает процессы на локальном компьютере. Устранимые ошибки возникает в том случае, если произошла ошибка при получении процесса. Этот командлет представляет упрощенную версию `Get-Process` командлет, предоставляемые Windows PowerShell 2.0.

## <a name="how-to-build-the-sample-using-visual-studio"></a>Способы создания образца с использованием Visual Studio.

1. С помощью Windows PowerShell 2.0 установлен пакет SDK перейдите к папке GetProcessSample04. Расположение по умолчанию — C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.

2. Дважды щелкните значок файла решения (SLN). Откроется пример проекта в Visual Studio.

3. В **построения** меню, выберите **построить решение**.

    Библиотеки для образца будет располагаться в папках \bin или \bin\debug по умолчанию.

### <a name="how-to-run-the-sample"></a>Запуск примера

1. Создайте следующую папку модуля:

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. Скопируйте сборку образца в папке модуля.

3. Запустите Windows PowerShell.

4. Выполните следующую команду, чтобы загрузить сборку в Windows PowerShell:

    `Import-module getprossessample04`

5. Выполните следующую команду, чтобы запустить командлет:

    `get-proc`

## <a name="requirements"></a>Требования

В этом примере требуется Windows PowerShell 2.0.

## <a name="demonstrates"></a>Демонстрирует

В этом примере демонстрируется следующее.

- Объявление класса командлет, используя атрибут командлета.

- Объявление параметра командлета, с помощью параметра атрибута.

- Задают позицию задаваемого параметра.

- Указание, что он принимает входные данные из конвейера. Входные данные могут быть взяты из объекта или значение из свойства объекта, имя свойства совпадает с именем параметра.

- Объявление атрибута проверки для входного параметра.

- Перехват устранимые ошибки и записи в поток ошибок сообщение об ошибке.

## <a name="example"></a>Пример

В этом примере показано, как создать командлет, который обрабатывает устранимые ошибки и записывает сообщения об ошибках в поток ошибок.

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
