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
ms.openlocfilehash: c23640b69d1e71a343e2bef2c6b3f8ffe19826d7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855690"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="24e0c-102">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="24e0c-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="24e0c-103">Команды Windows PowerShell, выполняются в пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="24e0c-103">Windows PowerShell commands run in a runspace.</span></span> <span data-ttu-id="24e0c-104">Чтобы разместить Windows PowerShell в вашем приложении, необходимо создать [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) объекта.</span><span class="sxs-lookup"><span data-stu-id="24e0c-104">To host Windows PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span> <span data-ttu-id="24e0c-105">Каждый пространства выполнения имеет [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объект, связанный с ним.</span><span class="sxs-lookup"><span data-stu-id="24e0c-105">Every runspace has an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span> <span data-ttu-id="24e0c-106">[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) указывает характеристики пространства выполнения, например, какие команды, переменные и модули доступны для этого пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="24e0c-106">The [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="24e0c-107">Создание InitialSessionState по умолчанию</span><span class="sxs-lookup"><span data-stu-id="24e0c-107">Create a default InitialSessionState</span></span>

 <span data-ttu-id="24e0c-108">[System.Management.Automation.Runspaces.Initialsessionstate.Createdefault\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault)и [System.Management.Automation.Runspaces.Initialsessionstate.Createdefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) можно использовать методы Чтобы создать [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) объектов.</span><span class="sxs-lookup"><span data-stu-id="24e0c-108">The [System.Management.Automation.Runspaces.Initialsessionstate.Createdefault\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault)and [System.Management.Automation.Runspaces.Initialsessionstate.Createdefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods can be used to create [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) objects.</span></span> <span data-ttu-id="24e0c-109">[System.Management.Automation.Runspaces.Initialsessionstate.Createdefault\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) создает InitialSessionState со встроенным командам загружена при [ System.Management.Automation.Runspaces.Initialsessionstate.Createdefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) загружает только те команды, необходимые для узла Windows PowerShell (команды из модуля Microsoft.PowerShell.Core.</span><span class="sxs-lookup"><span data-stu-id="24e0c-109">[System.Management.Automation.Runspaces.Initialsessionstate.Createdefault\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) creates an InitialSessionState with all of the built-in commands loaded, while [System.Management.Automation.Runspaces.Initialsessionstate.Createdefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) loads only the commands required to host Windows PowerShell (the commands from the Microsoft.PowerShell.Core module.</span></span>

 <span data-ttu-id="24e0c-110">Если вы хотите ограничить команды, доступные в своем хост-приложении необходимо создать ограниченное пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="24e0c-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span> <span data-ttu-id="24e0c-111">Сведения см. в разделе Создание ограниченное пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="24e0c-111">For information, see Creating a constrained runspace.</span></span>

 <span data-ttu-id="24e0c-112">Ниже показано, как создать InitialSessionState, назначьте его к пространству выполнения, как добавить команды в конвейер в это пространство выполнения и вызывать команды.</span><span class="sxs-lookup"><span data-stu-id="24e0c-112">The following code shows how to create an InitialSessionState, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span> <span data-ttu-id="24e0c-113">Дополнительные сведения о добавлении и вызова команд см. в разделе Добавление и вызова команд.</span><span class="sxs-lookup"><span data-stu-id="24e0c-113">For more information about adding and invoking commands, see Adding and invoking commands.</span></span>

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
      // Call the InitailSessionState.CreateDefault method to create
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

      // Call the PowerShell.Create() method to create the PowerShell
      // object,and then specify the runspace and commands to the pipeline.
      // and  create the command pipeline.
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

## <a name="see-also"></a><span data-ttu-id="24e0c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="24e0c-114">See Also</span></span>

 [<span data-ttu-id="24e0c-115">Создание ограниченное пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="24e0c-115">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)
