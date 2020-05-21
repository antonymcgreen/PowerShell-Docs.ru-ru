---
title: Создание действия рабочего процесса из командлета Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4174e84f-d516-4aca-b418-273047dcfb07
caps.latest.revision: 7
ms.openlocfilehash: f45b5e985fa38ca4ff41707f1842ddb8b930e2b1
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557505"
---
# <a name="creating-a-workflow-activity-from-a-windows-powershell-cmdlet"></a>Создание действия рабочего процесса из командлета Windows PowerShell

Любой модуль или командлет Windows PowerShell можно упаковать как действие рабочего процесса с помощью методов класса [Microsoft. PowerShell. activitys. активитиженератор](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) . Используйте методы Microsoft. PowerShell [. activitys. активитиженератор. женератефроммодулеинфо *](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromModuleInfo), [Microsoft. PowerShell. activitys. активитиженератор. Женератефромкоммандинфо *](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromCommandInfo)и [Microsoft. PowerShell. activitys. Activitygenerator. Generatefromname *](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator.GenerateFromName) класса [Microsoft. PowerShell. activitys. Activitygenerator](/dotnet/api/Microsoft.PowerShell.Activities.ActivityGenerator) для создания кода C#, представляющего действие. Затем полученный код C# можно скомпилировать в сборку, которую можно добавить в проект в качестве действия.

Затем полученный код C# можно скомпилировать в сборку, которую можно добавить в проект как действие с помощью командной строки со следующей формой.

**CSC/nologo/out: AssemblyName/target: Библиотека/Reference: System. Activitys. действие/Reference: Microsoft. PowerShell. Activitys codefile.cs**

## <a name="example"></a>Пример

В следующем примере показано, как создать код C# для действия из модуля Windows PowerShell.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Management.Automation;
using System.Collections.ObjectModel;
using Microsoft.PowerShell.Activities;

namespace MakeActivity
{
    class Program
    {
        static void Main(string[] args)

        {
            StreamWriter CodeFile = new StreamWriter("c:\\\\testmodule\\codefile.cs");
            Collection<PSModuleInfo> ModuleInfos = new Collection<PSModuleInfo> { };
            PSModuleInfo ModuleInfo;
            string ActivityCode = "";
            string ModulePath = "";
            Console.Write("Type the full path and filename of the module to process:");
            ModulePath = Console.ReadLine();

            PowerShell ps = PowerShell.Create();

            ps.AddCommand("Import-Module").AddArgument(ModulePath);
            ps.AddParameter("PassThru");
            ModuleInfos = ps.Invoke<PSModuleInfo>();

            ModuleInfo = (PSModuleInfo)ModuleInfos[0];

            ActivityCode = ActivityGenerator.GenerateFromModuleInfo(ModuleInfo, "MyNamespace").First<String>();

           CodeFile.Write(ActivityCode);
            Console.ReadLine();

        }
    }
}

```

## <a name="example"></a>Пример

В следующем примере показано, как создать код C# для действия из командлета Windows PowerShell.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Management.Automation;
using System.Collections.ObjectModel;
using Microsoft.PowerShell.Activities;

namespace MakeActivity
{
    class Program
    {
        static void Main(string[] args)

        {
            StreamWriter CodeFile = new StreamWriter("c:\\\\testmodule\\codefile.cs");
            Collection<PSModuleInfo> ModuleInfos = new Collection<PSModuleInfo> { };
            PSModuleInfo ModuleInfo;
            Collection<CommandInfo> CommandInfos = new Collection<CommandInfo> { };
            CommandInfo MyCommand;
            string ActivityCode = "";
            string ModulePath = "";
            Console.Write("Type the full path and filename of the module to process:");
            ModulePath = Console.ReadLine();

            PowerShell ps = PowerShell.Create();

            ps.AddCommand("Import-Module").AddArgument(ModulePath);
            ps.AddParameter("PassThru");
            ModuleInfos = ps.Invoke<PSModuleInfo>();

            ModuleInfo = (PSModuleInfo)ModuleInfos[0];

            ps.AddCommand("Get-Command").AddArgument(ModuleInfo);
            CommandInfos = ps.Invoke<CommandInfo>();

            MyCommand = CommandInfos[0];

            ActivityCode = ActivityGenerator.GenerateFromCommandInfo(MyCommand, "MyNamespace");

           CodeFile.Write(ActivityCode);
            Console.ReadLine();

        }
    }
}

```
