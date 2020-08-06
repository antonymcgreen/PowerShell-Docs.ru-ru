---
title: Создание удаленных пространств выполнения | Документация Майкрософт
ms.date: 09/12/2016
ms.openlocfilehash: 2b3c76eeae70de9ef116851313953bba1a1d890f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779596"
---
# <a name="creating-remote-runspaces"></a><span data-ttu-id="a13ed-102">Создание удаленных пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="a13ed-102">Creating remote runspaces</span></span>

<span data-ttu-id="a13ed-103">Команды PowerShell, которые принимают параметр **ComputerName** , могут выполняться на любом компьютере, на котором выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a13ed-103">PowerShell commands that take a **ComputerName** parameter can be run on any computer that runs PowerShell.</span></span> <span data-ttu-id="a13ed-104">Для выполнения команд, не принимающих параметр **ComputerName** , можно использовать WS-Management для настройки пространства выполнения, которое подключается к указанному компьютеру, и выполнять команды на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="a13ed-104">To run commands that don't take a **ComputerName** parameter, you can use WS-Management to configure a runspace that connects to a specified computer, and run commands on that computer.</span></span>

## <a name="using-a-wsmanconnection-to-create-a-remote-runspace"></a><span data-ttu-id="a13ed-105">Использование Всманконнектион для создания удаленного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="a13ed-105">Using a WSManConnection to create a remote runspace</span></span>

 <span data-ttu-id="a13ed-106">Чтобы создать пространство выполнения, которое подключается к удаленному компьютеру, создайте объект [System. Management. Automation. пространства. WSManConnectionInfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) .</span><span class="sxs-lookup"><span data-stu-id="a13ed-106">To create a runspace that connects to a remote computer, you create a [System.Management.Automation.Runspaces.WSManConnectionInfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object.</span></span> <span data-ttu-id="a13ed-107">Укажите целевую конечную точку для соединения, задав свойство [System. Management. Automation. пространства. WSManConnectionInfo. ConnectionURI](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ConnectionUri) объекта.</span><span class="sxs-lookup"><span data-stu-id="a13ed-107">You specify the target endpoint for the connection by setting the [System.Management.Automation.Runspaces.WSManConnectionInfo.ConnectionUri](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ConnectionUri) property of the object.</span></span> <span data-ttu-id="a13ed-108">Затем создайте пространство выполнения, вызвав метод [System. Management. Automation. пространства. рунспацефактори. креатерунспаце](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory.CreateRunspace) , указав в качестве параметра объект [System. Management. Automation. пространства. WSManConnectionInfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) . `connectionInfo`</span><span class="sxs-lookup"><span data-stu-id="a13ed-108">You then create a runspace by calling the [System.Management.Automation.Runspaces.RunspaceFactory.CreateRunspace](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory.CreateRunspace) method, specifying the [System.Management.Automation.Runspaces.WSManConnectionInfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object as the `connectionInfo` parameter.</span></span>

 <span data-ttu-id="a13ed-109">В следующем примере показано, как создать пространство выполнения, которое подключается к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a13ed-109">The following example shows how to create a runspace that connects to a remote computer.</span></span> <span data-ttu-id="a13ed-110">В этом примере `RemoteComputerUri` используется в качестве заполнителя для фактического URI удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="a13ed-110">In the example, `RemoteComputerUri` is used as a placeholder for the actual URI of a remote computer.</span></span>

```csharp
namespace Samples
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;            // PowerShell namespace.
  using System.Management.Automation.Runspaces;  // PowerShell namespace.

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class RemoteRunspace02
  {
    /// <summary>
    /// This sample shows how to create a remote runspace that
    /// runs commands on the local computer.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create a WSManConnectionInfo object using the default constructor
      // to connect to the "localHost". The WSManConnectionInfo object can
      // also be used to specify connections to remote computers.
      Uri RemoteComputerUri = new Uri("http://Server01:5985/WSMAN");
      WSManConnectionInfo connectionInfo = new WSManConnectionInfo(RemoteComputerUri);

      // Set the OperationTimeout property and OpenTimeout properties.
      // The OperationTimeout property is used to tell PowerShell
      // how long to wait (in milliseconds) before timing out for an
      // operation. The OpenTimeout property is used to tell Windows
      // PowerShell how long to wait (in milliseconds) before timing out
      // while establishing a remote connection.
      connectionInfo.OperationTimeout = 4 * 60 * 1000; // 4 minutes.
      connectionInfo.OpenTimeout = 1 * 60 * 1000; // 1 minute.

      // Create a remote runspace using the connection information.
      //using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace())
      using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace(connectionInfo))
      {
        // Establish the connection by calling the Open() method to open the runspace.
        // The OpenTimeout value set previously will be applied while establishing
        // the connection. Establishing a remote connection involves sending and
        // receiving some data, so the OperationTimeout will also play a role in this process.
          remoteRunspace.Open();

        // Create a PowerShell object to run commands in the remote runspace.
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = remoteRunspace;
          powershell.AddCommand("get-process");
          powershell.Invoke();

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

        // Close the connection. Call the Close() method to close the remote
        // runspace. The Dispose() method (called by using primitive) will call
        // the Close() method if it is not already called.
        remoteRunspace.Close();
      }
    }
  }
}
```
