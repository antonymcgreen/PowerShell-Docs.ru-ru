---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Выполнение задач по работе с сетями
description: В этой статье описывается, как использовать классы WMI в PowerShell для управления параметрами сетевой конфигурации в Windows.
ms.openlocfilehash: 95b05c193f4168cdcdf8414399c4f8c569bff754
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500255"
---
# <a name="performing-networking-tasks"></a>Выполнение задач по работе с сетями

Большая часть задач администрирования низкоуровневых сетевых протоколов связана с протоколом TCP/IP, так как это наиболее распространенный сетевой протокол. В этом разделе описано использование инструментария WMI и PowerShell для выполнения этих задач.

## <a name="listing-ip-addresses-for-a-computer"></a>Получение списка IP-адресов компьютера

Список всех IP-адресов, используемых локальным компьютером, возвращает следующая команда:

```powershell
 Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Select-Object -ExpandProperty IPAddress
```

Выходные данные этой команды отличаются от большинства списков свойств заключением значений в фигурные скобки:

```Output
10.0.0.1
fe80::60ea:29a7:a233:7cb7
2601:600:a27f:a470:f532:6451:5630:ec8b
2601:600:a27f:a470:e167:477d:6c5c:342d
2601:600:a27f:a470:b021:7f0d:eab9:6299
2601:600:a27f:a470:a40e:ebce:1a8c:a2f3
2601:600:a27f:a470:613c:12a2:e0e0:bd89
2601:600:a27f:a470:444f:17ec:b463:7edd
2601:600:a27f:a470:10fd:7063:28e9:c9f3
2601:600:a27f:a470:60ea:29a7:a233:7cb7
2601:600:a27f:a470::2ec1
```

Чтобы понять причину появления скобок, используйте командлет `Get-Member` для изучения свойства **IPAddress** :

```powershell
 Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Get-Member -Name IPAddress
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_NetworkAdapterConfiguration
Name      MemberType Definition
----      ---------- ----------
IPAddress Property   string[] IPAddress {get;}
```

Свойство IPAddress каждого сетевого адаптера в действительности представляет собой массив. Фигурные скобки в определении указывают на то, что свойство **IPAddress** содержит не значение типа **System.String** , а массив значений типа **System.String** .

## <a name="listing-ip-configuration-data"></a>Вывод данных IP-конфигурации

Для отображения подробных данных IP-конфигурации каждого сетевого адаптера воспользуйтесь следующей командой:

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true
```

По умолчанию отображается очень небольшая часть доступных сведений об объекте конфигурации сетевого адаптера. Для более глубокого изучения и устранения неполадок воспользуйтесь командлетом `Select-Object` или командлетом форматирования, например `Format-List`, чтобы задать отображаемые свойства.

В современных сетях TCP/IP вам, скорее всего, больше не понадобятся свойства IPX или WINS. Вы можете использовать параметр **ExcludeProperty** командлета `Select-Object`, чтобы скрыть свойства, имена которых начинаются на WINS или IPX.

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  Select-Object -ExcludeProperty IPX*,WINS*
```

Эта команда выводит подробные сведения о DHCP, DNS, маршрутизации и других менее значительных свойствах IP-конфигурации.

## <a name="pinging-computers"></a>Проверка связи с компьютерами

Простую проверку связи с компьютером можно выполнить с помощью **Win32_PingStatus** . Следующая команда производит проверку связи, но при этом выводит большой объем сведений:

```powershell
Get-CimInstance -Class Win32_PingStatus -Filter "Address='127.0.0.1'"
```

Удобнее отображать сводные данные, содержащие свойства Address, ResponseTime и StatusCode, как это делает приведенная ниже команда. Параметр **Autosize** командлета `Format-Table` изменяет размер столбцов таблицы для их правильного отображения в PowerShell.

```powershell
Get-CimInstance -Class Win32_PingStatus -Filter "Address='127.0.0.1'" |
  Format-Table -Property Address,ResponseTime,StatusCode -Autosize
```

```Output
Address   ResponseTime StatusCode
-------   ------------ ----------
127.0.0.1            0          0
```

Значение 0 свойства StatusCode указывает на успешно выполненную проверку связи.

Для проверки связи с несколькими компьютерами с помощью одной команды можно использовать массив. Так как адресов несколько, для проверки связи с каждым адресом по отдельности можно использовать `ForEach-Object`:

```powershell
'127.0.0.1','localhost','research.microsoft.com' |
  ForEach-Object -Process {
    Get-CimInstance -Class Win32_PingStatus -Filter ("Address='$_'") |
      Select-Object -Property Address,ResponseTime,StatusCode
  }
```

Один и тот же формат команды можно использовать для проверки связи со всеми компьютерами подсети. Например, при проверке частной сети, использующей номер сети 192.168.1.0 и стандартную маску подсети класса C (255.255.255.0), допустимы только локальные адреса в диапазоне от 192.168.1.1 до 192.168.1.254 (0 всегда зарезервирован в качестве номера сети, а 255 используется в качестве широковещательного адреса подсети).

Чтобы представить массив чисел от 1 до 254 в PowerShell, используйте оператор **1..254** .
Таким образом, полную проверку связи с подсетью можно осуществить, сформировав этот массив и добавляя его элементы к частичному адресу в операторе проверки связи:

```powershell
1..254| ForEach-Object -Process {
  Get-CimInstance -Class Win32_PingStatus -Filter ("Address='192.168.1.$_ '") } |
    Select-Object -Property Address,ResponseTime,StatusCode
```

Такой метод формирования диапазона адресов может быть использован в любых подобных случаях. Полный набор адресов можно сформировать следующим образом:

```powershell
$ips = 1..254 | ForEach-Object -Process {'192.168.1.' + $_}
```

## <a name="retrieving-network-adapter-properties"></a>Извлечение свойств сетевого адаптера

Ранее упоминалось о возможности извлечения общих свойств конфигурации с помощью класса **Win32_NetworkAdapterConfiguration** . Такие сведения о сетевом адаптере, как MAC-адреса и типы адаптеров, не относятся, строго говоря, к протоколу TCP/IP, но могут оказаться полезными для понимания того, что происходит в компьютере. Сводные данные можно получить с помощью следующей команды:

```powershell
Get-CimInstance -Class Win32_NetworkAdapter -ComputerName .
```

## <a name="assigning-the-dns-domain-for-a-network-adapter"></a>Назначение домена DNS сетевому адаптеру

Чтобы назначить домен DNS для автоматического разрешения имен, нужно использовать метод **SetDNSDomain** класса **Win32_NetworkAdapterConfiguration** . Так как назначение домена DNS для каждого сетевого адаптера производится независимо, необходимо воспользоваться оператором `ForEach-Object`, чтобы назначить домен для каждого адаптера:

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  ForEach-Object -Process { $_.SetDNSDomain('fabrikam.com') }
```

Здесь нужно использовать оператор фильтрации `IPEnabled=$true`, так как даже в сети, использующей лишь протокол TCP/IP, некоторые сетевые адаптеры компьютера не являются настоящими адаптерами TCP/IP. Они представляют собой общие программные элементы, поддерживающие службы RAS, PPTP, QoS и т. п. для всех адаптеров, и не имеют собственного адреса.

Фильтрацию в команде можно осуществить с помощью командлета `Where-Object` вместо фильтра `Get-CimInstance`.

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration |
  Where-Object {$_.IPEnabled} |
    ForEach-Object -Process {$_.SetDNSDomain('fabrikam.com')}
```

## <a name="performing-dhcp-configuration-tasks"></a>Выполнение задач настройки DHCP

Изменение сведений DHCP, так же как и настройка DNS, включает работу с набором сетевых адаптеров. Существует несколько отдельных действий, выполняемых с помощью инструментария WMI. Мы рассмотрим несколько наиболее типичных.

### <a name="determining-dhcp-enabled-adapters"></a>Определение адаптеров, поддерживающих DHCP

Найти на компьютере адаптеры, поддерживающие DHCP, можно с помощью следующей команды:

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "DHCPEnabled=$true"
```

Чтобы исключить из поиска адаптеры, имеющие проблемы в IP-конфигурации, можно добавить требование поддержки протокола IP:

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true"
```

### <a name="retrieving-dhcp-properties"></a>Извлечение свойств DHCP

Свойства адаптера, относящиеся к протоколу DHCP, обычно начинаются с `DHCP`, поэтому для отображения только этих свойств можно использовать параметр Property командлета `Format-Table`:

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "DHCPEnabled=$true" |
  Format-Table -Property DHCP*
```

### <a name="enabling-dhcp-on-each-adapter"></a>Включение поддержки DHCP на каждом адаптере

Чтобы включить поддержку DHCP на всех адаптерах, используйте команду:

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true |
  ForEach-Object -Process {$_.EnableDHCP()}
```

Вы можете воспользоваться оператором **Filter**`IPEnabled=$true and DHCPEnabled=$false` во избежание включения поддержки DHCP для адаптеров, у которых она уже включена, но пропуск этого шага не приведет к появлению ошибок.

### <a name="releasing-and-renewing-dhcp-leases-on-specific-adapters"></a>Отмена и обновление аренды адреса DHCP для отдельных адаптеров

Класс **Win32_NetworkAdapterConfiguration** использует методы **ReleaseDHCPLease** и **RenewDHCPLease** . Оба метода используются одинаково. Обычно их применяют лишь при необходимости отмены или обновления аренды адресов для адаптера в отдельной подсети. Простейшим способом фильтрации адаптеров в подсети является выбор лишь тех адаптеров, которые используют шлюз для этой подсети. Например, следующая команда отменяет все аренды адресов DHCP для адаптеров на локальном компьютере, которые арендуют адреса DHCP с 192.168.1.254:

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true" |
  Where-Object {$_.DHCPServer -contains '192.168.1.254'} |
    ForEach-Object -Process {$_.ReleaseDHCPLease()}
```

Единственное отличие при обновлении аренды адреса DHCP состоит в вызове метода **RenewDHCPLease** вместо метода **ReleaseDHCPLease** :

```powershell
Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled=$true and DHCPEnabled=$true" |
  Where-Object {$_.DHCPServer -contains '192.168.1.254'} |
    ForEach-Object -Process {$_.ReleaseDHCPLease()}
```

> [!NOTE]
> Если эти методы применяются на удаленном компьютере, возможна потеря доступа к удаленной системе, которая подключена через адаптер с отмененной или обновленной арендой.

### <a name="releasing-and-renewing-dhcp-leases-on-all-adapters"></a>Отмена и обновление аренды адресов DHCP для всех адаптеров

Отменить или обновить аренду адресов DHCP сразу для всех адаптеров можно с помощью методов **Win32_NetworkAdapterConfiguration** — **ReleaseDHCPLeaseAll** и **RenewDHCPLeaseAll** .
Однако эту команду следует применять к классу WMI, а не к отдельному адаптеру, поскольку глобальная отмена и обновление аренды осуществляется на уровне класса, а не отдельного адаптера.

Ссылку на класс WMI вместо ссылки на экземпляры класса можно получить путем перечисления всех классов WMI и выбора нужного класса по имени. Например, следующая команда возвращает класс **Win32_NetworkAdapterConfiguration** :

```powershell
Get-CimInstance -List | Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}
```

Эту команду можно рассматривать как класс и использовать ее при вызове метода **ReleaseDHCPAdapterLease** . В следующей команде элементы конвейера `Get-CimInstance` и `Where-Object` ограничены круглыми скобками, в результате чего PowerShell обрабатывает их первыми:

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}).ReleaseDHCPLeaseAll()
```

Такой же формат команды используется при вызове метода **RenewDHCPLeaseAll** :

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_NetworkAdapterConfiguration'}).RenewDHCPLeaseAll()
```

## <a name="creating-a-network-share"></a>Создание сетевой папки

Создать сетевую папку можно с помощью метода **Create** класса **Win32_Share** :

```powershell
(Get-CimInstance -List |
  Where-Object {$_.Name -eq 'Win32_Share'}).Create(
    'C:\temp','TempShare',0,25,'test share of the temp folder'
  )
```

Для этой же цели в Windows PowerShell можно использовать команду `net share`:

```powershell
net share tempshare=c:\temp /users:25 /remark:"test share of the temp folder"
```

## <a name="removing-a-network-share"></a>Удаление сетевой папки

Сетевую папку можно удалить с помощью **Win32_Share** , но этот процесс немного отличается от создания, так как требует получения именно удаляемой сетевой папки, а не класса **Win32_Share** . Следующий оператор удаляет сетевую папку **TempShare** :

```powershell
(Get-CimInstance -Class Win32_Share -Filter "Name='TempShare'").Delete()
```

Для Windows в этом случае подойдет и `net share`:

```powershell
net share tempshare /delete
```

```Output
tempshare was deleted successfully.
```

## <a name="connecting-a-windows-accessible-network-drive"></a>Подключение сетевого диска, доступного в Windows

Командлет `New-PSDrive` позволяет создавать диски PowerShell, но они доступны только в PowerShell. Для создания сетевого диска можно воспользоваться COM-объектом **WScript.Network** . Следующая команда сопоставляет сетевую папку `\\FPS01\users` с локальным диском `B:`:

```powershell
(New-Object -ComObject WScript.Network).MapNetworkDrive('B:', '\\FPS01\users')
```

В Windows также работает и команда `net use`:

```powershell
net use B: \\FPS01\users
```

Диски, сопоставленные с помощью **WScript.Network** или команды `net use`, мгновенно становятся доступными в PowerShell.
