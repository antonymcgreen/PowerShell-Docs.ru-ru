---
title: Примеры использования Windows PowerShell узла | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a134b81-bd0c-4e1c-a2f0-9acbe852745a
caps.latest.revision: 9
ms.openlocfilehash: cc014487a680747ad59437052f79d4576154a1cb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059683"
---
# <a name="windows-powershell-host-quickstart"></a><span data-ttu-id="9a457-102">Краткое руководство по узлам Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a457-102">Windows PowerShell Host Quickstart</span></span>

<span data-ttu-id="9a457-103">Чтобы разместить Windows PowerShell в приложении, используйте [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) класса.</span><span class="sxs-lookup"><span data-stu-id="9a457-103">To host Windows PowerShell in your application, you use the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class.</span></span> <span data-ttu-id="9a457-104">Этот класс предоставляет методы, создать конвейер команд, а затем выполните эти команды в пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a457-104">This class provides methods that create a pipeline of commands and then execute those commands in a runspace.</span></span> <span data-ttu-id="9a457-105">Создание ведущего приложения проще всего использовать пространству выполнения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9a457-105">The simplest way to create a host application is to use the default runspace.</span></span> <span data-ttu-id="9a457-106">Пространству выполнения по умолчанию содержит все основные команды Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a457-106">The default runspace contains all of the core Windows PowerShell commands.</span></span> <span data-ttu-id="9a457-107">Если требуется обновлять приложение, чтобы предоставить некоторое подмножество команд Windows PowerShell, необходимо создать пользовательские пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a457-107">If you want your application to expose only a subset of the Windows PowerShell commands, you must create a custom runspace.</span></span>

## <a name="using-the-default-runspace"></a><span data-ttu-id="9a457-108">Использование пространства имен по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9a457-108">Using the default runspace</span></span>

<span data-ttu-id="9a457-109">Для начала мы использовать пространству выполнения по умолчанию и использовать методы [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) класс, чтобы добавить команды, параметры, инструкций и скриптов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="9a457-109">To start, we'll use the default runspace, and use the methods of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands, parameters, statements, and scripts to a pipeline.</span></span>

### <a name="addcommand"></a><span data-ttu-id="9a457-110">AddCommand</span><span class="sxs-lookup"><span data-stu-id="9a457-110">AddCommand</span></span>

<span data-ttu-id="9a457-111">Использовании [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) метод [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) класс, чтобы добавить команды в конвейер.</span><span class="sxs-lookup"><span data-stu-id="9a457-111">You use the [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands to the pipeline.</span></span> <span data-ttu-id="9a457-112">Например предположим, что вы хотите получить список выполняющихся процессов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9a457-112">For example, suppose you want to get the list of running processes on the machine.</span></span> <span data-ttu-id="9a457-113">Способ выполнения этой команды выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a457-113">The way to run this command is as follows.</span></span>

1. <span data-ttu-id="9a457-114">Создание [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) объекта.</span><span class="sxs-lookup"><span data-stu-id="9a457-114">Create a [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="9a457-115">Добавьте в команду, которую требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="9a457-115">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="9a457-116">Вызовите команду.</span><span class="sxs-lookup"><span data-stu-id="9a457-116">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="9a457-117">При вызове метода [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) более одного раза, прежде чем вызывать метод [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) метод, результат Первая команда передается по конвейеру второго и т. д.</span><span class="sxs-lookup"><span data-stu-id="9a457-117">If you call the [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="9a457-118">Если вы не хотите передать результат выполнения предыдущей команды к команде, добавьте его, вызвав [System.Management.Automation.Powershell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9a457-118">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="9a457-119">AddParameter</span><span class="sxs-lookup"><span data-stu-id="9a457-119">AddParameter</span></span>

<span data-ttu-id="9a457-120">В предыдущем примере выполняется одну команду без параметров.</span><span class="sxs-lookup"><span data-stu-id="9a457-120">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="9a457-121">Можно добавить параметры к команде с помощью [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) метод к примеру, следующий код получает список всех процессов, которые называются `PowerShell` под управлением компьютер.</span><span class="sxs-lookup"><span data-stu-id="9a457-121">You can add parameters to the command by using the [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="9a457-122">Можно добавить дополнительные параметры, вызвав [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) несколько раз.</span><span class="sxs-lookup"><span data-stu-id="9a457-122">You can add additional parameters by calling [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

<span data-ttu-id="9a457-123">Можно также добавить словарь имен и значений параметров, вызвав [System.Management.Automation.PowerShell.AddParameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) метод.</span><span class="sxs-lookup"><span data-stu-id="9a457-123">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.PowerShell.AddParameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="9a457-124">AddStatement</span><span class="sxs-lookup"><span data-stu-id="9a457-124">AddStatement</span></span>

<span data-ttu-id="9a457-125">Вы можете имитировать пакетной обработки с помощью [System.Management.Automation.PowerShell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) метод, который добавляет дополнительные инструкции для завершения работы конвейера, следующий код получает список запущенных процессов с именем `PowerShell`, а затем возвращает список запущенных служб.</span><span class="sxs-lookup"><span data-stu-id="9a457-125">You can simulate batching by using the [System.Management.Automation.PowerShell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="9a457-126">AddScript</span><span class="sxs-lookup"><span data-stu-id="9a457-126">AddScript</span></span>

<span data-ttu-id="9a457-127">Вы можете запустить существующий скрипт, вызов [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод.</span><span class="sxs-lookup"><span data-stu-id="9a457-127">You can run an existing script by calling the [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="9a457-128">В следующем примере добавляется сценарий в конвейер и запускает его.</span><span class="sxs-lookup"><span data-stu-id="9a457-128">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="9a457-129">В этом примере предполагается, что уже имеется сценарий с именем `MyScript.ps1` в папку с именем `D:\PSScripts`.</span><span class="sxs-lookup"><span data-stu-id="9a457-129">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

<span data-ttu-id="9a457-130">Есть также версия [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) метод, который принимает логический параметр с именем `useLocalScope`.</span><span class="sxs-lookup"><span data-stu-id="9a457-130">There is also a version of the [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="9a457-131">Если этот параметр имеет значение `true`, а затем сценарий выполняется в локальной области.</span><span class="sxs-lookup"><span data-stu-id="9a457-131">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="9a457-132">Следующий код выполняет скрипт в локальной области.</span><span class="sxs-lookup"><span data-stu-id="9a457-132">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a><span data-ttu-id="9a457-133">Создание пользовательского пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="9a457-133">Creating a custom runspace</span></span>

<span data-ttu-id="9a457-134">Хотя пространству выполнения по умолчанию, используемый в предыдущих примерах загружает все команды Windows PowerShell core, можно создать пользовательские пространства выполнения, который загружает только конкретному подмножеству все команды.</span><span class="sxs-lookup"><span data-stu-id="9a457-134">While the default runspace used in the previous examples loads all of the core Windows PowerShell commands, you can create a custom runspace that loads only a specified subset of all commands.</span></span> <span data-ttu-id="9a457-135">Может потребоваться выполнить, чтобы повысить производительность (идет загрузка большее количество команд является снижение производительности), или чтобы ограничить возможности пользователя для выполнения операций.</span><span class="sxs-lookup"><span data-stu-id="9a457-135">You might want to do this to improve performance (loading a larger number of commands is a performance hit), or to restrict the capability of the user to perform operations.</span></span> <span data-ttu-id="9a457-136">Пространства выполнения, которая предоставляет только ограниченный набор команд, называется ограниченное пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a457-136">A runspace that exposes only a limited number of commands is called a constrained runspace.</span></span> <span data-ttu-id="9a457-137">Чтобы создать ограниченное пространство выполнения, используйте [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) и [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) классы.</span><span class="sxs-lookup"><span data-stu-id="9a457-137">To create a constrained runspace, you use the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) and [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) classes.</span></span>

### <a name="creating-an-initialsessionstate-object"></a><span data-ttu-id="9a457-138">Создание объекта InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="9a457-138">Creating an InitialSessionState object</span></span>

<span data-ttu-id="9a457-139">Чтобы создать пользовательские пространства выполнения, необходимо сначала создать [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта.</span><span class="sxs-lookup"><span data-stu-id="9a457-139">To create a custom runspace, you must first create an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span> <span data-ttu-id="9a457-140">В следующем примере мы используем [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) создать пространство выполнения после создания по умолчанию [System.Management.Automation.Runspaces.InitialSessionState ](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объекта.</span><span class="sxs-lookup"><span data-stu-id="9a457-140">In the following example, we use the [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) to create a runspace after creating a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a><span data-ttu-id="9a457-141">Ограничение пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="9a457-141">Constraining the runspace</span></span>

<span data-ttu-id="9a457-142">В предыдущем примере мы создали по умолчанию [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объект, который загружает все встроенные ядра Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a457-142">In the previous example, we created a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object that loads all of the built-in core Windows PowerShell.</span></span> <span data-ttu-id="9a457-143">Мы также мог бы вызвать [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) метод для создания объекта InitialSessionState, который будет загружать только команды в Microsoft.PowerShell.Core Оснастка.</span><span class="sxs-lookup"><span data-stu-id="9a457-143">We could also have called the [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) method to create an InitialSessionState object that would load only the commands in the Microsoft.PowerShell.Core snapin.</span></span> <span data-ttu-id="9a457-144">Чтобы создать более ограниченное пространство выполнения, необходимо создать пустой [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) путем вызова метода [ System.Management.Automation.Runspaces.InitialSessionState.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) метод и чтобы InitialSessionState команд.</span><span class="sxs-lookup"><span data-stu-id="9a457-144">To create a more constrained runspace, you must create an empty [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object by calling the [System.Management.Automation.Runspaces.InitialSessionState.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add commands to the InitialSessionState.</span></span>

<span data-ttu-id="9a457-145">Использование пространства имен, который загружает только те команды, указываемые обеспечивает значительно улучшенную производительность.</span><span class="sxs-lookup"><span data-stu-id="9a457-145">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

<span data-ttu-id="9a457-146">Использование методов [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) класс определяет командлеты для начального состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a457-146">You use the methods of the [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span> <span data-ttu-id="9a457-147">В следующем примере создается пустой начальное состояние сеанса, а затем определяет и добавляет `Get-Command` и `Import-Module` команды для начального состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a457-147">The following example creates an empty initial session state, then defines and adds the `Get-Command` and `Import-Module` commands to the initial session state.</span></span> <span data-ttu-id="9a457-148">Затем мы создания пространства выполнения, ограничены, начальное состояние сеанса и выполните команды в этом пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a457-148">We then create a runspace constrained by that initial session state, and execute the commands in that runspace.</span></span>

<span data-ttu-id="9a457-149">Создание начального состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a457-149">Create the initial session state.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

<span data-ttu-id="9a457-150">Определение и добавлены команды для начального состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="9a457-150">Define and add commands to the initial session state.</span></span>

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

<span data-ttu-id="9a457-151">Создайте и откройте пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a457-151">Create and open the runspace.</span></span>

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

<span data-ttu-id="9a457-152">Выполнение команды и отображения результатов.</span><span class="sxs-lookup"><span data-stu-id="9a457-152">Execute a command and show the result.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
Collection<CommandInfo> result = ps.Invoke<CommandInfo>();
foreach (var entry in result)
{
       Console.WriteLine(entry.Name);
}
```

<span data-ttu-id="9a457-153">При запуске, результат выполнения этого кода будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a457-153">When run, the output of this code will look as follows.</span></span>

```powershell
Get-Command
Import-Module
```
