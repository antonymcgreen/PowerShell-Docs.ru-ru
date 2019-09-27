---
title: Добавление и вызов команд | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62be8432-28c1-4ca2-bcdb-d0350163fa8c
caps.latest.revision: 5
ms.openlocfilehash: f776f13fe743a3f5f67de0d94883e3f754040ffc
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71323485"
---
# <a name="adding-and-invoking-commands"></a><span data-ttu-id="5644a-102">Добавление и вызов команд</span><span class="sxs-lookup"><span data-stu-id="5644a-102">Adding and invoking commands</span></span>

<span data-ttu-id="5644a-103">После создания пространства выполнения можно добавить в конвейер Повершеллкоммандс и скрипты Windows, а затем вызывать конвейер синхронно или асинхронно.</span><span class="sxs-lookup"><span data-stu-id="5644a-103">After creating a runspace, you can add Windows PowerShellcommands and scripts to a pipeline, and then invoke the pipeline synchronously or asynchronously.</span></span>

## <a name="creating-a-pipeline"></a><span data-ttu-id="5644a-104">Создание конвейера</span><span class="sxs-lookup"><span data-stu-id="5644a-104">Creating a pipeline</span></span>

 <span data-ttu-id="5644a-105">Класс [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) предоставляет несколько методов для добавления команд, параметров и скриптов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="5644a-105">The [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class provides several methods to add commands, parameters, and scripts to the pipeline.</span></span> <span data-ttu-id="5644a-106">Конвейер можно вызвать синхронно, вызвав перегрузку метода [System. Management. Automation. PowerShell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) или асинхронно, вызвав перегрузку класса [System. Management. Automation. PowerShell. BeginInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) а затем метод [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .</span><span class="sxs-lookup"><span data-stu-id="5644a-106">You can invoke the pipeline synchronously by calling an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, or asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) and then the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

### <a name="addcommand"></a><span data-ttu-id="5644a-107">AddCommand</span><span class="sxs-lookup"><span data-stu-id="5644a-107">AddCommand</span></span>

1. <span data-ttu-id="5644a-108">Создайте объект [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) .</span><span class="sxs-lookup"><span data-stu-id="5644a-108">Create a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="5644a-109">Добавьте команду, которую требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="5644a-109">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="5644a-110">Вызовите команду.</span><span class="sxs-lookup"><span data-stu-id="5644a-110">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

 <span data-ttu-id="5644a-111">Если метод [System. Management. Automation. PowerShell. AddCommand \*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) вызывается более одного раза перед вызовом метода [System. Management. Automation. PowerShell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) , результат первой команды передается второму и т. д.</span><span class="sxs-lookup"><span data-stu-id="5644a-111">If you call the [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="5644a-112">Если вы не хотите передавать результат предыдущей команды команде, добавьте ее, вызвав метод [System. Management. Automation. PowerShell. аддстатемент \*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) .</span><span class="sxs-lookup"><span data-stu-id="5644a-112">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="5644a-113">аддпараметер</span><span class="sxs-lookup"><span data-stu-id="5644a-113">AddParameter</span></span>

 <span data-ttu-id="5644a-114">В предыдущем примере выполняется одна команда без параметров.</span><span class="sxs-lookup"><span data-stu-id="5644a-114">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="5644a-115">Можно добавить параметры в команду с помощью метода [System. Management. Automation. пскомманд. аддпараметер \*.](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) например, следующий код возвращает список всех процессов, именованных `PowerShell` на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5644a-115">You can add parameters to the command by using the [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 <span data-ttu-id="5644a-116">Можно добавить дополнительные параметры путем многократного вызова [System. Management. Automation. пскомманд. аддпараметер \*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) .</span><span class="sxs-lookup"><span data-stu-id="5644a-116">You can add additional parameters by calling [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 <span data-ttu-id="5644a-117">Также можно добавить словарь имен и значений параметров, вызвав метод [System. Management. Automation. PowerShell. аддпараметерс \*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) .</span><span class="sxs-lookup"><span data-stu-id="5644a-117">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="5644a-118">аддстатемент</span><span class="sxs-lookup"><span data-stu-id="5644a-118">AddStatement</span></span>

 <span data-ttu-id="5644a-119">Пакетную обработку можно имитировать с помощью метода [System. Management. Automation. PowerShell. аддстатемент \*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) , который добавляет дополнительный оператор в конец конвейера. следующий код возвращает список запущенных процессов с именем `PowerShell`. затем получает список выполняющихся служб.</span><span class="sxs-lookup"><span data-stu-id="5644a-119">You can simulate batching by using the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="5644a-120">аддскрипт</span><span class="sxs-lookup"><span data-stu-id="5644a-120">AddScript</span></span>

 <span data-ttu-id="5644a-121">Можно запустить существующий скрипт, вызвав метод [System. Management. Automation. PowerShell. аддскрипт \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) .</span><span class="sxs-lookup"><span data-stu-id="5644a-121">You can run an existing script by calling the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="5644a-122">В следующем примере в конвейер добавляется скрипт и выполняется его выполнение.</span><span class="sxs-lookup"><span data-stu-id="5644a-122">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="5644a-123">В этом примере предполагается, что в `MyScript.ps1` `D:\PSScripts`папке уже есть скрипт с именем.</span><span class="sxs-lookup"><span data-stu-id="5644a-123">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 <span data-ttu-id="5644a-124">Существует также версия метода [System. Management. Automation. PowerShell. аддскрипт \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) , принимающая логический параметр с именем `useLocalScope`.</span><span class="sxs-lookup"><span data-stu-id="5644a-124">There is also a version of the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="5644a-125">Если этот параметр имеет значение `true`, скрипт выполняется в локальной области.</span><span class="sxs-lookup"><span data-stu-id="5644a-125">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="5644a-126">Следующий код запустит скрипт в локальной области.</span><span class="sxs-lookup"><span data-stu-id="5644a-126">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a><span data-ttu-id="5644a-127">Синхронный вызов конвейера</span><span class="sxs-lookup"><span data-stu-id="5644a-127">Invoking a pipeline synchronously</span></span>

 <span data-ttu-id="5644a-128">После добавления элементов в конвейер вы вызываете его.</span><span class="sxs-lookup"><span data-stu-id="5644a-128">After you add elements to the pipeline, you invoke it.</span></span> <span data-ttu-id="5644a-129">Для синхронного вызова конвейера вызывается перегрузка метода [System. Management. Automation. PowerShell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) .</span><span class="sxs-lookup"><span data-stu-id="5644a-129">To invoke the pipeline synchronously, you call an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method.</span></span> <span data-ttu-id="5644a-130">В следующем примере показано, как синхронно вызвать конвейер.</span><span class="sxs-lookup"><span data-stu-id="5644a-130">The following example shows how to synchronously invoke a pipeline.</span></span>

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

### <a name="invoking-a-pipeline-asynchronously"></a><span data-ttu-id="5644a-131">Асинхронный вызов конвейера</span><span class="sxs-lookup"><span data-stu-id="5644a-131">Invoking a pipeline asynchronously</span></span>

 <span data-ttu-id="5644a-132">Асинхронный вызов конвейера вызывает перегрузку метода [System. Management. Automation. PowerShell. BeginInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) для создания объекта [IAsyncResult](https://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) и последующего вызова метода [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) метод.</span><span class="sxs-lookup"><span data-stu-id="5644a-132">You invoke a pipeline asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) to create an [IAsyncResult](https://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) object, and then calling the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

 <span data-ttu-id="5644a-133">В следующем примере показано, как вызвать конвейер асинхронно.</span><span class="sxs-lookup"><span data-stu-id="5644a-133">The following example shows how to invoke a pipeline asynchronously.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5644a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5644a-134">See Also</span></span>

 [<span data-ttu-id="5644a-135">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="5644a-135">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

 [<span data-ttu-id="5644a-136">Создание ограниченного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="5644a-136">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)
