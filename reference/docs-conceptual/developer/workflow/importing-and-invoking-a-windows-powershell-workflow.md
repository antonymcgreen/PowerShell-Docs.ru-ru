---
title: Импорт и вызов рабочего процесса Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50e6f9b1-2678-4f53-9250-7c48843a9549
caps.latest.revision: 5
ms.openlocfilehash: 1113c0d1cd68bb97d2f96b529f755b62137d1f40
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366043"
---
# <a name="importing-and-invoking-a-windows-powershell-workflow"></a>Импорт и вызов рабочего процесса Windows PowerShell

Windows PowerShell 3 позволяет импортировать и вызывать рабочий процесс, упакованный в виде модуля Windows PowerShell. Сведения о модулях Windows PowerShell см. [в разделе Написание модуля Windows PowerShell](../module/writing-a-windows-powershell-module.md).

Класс [System. Management. Automation. псжобпрокси](/dotnet/api/System.Management.Automation.PSJobProxy)используется в качестве прокси на стороне клиента для объектов рабочего процесса на сервере. В следующей процедуре объясняется, как использовать объект [System. Management. Automation. псжобпрокси](/dotnet/api/System.Management.Automation.PSJobProxy)для вызова рабочего процесса.

### <a name="creating-a-psjobproxy-object-to-execute-workflow-commands-on-a-remote-server"></a>Создание объекта Псжобпрокси для выполнения команд рабочего процесса на удаленном сервере.

1. Создайте объект [System. Management. Automation. пространства. Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo), чтобы создать соединение с удаленным пространством выполнения.

2. Задайте для свойства [System. Management. Automation. пространства. Wsmanconnectioninfo. шеллури *](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ShellUri) объекта [System. Management. Automation. пространства. Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)значение `Microsoft.PowerShell.Workflow`, чтобы указать конечную точку Windows PowerShell.

3. Создайте пространство выполнения, использующее соединение, созданное путем выполнения предыдущих шагов.

4. Создайте объект [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell)и задайте для него свойство [System. Management. Automation. PowerShell. пространство](/dotnet/api/System.Management.Automation.PowerShell.Runspace) выполнения, созданное на предыдущем шаге.

5. Импортируйте модуль рабочего процесса и его команды в [System. Management. Automation. PowerShell](/dotnet/api/System.Management.Automation.PowerShell).

6. Создайте объект [System. Management. Automation. псжобпрокси](/dotnet/api/System.Management.Automation.PSJobProxy) и используйте его для выполнения команд рабочего процесса на удаленном сервере.

## <a name="example"></a>Пример

В следующем примере кода показано, как вызвать рабочий процесс с помощью Windows PowerShell.

Для этого примера требуется Windows PowerShell 3.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;
using System.Management.Automation.Runspaces;

namespace WorkflowHostTest
{

class Program
    {
        static void Main(string[] args)
        {
            if (args.Length == 0)
            {
                Console.WriteLine("Specify path to Workflow module");
                return;
            }

            string moduleFile = args[0];

            Console.Write("Creating Remote runspace connection...");
            WSManConnectionInfo connectionInfo = new WSManConnectionInfo();

            //Set the shellURI to workflow endpoint Microsoft.PowerShell.Workflow
            connectionInfo.ShellUri = "Microsoft.PowerShell.Workflow";

            //Create and open a runspace.
            Runspace runspace = RunspaceFactory.CreateRunspace(connectionInfo);
            runspace.Open();
            Console.WriteLine("done");

            PowerShell powershell = PowerShell.Create();
            powershell.Runspace = runspace;
            Console.Write("Setting $VerbosePreference=\"Continue\"...");
            powershell.AddScript("$VerbosePreference=\"Continue\"");
            powershell.Invoke();
            Console.WriteLine("done");

            Console.Write("Importing Workflow module...");
            powershell.Commands.Clear();

            //Import the module in to the PowerShell runspace. A XAML file could also be imported directly by using Import-Module.
            powershell.AddCommand("Import-Module").AddArgument(moduleFile);
            powershell.Invoke();
            Console.WriteLine("done");

            Console.Write("Creating job proxy...");
            powershell.Commands.Clear();
            powershell.AddCommand("Get-Proc").AddArgument("*");
            PSJobProxy job = powershell.AsJobProxy();
            Console.WriteLine("done");

                Console.WriteLine();
                Console.WriteLine("Using job proxy and performing operations...");
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());
                Console.WriteLine("Starting job...");
                job.StartJob();
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());

                // use blocking enumerator to wait for objects until job finishes
                job.Output.BlockingEnumerator = true;
                foreach (PSObject o in job.Output)
                {
                    Console.WriteLine(o.Properties["ProcessName"].Value.ToString());
                }

                // wait for a random time before attempting to stop job
                Random random = new Random();
                int time = random.Next(1, 10);
                Console.Write("Sleeping for {0} seconds when job is running on another thread...", time);
                System.Threading.Thread.Sleep(time * 1000);
                Console.WriteLine("done");
                Console.WriteLine("Stopping job...");
                job.StopJob();
                Console.WriteLine("State of Job :" + job.JobStateInfo.State.ToString());
                Console.WriteLine();
                job.Finished.WaitOne();
                Console.WriteLine("Output from job");
                Console.WriteLine("---------------");

                foreach (PSObject o in job.Output)
                {
                    Console.WriteLine(o.Properties["ProcessName"].Value.ToString());
                }

                Console.WriteLine();
                Console.WriteLine("Verbose messages from job");
                Console.WriteLine("-------------------------");
                foreach (VerboseRecord v in job.Verbose)
                {
                    Console.WriteLine(v.Message);
                }

            runspace.Close();
        }
    }
}

```