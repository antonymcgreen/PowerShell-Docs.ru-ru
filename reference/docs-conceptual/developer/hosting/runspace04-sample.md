---
ms.date: 09/13/2016
ms.topic: reference
title: Пример Runspace04
description: Пример Runspace04
ms.openlocfilehash: 5a2e1137963e02def419bb924c63b0d651b0fdfa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657751"
---
# <a name="runspace04-sample"></a><span data-ttu-id="7332e-103">Пример Runspace04</span><span class="sxs-lookup"><span data-stu-id="7332e-103">Runspace04 Sample</span></span>

<span data-ttu-id="7332e-104">В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения команд и перехвата ошибок, возникающих при выполнении команд.</span><span class="sxs-lookup"><span data-stu-id="7332e-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="7332e-105">Выполняются две команды, и последняя получает недопустимый аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="7332e-105">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="7332e-106">В результате объекты не возвращаются и создается неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7332e-106">As a result, no objects are returned and a terminating error is thrown.</span></span>

## <a name="requirements"></a><span data-ttu-id="7332e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7332e-107">Requirements</span></span>

<span data-ttu-id="7332e-108">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="7332e-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="7332e-109">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="7332e-109">Demonstrates</span></span>

<span data-ttu-id="7332e-110">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="7332e-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="7332e-111">Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="7332e-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="7332e-112">Добавление команд в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="7332e-112">Adding commands to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="7332e-113">Добавление аргументов параметров в конвейер.</span><span class="sxs-lookup"><span data-stu-id="7332e-113">Adding parameter arguments to the pipeline.</span></span>

- <span data-ttu-id="7332e-114">Синхронный вызов команд.</span><span class="sxs-lookup"><span data-stu-id="7332e-114">Invoking the commands synchronously.</span></span>

- <span data-ttu-id="7332e-115">Использование объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) для извлечения и вывода свойств из объектов, возвращаемых командами.</span><span class="sxs-lookup"><span data-stu-id="7332e-115">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the commands.</span></span>

- <span data-ttu-id="7332e-116">Получение и отображение записей об ошибках, созданных во время выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="7332e-116">Retrieving and displaying error records that were generated during the running of the commands.</span></span>

- <span data-ttu-id="7332e-117">Перехват и отображение завершающих исключений, вызванных командами.</span><span class="sxs-lookup"><span data-stu-id="7332e-117">Catching and displaying terminating exceptions thrown by the commands.</span></span>

## <a name="example"></a><span data-ttu-id="7332e-118">Пример</span><span class="sxs-lookup"><span data-stu-id="7332e-118">Example</span></span>

<span data-ttu-id="7332e-119">В этом примере команды выполняются синхронно в пространстве выполнения по умолчанию, предоставляемом Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7332e-119">This sample runs commands synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="7332e-120">Последняя команда вызывает завершающую ошибку, так как аргумент параметра, который является недопустимым, передается команде.</span><span class="sxs-lookup"><span data-stu-id="7332e-120">The last command throws a terminating error because a parameter argument that is not valid is passed to the command.</span></span> <span data-ttu-id="7332e-121">Происходит перехват и отображение ошибки.</span><span class="sxs-lookup"><span data-stu-id="7332e-121">The terminating error is trapped and displayed.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace04
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands.
    /// The commands generate a terminating exception that the caller
    /// should catch and process.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run commands.
    /// 2. Adding commands to the pipeline of  the PowerShell object.
    /// 3. Passing input objects to the commands from the calling program.
    /// 4. Using PSObject objects to extract and display properties from the
    ///    objects returned by the commands.
    /// 5. Retrieving and displaying error records that were generated
    ///    while running the commands.
    /// 6. Catching and displaying terminating exceptions generated
    ///    while running the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object.
      using (PowerShell powershell = PowerShell.Create())
      {
        // Add the commands to the PowerShell object.
        powershell.AddCommand("Get-ChildItem").AddCommand("Select-String").AddArgument("*");

        // Run the commands synchronously. Because of the bad regular expression,
        // no objects will be returned. Instead, an exception will be thrown.
        try
        {
          foreach (PSObject result in powershell.Invoke())
          {
            Console.WriteLine("'{0}'", result.ToString());
          }

          // Process any error records that were generated while running the commands.
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
        catch (RuntimeException runtimeException)
        {
          // Trap any exception generated by the commands. These exceptions
          // will all be derived from the RuntimeException exception.
          System.Console.WriteLine(
                        "Runtime exception: {0}: {1}\n{2}",
                        runtimeException.ErrorRecord.InvocationInfo.InvocationName,
                        runtimeException.Message,
                        runtimeException.ErrorRecord.InvocationInfo.PositionMessage);
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="7332e-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="7332e-122">See Also</span></span>

[<span data-ttu-id="7332e-123">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7332e-123">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
