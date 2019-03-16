---
title: Способы вызова командлета в командлет из | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efa4dc9c-ddee-46a3-978a-9dbb61e9bb6f
caps.latest.revision: 12
ms.openlocfilehash: 57543a88d04eb66c9d109249a99ddd272b02ef9d
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055909"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a>Как вызвать командлет из другого командлета

В этом примере показано, как для вызова командлета из в другой командлет, который позволяет добавлять функциональные возможности вызванного командлета в командлет, в которой вы выполняете разработку. В этом примере `Get-Process` командлет вызывается для получения процессов, запущенных на локальном компьютере. Вызов `Get-Process` командлет является эквивалентом следующую команду. Эта команда извлекает все процессы, имена которых начинаются с символов «» до «t».

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> Можно вызвать только нужные командлеты, которые наследуются от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класса. Не удается вызвать командлет, который является производным от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) класса.

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a>Для вызова из командлета в командлет

1. Убедитесь, что существует ссылка на сборку, определяющую командлет, чтобы вызвать и что соответствующие `using` добавляется инструкция. В этом примере добавляются следующие пространства имен.

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. В метод командлета обработки входных данных создайте новый экземпляр для вызова командлета. В этом примере объект типа [Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) создается вместе с строка, содержащая аргументы, используемые при вызове командлета.

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. Вызовите [System.Management.Automation.Cmdlet.Invoke*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) вызываемого метода `Get-Process` командлета.

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a>Пример

В этом примере `Get-Process` командлет вызывается изнутри [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод командлета.

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;   // Windows PowerShell assembly.
using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify an
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "GreetingInvoke")]
  public class SendGreetingInvokeCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the BeginProcessing method to invoke
    // the Get-Process cmdlet.
    protected override void BeginProcessing()
    {
      GetProcessCommand gp = new GetProcessCommand();
      gp.Name = new string[] { "[a-t]*" };
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
