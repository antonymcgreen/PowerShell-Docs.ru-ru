---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pstransportoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSTransportOption
ms.openlocfilehash: 9257c0a1829cc9cc85029f7c6fdc8e61b0ed7e56
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229749"
---
# New-PSTransportOption

## Краткий обзор

Создает объект, содержащий дополнительные параметры для конфигурации сеанса.

## SYNTAX

```
New-PSTransportOption [-MaxIdleTimeoutSec <Int32>] [-ProcessIdleTimeoutSec <Int32>] [-MaxSessions <Int32>]
 [-MaxConcurrentCommandsPerSession <Int32>] [-MaxSessionsPerUser <Int32>] [-MaxMemoryPerSessionMB <Int32>]
 [-MaxProcessesPerSession <Int32>] [-MaxConcurrentUsers <Int32>] [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **New-PSTransportOption** создает объект, содержащий параметры транспорта для конфигураций сеансов.
Объект можно использовать в качестве значения параметра *транспортоптион* командлетов, которые создают или изменяют конфигурацию сеанса, например командлеты Register-PSSessionConfiguration и Set-PSSessionConfiguration.

Кроме того, параметры транспорта можно менять, корректируя значения свойств конфигурации сеанса на диске WSMan:.
Дополнительные сведения см. в разделе Поставщик WSMan.

Параметры конфигурации сеанса представляют значения сеанса, заданные на стороне сервера или при получении конца удаленного соединения.
На стороне клиента или при отправке соединения можно задавать значения параметров сеанса при создании сеанса, а также при отключении или повторном подключении клиента к сеансу.
Если не указано иное, то в случае конфликта между значениями параметров превалируют значения на стороне клиента.
При этом значения на стороне клиента не могут превышать максимальные значения и квоты, установленные в конфигурации сеанса.

Без параметров командлет **New-пстранспортоптион** создает объект параметра транспорта, который имеет значения NULL для всех параметров.
Если параметр не указан, свойство объекта, представляемое этим параметром, получает нулевое значение.
Значение NULL не влияет на конфигурацию сеанса.

Дополнительные сведения о параметрах сеанса см. в разделе New-PSSessionOption.
Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Создание параметра транспорта по умолчанию

```
PS C:\> New-PSTransportOption
ProcessIdleTimeoutSec           :
MaxIdleTimeoutSec               :
MaxSessions                     :
MaxConcurrentCommandsPerSession :
MaxSessionsPerUser              :
MaxMemoryPerSessionMB           :
MaxProcessesPerSession          :
MaxConcurrentUsers              :
IdleTimeoutSec                  :
OutputBufferingMode             :
```

Эта команда выполняет команду **New-пстранспортоптион** без параметров.
Выходные данные показывают, что командлет создает объект параметра транспорта, который имеет значения NULL для всех свойств.

### Пример 2. получение параметров конфигурации сеанса

```
The first command uses the **New-PSTransportOption** cmdlet to create a transport options object, which it saves in the $t variable. The command uses the *MaxSessions* parameter to increase the maximum number of sessions to 40.
PS C:\> $t = New-PSTransportOption -MaxSessions 40

The second command uses the **Register-PSSessionConfiguration** cmdlet create the ITTasks session configuration. The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.
PS C:\> Register-PSSessionConfiguration -Name ITTasks -TransportOption $t

The third command uses the Get-PSSessionConfiguration cmdlet to get the ITTasks session configurations and the Format-List cmdlet to display all of the properties of the session configuration object in a list. The output shows that the value of the **MaxShells** property of the session configuration is 40.
PS C:\> Get-PSSessionConfiguration -Name ITTasks | Format-List -Property *
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITTasks
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
MaxShells                     : 40
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 2
Name                          : ITTasks
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
Enabled                       : True
MaxShellsPerUser              : 25
Permission                    :
```

В этом примере показано, как использовать объект параметров транспорта для задания параметров конфигурации сеанса.

### Пример 3. Настройка параметра транспорта

```
The first command uses the **New-PSTransportOption** cmdlet to create a transport option object. The command uses the *IdleTimeoutSec* parameter to set the **IdleTimeoutSec** property value of the object to one hour (3600 seconds). The command saves the transport objects object in the $t variable.
PS C:\> $t = New-PSTransportOption -IdleTimeoutSec 3600

The second command uses the Set-PSSessionConfiguration cmdlet to change the transport options of the ITTasks session configuration. The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.
PS C:\> Set-PSSessionConfiguration -Name ITTasks -TransportOption $t

The third command uses the New-PSSession cmdlet to create the MyITTasks session on the local computer. The command uses the **ConfigurationName** property to specify the ITTasks session configuration. The command saves the session in the $s variable.Notice that the command does not use the *SessionOption* parameter of **New-PSSession** to set a custom idle time-out for the session. If it did, the idle time-out value set in the session option would take precedence over the idle time-out set in the session configuration.
PS C:\> $s = New-PSSession -Name MyITTasks -ConfigurationName ITTasks

The fourth command uses the Format-List cmdlet to display all properties of the session in the $s variable in a list. The output shows that the session has an idle time-out of one hour (360,000 milliseconds).
PS C:\> $s | Format-List -Property *
State                  : Opened
IdleTimeout            : 3600000
OutputBufferingMode    : Block
ComputerName           : localhost
ConfigurationName      : ITTasks
InstanceId             : 4110c3f5-68ea-40fa-9bbf-04a433dbb02d
Id                     : 1
Name                   : MyITTasks
Availability           : Available
ApplicationPrivateData : {PSVersionTable}
Runspace               : System.Management.Automation.RemoteRunspace
```

Эта команда показывает, как настройка параметра транспорта в конфигурации сеанса влияет на сеансы, в которых используется эта конфигурация.

## PARAMETERS

### -Идлетимеаутсек

Определяет, как долго каждый сеанс остается открытым, если удаленный компьютер не получает никаких сообщений от локального компьютера.
Сюда входит сигнал пульса.
По истечении этого времени сеанс закрывается.

Значение времени ожидания простоя имеет значительную важность, когда пользователь намеревается отключиться и повторно подключиться к сеансу.
Пользователь может подключаться к сеансу только в том случае, если время ожидания не истекло.

Параметр *IdleTimeoutSec* соответствует свойству **IdleTimeoutMs** в конфигурации сеанса.

Введите значение в секундах.
Значение по умолчанию составляет 7200 секунд (2 часа).
Минимальное значение — 60 секунд (1 минута).
Максимальное значение является значением свойства **IdleTimeout** объектов оболочки в конфигурации WSMan ( `WSMan:\\\<ComputerName\>\Shell\IdleTimeout` ).
Значение по умолчанию составляет 7200000 миллисекунд (2 часа).

Если значение времени ожидания простоя задано в параметрах сеанса и в конфигурации сеанса, приоритет имеет значение, заданное в параметрах сеанса, но не может превышать значение свойства **максидлетимеаутмс** конфигурации сеанса.
Для установки значения свойства **MaxIdleTimeoutMs** используется параметр *MaxIdleTimeoutSec*.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Максконкурренткоммандсперсессион

Ограничивает количество команд, которые могут выполняться одновременно в каждом сеансе, с указанным значением.
Значение по умолчанию ― 1000.

Параметр *максконкурренткоммандсперсессион* соответствует свойству **максконкурренткоммандспершелл** конфигурации сеанса.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Максконкуррентусерс

Ограничивает число пользователей, которые могут одновременно выполнять команды в каждом сеансе с указанным значением.
Значение по умолчанию — 5.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Максидлетимеаутсек

Ограничивает время ожидания простоя, установленное для каждого сеанса, на указанное значение.
Значение по умолчанию — \[ int \] :: MaxValue (~ 25 дней).

Значение времени ожидания простоя имеет значительную важность, когда пользователь намеревается отключиться и повторно подключиться к сеансу.
Пользователь может подключаться к сеансу только в том случае, если время ожидания не истекло.

Параметр *максидлетимеаутсек* соответствует свойству **максидлетимеаутмс** конфигурации сеанса.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Максмемориперсессионмб

Ограничивает максимальный объем памяти, который может использоваться каждым сеансом.
Введите значение в мегабайтах.
Значение по умолчанию — 1024 МБ (1 ГБ).

Параметр *максмемориперсессионмб* соответствует свойству **максмеморипершеллмб** конфигурации сеанса.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Макспроцессесперсессион

Устанавливает максимальное количество процессов, которые могут выполняться в одном сеансе.
Значение по умолчанию — 15.

Параметр *макспроцессесперсессион* соответствует свойству **макспроцессеспершелл** конфигурации сеанса.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Макссессионс

Ограничивает количество сеансов, которые могут использовать соответствующую конфигурацию.
По умолчанию используется значение 25.

Параметр *макссессионс* соответствует свойству **максшеллс** конфигурации сеанса.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Макссессионсперусер

Ограничивает максимальное количество сеансов с использованием соответствующей конфигурации и учетных данных указанного пользователя.
По умолчанию используется значение 25.

При указании этого значения следует учесть, что многие пользователи могут использовать учетные данные пользователя запуска от имени.

Параметр *макссессионсперусер* соответствует свойству **максшеллсперусер** конфигурации сеанса.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Аутпутбуфферингмоде

Определяет порядок управления выходным потоком команды в отключенных сеансах при заполнении .
Допустимые значения для этого параметра:

- Блокировка.
при заполнении выходного буфера выполнение команды приостанавливается до тех пор, пока буфер не будет очищен.
- Drop.
при заполнении выходного буфера выполнение команды продолжается.
Новые выходные данные сохраняются вместо наиболее старых.
- Отсутствует.
порядок действий в случае переполнения выходного буфера не установлен.

Значение свойства **аутпутбуфферингмоде** в сеансах по умолчанию — Block.

```yaml
Type: System.Nullable`1[System.Management.Automation.Runspaces.OutputBufferingMode]
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Процессидлетимеаутсек

Ограничивает время ожидания для каждого хост-процесса указанным значением.
Значение по умолчанию 0 означает отсутствие значения времени ожидания для процесса.

Другие конфигурации сеанса имеют значения времени ожидания для каждого процесса.
Например, конфигурация сеанса **Microsoft. PowerShell. Workflow** имеет значение времени ожидания для каждого процесса, равное 28800 секундам (8 часов).

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Microsoft. PowerShell. Commands. Всманконфигуратионоптион

## ПРИМЕЧАНИЯ

- Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров. Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.

## Связанные ссылки

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)
