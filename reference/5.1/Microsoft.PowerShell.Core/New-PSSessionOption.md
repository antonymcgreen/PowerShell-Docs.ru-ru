---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: 4f46aec8b22814ca95280380433787c6b41953ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226642"
---
# New-PSSessionOption

## Краткий обзор
Создает объект, содержащий дополнительные параметры для сеанса PSSession.

## SYNTAX

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## DESCRIPTION

`New-PSSessionOption`Командлет создает объект, содержащий дополнительные параметры для управляемого пользователем сеанса ( **PSSession** ). Объект можно использовать в качестве значения параметра **SessionOption** командлетов, которые создают **сеанс PSSession** , например `New-PSSession` , `Enter-PSSession` и `Invoke-Command` .

Без параметров `New-PSSessionOption` создает объект, содержащий значения по умолчанию для всех параметров. Поскольку все свойства доступны для изменения, вы можете использовать итоговый объект в качестве шаблона и создавать стандартные объекты параметров для своей организации.

Объект параметра сеанса также можно сохранить в `$PSSessionOption` переменной предпочтений. Значения этой переменной устанавливают новые значения по умолчанию для параметров сеанса. Они действительны, если для сеанса не задано никаких параметров, и имеют приоритет над параметрами, заданными в конфигурации сеанса, однако их можно переопределить, указав параметры сеанса или объект параметров сеанса в командлете, создающем сеанс. Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

При использовании объекта параметров сеанса в командлете, создающем сеанс, значения параметров сеанса имеют приоритет над значениями по умолчанию, заданными в привилегированной переменной $PSSessionOption и в конфигурации сеанса. Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса. Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

## Примеры

### Пример 1. Создание параметра сеанса по умолчанию

Эта команда создает объект параметра сеанса со всеми значениями по умолчанию.

```powershell
New-PSSessionOption
```

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

### Пример 2. Настройка сеанса с помощью объекта параметров сеанса

В этом примере показано, как использовать объект параметров сеанса для настройки сеанса.

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

Первая команда создает новый объект параметра сеанса и сохраняет его в значении `$pso` переменной. Вторая команда использует `New-PSSession` командлет для создания сеанса на удаленном компьютере Server01. Команда использует объект параметра сеанса в значении `$pso` переменной в качестве значения параметра **SessionOption** команды.

### Пример 3. Запуск интерактивного сеанса

Эта команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с компьютером Server01.

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

Значение параметра **SessionOption** — это `New-PSSessionOption` команда, которая имеет параметры WITH **ENCRYPTION** и **Compression** .

`New-PSSessionOption`Команда заключается в круглые скобки, чтобы убедиться, что она выполняется перед `Enter-PSSession` командой.

### Пример 4. изменение объекта параметров сеанса

В этом примере показано, как можно изменить объект параметра сеанса. Все свойства имеют значения для чтения и записи.

```powershell
$a = New-PSSessionOption
$a.OpenTimeout
```

```Output
Days              : 0
Hours             : 0
Minutes           : 3
Seconds           : 0
Milliseconds      : 0
Ticks             : 1800000000
TotalDays         : 0.00208333333333333
TotalHours        : 0.05
TotalMinutes      : 3
TotalSeconds      : 180
TotalMilliseconds : 180000
```

```powershell
$a.UICulture = (Get-UICulture)
$a.OpenTimeout = (New-Timespan -Minutes 4)
$a.MaximumConnectionRedirectionCount = 1
$a
```

```Output
MaximumConnectionRedirectionCount : 1
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         : en-US
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:04:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

Используйте этот метод для создания стандартного объекта сеанса в своей организации, а затем настраивайте отдельные его версии для определенных целей.

### Пример 5. Создание привилегированной переменной

Эта команда создает `$PSSessionOption` переменную предпочтений.

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

Когда `$PSSessionOption` в сеансе происходит переменная предпочтений, она устанавливает значения по умолчанию для параметров в сеансах, созданных с помощью `New-PSSession` `Enter-PSSession` командлетов, и `Invoke-Command` .

Чтобы сделать `$PSSessionOption` переменную доступной во всех сеансах, добавьте ее в сеанс PowerShell и в профиль PowerShell.

Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).
Дополнительные сведения о профилях см. в разделе [about_Profiles](About/about_Profiles.md).

### Пример 6. соблюдение требований к конфигурации удаленного сеанса

В этом примере показано, как использовать объект **SessionOption** для удовлетворения требований, предъявляемых к конфигурации удаленного сеанса.

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

Первая команда использует `New-PSSessionOption` командлет для создания объекта параметра сеанса со свойством **SkipCNCheck** . Команда сохраняет результирующий объект сеанса в `$skipCN` переменной.

Вторая команда использует `New-PSSession` командлет для создания нового сеанса на удаленном компьютере. `$skipCN`Переменная Check используется в значении параметра **SessionOption** .

Так как компьютер идентифицируется по его IP-адресу, значение параметра **ComputerName** не соответствует ни одному из общих имен в сертификате, используемом для SSL (SSL). По этой причине параметр **SkipCNCheck** является обязательным.

### Пример 7. предоставление доступа к аргументам в удаленном сеансе

В этом примере показано, как использовать параметр **аппликатионаргументс** `New-PSSessionOption` командлета, чтобы сделать дополнительные данные доступными для удаленного сеанса.

```powershell
$team = @{Team="IT"; Use="Testing"}
$TeamOption = New-PSSessionOption -ApplicationArguments $team
$s = New-PSSession -ComputerName Server01 -SessionOption $TeamOption
Invoke-Command -Session $s {$PSSenderInfo.ApplicationArguments}
```

```Output
Name                 Value
----                 -----
Team                 IT
Use                  Testing
PSVersionTable       {CLRVersion, BuildVersion, PSVersion, WSManStackVersion...}
```

```powershell
Invoke-Command -Session $s {
  if ($PSSenderInfo.ApplicationArguments.Use -ne "Testing") {
    .\logFiles.ps1
  }
  else {
    "Just testing."
  }
}
```

```Output
Just testing.
```

Первая команда создает хэш-таблицу с двумя ключами, **группой** и **использованием**. Команда сохраняет хэш-таблицу в `$team` переменной. Дополнительные сведения о хэш-таблицах см. [здесь](about/about_Hash_Tables.md).

Затем `New-PSSessionOption` командлет, использующий параметр **аппликатионаргументс** , создает объект параметра сеанса, сохраненный в `$team` переменной. При `New-PSSessionOption` создании объекта параметра сеанса он автоматически преобразует хэш-таблицу в значение параметра **аппликатионаргументс** в словарь примитива, чтобы данные могли быть надежно переданы в удаленный сеанс.

`New-PSSession`Командлет запускает сеанс на компьютере Server01. Для включения параметров в переменную используется параметр **SessionOption** `$teamOption` .

`Invoke-Command`Командлет показывает, что данные в `$team` переменной доступны командам в удаленном сеансе. Данные отображаются в свойстве **аппликатионаргументс** `$PSSenderInfo` автоматической переменной.

В последнем `Invoke-Command` показывается, как можно использовать данные.

## PARAMETERS

### -Аппликатионаргументс

Указывает словарь примитивов, отправляемый в удаленный сеанс. Команды и скрипты в удаленном сеансе, включая сценарии запуска в конфигурации сеанса, могут найти этот словарь в свойстве **аппликатионаргументс** `$PSSenderInfo` автоматической переменной. Этот параметр можно использовать для отправки данных в удаленный сеанс.

Дополнительные сведения см. в разделе [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md)и [about_Automatic_Variables](about/about_Automatic_Variables.md).

```yaml
Type: System.Management.Automation.PSPrimitiveDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Канцелтимеаут

Определяет, сколько времени PowerShell ожидает завершения операции отмены (CTRL + C), прежде чем ее завершить.
Введите значение в миллисекундах.

Значение по умолчанию — 60 000 (одна минута). Значение 0 (ноль) означает отсутствие времени ожидания; команда будет продолжать выполняться неопределенно долго.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: CancelTimeoutMSec

Required: False
Position: Named
Default value: 60000
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Указывает язык и региональные параметры, используемые для сеанса. Введите имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате (например `ja-JP` ,), переменную, которая содержит объект **CultureInfo** , или команду, которая получает объект **CultureInfo** .

Значение по умолчанию — `$Null` , а язык и региональные параметры, заданные в операционной системе, используются в сеансе.

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeout

Определяет, как долго сеанс остается открытым, если удаленный компьютер не получает никаких сообщений от локального компьютера. Сюда входит сигнал пульса. По истечении этого времени сеанс закрывается.

Значение времени ожидания простоя имеет значительную важность, если планируется отключение и повторное подключение к сеансу. Повторно подключиться можно только в том случае, если не истекло время ожидания сеанса.

Введите значение в миллисекундах. Минимальное значение — 60000 (1 минута). Максимальное значение задано свойством **MaxIdleTimeoutms** конфигурации сеанса. Значение по умолчанию-1 не задает время ожидания простоя.

В сеансе используется время ожидания простоя, заданное в параметрах сеанса, если таковые имеются. Если значение не задано (-1), то в сеансе используется значение свойства **идлетимеаутмс** конфигурации сеанса или значение времени ожидания оболочки WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ), в зависимости от того, какой из них является самым коротким.

Если заданное в параметрах сеанса время ожидания простоя превышает значение свойства **MaxIdleTimeoutMs** в конфигурации сеанса, команда создания сеанса завершается с ошибкой.

Значение **идлетимеаутмс** для конфигурации сеанса **Microsoft. PowerShell** по умолчанию составляет 7200000 мс (2 часа). Его значение **максидлетимеаутмс** составляет 2147483647 миллисекунд ( \> 24 дня). Значение по умолчанию времени ожидания простоя оболочки WSMan ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ) составляет 7200000 миллисекунд (2 часа).

Значение времени ожидания простоя сеанса также может быть изменено при отключении от сеанса или при повторном подключении к сеансу. Дополнительные сведения см. в разделах `Disconnect-PSSession` и `Connect-PSSession`.

В Windows PowerShell 2.0 значение по умолчанию для параметра **IdleTimeout** равно 240 000 (4 минуты).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: IdleTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инклудепортинспн

Включает номер порта в имени участника-службы (SPN), используемый для проверки подлинности Kerberos, например `HTTP://<ComputerName>:5985` . Этот параметр позволяет клиенту, который использует имя субъекта-службы, отличное от значения по умолчанию, выполнять аутентификацию для удаленного компьютера, который использует аутентификацию Kerberos.

Параметр предназначен для организаций, где несколько служб, поддерживающих аутентификацию Kerberos, выполняются с использованием разных учетных записей пользователей. Например, приложение IIS, которое разрешает проверку подлинности Kerberos, может потребовать регистрации имени субъекта-службы по умолчанию для учетной записи пользователя, которая отличается от учетной записи компьютера. В таких случаях удаленное взаимодействие PowerShell не может использовать Kerberos для проверки подлинности, так как для этого требуется имя участника-службы, зарегистрированное в учетной записи компьютера. Чтобы устранить эту проблему, администраторы могут создавать разные имена участников-служб, например с помощью **Setspn.exe** , которые зарегистрированы для разных учетных записей пользователей, и могут различать их путем включения номера порта в имя участника-службы.

Дополнительные сведения см. в разделе [Обзор SetSPN](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Максконнектионретрикаунт

Указывает, сколько раз PowerShell пытается установить подключение к целевому компьютеру, если текущая попытка не удалась из-за проблем с сетью. Значение по умолчанию — 5.

Этот параметр был добавлен для PowerShell версии 5,0.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Максимумрецеиведдатасизеперкомманд

Указывает максимальное число байтов, которые может получить локальный компьютер с удаленного компьютера в рамках одной команды. Введите значение в байтах. По умолчанию ограничения размера данных отсутствуют.

Этот параметр предназначен для защиты ресурсов на клиентском компьютере.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Максимумрецеиведобжектсизе

Указывает максимальный размер объекта, который может получить локальный компьютер с удаленного компьютера. Этот параметр предназначен для защиты ресурсов на клиентском компьютере. Введите значение в байтах.

Если пропустить этот параметр в Windows PowerShell 2.0, ограничение на размер объекта не действует. Начиная с Windows PowerShell 3.0, при отсутствии этого параметра применяется значение по умолчанию — 200 МБ.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 200 MB
Accept pipeline input: False
Accept wildcard characters: False
```

### -Максимумредиректион

Определяет, сколько раз PowerShell перенаправляет соединение на другой универсальный идентификатор ресурса (URI), прежде чем произойдет сбой подключения. Значение по умолчанию — 5. Значение 0 (ноль) запрещает любые перенаправления.

Этот параметр используется в сеансе только в том случае, если параметр **AllowRedirection** используется в команде, которая создает сеанс.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -Уплотнение

Отключает сжатие пакетов в сеансе. Сжатие требует большего числа рабочих циклов процессора, но ускоряет передачу.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoEncryption

Отключает шифрование данных.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Номачинепрофиле

Запрещает загрузку профиля пользователя Windows. В результате сеанс может создаваться быстрее, но в нем будут недоступны параметры реестра для конкретного пользователя, элементы, такие как переменные среды, и сертификаты.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -OpenTimeout

Определяет время ожидания клиентского компьютера при установлении соединения сеанса. По истечении периода команда для установления соединения завершается с ошибкой. Введите значение в миллисекундах.

Значение по умолчанию — 180 000 (3 минуты). Значение 0 (ноль) означает отсутствие времени ожидания; команда будет продолжать выполняться неопределенно долго.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OpenTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationTimeout

Определяет максимальное время выполнения любой операции в сеансе. По истечении периода операция завершается с ошибкой. Введите значение в миллисекундах.

Значение по умолчанию — 180 000 (3 минуты). Значение 0 (ноль) означает отсутствие времени ожидания; операция будет продолжать выполняться неопределенно долго.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Аутпутбуфферингмоде

Определяет порядок управления выходным потоком команды в отключенных сеансах при заполнении .

Если в сеансе или его конфигурации не задан режим буферизации выходных данных, используется значение по умолчанию **Block**. Пользователи также могут изменять режим буферизации выходных данных при отключении сеанса.

Если этот параметр не задан, значение параметра **аутпутбуфферингмоде** объекта параметра Session не равно None. Значение **Block** или **Drop** переопределяет параметр режим буферизации выходных данных, заданный в конфигурации сеанса. Допустимые значения для этого параметра:

- Блокировка. при заполнении выходного буфера выполнение команды приостанавливается до тех пор, пока буфер не будет очищен.
- Drop. при заполнении выходного буфера выполнение команды продолжается. Новые выходные данные сохраняются вместо наиболее старых.
- Отсутствует. порядок действий в случае переполнения выходного буфера не установлен.

Дополнительные сведения о параметре транспорта режим буферизации вывода см. в разделе `New-PSTransportOption` .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Проксякцесстипе

Определяет, какой механизм используется для разрешения имени узла. Допустимые значения для этого параметра:

- иеконфиг
- винхттпконфиг
- AutoDetect
- нопроксисервер
- Нет

По умолчанию используется None.

Сведения о значениях этого параметра см. в разделе [Проксякцесстипе enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype?redirectedfrom=MSDN&view=powershellsdk-1.1.0).

```yaml
Type: System.Management.Automation.Remoting.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: None, IEConfig, WinHttpConfig, AutoDetect, NoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Проксяусентикатион

Задает метод аутентификации, используемый для разрешения прокси-сервера. Допустимые значения для этого параметра: **Basic** , **Digest** и **Negotiate**. Значение по умолчанию — **Negotiate**.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?redirectedfrom=MSDN&view=powershellsdk-1.1.0).

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyCredential

Задает учетные данные, используемые для аутентификации прокси-сервера. Введите переменную, содержащую объект **PSCredential** , или команду, которая получает объект **PSCredential** , например `Get-Credential` команду. Если этот параметр не установлен, учетные данные не заданы.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скипкачекк

Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).

Используйте этот параметр только в том случае, если имеются другие основания считать удаленный компьютер доверенным, например, если он входит в состав физически защищенной и изолированной сети либо указан в качестве доверенного узла в конфигурации службы удаленного управления Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipCNCheck

Указывает, что общее имя сертификата (CN) сервера не обязательно должен совпадать с именем узла сервера. Этот параметр используется только для удаленных операций, использующих протокол HTTPS.

Используйте этот параметр только для доверенных компьютеров.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скипревокатиончекк

Не проверяет состояние отзыва сертификата сервера.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -UICulture

Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса.

Допустимые значения:

- Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например `ja-JP`
- Переменная, содержащая объект **CultureInfo** .
- Команда, которая получает объект **CultureInfo** , например `Get-Culture`

Значение по умолчанию — `$null` , а язык и региональные параметры пользовательского интерфейса, заданные в операционной системе при создании сеанса, используются в сеансе.

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseUTF16

Указывает, что этот командлет кодирует запрос в формате UTF16, а не в формате UTF8.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. Remoting. PSSessionOption

## ПРИМЕЧАНИЯ

Если параметр **SessionOption** не используется в команде для создания **PSSession** , параметры сеанса определяются значениями свойств `$PSSessionOption` привилегированной переменной, если они заданы. Дополнительные сведения о `$PSSessionOption` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

Свойства объекта конфигурации сеанса зависят от заданных для конфигурации сеанса параметров и значений этих параметров. Кроме того, конфигурации сеансов, определяющие с помощью файла конфигурации, включают дополнительные свойства.

## Связанные ссылки

[Enter-PSSession](Enter-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)
