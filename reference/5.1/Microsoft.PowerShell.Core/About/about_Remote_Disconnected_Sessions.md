---
description: Объясняет, как отключиться и повторно подключиться к сеансу PowerShell (PSSession).
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_disconnected_sessions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Disconnected_Sessions
ms.openlocfilehash: 421db8bc07bcab299494c00ea4d38f6e8de455b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232317"
---
# <a name="about-remote-disconnected-sessions"></a>Об удаленных отключенных сеансах

## <a name="short-description"></a>Краткое описание

Объясняет, как отключиться и повторно подключиться к сеансу PowerShell (PSSession).

## <a name="long-description"></a>Подробное описание

Начиная с PowerShell 3,0 можно отключиться от PSSession и повторно подключиться к сеансу PSSession на том же или другом компьютере. Состояние сеанса сохраняется, а команды в PSSession продолжают выполняться, пока сеанс отключен.

Функция отключенных сеансов доступна только в том случае, если на удаленном компьютере работает PowerShell 3,0 или более поздней версии.

Функция отключенных сеансов позволяет закрыть сеанс, в котором был создан сеанс PSSession, и даже закрыть PowerShell и завершить работу компьютера без прерывания выполнения команд в сеансе PSSession. Отключенные сеансы полезны для выполнения команд, которые занимают длительное время и предоставляют ИТ-специалистам необходимое время и гибкость устройств.

Невозможно отключиться от интерактивного сеанса, запущенного с помощью `Enter-PSSession` командлета.

Можно использовать отключенные сеансы для управления PSSession, которые были отключены непреднамеренно в результате сбоя компьютера или сети.

В реальном использовании функция отключенных сеансов позволяет приступить к решению проблемы, подать особое внимание на проблему с более высоким приоритетом, а затем возобновить работу решения даже на другом компьютере в другом расположении.

## <a name="disconnected-session-cmdlets"></a>Командлеты отключенных сеансов

Следующие командлеты поддерживают функцию отключенных сеансов:

- `Connect-PSSession`: Подключается к отключенному сеансу PSSession.
- `Disconnect-PSSession`: Отключает сеанс PSSession.
- `Get-PSSession`: Получает PSSession на локальном компьютере или на удаленных компьютерах.
- `Receive-PSSession`: Возвращает результаты команд, которые выполнялись в отключенных сеансах.
- `Invoke-Command`: Параметр **InDisconnectedSession** создает сеанс PSSession и немедленно отключается.

## <a name="how-the-disconnected-sessions-feature-works"></a>Как работает функция отключенных сеансов

Начиная с PowerShell 3,0, PSSession не зависят от сеансов, в которых они созданы. Активные PSSession хранятся на удаленном компьютере или на **стороне сервера** соединения, даже если сеанс, в котором был создан PSSession, закрыт, а исходный компьютер выключен или отключен от сети.

В PowerShell 2,0 сеанс PSSession удаляется с удаленного компьютера, когда он отключается от исходного сеанса или после завершения сеанса, в котором он был создан.

При отключении сеанса PSSession сеанс PSSession остается активным и сохраняется на удаленном компьютере. Состояние сеанса меняется с " **работает** " на " **отключено** ". Можно повторно подключиться к отключенному сеансу PSSession из текущего сеанса или из другого сеанса на том же компьютере или на другом компьютере. Удаленный компьютер, поддерживающий сеанс, должен быть установлен и подключен к сети.

Команды в отключенном сеансе PSSession продолжают выполняться на удаленном компьютере до завершения выполнения команды или заполнения буфера вывода. Чтобы предотвратить приостановку выполнения команды в полном буфере вывода, используйте параметр **аутпутбуфферингмоде** `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` командлетов, или.

Отключенные сеансы хранятся в отключенном состоянии на удаленном компьютере. Они доступны для повторного подключения до тех пор, пока не будет удален сеанс PSSession, например с помощью `Remove-PSSession` командлета или до истечения времени ожидания сеанса PSSession. Можно настроить время ожидания простоя сеанса PSSession с помощью параметров **идлетимеаутсек** или **IdleTimeout** `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` командлетов, или.

Другой пользователь может подключиться к PSSession, который вы создали, но только в том случае, если они смогут предоставить учетные данные, которые использовались для создания сеанса, или использовать `RunAs` учетные данные конфигурации сеанса.

## <a name="how-to-get-pssessions"></a>Как получить PSSession

Начиная с PowerShell 3,0 `Get-PSSession` командлет получает PSSession на локальном компьютере и на удаленных компьютерах. Он также может получить PSSession, созданные в текущем сеансе.

Чтобы получить PSSession на локальном компьютере или на удаленных компьютерах, используйте параметры **ComputerName** или **ConnectionURI** . Без параметров `Get-PSSession` получает значение PSSession, созданное в локальном сеансе, независимо от того, где они завершаются.

При получении PSSession не забудьте найти их на компьютере, где они поддерживаются, то есть на удаленном или **серверном** компьютере.

Например, если вы создадите сеанс PSSession на компьютере Server01, получите его с компьютера Server01. При создании сеанса PSSession с другого компьютера на локальный компьютер получает сеанс с локального компьютера.

В следующей последовательности команд показано, как `Get-PSSession` работает.

Первая команда создает сеанс на компьютере Server01. Сеанс находится на компьютере Server01.

```powershell
New-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

Чтобы получить сеанс, используйте параметр **ComputerName** параметра `Get-PSSession` со значением Server01.

```powershell
Get-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

Если параметр **ComputerName** параметра `Get-PSSession` имеет значение localhost, `Get-PSSession` получает PSSession, которые завершаются в и сохраняются на локальном компьютере. Он не получает PSSession на компьютере Server01, даже если они были запущены на локальном компьютере.

```powershell
Get-PSSession -ComputerName localhost
```

Чтобы получить сеансы, созданные в текущем сеансе, используйте `Get-PSSession` командлет без параметров. В этом примере `Get-PSSession` получает сеанс PSSession, который был создан в текущем сеансе, и подключается к компьютеру Server01.

```powershell
Get-PSSession
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-disconnect-sessions"></a>Отключение сеансов

Чтобы отключить сеанс PSSession, используйте `Disconnect-PSSession` командлет. Чтобы указать PSSession, используйте параметр **Session** или конвейер a PSSession из `New-PSSession` `Get-PSSession` командлетов или в `Disconnect-PSSession` .

Следующая команда отключает сеанс PSSession на компьютере Server01.
Обратите внимание, что значение свойства **State** — **disconnected** , а **доступность** — **нет**.

```powershell
Get-PSSession -ComputerName Server01 | Disconnect-PSSession
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 2 Session2  Server01      Disconnected  Microsoft.PowerShell          None
```

Чтобы создать отключенный сеанс, используйте параметр **InDisconnectedSession** `Invoke-Command` командлета. Он создает сеанс, запускает команду и немедленно отключается, прежде чем команда сможет вернуть выходные данные.

Следующая команда выполняет `Get-WinEvent` команду в отключенном сеансе на удаленном компьютере Server02.

```powershell
Invoke-Command -ComputerName Server02 -InDisconnectedSession -ScriptBlock {
   Get-WinEvent -LogName "*PowerShell*" }
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 4 Session3  Server02      Disconnected  Microsoft.PowerShell          None
```

## <a name="how-to-connect-to-disconnected-sessions"></a>Подключение к отключенным сеансам

Можно подключиться к любому доступному отключенному сеансу PSSession из сеанса, в котором был создан сеанс PSSession, или из других сеансов на локальном компьютере или на других компьютерах.

Можно создать сеанс PSSession, выполнить команды в сеансе PSSession, отключиться от сеанса PSSession, закрыть PowerShell и завершить работу компьютера. Часы позже можно будет открыть другой компьютер, получить сеанс PSSession, подключиться к нему и получить результаты команд, которые выполнялись в сеансе PSSession, пока он был отключен. Затем в сеансе можно выполнить дополнительные команды.

Чтобы подключить отключенный сеанс PSSession, используйте `Connect-PSSession` командлет. Используйте параметры **ComputerName** или **ConnectionURI** , чтобы указать PSSession или конвейер a PSSession от `Get-PSSession` до `Connect-PSSession` .

Следующая команда получает сеансы на компьютере Server02. Выходные данные включают два отключенных сеанса, оба из которых доступны.

```powershell
Get-PSSession -ComputerName Server02
```

```Output
Id Name      ComputerName   State         ConfigurationName     Availability
-- ----      ------------   -----         -----------------     ------------
 2 Session2  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
 4 Session3  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
```

Следующая команда подключается к Session2. Сеанс PSSession теперь открыт и доступен.

```powershell
Connect-PSSession -ComputerName Server02 -Name Session2
```

```Output
Id Name      ComputerName    State    ConfigurationName     Availability
-- ----      ------------    -----    -----------------     ------------
 2 Session2  juneb-srv8320   Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-get-the-results"></a>Как получить результаты

Чтобы получить результаты команд, которые выполнялись в отключенном сеансе PSSession, используйте `Receive-PSSession` командлет.

`Receive-PSSession`Вместо использования `Connect-PSSession` командлета можно использовать. Если сеанс уже подключен повторно, `Receive-PSSession` получает результаты команд, которые выполнялись в момент отключения сеанса. Если сеанс PSSession по-прежнему отключен, `Receive-PSSession` подключается к нему и получает результаты команд, которые выполнялись в момент отключения.

`Receive-PSSession` может возвращать результаты в задании (асинхронно) или в ведущем приложении (синхронно). Используйте параметр **Target** для выбора **задания** или **узла**. Значение по умолчанию — **Host**. Однако если полученная команда была запущена в текущем сеансе как **Задание** , по умолчанию она возвращается как **Задание** .

Следующая команда использует `Receive-PSSession` командлет для подключения к сеансу PSSession на компьютере Server02 и получения результатов `Get-WinEvent` команды, которая выполнялась в сеансе Session3. Команда использует параметр **Target** для получения результатов в **задании**.

```powershell
Receive-PSSession -ComputerName Server02 -Name Session3 -OutTarget Job
```

```Output
Id   Name   PSJobTypeName   State         HasMoreData     Location
--   ----   -------------   -----         -----------     --------
 3   Job3   RemoteJob       Running       True            Server02
```

Чтобы получить результаты задания, используйте `Receive-Job` командлет.

```powershell
Get-Job | Receive-Job -Keep
```

```Output
ProviderName: PowerShell

TimeCreated             Id LevelDisplayName Message     PSComputerName
-----------             -- ---------------- -------     --------------
5/14/2012 7:26:04 PM   400 Information      Engine stat Server02
5/14/2012 7:26:03 PM   600 Information      Provider "W Server02
5/14/2012 7:26:03 PM   600 Information      Provider "C Server02
5/14/2012 7:26:03 PM   600 Information      Provider "V Server02
```

## <a name="state-and-availability-properties"></a>Свойства состояния и доступности

Свойства **состояние** и **доступность** отключенного сеанса PSSession сообщают о том, доступен ли сеанс для повторного подключения.

Когда сеанс PSSession подключен к текущему сеансу, его состояние **открывается** , а доступность становится **доступной**. При отключении от PSSession состояние PSSession **отключается** , а его доступность — **нет**.

Значение свойства **State** определяется текущим сеансом. Значение **disconnected** означает, что сеанс PSSession не подключен к текущему сеансу. Но это не значит, что сеанс PSSession отключен от всех сеансов. Он может быть подключен к другому сеансу.

Чтобы определить, можно ли подключиться к сеансу PSSession или повторно подключиться к нему, используйте свойство **Availability** . Значение **None** означает, что можно подключиться к сеансу. Значение **занято** указывает, что невозможно подключиться к сеансу PSSession, так как он подключен к другому сеансу.

Следующий пример выполняется в двух сеансах PowerShell на одном компьютере.
Обратите внимание на изменение значений свойств **State** и **Availability** в каждом сеансе, так как сеанс PSSession отключен и повторно подключен.

```powershell
# Session 1
New-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30 -Name Test | Disconnect-PSSession
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Connect-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
3 Test    Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```Output
# Idle Timeout
```

Отключенные сеансы сохраняются на удаленном компьютере, пока вы не удалите их, например с помощью `Remove-PSSession` командлета, или истечет время ожидания. Свойство **IdleTimeout** параметра PSSession определяет время, в течение которого отключенный сеанс сохраняется до его удаления.

PSSession бездействует, когда **поток пульса** не получает ответа.
Отключение сеанса делает его неактивным и запускает часы **IdleTimeout** , даже если команды по-прежнему выполняются в отключенном сеансе. PowerShell считает, что отключенные сеансы активны, но в режиме простоя.

При создании и отключении сеансов убедитесь, что время ожидания простоя в PSSession достаточно велико для поддержания сеанса в соответствии с вашими потребностями, но не настолько долго, что он потребляет ненужные ресурсы на удаленном компьютере.

Свойство **идлетимеаутмс** конфигурации сеанса определяет время ожидания простоя по умолчанию для сеансов, использующих конфигурацию сеанса. Можно переопределить значение по умолчанию, но используемое значение не может превышать свойство **максидлетимеаутмс** конфигурации сеанса.

Чтобы найти значения **идлетимеаутмс** и **максидлетимеаутмс** для конфигурации сеанса, используйте следующий формат команды:

```powershell
Get-PSSessionConfiguration |
  Format-Table Name, IdleTimeoutMs, MaxIdleTimeoutMs
```

Можно переопределить значение по умолчанию в конфигурации сеанса и установить время ожидания сеанса PSSession в режиме простоя при создании сеанса PSSession и при отключении.

Если вы являетесь членом группы администраторов на удаленном компьютере, вы можете создавать и изменять свойства **идлетимеаутмс** и **максидлетимеаутмс** конфигураций сеансов.

## <a name="idle-timeout-values"></a>Значения времени ожидания простоя

Значение времени ожидания простоя конфигураций сеанса и параметров сеанса указано в миллисекундах. Значение времени ожидания простоя сеанса и параметры конфигурации сеанса находятся в секундах.

Можно задать время ожидания простоя сеанса PSSession при создании сеанса PSSession ( `New-PSSession` , `Invoke-Command` ) и при отключении от него ( `Disconnect-PSSession` ). Однако значение **IdleTimeout** нельзя изменить при соединении с PSSession ( `Connect-PSSession` ) или Get Results ( `Receive-PSSession` ).

`Connect-PSSession` `Receive-PSSession` Командлеты и имеют параметр **SessionOption** , принимающий объект **SessionOption** , например, возвращаемый `New-PSSessionOption` командлетом. Значение **IdleTimeout** в объекте **SessionOption** и значение **IdleTimeout** в `$PSSessionOption` привилегированной переменной не изменяют значение параметра **IdleTimeout** для PSSession в `Connect-PSSession` `Receive-PSSession` команде или.

Чтобы создать сеанс PSSession с определенным значением времени ожидания простоя, создайте `$PSSessionOption` переменную предпочтение. Задайте в качестве значения свойства **IdleTimeout** нужное значение (в миллисекундах).

При создании PSSession значения в `$PSSessionOption` переменной имеют приоритет над значениями в конфигурации сеанса.

Например, следующая команда устанавливает время ожидания простоя в 48 ч.:

```powershell
$PSSessionOption = New-PSSessionOption -IdleTimeoutMSec 172800000
```

Чтобы создать сеанс PSSession с определенным значением времени ожидания простоя, используйте параметр **идлетимеаутмсек** `New-PSSessionOption` командлета. Затем используйте параметр Session в значении параметра **SessionOption** `New-PSSession` `Invoke-Command` командлетов или.

Значения, заданные при создании сеанса, имеют приоритет над значениями, заданными в `$PSSessionOption` привилегированной переменной и конфигурации сеанса.

Пример:

```powershell
$o = New-PSSessionOption -IdleTimeoutMSec 172800000
New-PSSession -SessionOption $o
```

Чтобы изменить время ожидания простоя сеанса PSSession при отключении, используйте параметр **идлетимеаутсек** `Disconnect-PSSession` командлета.

Пример:

```powershell
Disconnect-PSSession -IdleTimeoutSec 172800
```

Чтобы создать конфигурацию сеанса с определенным временем ожидания простоя и максимальным временем ожидания простоя, используйте параметры **идлетимеаутсек** и **максидлетимеаутсек** `New-PSTransportOption` командлета. Затем используйте параметр Transport в значении параметра **транспортоптион** в параметре `Register-PSSessionConfiguration` .

Пример:

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

Чтобы изменить время ожидания простоя по умолчанию и максимальное время ожидания простоя для конфигурации сеанса, используйте параметры **идлетимеаутсек** и **максидлетимеаутсек** `New-PSTransportOption` командлета. Затем используйте параметр Transport в значении параметра **транспортоптион** в параметре `Set-PSSessionConfiguration` .

Пример:

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="output-buffering-mode"></a>Режим буферизации вывода

Режим буферизации вывода сеанса PSSession определяет управление выводом команд, когда выходной буфер сеанса PSSession заполнен.

В отключенном сеансе режим буферизации вывода фактически определяет, будет ли команда продолжать выполняться, пока сеанс отключен.

Допустимы следующие значения:

- **Заблокировать**. при заполнении выходного буфера выполнение команды приостанавливается до тех пор, пока буфер не будет очищен. Значение по умолчанию.
- **Удалить**. при заполнении выходного буфера выполнение команды продолжается. При формировании новых выходных данных самые старые выходные данные удаляются.

**Блок** сохраняет данные, но может прерывать выполнение команды. Значение **Drop** позволяет завершить выполнение команды, несмотря на возможную потерю данных. При использовании значения **Drop** выходные данные команды необходимо перенаправить в какой-либо файл на диске. Это значение рекомендуется для отключенных сеансов.

Свойство **аутпутбуфферингмоде** конфигурации сеанса определяет режим буферизации вывода по умолчанию для сеансов, использующих конфигурацию сеанса.

Чтобы найти значение конфигурации сеанса **аутпутбуфферингмоде** , можно использовать любой из следующих форматов команд:

```powershell
(Get-PSSessionConfiguration <ConfigurationName>).OutputBufferingMode
```

```powershell
Get-PSSessionConfiguration | Format-Table Name, OutputBufferingMode
```

Можно переопределить значение по умолчанию в конфигурации сеанса и установить режим буферизации вывода сеанса PSSession при создании PSSession, при отключении и при повторном подключении.

Если вы являетесь членом группы "Администраторы" на удаленном компьютере, вы можете создать и изменить режим буферизации вывода конфигураций сеанса.

Чтобы создать сеанс PSSession с режимом буферизации **вывода, создайте** `$PSSessionOption` переменную предпочтение, в которой значение свойства **аутпутбуфферингмоде** равно **Drop**.

При создании PSSession значения в `$PSSessionOption` переменной имеют приоритет над значениями в конфигурации сеанса.

Пример:

```powershell
$PSSessionOption = New-PSSessionOption -OutputBufferingMode Drop
```

Чтобы создать сеанс PSSession с режимом буферизации **вывода, используйте** параметр **аутпутбуфферингмоде** `New-PSSessionOption` командлета, чтобы создать параметр сеанса со значением **Drop**. Затем используйте параметр Session в значении параметра **SessionOption** `New-PSSession` `Invoke-Command` командлетов или.

Значения, заданные при создании сеанса, имеют приоритет над значениями, заданными в `$PSSessionOption` привилегированной переменной и конфигурации сеанса.

Пример:

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
New-PSSession -SessionOption $o
```

Чтобы изменить режим буферизации вывода сеанса PSSession при отключении, используйте параметр **аутпутбуфферингмоде** `Disconnect-PSSession` командлета.

Пример:

```powershell
Disconnect-PSSession -OutputBufferingMode Drop
```

Чтобы изменить режим буферизации вывода PSSession при повторном подключении, используйте параметр **аутпутбуфферингмоде** `New-PSSessionOption` командлета, чтобы создать параметр сеанса со значением **Drop**. Затем используйте параметр Session в значении параметра **SessionOption** в параметре `Connect-PSSession` или `Receive-PSSession` .

Пример:

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
Connect-PSSession -ComputerName Server01 -Name Test -SessionOption $o
```

Чтобы создать конфигурацию сеанса с режимом буферизации вывода по умолчанию **, используйте** параметр **аутпутбуфферингмоде** `New-PSTransportOption` командлета, чтобы создать объект параметра транспорта со значением **Drop**. Затем используйте параметр Transport в значении параметра **транспортоптион** в параметре `Register-PSSessionConfiguration` .

Пример:

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

Чтобы изменить режим буферизации вывода по умолчанию в конфигурации сеанса, используйте параметр **аутпутбуфферингмоде** `New-PSTransportOption` командлета, чтобы создать параметр транспорта со значением **Drop**. Затем используйте параметр Transport в значении параметра **SessionOption** в параметре `Set-PSSessionConfiguration` .

Пример:

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="disconnecting-loopback-sessions"></a>Отключение замыканий на себя сеансов

Сеансы замыкания на себя или локальные сеансы являются PSSession, которые происходят и завершаются на одном и том же компьютере. Как и другие PSSession, активные сеансы замыкания на себя сохраняются на компьютере на удаленном конце подключения (локальный компьютер), поэтому можно отключиться от и повторно подключиться к сеансам замыкания на себя.

По умолчанию, сеансы замыкания на себя создаются с маркером безопасности сети, который не позволяет выполнять команды в сеансе для доступа к другим компьютерам. Вы можете повторно подключиться к сеансам замыкания на себя с маркером безопасности сети из любого сеанса на локальном или удаленном компьютере.

Однако если используется параметр **EnableNetworkAccess** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлета, или, то сеанс замыкания на себя создается с помощью интерактивного маркера безопасности. Интерактивный токен позволяет командам, выполняемым в сеансе замыкания на себя, получать данные с других компьютеров.

Вы можете отключить сеансы замыкания на себя с помощью интерактивных маркеров, а затем повторно подключиться к ним из того же сеанса или другого сеанса на том же компьютере.
Однако, чтобы предотвратить вредоносный доступ, можно повторно подключиться к сеансам замыкания на себя с помощью интерактивных маркеров только с того компьютера, на котором они были созданы.

## <a name="waiting-for-jobs-in-disconnected-sessions"></a>Ожидание заданий в отключенных сеансах

`Wait-Job`Командлет ожидает завершения задания, а затем возвращает его в командную строку или следующую команду. По умолчанию `Wait-Job` возвращает значение, если сеанс, в котором выполняется задание, отключен. Чтобы направить `Wait-Job` командлет в ожидание повторного подключения сеанса, в **открытом** состоянии используйте параметр **Force** . Дополнительные сведения см. в разделе [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).

## <a name="robust-sessions-and-unintentional-disconnection"></a>Устойчивые сеансы и непреднамеренное отключение

Сеанс PSSession может быть непреднамеренно отключен из-за сбоя компьютера или отключения сети. PowerShell пытается восстановить PSSession, но его успешность зависит от серьезности и длительности причины.

Состояние непреднамеренного разъединения PSSession может быть **разорвано** или **закрыто** , но оно также может быть **отключено**. Если значение **State** равно **disconnected** , то для управления сеансом PSSession можно использовать те же методы, что и при намеренном отключении сеанса. Например, можно использовать `Connect-PSSession` командлет для повторного подключения к сеансу и `Receive-PSSession` командлет для получения результатов команд, которые выполнялись во время отключения сеанса.

При закрытии (выходе) сеанса, в котором был создан PSSession во время выполнения команд в сеансе PSSession, PowerShell обслуживает сеанс PSSession в состоянии **disconnected (отключено** ) на удаленном компьютере. При закрытии (выходе) сеанса, в котором был создан PSSession, но в сеансе PSSession не выполняется ни одной команды, PowerShell не пытается сохранить PSSession.

## <a name="see-also"></a>См. также статью

[about_Jobs](about_Jobs.md)

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[about_PSSessions](about_PSSessions.md)

[about_Session_Configurations](about_Session_Configurations.md)

[Connect-PSSession](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[Disconnect-PSSession](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[Get-PSSession](xref:Microsoft.PowerShell.Core.Get-PSSession)

[Receive-PSSession](xref:Microsoft.PowerShell.Core.Receive-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
