---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Управление службами
ms.assetid: 7a410e4d-514b-4813-ba0c-0d8cef88df31
ms.openlocfilehash: 81fd8802215da80ce22fa3fd4750b1df6efe8206
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268081"
---
# <a name="managing-services"></a>Управление службами

Существует восемь основных командлетов Service, предназначенных для широкого спектра задач обслуживания. Мы рассмотрим только вывод списка служб и изменение состояния их выполнения, но вы можете получить весь список командлетов Service с помощью `Get-Help \*-Service`, а сведения о каждом из них можно просмотреть с помощью командлета`Get-Help <Cmdlet-Name>`, например`Get-Help New-Service`.

## <a name="getting-services"></a>Получение служб

Получить службы на локальном или удаленном компьютере можно с помощью командлета `Get-Service`. Как и в случае с `Get-Process`, использование команды `Get-Service` без параметров возвращает все службы. Можно фильтровать по имени, даже используя звездочку как подстановочный знак:

```powershell
PS> Get-Service -Name se*

Status   Name               DisplayName
------   ----               -----------
Running  seclogon           Secondary Logon
Running  SENS               System Event Notification
Stopped  ServiceLayer       ServiceLayer
```

Так как реальное имя службы не всегда очевидно, может потребоваться найти службы по отображаемому имени. Это можно сделать с использованием определенного имени, подстановочных знаков или списка отображаемых имен:

```powershell
PS> Get-Service -DisplayName se*

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Running  SamSs              Security Accounts Manager
Running  seclogon           Secondary Logon
Stopped  ServiceLayer       ServiceLayer
Running  wscsvc             Security Center

PS> Get-Service -DisplayName ServiceLayer,Server

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Stopped  ServiceLayer       ServiceLayer
```

Параметр ComputerName командлета Get-Service можно использовать для получения служб на удаленных компьютерах. Параметр ComputerName принимает несколько значений и подстановочные знаки, что позволяет получить службы на нескольких компьютерах с помощью одной команды. Например, приведенная ниже команда получает службы на удаленном компьютере Server01.

```powershell
Get-Service -ComputerName Server01
```

## <a name="getting-required-and-dependent-services"></a>Получение необходимых и зависимых служб

Командлет Get-Service имеет два параметра, которые удобно использовать при администрировании служб. Параметр DependentServices получает службы, которые зависят от данной службы. Параметр RequiredServices получает службы, от которых зависит данная служба.

Эти параметры просто отображают значения свойств DependentServices и ServicesDependedOn (псевдоним RequiredServices) объекта System.ServiceProcess.ServiceController, возвращаемого Get-Service, но они упрощают работу с командами и получение этой информации.

Приведенная ниже команда получает службы, необходимые службе LanmanWorkstation.

```powershell
PS> Get-Service -Name LanmanWorkstation -RequiredServices

Status   Name               DisplayName
------   ----               -----------
Running  MRxSmb20           SMB 2.0 MiniRedirector
Running  bowser             Bowser
Running  MRxSmb10           SMB 1.x MiniRedirector
Running  NSI                Network Store Interface Service
```

Приведенная ниже команда получает службы, которым требуется служба LanmanWorkstation.

```powershell
PS> Get-Service -Name LanmanWorkstation -DependentServices

Status   Name               DisplayName
------   ----               -----------
Running  SessionEnv         Terminal Services Configuration
Running  Netlogon           Netlogon
Stopped  Browser            Computer Browser
Running  BITS               Background Intelligent Transfer Ser...
```

Вы даже можете получить все службы, имеющие зависимости. Следующая команда делает именно это, а затем она использует командлет Format-Table для отображения свойств Status, Name, RequiredServices и DependentServices для служб на компьютере.

```powershell
Get-Service -Name * | Where-Object {$_.RequiredServices -or $_.DependentServices} | Format-Table -Property Status, Name, RequiredServices, DependentServices -auto
```

## <a name="stopping-starting-suspending-and-restarting-services"></a>Остановка, запуск, приостановка и перезапуск служб

Все командлеты Service имеют схожую общую форму. Службы можно указать по общему имени или отображаемому имени, они также принимают списки и подстановочные знаки в качестве значений. Для остановки очереди печати принтера используйте:

```powershell
Stop-Service -Name spooler
```

Для запуска очереди печати принтера после ее остановки используйте:

```powershell
Start-Service -Name spooler
```

Для приостановки очереди печати принтера используйте:

```powershell
Suspend-Service -Name spooler
```

Командлет `Restart-Service` работает так же, как другие командлеты Service, но для него будет приведено несколько более сложных примеров. В самом простом случае указывается имя службы:

```powershell
PS> Restart-Service -Name spooler

WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
PS>
```

Вы получите повторяющееся предупреждение о запуске очереди печати принтера. При выполнении операции службы, занимающей некоторое время, Windows PowerShell сообщит, что по-прежнему пытается выполнить задачу.

Если требуется перезапустить несколько служб, можно получить список служб, отфильтровать его и выполнить перезапуск:

```powershell
PS> Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service

WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
Restart-Service : Cannot stop service 'Logical Disk Manager (dmserver)' because
 it has dependent services. It can only be stopped if the Force flag is set.
At line:1 char:57
+ Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service <<<<
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
```

У этих командлетов Service нет параметра ComputerName, но их можно выполнить на удаленном компьютере с помощью командлета Invoke-Command. Например, приведенная ниже команда перезапускает службу очередь печати принтера на удаленном компьютере Server01.

```powershell
Invoke-Command -ComputerName Server01 {Restart-Service Spooler}
```

## <a name="setting-service-properties"></a>Задание свойств служб

Командлет `Set-Service` изменяет свойства службы на локальном или удаленном компьютере. Так как состояние службы является свойством, этот командлет можно использовать для запуска, остановки и приостановки службы.
Командлет Set-Service также имеет параметр StartupType, позволяющий изменять тип запуска службы.

Чтобы использовать командлет `Set-Service` в Windows Vista и более поздних версиях Windows, откройте среду Windows PowerShell, используя параметр "Запуск от имени администратора".

Дополнительные сведения см. в статье [Set-Service [m2]](https://technet.microsoft.com/library/b71e29ed-372b-4e32-a4b7-5eb6216e56c3).

## <a name="see-also"></a>См. также

- [Get-Service [m2]](https://technet.microsoft.com/en-us/library/0a09cb22-0a1c-4a79-9851-4e53075f9cf6)
- [Set-Service [m2]](https://technet.microsoft.com/library/b71e29ed-372b-4e32-a4b7-5eb6216e56c3)
- [Restart-Service [m2]](https://technet.microsoft.com/en-us/library/45acf50d-2277-4523-baf7-ce7ced977d0f)
- [Suspend-Service [m2]](https://technet.microsoft.com/en-us/library/c8492b87-0e21-4faf-8054-3c83c2ec2826)