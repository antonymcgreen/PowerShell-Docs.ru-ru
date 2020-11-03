---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: 7694154c4724bef35aeb1ccdc46aee6a1875cf57
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229777"
---
# Disconnect-PSSession

## Краткий обзор
Отключает от сеанса.

## SYNTAX

### Сеанс (значение по умолчанию)

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### name

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Идентификатор

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Disconnect-PSSession`Командлет отключает сеанс PowerShell (PSSession), например, запущенный с помощью `New-PSSession` командлета, из текущего сеанса. В результате PSSession переходит в отключенное состояние. К отключенному сеансу PSSession можно подключиться из текущего или другого сеанса на локальном или другом компьютере.

`Disconnect-PSSession`Командлет отключает только открытые PSSession, подключенные к текущему сеансу. `Disconnect-PSSession` не удается отключить разорванные или закрытые PSSession или интерактивный PSSession, запущенный с помощью `Enter-PSSession` командлета, и он не может отключить PSSession, подключенные к другим сеансам.

Чтобы повторно подключиться к отключенному сеансу PSSession, `Connect-PSSession` Используйте `Receive-PSSession` командлеты или.

При отключении PSSession, запущенные в этом сеансе команды выполняются до завершения или до окончания времени ожидания сеанса PSSession либо блокируются полным выходным буфером. Чтобы изменить время ожидания простоя, используйте параметр **IdleTimeoutSec**. Чтобы изменить режим буферизации вывода, используйте параметр **аутпутбуфферингмоде** . также можно использовать параметр **InDisconnectedSession** `Invoke-Command` командлета для выполнения команды в отключенном сеансе.

Дополнительные сведения о функции отключенных сеансов см. в разделе [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Отключение сеанса по имени

Эта команда отключает сеанс UpdateSession на компьютере Server01 от текущего сеанса. Для идентификации сеанса PSSession в команде используется параметр **Name**.

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

Выходные данные показывают, что попытка отключения оказалась успешной. Сеанс перешел в состояние Disconnected, а свойство Availability получило значение None — это значит, что сеанс не занят и к нему можно подключиться повторно.

### Пример 2. Отключение сеанса от определенного компьютера

Эта команда отключает сеанс ITTask на компьютере Server12 от текущего сеанса.
Сеанс ITTask был создан в текущем сеансе и подключен к компьютеру Server12. Команда использует `Get-PSSession` командлет для получения сеанса и `Disconnect-PSSession` командлет для его отключения.

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

`Disconnect-PSSession`Команда использует параметр **аутпутбуфферингмоде** , чтобы установить режим вывода для **удаления**. Это гарантирует, что выполнения скрипта, запущенного в данном сеансе, будет продолжено, даже если выходной буфер сеанса заполнен. Поскольку скрипт записывает выходные данные в отчет, находящийся в общей папке, другие выходные данные могут быть потеряны без последствий.

Кроме того, команда включает параметр **IdleTimeoutSec** , увеличивающий время ожидания простоя сеанса до 24 часов. Это позволит данному или другим администраторам восстановить подключение к сеансу, убедиться, что скрипт был выполнен, и устранить неполадки, если потребуется.

### Пример 3. Использование нескольких PSSession на нескольких компьютерах

Эта серия команд показывает, как `Disconnect-PSSession` можно использовать командлет в корпоративном сценарии. В данном случае новый специалист запускает скрипт в сеансе на удаленном компьютере и сталкивается с проблемой. Специалист отключается от сеанса, чтобы более опытный менеджер смогу подключиться к сеансу и устранить проблему.

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

Для начала специалист создает сеансы на нескольких удаленных компьютерах и запускает скрипт в каждом из этих сеансов. Первая команда использует `New-PSSession` командлет для создания сеанса иттаск на трех удаленных компьютерах. Сеансы сохраняются в переменную $s. Вторая команда использует параметр **FilePath** `Invoke-Command` командлета для выполнения скрипта в сеансах в переменной $s.

Скрипт, запущенный на компьютере Srv1, вызывает непредвиденные ошибки. Специалист обращается за помощью к менеджеру. Руководитель направляет специалисту отключиться от сеанса, чтобы он мог исследовать его. Вторая команда использует `Get-PSSession` командлет для получения сеанса иттаск на компьютере Srv1 и `Disconnect-PSSession` командлет для его отключения. Эта команда не влияет на сеансы Иттаск на других компьютерах.

Третья команда использует `Get-PSSession` командлет для получения сеансов иттаск. Выходные данные показывают, что команда отключения не повлияла на сеансы ITTask, созданные на компьютерах Srv2 и Srv30.

Диспетчер выполняет вход на свой домашний компьютер, подключается к корпоративной сети, запускает Windows PowerShell и использует `Get-PSSession` командлет для получения сеанса иттаск на компьютере Srv1. Для доступа к сеансу он использует учетные данные специалиста.

Затем диспетчер использует `Connect-PSSession` командлет для подключения к сеансу иттаск на компьютере Srv1. Сеанс сохраняется в переменную $s.

Диспетчер использует `Invoke-Command` командлет для выполнения некоторых диагностических команд в сеансе в `$s` переменной. Он понимает, что скрипт не выполняется, так как не может найти необходимый каталог.
Диспетчер использует `MkDir` функцию для создания каталога, а затем перезапускает `Get-PatchStatus.ps1` сценарий и отключает его от сеанса. Руководитель сообщает о своих возможностях, предлагая, что он повторно подключится к сеансу для выполнения задач, и попросит добавить в `Get-PatchStatus.ps1` сценарий команду, которая создает требуемый каталог, если он не существует.

### Пример 4. изменение значения времени ожидания для PSSession

В этом примере показано, как скорректировать значение свойства **IdleTimeout** сеанса таким образом, чтобы сеанс можно было отключить.

Свойство времени ожидания простоя имеет важное значение для отключенных сеансов, поскольку определяет, как долго отключенный сеанс будет храниться до удаления. Время ожидания простоя можно настроить при создании сеанса, а также при отключении. Значения по умолчанию для времени ожидания простоя сеанса задаются в `$PSSessionOption` переменной предпочтений на локальном компьютере и в конфигурации сеанса на удаленном компьютере. Значения, установленные для сеанса, превалируют над значениями, установленными в конфигурации сеанса, но не могут превышать квоты, предусмотренные конфигурацией сеанса, например, значением **MaxIdleTimeoutMs**.

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

Первая команда использует `New-PSSessionOption` командлет для создания объекта параметра сеанса. Она включает параметр **IdleTimeout** , определяющий время ожидания простоя, равное 48 часам (172 800 000 миллисекундам). Объект параметров сеанса сохраняется в переменную $Timeout .

Вторая команда использует `New-PSSession` командлет для создания сеанса иттаск на компьютере Server01. Сеанс сохраняется в переменную $s. Параметр **SessionOption** получает значение 48 часов в соответствии со временем ожидания простоя, указанным в переменной $Timeout.

Третья команда отключает сеанс ITTask из переменной $s. Команда завершается ошибкой, так как превышает квоту **MaxIdleTimeoutMs** для времени ожидания простоя, указанную в конфигурации сеанса. Поскольку значение времени ожидания простоя не используется, пока сеанс не будет отключен, это нарушение может оставаться незамеченными, пока сеанс еще используется.

Четвертая команда использует `Invoke-Command` командлет для выполнения `Get-PSSessionConfiguration` команды для конфигурации сеанса Microsoft. PowerShell на компьютере Server01. Команда использует `Format-List` командлет для вывода всех свойств конфигурации сеанса в списке. Выходные данные показывают, что свойство **максидлетимеаутмс** , устанавливающее максимально допустимое значение **IdleTimeout** для сеансов, использующих конфигурацию сеанса, составляет 43200000 миллисекунд (12 часов).

Пятая команда возвращает значения параметров для сеанса, сохраненного в переменную $s. Значения многих параметров сеанса являются свойствами свойства **ConnectionInfo** свойства **пространства выполнения** сеанса. Выходные данные показывают, что значение свойства **IdleTimeout** сеанса составляет 172800000 миллисекунд (48 часа), что нарушает квоту **максидлетимеаутмс** в 12 часов в конфигурации сеанса. Чтобы устранить этот конфликт, можно использовать параметр **configurationName** , чтобы выбрать другую конфигурацию сеанса или использовать параметр **IdleTimeout** для сокращения времени ожидания простоя сеанса.

Шестая команда отключает сеанс. С помощью параметра **IdleTimeoutSec** она устанавливает время ожидания простоя, равное 12 часовому максимуму.

Седьмая команда получает значение свойства **IdleTimeout** отключенного сеанса, которое измеряется в миллисекундах. Выходные данные подтверждают, что команда выполнена успешно.

## PARAMETERS

### -Id

Отключается от сеансов с указанным идентификатором сеанса. Введите один или несколько идентификаторов (разделенные запятыми) или укажите диапазон идентификаторов, используя соответствующий оператор (.).

Чтобы получить идентификатор сеанса, используйте `Get-PSSession` командлет. Идентификатор экземпляра хранится в свойстве **ID** сеанса.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Идлетимеаутсек

Изменяет значение времени ожидания простоя для отключенного сеанса PSSession. Введите значение в секундах. Минимальное значение — 60 секунд (1 минута).

Время ожидания простоя определяет, как долго отключенный сеанс PSSession будет храниться на удаленном компьютере. По истечении времени ожидания сеанс PSSession будет удален.

Время простоя отключенных сеансов PSSession отсчитывается с момента их отключения, даже если в отключенном сеансе выполняются команды.

Время ожидания простоя сеанса по умолчанию определяется значением свойства **IdleTimeoutMs** конфигурации сеанса. Значение по умолчанию составляет 7200000 миллисекунд (2 часа).

Значение этого параметра превалирует над значением свойства **IdleTimeout** привилегированной переменной $PSSessionOption и значением времени ожидания простоя по умолчанию, предусмотренным конфигурацией сеанса. Тем не менее, это значение не может превышать значение свойства **MaxIdleTimeoutMs** конфигурации сеанса. Значение свойства **MaxIdleTimeoutMs** по умолчанию составляет 12 часов (43200000 миллисекунд).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Отключается от сеансов с указанными идентификаторами экземпляров.

Идентификатор экземпляра — это GUID, однозначно определяющий сеанс на локальном или удаленном компьютере. Идентификатор экземпляра уникален даже для нескольких сеансов на различных компьютерах.

Чтобы получить идентификатор экземпляра сеанса, используйте `Get-PSSession` командлет. Идентификатор экземпляра хранится в свойстве **InstanceId** сеанса.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Отключается от сеансов с указанными понятными именами. Разрешено использовать подстановочные знаки.

Чтобы получить понятное имя сеанса, используйте `Get-PSSession` командлет. Понятное имя хранится в свойстве **Name** сеанса.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Session

Отключается от указанных сеансов PSSession. Введите объекты PSSession, например те, которые `New-PSSession` возвращает командлет. Объект PSSession также можно передать в `Disconnect-PSSession` .

`Get-PSSession`Командлет может получить все PSSession, которые завершаются на удаленном компьютере, включая PSSession, которые отключены и PSSession, подключенные к другим сеансам на других компьютерах. `Disconnect-PSSession` отключает только сеанс PSSession, подключенный к текущему сеансу. Если передать другие PSSession в `Disconnect-PSSession` , `Disconnect-PSSession` команда завершится ошибкой.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit

Задает ограничение регулирования для `Disconnect-PSSession` команды.

Предел регулирования — это максимальное количество одновременных подключений, которые могут быть установлены для выполнения этой команды. Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.

Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Аутпутбуфферингмоде

Определяет порядок управления выходным потоком команды в отключенном сеансе при заполнении . Значение по умолчанию — **Block**.

Если команда в отключенном сеансе возвращает данные и заполняет выходной буфер, значение этого параметра определяет, продолжится ли выполнение этой команды в отключенном сеансе. Значение **Block** приостанавливает команду до повторного подключения к сеансу. Значение **Drop** позволяет завершить выполнение команды, несмотря на возможную потерю данных. При использовании значения **Drop** выходные данные команды необходимо перенаправить в какой-либо файл на диске.

Допустимые значения:

- **Блокировать** : когда выходной буфер полон, выполнение приостанавливается до тех пор, пока буфер не будет очищен.
- **Drop** : когда выходной буфер полон, выполнение продолжится. Новые выходные данные сохраняются вместо наиболее старых.
- **Нет** : режим буферизации вывода не указан. Значение свойства **OutputBufferingMode** конфигурации сеанса используется для отключенного сеанса.

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).

## Входные данные

### System.Management.Automation.Runspaces.PSSession

Можно передать сеанс в `Disconnect-PSSession` .

## Выходные данные

### System.Management.Automation.Runspaces.PSSession

`Disconnect-PSSession` Возвращает объект, представляющий сеанс, который он отключил.

## ПРИМЕЧАНИЯ

- `Disconnect-PSSession`Командлет работает, только если на локальном и удаленном компьютерах работает PowerShell 3,0 или более поздней версии.
- При использовании `Disconnect-PSSession` командлета в отключенном сеансе команда не оказывает влияния на сеанс и не создает ошибок.
- Повторно подключиться к отключенному сеансу замыкания на себя с интерактивным маркером безопасности, созданным с помощью параметра **EnableNetworkAccess** , можно только с компьютера, на котором этот сеанс был создан. Это ограничение защищает компьютер от вредоносного доступа.
- Отключенный сеанс PSSession переходит в состояние **Disconnected** и получает доступность **None**.

  Значение свойства **State** определяется текущим сеансом. Таким образом, значение **Disconnected** показывает, что сеанс PSSession не подключен к текущему сеансу. При этом оно не означает, что сеанс PSSession отключен от всех сеансов. Он может быть подключен к другому сеансу. Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability**.

  Если свойство **Availability** имеет значение **None** , подключиться к сеансу можно. Значение **Busy** показывает, что подключиться сеансу к PSSession нельзя, так как он подключен к другому сеансу.

  Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).

  Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## Связанные ссылки

[Connect-PSSession](Connect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession;](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)

[about_Remote_Disconnected_Sessions](About/about_Remote_Disconnected_Sessions.md)
