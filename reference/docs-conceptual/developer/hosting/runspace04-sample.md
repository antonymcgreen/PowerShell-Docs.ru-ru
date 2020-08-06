---
title: Пример Runspace04 | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 73f48c797a4ce9bf4bc78ff34abb5efa41cda121
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779511"
---
# <a name="runspace04-sample"></a><span data-ttu-id="ed153-102">Пример Runspace04</span><span class="sxs-lookup"><span data-stu-id="ed153-102">Runspace04 Sample</span></span>

<span data-ttu-id="ed153-103">В этом примере показано, как использовать класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) для выполнения команд и перехвата ошибок, возникающих при выполнении команд.</span><span class="sxs-lookup"><span data-stu-id="ed153-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="ed153-104">Выполняются две команды, и последняя получает недопустимый аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="ed153-104">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="ed153-105">В результате объекты не возвращаются и создается неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="ed153-105">As a result, no objects are returned and a terminating error is thrown.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed153-106">Требования</span><span class="sxs-lookup"><span data-stu-id="ed153-106">Requirements</span></span>

<span data-ttu-id="ed153-107">Для работы с этим образцом требуется Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="ed153-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ed153-108">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="ed153-108">Demonstrates</span></span>

<span data-ttu-id="ed153-109">В этом образце демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="ed153-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="ed153-110">Создание объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="ed153-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="ed153-111">Добавление команд в конвейер объекта [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="ed153-111">Adding commands to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="ed153-112">Добавление аргументов параметров в конвейер.</span><span class="sxs-lookup"><span data-stu-id="ed153-112">Adding parameter arguments to the pipeline.</span></span>

- <span data-ttu-id="ed153-113">Синхронный вызов команд.</span><span class="sxs-lookup"><span data-stu-id="ed153-113">Invoking the commands synchronously.</span></span>

- <span data-ttu-id="ed153-114">Использование объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) для извлечения и вывода свойств из объектов, возвращаемых командами.</span><span class="sxs-lookup"><span data-stu-id="ed153-114">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the commands.</span></span>

- <span data-ttu-id="ed153-115">Получение и отображение записей об ошибках, созданных во время выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="ed153-115">Retrieving and displaying error records that were generated during the running of the commands.</span></span>

- <span data-ttu-id="ed153-116">Перехват и отображение завершающих исключений, вызванных командами.</span><span class="sxs-lookup"><span data-stu-id="ed153-116">Catching and displaying terminating exceptions thrown by the commands.</span></span>

## <a name="example"></a><span data-ttu-id="ed153-117">Пример</span><span class="sxs-lookup"><span data-stu-id="ed153-117">Example</span></span>

<span data-ttu-id="ed153-118">В этом примере команды выполняются синхронно в пространстве выполнения по умолчанию, предоставляемом Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed153-118">This sample runs commands synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="ed153-119">Последняя команда вызывает завершающую ошибку, так как аргумент параметра, который является недопустимым, передается команде.</span><span class="sxs-lookup"><span data-stu-id="ed153-119">The last command throws a terminating error because a parameter argument that is not valid is passed to the command.</span></span> <span data-ttu-id="ed153-120">Происходит перехват и отображение ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed153-120">The terminating error is trapped and displayed.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ed153-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ed153-121">See Also</span></span>

[<span data-ttu-id="ed153-122">Написание ведущего приложения Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed153-122">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
