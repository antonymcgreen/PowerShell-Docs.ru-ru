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
# <a name="runspace03-sample"></a><span data-ttu-id="eee70-102">Пример Runspace03</span><span class="sxs-lookup"><span data-stu-id="eee70-102">Runspace03 Sample</span></span>

<span data-ttu-id="eee70-103">В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для синхронного выполнения скрипта и для решения неустранимых ошибок.</span><span class="sxs-lookup"><span data-stu-id="eee70-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span> <span data-ttu-id="eee70-104">Скрипт получает список имен процессов, а затем извлекает эти процессы.</span><span class="sxs-lookup"><span data-stu-id="eee70-104">The script receives a list of process names and then retrieves those processes.</span></span> <span data-ttu-id="eee70-105">Результаты выполнения скрипта, включая вызванные им устранимые ошибки, отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="eee70-105">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="eee70-106">Требования</span><span class="sxs-lookup"><span data-stu-id="eee70-106">Requirements</span></span>

<span data-ttu-id="eee70-107">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="eee70-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="eee70-108">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="eee70-108">Demonstrates</span></span>

<span data-ttu-id="eee70-109">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="eee70-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="eee70-110">Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="eee70-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a script.</span></span>

- <span data-ttu-id="eee70-111">Добавление скрипта в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="eee70-111">Adding a script to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="eee70-112">Передача входных объектов в скрипт из вызывающей программы.</span><span class="sxs-lookup"><span data-stu-id="eee70-112">Passing input objects to the script from the calling program.</span></span>

- <span data-ttu-id="eee70-113">Синхронный запуск скрипта.</span><span class="sxs-lookup"><span data-stu-id="eee70-113">Running the script synchronously.</span></span>

- <span data-ttu-id="eee70-114">Использование объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) для извлечения и вывода свойств из объектов, возвращаемых скриптом.</span><span class="sxs-lookup"><span data-stu-id="eee70-114">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the script.</span></span>

- <span data-ttu-id="eee70-115">Получение и отображение записей об ошибках, созданных при выполнении скрипта.</span><span class="sxs-lookup"><span data-stu-id="eee70-115">Retrieving and displaying error records that were generated when the script was run.</span></span>

## <a name="example"></a><span data-ttu-id="eee70-116">Пример</span><span class="sxs-lookup"><span data-stu-id="eee70-116">Example</span></span>

<span data-ttu-id="eee70-117">Этот пример выполняет скрипт синхронно в пространстве выполнения по умолчанию, предоставляемом Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eee70-117">This sample runs a script synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="eee70-118">Выходные данные скрипта и все созданные неустранимые ошибки отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="eee70-118">The output of the script and any non-terminating errors that were generated are displayed in a console window.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="eee70-119">См. также</span><span class="sxs-lookup"><span data-stu-id="eee70-119">See Also</span></span>

[<span data-ttu-id="eee70-120">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee70-120">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
