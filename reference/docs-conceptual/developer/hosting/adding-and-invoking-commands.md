---
ms.date: 09/13/2016
ms.topic: reference
title: Добавление и вызов команд
description: Добавление и вызов команд
ms.openlocfilehash: f539172eaf119fe5774e158c77a00276c8ba9e0a
ms.sourcegitcommit: 880b00218708724a76503000c9eca181f4e00891
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "99049431"
---
# <a name="adding-and-invoking-commands"></a><span data-ttu-id="49973-103">Добавление и вызов команд</span><span class="sxs-lookup"><span data-stu-id="49973-103">Adding and invoking commands</span></span>

<span data-ttu-id="49973-104">После создания пространства выполнения можно добавить в конвейер Повершеллкоммандс и скрипты Windows, а затем вызывать конвейер синхронно или асинхронно.</span><span class="sxs-lookup"><span data-stu-id="49973-104">After creating a runspace, you can add Windows PowerShellcommands and scripts to a pipeline, and then invoke the pipeline synchronously or asynchronously.</span></span>

## <a name="creating-a-pipeline"></a><span data-ttu-id="49973-105">Создание конвейера</span><span class="sxs-lookup"><span data-stu-id="49973-105">Creating a pipeline</span></span>

<span data-ttu-id="49973-106">Класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) предоставляет несколько методов для добавления команд, параметров и скриптов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="49973-106">The [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class provides several methods to add commands, parameters, and scripts to the pipeline.</span></span> <span data-ttu-id="49973-107">Конвейер можно вызвать синхронно, вызвав перегрузку метода [System. Management. Automation. PowerShell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) или асинхронно, вызвав перегрузку метода [System. Management. Automation. PowerShell. BeginInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) , а затем метод [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="49973-107">You can invoke the pipeline synchronously by calling an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, or asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) and then the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

### <a name="addcommand"></a><span data-ttu-id="49973-108">AddCommand</span><span class="sxs-lookup"><span data-stu-id="49973-108">AddCommand</span></span>

1. <span data-ttu-id="49973-109">Создайте объект [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="49973-109">Create a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="49973-110">Добавьте команду, которую требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="49973-110">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="49973-111">Вызовите команду.</span><span class="sxs-lookup"><span data-stu-id="49973-111">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="49973-112">Если метод [System. Management. Automation. PowerShell. AddCommand \*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) вызывается более одного раза перед вызовом метода [System. Management. Automation. PowerShell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , результат первой команды передается второму и т. д.</span><span class="sxs-lookup"><span data-stu-id="49973-112">If you call the [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="49973-113">Если вы не хотите передавать результат предыдущей команды команде, добавьте ее, вызвав метод [System. Management. Automation. PowerShell. аддстатемент \*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) .</span><span class="sxs-lookup"><span data-stu-id="49973-113">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="49973-114">аддпараметер</span><span class="sxs-lookup"><span data-stu-id="49973-114">AddParameter</span></span>

 <span data-ttu-id="49973-115">В предыдущем примере выполняется одна команда без параметров.</span><span class="sxs-lookup"><span data-stu-id="49973-115">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="49973-116">Можно добавить параметры в команду с помощью метода [System. Management. Automation. пскомманд. аддпараметер \*.](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) например, следующий код возвращает список всех процессов, именованных `PowerShell` на компьютере.</span><span class="sxs-lookup"><span data-stu-id="49973-116">You can add parameters to the command by using the [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="49973-117">Можно добавить дополнительные параметры путем многократного вызова [System. Management. Automation. пскомманд. аддпараметер \*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) .</span><span class="sxs-lookup"><span data-stu-id="49973-117">You can add additional parameters by calling [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Command")
                   .AddParameter("Name", "Get-VM")
                   .AddParameter("Module", "Hyper-V")
                   .Invoke();
```

<span data-ttu-id="49973-118">Также можно добавить словарь имен и значений параметров, вызвав метод [System. Management. Automation. PowerShell. аддпараметерс \*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) .</span><span class="sxs-lookup"><span data-stu-id="49973-118">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "Get-VM");

parameters.Add("Module", "Hyper-V");
PowerShell.Create().AddCommand("Get-Command")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="49973-119">аддстатемент</span><span class="sxs-lookup"><span data-stu-id="49973-119">AddStatement</span></span>

<span data-ttu-id="49973-120">Пакетную обработку можно имитировать с помощью метода [System. Management. Automation. PowerShell. аддстатемент \*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) , который добавляет дополнительный оператор в конец конвейера. следующий код возвращает список запущенных процессов с именем `PowerShell` , а затем получает список запущенных служб.</span><span class="sxs-lookup"><span data-stu-id="49973-120">You can simulate batching by using the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="49973-121">аддскрипт</span><span class="sxs-lookup"><span data-stu-id="49973-121">AddScript</span></span>

<span data-ttu-id="49973-122">Можно запустить существующий скрипт, вызвав метод [System. Management. Automation. PowerShell. аддскрипт \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) .</span><span class="sxs-lookup"><span data-stu-id="49973-122">You can run an existing script by calling the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="49973-123">В следующем примере в конвейер добавляется скрипт и выполняется его выполнение.</span><span class="sxs-lookup"><span data-stu-id="49973-123">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="49973-124">В этом примере предполагается, что в папке уже есть скрипт с именем `MyScript.ps1` `D:\PSScripts` .</span><span class="sxs-lookup"><span data-stu-id="49973-124">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(File.ReadAllText(@"D:\PSScripts\MyScript.ps1")).Invoke();
```

<span data-ttu-id="49973-125">Существует также версия метода [System. Management. Automation. PowerShell. аддскрипт \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) , принимающая логический параметр с именем `useLocalScope` .</span><span class="sxs-lookup"><span data-stu-id="49973-125">There is also a version of the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="49973-126">Если этот параметр имеет значение `true` , скрипт выполняется в локальной области.</span><span class="sxs-lookup"><span data-stu-id="49973-126">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="49973-127">Следующий код запустит скрипт в локальной области.</span><span class="sxs-lookup"><span data-stu-id="49973-127">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(File.ReadAllText(@"D:\PSScripts\MyScript.ps1"), true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a><span data-ttu-id="49973-128">Синхронный вызов конвейера</span><span class="sxs-lookup"><span data-stu-id="49973-128">Invoking a pipeline synchronously</span></span>

<span data-ttu-id="49973-129">После добавления элементов в конвейер вы вызываете его.</span><span class="sxs-lookup"><span data-stu-id="49973-129">After you add elements to the pipeline, you invoke it.</span></span> <span data-ttu-id="49973-130">Для синхронного вызова конвейера вызывается перегрузка метода [System. Management. Automation. PowerShell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) .</span><span class="sxs-lookup"><span data-stu-id="49973-130">To invoke the pipeline synchronously, you call an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method.</span></span> <span data-ttu-id="49973-131">В следующем примере показано, как синхронно вызвать конвейер.</span><span class="sxs-lookup"><span data-stu-id="49973-131">The following example shows how to synchronously invoke a pipeline.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS1e
{
  class HostPS1e
  {
    static void Main(string[] args)
    {
      // Using the PowerShell.Create and AddCommand
      // methods, create a command pipeline.
      PowerShell ps = PowerShell.Create().AddCommand ("Sort-Object");

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the supplied input.
      foreach (PSObject result in ps.Invoke(new int[] { 3, 1, 6, 2, 5, 4 }))
      {
          Console.WriteLine("{0}", result);
      } // End foreach.
    } // End Main.
  } // End HostPS1e.
}
```

### <a name="invoking-a-pipeline-asynchronously"></a><span data-ttu-id="49973-132">Асинхронный вызов конвейера</span><span class="sxs-lookup"><span data-stu-id="49973-132">Invoking a pipeline asynchronously</span></span>

<span data-ttu-id="49973-133">Асинхронный вызов конвейера вызывает перегрузку [System. Management. Automation. PowerShell. BeginInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) для создания объекта [IAsyncResult](/dotnet/api/system.iasyncresult) и последующего вызова метода [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="49973-133">You invoke a pipeline asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) to create an [IAsyncResult](/dotnet/api/system.iasyncresult) object, and then calling the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

 <span data-ttu-id="49973-134">В следующем примере показано, как вызвать конвейер асинхронно.</span><span class="sxs-lookup"><span data-stu-id="49973-134">The following example shows how to invoke a pipeline asynchronously.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS3
{
  class HostPS3
  {
    static void Main(string[] args)
    {
      // Use the PowerShell.Create and PowerShell.AddCommand
      // methods to create a command pipeline that includes
      // Get-Process cmdlet. Do not include spaces immediately
      // before or after the cmdlet name as that will cause
      // the command to fail.
      PowerShell ps = PowerShell.Create().AddCommand("Get-Process");

      // Create an IAsyncResult object and call the
      // BeginInvoke method to start running the
      // command pipeline asynchronously.
      IAsyncResult asyncpl = ps.BeginInvoke();

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the default runspace.
      foreach (PSObject result in ps.EndInvoke(asyncpl))
      {
        Console.WriteLine("{0,-20}{1}",
                result.Members["ProcessName"].Value,
                result.Members["Id"].Value);
      } // End foreach.
      System.Console.WriteLine("Hit any key to exit.");
      System.Console.ReadKey();
    } // End Main.
  } // End HostPS3.
}
```

## <a name="see-also"></a><span data-ttu-id="49973-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="49973-135">See Also</span></span>

 [<span data-ttu-id="49973-136">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="49973-136">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

 [<span data-ttu-id="49973-137">Создание ограниченного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="49973-137">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)
