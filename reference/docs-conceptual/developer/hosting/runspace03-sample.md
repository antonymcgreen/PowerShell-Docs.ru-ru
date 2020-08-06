---
title: Пример Runspace03 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d4fa3bca883fb8d78ca1bc8b0c0f9b70f304be06
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772184"
---
# <a name="runspace03-sample"></a>Пример Runspace03

В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения скрипта и для решения неустранимых ошибок. Скрипт получает список имен процессов, а затем извлекает эти процессы. Результаты выполнения скрипта, включая вызванные им устранимые ошибки, отображаются в окне консоли.

## <a name="requirements"></a>Требования

Для работы с этим образцом требуется Windows PowerShell 2,0.

## <a name="demonstrates"></a>Что демонстрирует

В этом образце демонстрируется следующее.

- Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения скрипта.

- Добавление скрипта в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .

- Передача входных объектов в скрипт из вызывающей программы.

- Синхронный запуск скрипта.

- Использование объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) для извлечения и вывода свойств из объектов, возвращаемых скриптом.

- Получение и отображение записей об ошибках, созданных при выполнении скрипта.

## <a name="example"></a>Пример

Этот пример выполняет скрипт синхронно в пространстве выполнения по умолчанию, предоставляемом Windows PowerShell. Выходные данные скрипта и все созданные неустранимые ошибки отображаются в окне консоли.

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace03
  {
    /// <summary>
    /// This sample shows how to use the PowerShell class to run a
    /// script that retrieves process information for the list of
    /// process names passed to the script. It shows how to pass input
    /// objects to a script and how to retrieve error objects as well
    /// as the output objects.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerSHell object to run a script.
    /// 2. Adding a script to the pipeline of the PowerShell object.
    /// 3. Passing input objects to the script from the calling program.
    /// 4. Running the script synchronously.
    /// 5. Using PSObject objects to extract and display properties from
    ///    the objects returned by the script.
    /// 6. Retrieving and displaying error records that were generated
    ///    when the script was run.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Define a list of processes to look for.
      string[] processNames = new string[]
      {
        "lsass", "nosuchprocess", "services", "nosuchprocess2"
      };

      // The script to run to get these processes. Input passed
      // to the script will be available in the $input variable.
      string script = "$input | get-process -name {$_}";

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the script.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddScript(script);

        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the script synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke(processNames))
        {
          Console.WriteLine(
                            "{0,-20} {1}",
                            result.Members["ProcessName"].Value,
                            result.Members["HandleCount"].Value);
        }

        // Process any error records that were generated while running
        //  the script.
        Console.WriteLine("\nThe following non-terminating errors occurred:\n");
        PSDataCollection<ErrorRecord> errors = powershell.Streams.Error;
        if (errors != null && errors.Count > 0)
        {
          foreach (ErrorRecord err in errors)
          {
            System.Console.WriteLine("    error: {0}", err.ToString());
          }
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a>См. также

[Написание ведущего приложения Windows PowerShell](./writing-a-windows-powershell-host-application.md)
