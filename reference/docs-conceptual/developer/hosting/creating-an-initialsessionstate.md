---
title: Создание InitialSessionState | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 946adf1006d1afcad2810c85e39f14514e837327
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779732"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="4f99c-102">Создание InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="4f99c-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="4f99c-103">Команды PowerShell выполняются в пространстве выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f99c-103">PowerShell commands run in a runspace.</span></span>
<span data-ttu-id="4f99c-104">Чтобы разместить PowerShell в приложении, необходимо создать объект [System. Management. Automation. пространства. пространство](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .</span><span class="sxs-lookup"><span data-stu-id="4f99c-104">To host PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>
<span data-ttu-id="4f99c-105">С каждым пространством выполнения связано [System.Management.Automation.Runspaces.Iniобъект тиалсессионстате](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .</span><span class="sxs-lookup"><span data-stu-id="4f99c-105">Every runspace has an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span>
<span data-ttu-id="4f99c-106">InitialSessionState указывает характеристики пространства выполнения, например, какие команды, переменные и модули доступны для этого пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f99c-106">The InitialSessionState specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="4f99c-107">Создание InitialSessionState по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4f99c-107">Create a default InitialSessionState</span></span>

<span data-ttu-id="4f99c-108">Методы [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) и [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) класса **InitialSessionState** можно использовать для создания объекта **InitialSessionState** .</span><span class="sxs-lookup"><span data-stu-id="4f99c-108">The [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) and [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods of the **InitialSessionState** class can be used to create an **InitialSessionState** object.</span></span>
<span data-ttu-id="4f99c-109">Метод **CreateDefault** создает объект **InitialSessionState** со всеми загруженными встроенными командами, а метод **CreateDefault2** загружает только команды, необходимые для размещения PowerShell (команды из модуля Microsoft. PowerShell. Core).</span><span class="sxs-lookup"><span data-stu-id="4f99c-109">The **CreateDefault** method creates an **InitialSessionState** with all of the built-in commands loaded, while the **CreateDefault2** method loads only the commands required to host PowerShell (the commands from the Microsoft.PowerShell.Core module).</span></span>

<span data-ttu-id="4f99c-110">Если вы хотите дополнительно ограничить команды, доступные в ведущем приложении, необходимо создать ограниченное пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f99c-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span>
<span data-ttu-id="4f99c-111">Дополнительные сведения см. [в разделе Создание ограниченного пространства выполнения](creating-a-constrained-runspace.md).</span><span class="sxs-lookup"><span data-stu-id="4f99c-111">For information, see [Creating a constrained runspace](creating-a-constrained-runspace.md).</span></span>

<span data-ttu-id="4f99c-112">В следующем коде показано, как создать **InitialSessionState**, присвоить ему пространство выполнения, добавить команды в конвейер в этом пространстве выполнения и вызвать команды.</span><span class="sxs-lookup"><span data-stu-id="4f99c-112">The following code shows how to create an **InitialSessionState**, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span>
<span data-ttu-id="4f99c-113">Дополнительные сведения о добавлении и вызове команд см. в разделе [Добавление и вызов команд](adding-and-invoking-commands.md).</span><span class="sxs-lookup"><span data-stu-id="4f99c-113">For more information about adding and invoking commands, see [Adding and invoking commands](adding-and-invoking-commands.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4f99c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4f99c-114">See Also</span></span>

[<span data-ttu-id="4f99c-115">Создание ограниченного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="4f99c-115">Creating a constrained runspace</span></span>](creating-a-constrained-runspace.md)

[<span data-ttu-id="4f99c-116">Добавление и вызов команд</span><span class="sxs-lookup"><span data-stu-id="4f99c-116">Adding and invoking commands</span></span>](adding-and-invoking-commands.md)
