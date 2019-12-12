---
title: Создание InitialSessionState | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ae707db-52e0-408c-87fa-b35c42eaaab1
caps.latest.revision: 5
ms.openlocfilehash: 9140d03e046def2fbbcc2a842b9ea1b9e1fa2985
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367623"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="a80d2-102">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="a80d2-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="a80d2-103">Команды PowerShell выполняются в пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="a80d2-103">PowerShell commands run in a runspace.</span></span>
<span data-ttu-id="a80d2-104">Чтобы разместить PowerShell в приложении, необходимо создать объект [System. Management. Automation. пространства. пространство](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .</span><span class="sxs-lookup"><span data-stu-id="a80d2-104">To host PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>
<span data-ttu-id="a80d2-105">Каждому пространству выполнения соответствует связанный с ним объект [System. Management. Automation. пространства. InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .</span><span class="sxs-lookup"><span data-stu-id="a80d2-105">Every runspace has an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span>
<span data-ttu-id="a80d2-106">InitialSessionState указывает характеристики пространства выполнения, например, какие команды, переменные и модули доступны для этого пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="a80d2-106">The InitialSessionState specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="a80d2-107">Создание InitialSessionState по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a80d2-107">Create a default InitialSessionState</span></span>

<span data-ttu-id="a80d2-108">Методы [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) и [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) класса **InitialSessionState** можно использовать для создания объекта **InitialSessionState** .</span><span class="sxs-lookup"><span data-stu-id="a80d2-108">The [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) and [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods of the **InitialSessionState** class can be used to create an **InitialSessionState** object.</span></span>
<span data-ttu-id="a80d2-109">Метод **CreateDefault** создает объект **InitialSessionState** со всеми загруженными встроенными командами, а метод **CreateDefault2** загружает только команды, необходимые для размещения PowerShell (команды из модуля Microsoft. PowerShell. Core).</span><span class="sxs-lookup"><span data-stu-id="a80d2-109">The **CreateDefault** method creates an **InitialSessionState** with all of the built-in commands loaded, while the **CreateDefault2** method loads only the commands required to host PowerShell (the commands from the Microsoft.PowerShell.Core module).</span></span>

<span data-ttu-id="a80d2-110">Если вы хотите дополнительно ограничить команды, доступные в ведущем приложении, необходимо создать ограниченное пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="a80d2-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span>
<span data-ttu-id="a80d2-111">Дополнительные сведения см. [в разделе Создание ограниченного пространства выполнения](creating-a-constrained-runspace.md).</span><span class="sxs-lookup"><span data-stu-id="a80d2-111">For information, see [Creating a constrained runspace](creating-a-constrained-runspace.md).</span></span>

<span data-ttu-id="a80d2-112">В следующем коде показано, как создать **InitialSessionState**, присвоить ему пространство выполнения, добавить команды в конвейер в этом пространстве выполнения и вызвать команды.</span><span class="sxs-lookup"><span data-stu-id="a80d2-112">The following code shows how to create an **InitialSessionState**, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span>
<span data-ttu-id="a80d2-113">Дополнительные сведения о добавлении и вызове команд см. в разделе [Добавление и вызов команд](adding-and-invoking-commands.md).</span><span class="sxs-lookup"><span data-stu-id="a80d2-113">For more information about adding and invoking commands, see [Adding and invoking commands](adding-and-invoking-commands.md).</span></span>

```csharp
namespace SampleHost
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  class HostP4b
  {
    static void Main(string[] args)
    {
      // Call the InitialSessionState.CreateDefault method to create
      // an empty InitialSessionState object, and then add the
      // elements that will be available when the runspace is opened.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      SessionStateVariableEntry var1 = new
          SessionStateVariableEntry("test1",
                                    "MyVar1",
                                    "Initial session state MyVar1 test");
      iss.Variables.Add(var1);

      SessionStateVariableEntry var2 = new
          SessionStateVariableEntry("test2",
                                    "MyVar2",
                                    "Initial session state MyVar2 test");
      iss.Variables.Add(var2);

      // Call the RunspaceFactory.CreateRunspace(InitialSessionState)
      // method to create the runspace where the pipeline is run.
      Runspace rs = RunspaceFactory.CreateRunspace(iss);
      rs.Open();

      // Call the PowerShell.Create() method to create the PowerShell object,
      // and then specify the runspace and commands to the pipeline.
      // and create the command pipeline.
      PowerShell ps = PowerShell.Create();
      ps.Runspace = rs;
      ps.AddCommand("Get-Variable");
      ps.AddArgument("test*");

      Console.WriteLine("Variable             Value");
      Console.WriteLine("--------------------------");

      // Call the PowerShell.Invoke() method to run
      // the pipeline synchronously.
      foreach (PSObject result in ps.Invoke())
      {
        Console.WriteLine("{0,-20}{1}",
            result.Members["Name"].Value,
            result.Members["Value"].Value);
      } // End foreach.

      // Close the runspace to free resources.
      rs.Close();

    } // End Main.
  } // End SampleHost.
}
```

## <a name="see-also"></a><span data-ttu-id="a80d2-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="a80d2-114">See Also</span></span>

[<span data-ttu-id="a80d2-115">Создание ограниченного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="a80d2-115">Creating a constrained runspace</span></span>](creating-a-constrained-runspace.md)

[<span data-ttu-id="a80d2-116">Добавление и вызов команд</span><span class="sxs-lookup"><span data-stu-id="a80d2-116">Adding and invoking commands</span></span>](adding-and-invoking-commands.md)
