---
title: Добавление и вызова команд | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62be8432-28c1-4ca2-bcdb-d0350163fa8c
caps.latest.revision: 5
ms.openlocfilehash: 31371797ee57f07075da3436e0b42b2ca01aaffd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857350"
---
# <a name="adding-and-invoking-commands"></a><span data-ttu-id="f0e04-102">Добавление и вызов команд</span><span class="sxs-lookup"><span data-stu-id="f0e04-102">Adding and invoking commands</span></span>

<span data-ttu-id="f0e04-103">После создания пространства выполнения, можно добавить Windows PowerShellcommands и сценарии конвейера и затем вызвать конвейер синхронно или асинхронно.</span><span class="sxs-lookup"><span data-stu-id="f0e04-103">After creating a runspace, you can add Windows PowerShellcommands and scripts to a pipeline, and then invoke the pipeline synchronously or asynchronously.</span></span>

## <a name="creating-a-pipeline"></a><span data-ttu-id="f0e04-104">Создание конвейера</span><span class="sxs-lookup"><span data-stu-id="f0e04-104">Creating a pipeline</span></span>

 <span data-ttu-id="f0e04-105">[System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) класс предоставляет несколько методов для добавления команды, параметры и сценарии в конвейер.</span><span class="sxs-lookup"><span data-stu-id="f0e04-105">The [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class provides several methods to add commands, parameters, and scripts to the pipeline.</span></span> <span data-ttu-id="f0e04-106">Конвейер можно вызвать синхронно, вызвав перегрузку [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод, или асинхронно путем вызова перегрузки [ System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) и затем [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) метод.</span><span class="sxs-lookup"><span data-stu-id="f0e04-106">You can invoke the pipeline synchronously by calling an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, or asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) and then the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

### <a name="addcommand"></a><span data-ttu-id="f0e04-107">AddCommand</span><span class="sxs-lookup"><span data-stu-id="f0e04-107">AddCommand</span></span>

1. <span data-ttu-id="f0e04-108">Создание [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) объекта.</span><span class="sxs-lookup"><span data-stu-id="f0e04-108">Create a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="f0e04-109">Добавьте в команду, которую требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="f0e04-109">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="f0e04-110">Вызовите команду.</span><span class="sxs-lookup"><span data-stu-id="f0e04-110">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

 <span data-ttu-id="f0e04-111">При вызове метода [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) более одного раза, прежде чем вызывать метод [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод, результат Первая команда передается по конвейеру второго и т. д.</span><span class="sxs-lookup"><span data-stu-id="f0e04-111">If you call the [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="f0e04-112">Если вы не хотите передать результат выполнения предыдущей команды к команде, добавьте его, вызвав [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="f0e04-112">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="f0e04-113">AddParameter</span><span class="sxs-lookup"><span data-stu-id="f0e04-113">AddParameter</span></span>

 <span data-ttu-id="f0e04-114">В предыдущем примере выполняется одну команду без параметров.</span><span class="sxs-lookup"><span data-stu-id="f0e04-114">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="f0e04-115">Можно добавить параметры к команде с помощью [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) метод к примеру, следующий код получает список всех процессов, которые называются `PowerShell` под управлением компьютер.</span><span class="sxs-lookup"><span data-stu-id="f0e04-115">You can add parameters to the command by using the [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 <span data-ttu-id="f0e04-116">Можно добавить дополнительные параметры, вызвав [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) несколько раз.</span><span class="sxs-lookup"><span data-stu-id="f0e04-116">You can add additional parameters by calling [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 <span data-ttu-id="f0e04-117">Можно также добавить словарь имен и значений параметров, вызвав [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) метод.</span><span class="sxs-lookup"><span data-stu-id="f0e04-117">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="f0e04-118">AddStatement</span><span class="sxs-lookup"><span data-stu-id="f0e04-118">AddStatement</span></span>

 <span data-ttu-id="f0e04-119">Вы можете имитировать пакетной обработки с помощью [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) метод, который добавляет дополнительные инструкции для завершения работы конвейера, следующий код получает список запущенных процессов с именем `PowerShell`, а затем возвращает список запущенных служб.</span><span class="sxs-lookup"><span data-stu-id="f0e04-119">You can simulate batching by using the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="f0e04-120">AddScript</span><span class="sxs-lookup"><span data-stu-id="f0e04-120">AddScript</span></span>

 <span data-ttu-id="f0e04-121">Вы можете запустить существующий скрипт, вызов [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод.</span><span class="sxs-lookup"><span data-stu-id="f0e04-121">You can run an existing script by calling the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="f0e04-122">В следующем примере добавляется сценарий в конвейер и запускает его.</span><span class="sxs-lookup"><span data-stu-id="f0e04-122">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="f0e04-123">В этом примере предполагается, что уже имеется сценарий с именем `MyScript.ps1` в папку с именем `D:\PSScripts`.</span><span class="sxs-lookup"><span data-stu-id="f0e04-123">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 <span data-ttu-id="f0e04-124">Есть также версия [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод, который принимает логический параметр с именем `useLocalScope`.</span><span class="sxs-lookup"><span data-stu-id="f0e04-124">There is also a version of the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="f0e04-125">Если этот параметр имеет значение `true`, а затем сценарий выполняется в локальной области.</span><span class="sxs-lookup"><span data-stu-id="f0e04-125">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="f0e04-126">Следующий код выполняет скрипт в локальной области.</span><span class="sxs-lookup"><span data-stu-id="f0e04-126">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a><span data-ttu-id="f0e04-127">Вызов конвейера синхронно</span><span class="sxs-lookup"><span data-stu-id="f0e04-127">Invoking a pipeline synchronously</span></span>

 <span data-ttu-id="f0e04-128">После добавления элементов в конвейер, ее можно вызвать.</span><span class="sxs-lookup"><span data-stu-id="f0e04-128">After you add elements to the pipeline, you invoke it.</span></span> <span data-ttu-id="f0e04-129">Для вызова конвейера синхронно, вызовите перегрузку [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод.</span><span class="sxs-lookup"><span data-stu-id="f0e04-129">To invoke the pipeline synchronously, you call an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method.</span></span> <span data-ttu-id="f0e04-130">В следующем примере показано, как синхронный вызов конвейера.</span><span class="sxs-lookup"><span data-stu-id="f0e04-130">The following example shows how to synchronously invoke a pipeline.</span></span>

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

### <a name="invoking-a-pipeline-asynchronously"></a><span data-ttu-id="f0e04-131">Вызов конвейера асинхронно</span><span class="sxs-lookup"><span data-stu-id="f0e04-131">Invoking a pipeline asynchronously</span></span>

 <span data-ttu-id="f0e04-132">Вызов конвейера асинхронно путем вызова перегрузки [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) для создания [IAsyncResult](http://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) объекта и последующего вызова [ System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) метод.</span><span class="sxs-lookup"><span data-stu-id="f0e04-132">You invoke a pipeline asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) to create an [IAsyncResult](http://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) object, and then calling the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

 <span data-ttu-id="f0e04-133">Приведенный ниже показано, как вызвать asynchronoulsy конвейера.</span><span class="sxs-lookup"><span data-stu-id="f0e04-133">The following example shows how to invoke a pipeline asynchronoulsy.</span></span>

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
      // Get-Process cmdlet. Do not include spaces immediatly
      // before or after the cmdlet name as that will cause
      // the command to fail.
      PowerShell ps = PowerShell.Create().AddCommand("Get-Process");

      // Create an IAsyncResult object and call the
      // BeginInvoke method to start running the
      // command pipeline asynchronously.
      IAsyncResult async = ps.BeginInvoke();

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the default runspace.
      foreach (PSObject result in ps.EndInvoke(async))
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

## <a name="see-also"></a><span data-ttu-id="f0e04-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f0e04-134">See Also</span></span>

 [<span data-ttu-id="f0e04-135">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="f0e04-135">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

 [<span data-ttu-id="f0e04-136">Создание ограниченное пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="f0e04-136">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)
