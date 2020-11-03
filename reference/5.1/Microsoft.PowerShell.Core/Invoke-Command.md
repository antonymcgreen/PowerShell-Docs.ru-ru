---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: 652ff321ea1c6507915be9748715604166207200
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229782"
---
# Invoke-Command

## Краткий обзор
Выполняет команды на локальных и удаленных компьютерах.

## SYNTAX

### Необрабатываемый (по умолчанию)

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Сеанс

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### филепасрунспаце

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### филепаскомпутернаме

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### ИмяКомпьютера

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### URI

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### филепасури

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### VMId

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### VMName

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### филепасвмид

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### филепасвмнаме

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### ContainerId

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### филепасконтаинерид

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

## DESCRIPTION

`Invoke-Command`Командлет выполняет команды на локальном или удаленном компьютере и возвращает все выходные данные команд, включая ошибки. С помощью одной `Invoke-Command` команды можно выполнять команды на нескольких компьютерах.

Чтобы выполнить одну команду на удаленном компьютере, используйте параметр **ComputerName**. Чтобы выполнить ряд связанных команд, совместно использующих данные, используйте `New-PSSession` командлет, чтобы создать **сеанс PSSession** (постоянное подключение) на удаленном компьютере, а затем используйте параметр **Session** для, `Invoke-Command` чтобы выполнить команду в **PSSession**. Чтобы выполнить команду в отключенном сеансе, используйте параметр **InDisconnectedSession**. Чтобы выполнить команду в фоновом задании, используйте параметр **AsJob**.

Можно также использовать `Invoke-Command` на локальном компьютере в качестве команды в блоке сценария. PowerShell сразу же выполняет блок сценария в дочерней области текущей области.

Прежде чем использовать `Invoke-Command` для запуска команд на удаленном компьютере, прочитайте [about_Remote](./About/about_Remote.md).

В некоторых примерах кода для уменьшения длины строки используется Сплаттинг. Дополнительные сведения см. в разделе [about_Splatting](./About/about_Splatting.md).

## Примеры

### Пример 1. Запуск скрипта на сервере

В этом примере `Test.ps1` сценарий выполняется на компьютере Server01.

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

Параметр **FilePath** указывает скрипт, расположенный на локальном компьютере. Скрипт выполняется на удаленном компьютере, и результаты возвращаются на локальный компьютер.

### Пример 2. выполнение команды на удаленном сервере

В этом примере выполняется `Get-Culture` команда на удаленном компьютере Server01.

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

Параметр **ComputerName** задает имя удаленного компьютера. Параметр **Credential** используется для выполнения команды в контексте безопасности Domain01\User01 — пользователя, имеющего разрешение на выполнение команд. Параметр **ScriptBlock** указывает команду, выполняемую на удаленном компьютере.

В ответ PowerShell запрашивает пароль и метод проверки подлинности для учетной записи User01.
Затем на компьютере Server01 запускается команда и возвращается результат.

### Пример 3. выполнение команды в постоянном подключении

В этом примере выполняется та же `Get-Culture` команда в сеансе с использованием постоянного подключения на удаленном компьютере с именем Server02.

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

`New-PSSession`Командлет создает сеанс на удаленном компьютере Server02 и сохраняет его в `$s` переменной. Как правило, сеанс создается только при выполнении ряда команд на удаленном компьютере.

`Invoke-Command`Командлет выполняет `Get-Culture` команду в Server02. Параметр **Session** указывает сеанс, сохраненный в `$s` переменной.

В ответ PowerShell выполняет команду в сеансе на компьютере Server02.

### Пример 4. Использование сеанса для выполнения ряда команд, которые совместно используют данные

В этом примере сравниваются последствия использования **ComputerName** и параметров **сеанса** `Invoke-Command` . В нем показано, как использовать сеанс для запуска ряда команд с общими данными.

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

Первые две команды используют параметр **ComputerName** `Invoke-Command` команды для выполнения команд на удаленном компьютере Server02. Первая команда использует командлет, `Get-Process` чтобы получить процесс PowerShell на удаленном компьютере и сохранить его в `$p` переменной. Вторая команда получает значение свойства **VirtualMemorySize** процесса PowerShell.

При использовании параметра **ComputerName** PowerShell создает новый сеанс для выполнения команды.
Сеанс закрывается после завершения выполнения команды. `$p`Переменная была создана в одном соединении, но не существует в соединении, созданном для второй команды.

Проблему можно решить, создав постоянный сеанс на удаленном компьютере, а затем выполнив обе команды в том же сеансе.

`New-PSSession`Командлет создает постоянный сеанс на компьютере Server02 и сохраняет сеанс в `$s` переменной. `Invoke-Command`Следующие строки используют параметр **Session** для выполнения обеих команд в одном сеансе. Так как обе команды выполняются в одном сеансе, `$p` значение остается активным.

### Пример 5. Ввод команды, хранящейся в локальной переменной

В этом примере показано, как создать команду, которая хранится в виде блока скрипта в локальной переменной.
При сохранении блока скрипта в локальной переменной можно указать переменную в качестве значения параметра **ScriptBlock** .

```powershell
$command = { Get-EventLog -LogName "Windows PowerShell" |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

`$command`Переменная хранит `Get-EventLog` команду, отформатированную в виде блока скрипта. `Invoke-Command`Запускает команду, сохраненную в `$command` на удаленных компьютерах S1 и S2.

### Пример 6. выполнение одной команды на нескольких компьютерах

В этом примере демонстрируется использование `Invoke-Command` для выполнения одной команды на нескольких компьютерах.

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-EventLog "Windows PowerShell" }
}
Invoke-Command @parameters
```

Параметр **ComputerName** задает разделенный запятыми список имен компьютеров. Список компьютеров содержит значение localhost, которое представляет локальный компьютер. Параметр **configurationName** задает альтернативную конфигурацию сеанса. Параметр **ScriptBlock** запускается `Get-EventLog` для получения журналов событий Windows PowerShell с каждого компьютера.

### Пример 7. Получение версии основной программы на нескольких компьютерах

В этом примере получается версия программы PowerShell Host, работающей на 200 удаленных компьютерах.

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

Поскольку выполняется только одна команда, не нужно создавать постоянные подключения к каждому из этих компьютеров. Вместо этого команда использует параметр **ComputerName** для указания компьютеров. Чтобы указать компьютеры, он использует `Get-Content` командлет для получения содержимого файла Machine.txt, файла имен компьютеров.

`Invoke-Command`Командлет выполняет `Get-Host` команду на удаленных компьютерах. Он использует точечную нотацию для получения свойства **Version** узла PowerShell.

Эти команды выполняются по одному за раз. После выполнения команд выходные данные команд из всех компьютеров сохраняются в `$version` переменной. В выходные данные включается имя компьютера, с которого были получены данные.

### Пример 8. Выполнение фонового задания на нескольких удаленных компьютерах

В этом примере выполняется команда на двух удаленных компьютерах. `Invoke-Command`Команда использует параметр **AsJob** , чтобы команда выполнялась как фоновое задание. Команды выполняются на удаленных компьютерах, но задание существует на локальном компьютере. Результаты передаются на локальный компьютер.

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

`New-PSSession`Командлет создает сеансы на удаленных компьютерах Server01 и Server02. `Invoke-Command`Командлет запускает фоновое задание в каждом сеансе. Команда с помощью параметра **AsJob** выполняет команду как фоновое задание. Эта команда возвращает объект задания, который содержит два дочерних объекта задания: один для каждого из заданий, запущенных на двух удаленных компьютерах.

`Get-Job`Команда сохраняет объект задания в `$j` переменной. `$j`Затем переменная передается в `Format-List` командлет для вывода всех свойств объекта Job в списке. Последняя команда возвращает результаты заданий. Он передает объект задания в `$j` `Receive-Job` командлет и сохраняет результаты в `$results` переменной.

### Пример 9. Включение локальных переменных в команде, выполняемой на удаленном компьютере

В этом примере показано, как включить значения локальных переменных в команду, запущенную на удаленном компьютере. Команда использует `Using` Модификатор области для определения локальной переменной в удаленной команде. По умолчанию предполагается, что все переменные определяются в удаленном сеансе. `Using`Модификатор области появился в PowerShell 3,0. Дополнительные сведения об `Using` модификаторе области см. в разделе [about_Remote_Variables](./About/about_Remote_Variables.md) и [about_Scopes](./about/about_scopes.md).

```powershell
$Log = "Windows PowerShell"
Invoke-Command -ComputerName Server01 -ScriptBlock { Get-EventLog -LogName $Using:Log -Newest 10 }
```

`$Log`Переменная хранит имя журнала событий, Windows PowerShell. `Invoke-Command`Командлет выполняется `Get-EventLog` в Server01 для получения десяти самых новых событий из журнала событий. Значением параметра "параметр **задания" является** `$Log` переменная, которая предваряется `Using` модификатором области, чтобы указать, что она была создана в локальном сеансе, а не в удаленном сеансе.

### Пример 10. Скрытие имени компьютера

В этом примере показан результат использования параметра **хидекомпутернаме** метода `Invoke-Command` .
**Хидекомпутернаме** не изменяет объект, возвращаемый этим командлетом. Он изменяет только отображение. Вы по-прежнему можете использовать командлеты **Format** для вывода свойства **PSComputerName** любого из затронутых объектов.

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

Первые две команды используют `Invoke-Command` для выполнения `Get-Process` команды для процесса PowerShell. В выходных данных первой команды содержится свойство **PsComputerName** с именем компьютера, на котором запущена команда. Выходные данные второй команды, в которой используется **хидекомпутернаме** , не включают столбец **PSComputerName** .

### Пример 11. Использование ключевого слова param в блоке script

`Param`Ключевое слово и параметр **ArgumentList** используются для передачи значений переменных в именованные параметры в блоке script. В этом примере отображаются имена файлов, которые начинаются с буквы `a` и имеют `.pdf` расширение.

Дополнительные сведения о `Param` ключевом слове см. в разделе [about_Language_Keywords](./about/about_language_keywords.md#param).

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

`Invoke-Command` использует параметр **ScriptBlock** , определяющий две переменные: `$param1` и `$param2` . `Get-ChildItem` использует именованные параметры, **Name** и **include** с именами переменных. **ArgumentList** передает значения переменным.

### Пример 12. Использование автоматической переменной $args в блоке сценария

`$args`Автоматическая переменная и параметр **ArgumentList** используются для передачи значений массива позициям параметров в блоке скрипта. В этом примере отображается содержимое файлов каталога сервера `.txt` . Параметр `Get-ChildItem` **path** имеет значение расположения 0, а параметр **фильтра** — "расположение"
1.

Дополнительные сведения о `$args` переменной см. в разделе [about_Automatic_Variables](./about/about_automatic_variables.md#args)

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

`Invoke-Command` использует параметр **ScriptBlock** и `Get-ChildItem` задает `$args[0]` `$args[1]` значения массива и. **ArgumentList** передает `$args` значения массива на `Get-ChildItem` позиции параметров для **path** и **Filter**.

### Пример 13. выполнение сценария на всех компьютерах, перечисленных в текстовом файле

В этом примере используется `Invoke-Command` командлет для выполнения `Sample.ps1` скрипта на всех компьютерах, перечисленных в `Servers.txt` файле. Команда использует параметр **FilePath** , чтобы указать файл скрипта. Эта команда позволяет запустить сценарий на удаленных компьютерах, даже если файл скрипта недоступен для удаленных компьютеров.

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

При отправке команды содержимое `Sample.ps1` файла копируется в блок скрипта, а блок сценария выполняется на каждом удаленном компьютере. Эта процедура эквивалентна использованию параметра **ScriptBlock** для отправки содержимого скрипта.

### Пример 14. выполнение команды на удаленном компьютере с помощью URI

В этом примере показано, как выполнить команду на удаленном компьютере, идентифицируемом по универсальному идентификатору ресурса (URI). В этом конкретном примере выполняется `Set-Mailbox` команда на удаленном сервере Exchange.

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

В первой строке используется `Get-Credential` командлет для хранения учетных данных Windows Live ID в `$LiveCred` переменной. PowerShell предлагает пользователю ввести учетные данные Windows Live ID.

`$parameters`Переменная является хэш-таблицей, содержащей параметры, передаваемые в `Invoke-Command` командлет. `Invoke-Command`Командлет выполняет `Set-Mailbox` команду, используя конфигурацию сеанса **Microsoft. Exchange** . Параметр **ConnectionURI** указывает URL-адрес конечной точки сервера Exchange Server. Параметр **Credential** указывает учетные данные, хранящиеся в `$LiveCred` переменной. Параметр **AuthenticationMechanism** указывает способ использования обычной проверки подлинности. Параметр **ScriptBlock** указывает блок скрипта, который содержит команду.

### Пример 15. Использование параметра Session

В этом примере показано, как создать и использовать параметр **SessionOption** .

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

`New-PSSessionOption`Командлет создает объект параметра сеанса, который заставляет удаленный элемент не проверять центр сертификации, каноническое имя и списки отзыва при оценке ВХОДЯЩЕГО HTTPS-подключения. Объект **SessionOption** сохраняется в `$so` переменной.

> [!NOTE]
> Отключение этих проверок удобно для устранения неполадок, но очевидно небезопасно.

`Invoke-Command`Командлет запускает `Get-HotFix` команду удаленно. Параметр **SessionOption** получает `$so` переменную.

### Пример 16. Управление перенаправлением URI в удаленной команде

В этом примере показано, как использовать параметры **AllowRedirection** и **SessionOption** для управления перенаправлением URI в удаленной команде.

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

`New-PSSessionOption`Командлет создает объект **PSSessionOption** , который сохраняется в `$max` переменной. Команда использует параметр **MaximumRedirection** , чтобы задать для свойства **MaximumConnectionRedirectionCount** объекта **PSSessionOption** значение 1.

`Invoke-Command`Командлет выполняет `Get-Mailbox` команду на удаленном сервере Microsoft Exchange. Параметр **AllowRedirection** предоставляет явное разрешение для перенаправления подключения к альтернативной конечной точке. Параметр **SessionOption** использует объект Session, хранящийся в `$max` переменной.

В результате, если удаленный компьютер, указанный параметром **ConnectionURI** , возвращает сообщение о перенаправлении, то PowerShell перенаправляет соединение, но если новое назначение возвращает другое сообщение перенаправления, то превышено значение счетчика перенаправления, равное 1, и `Invoke-Command` возвращает неустранимую ошибку.

### Пример 17. доступ к сетевой папке в удаленном сеансе

В этом примере показано, как получить доступ к сетевой папке из удаленного сеанса. Для демонстрации примера используются три компьютера. Server01 — локальный компьютер, Server02 — удаленный компьютер, а Net03 содержит сетевую папку. Server01 подключается к Server02, а затем Server02 выполняет второй прыжок к Net03 для доступа к сетевой папке. Дополнительные сведения о том, как удаленное взаимодействие PowerShell поддерживает переходы между компьютерами, см. [в статье Создание второго прыжка в удаленном взаимодействии PowerShell](/powershell/scripting/learn/remoting/ps-remoting-second-hop).

Требуемое делегирование поставщика поддержки безопасности учетных данных (CredSSP) включено в параметрах клиента на локальном компьютере и в параметрах службы на удаленном компьютере. Для выполнения команд в этом примере необходимо быть членом группы " **Администраторы** " на локальном компьютере и удаленном компьютере.

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

`Enable-WSManCredSSP`Командлет включает делегирование CredSSP с локального компьютера Server01 на удаленный компьютер Server02. Параметр **Role** указывает **клиент** для настройки параметра клиента CredSSP на локальном компьютере.

`New-PSSession` Создает объект **PSSession** для Server02 и сохраняет объект в `$s` переменной.

`Invoke-Command`Командлет использует `$s` переменную для подключения к удаленному компьютеру Server02. Параметр **ScriptBlock** выполняется `Enable-WSManCredSSP` на удаленном компьютере. Параметр **Role** указывает **сервер** для настройки параметра сервера CredSSP на удаленном компьютере.

`$parameters`Переменная содержит значения параметров для подключения к сетевой папке. `Invoke-Command`Командлет выполняет `Get-Item` команду в сеансе в `$s` . Эта команда возвращает скрипт из `\\Net03\Scripts` общей сетевой папки. Команда использует параметр **authentication** со значением **CredSSP** и параметром **Credential** со значением **Domain01\Admin01**.

### Пример 18. Запуск сценариев на многих удаленных компьютерах

В этом примере сценарий выполняется на более чем сотни компьютерах. Чтобы свести к минимуму влияние на локальный компьютер, она подключается к каждому компьютеру, запускает скрипт, а затем отключается.
Скрипт продолжает выполняться в отключенных сеансах.

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

Команда использует `Invoke-Command` для запуска скрипта. Значение параметра **ComputerName** — это `Get-Content` команда, которая получает имена удаленных компьютеров из текстового файла. Параметр **InDisconnectedSession** отключает сеансы сразу при запуске команды. Значение параметра **FilePath** — это скрипт, который `Invoke-Command` выполняется на каждом компьютере.

Значение **SessionOption** является хэш-таблицей. Для параметра **аутпутбуфферингмоде** устанавливается значение **Drop** , а для параметра **IdleTimeout** — значение **43200000** миллисекунд (12 часов).

Чтобы получить результаты выполнения команд и сценариев в отключенных сеансах, используйте `Receive-PSSession` командлет.

## PARAMETERS

### -AllowRedirection

Разрешает перенаправление данного соединения на альтернативный URI.

При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI. По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить перенаправление подключения.

Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount**. Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений. Значение по умолчанию — 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Определяет сегмент имени приложения в URI соединения. Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI** .

Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере. Если эта переменная предпочтений не определена, по умолчанию используется значение WSMAN. Это значение подходит для большинства случаев Дополнительные сведения см. в разделе [about_Preference_Variables](./About/about_Preference_Variables.md).

Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.
Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ArgumentList

Предоставляет значения локальных переменных в команде. Переменные в команде заменяются этими значениями до выполнения команды на удаленном компьютере. Введите значения в список с разделителями-запятыми. Значения связаны с переменными в том порядке, в котором они перечислены. Псевдоним для **ArgumentList** — args.

Значения в параметре **ArgumentList** могут быть фактическими значениями, например 1024, или ссылками на локальные переменные, например `$max` .

Чтобы использовать локальные переменные в команде, воспользуйтесь следующим форматом команды:

`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -или- `<local-variable>`

Ключевое слово **param** перечисляет локальные переменные, используемые в команде. **ArgumentList** предоставляет значения переменных в том порядке, в котором они перечислены. Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Указывает, что этот командлет выполняет команду в качестве фонового задания на удаленном компьютере. Этот параметр используется для выполнения команд, выполнение которых занимает много времени.

При использовании параметра **AsJob** команда возвращает объект, представляющий задание, а затем отображает командную строку. Можно продолжить работу в рамках данного сеанса, пока задание завершается. Для управления заданием используйте `*-Job` командлеты. Чтобы получить результаты задания, используйте `Receive-Job` командлет.

Параметр **AsJob** напоминает использование `Invoke-Command` командлета для `Start-Job` удаленного выполнения командлета. Однако при использовании **AsJob** задание создается на локальном компьютере, даже если задание выполняется на удаленном компьютере. Результаты удаленного задания автоматически возвращаются на локальный компьютер.

Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](About/about_Jobs.md) и [about_Remote_Jobs](About/about_Remote_Jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication

Указывает механизм, используемый для проверки подлинности учетных данных пользователя. Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.

Для этого параметра допустимы следующие значения:

- По умолчанию
- Базовый
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential

Значение по умолчанию — Default.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом. Дополнительные сведения см. в разделе [поставщик поддержки безопасности учетных данных](/windows/win32/secauthn/credential-security-support-provider).

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для подключения к отсоединенному сеансу. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут быть сопоставлены только с локальными учетными записями пользователей и не работают с учетными записями домена.

Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает компьютеры, на которых выполняется команда. По умолчанию это локальный компьютер.

При использовании параметра **ComputerName** PowerShell создает временное подключение, которое используется только для выполнения указанной команды и затем закрывается. Если требуется постоянное подключение, используйте параметр **Session** .

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров в списке с разделителями запятыми. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку ( `.` ).

Чтобы использовать IP-адрес в значении **ComputerName** , команда должна включать параметр **Credential** . Компьютер должен быть настроен для транспорта HTTPS, или IP-адрес удаленного компьютера должен быть включен в список **TrustedHosts** для WinRM локального компьютера. Инструкции по добавлению имени компьютера в список **TrustedHosts** см. в разделе [Добавление компьютера в список надежных узлов](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).

В Windows Vista и более поздних версиях операционной системы Windows для включения локального компьютера в значение **ComputerName** необходимо запустить PowerShell с параметром **Запуск от имени администратора** .

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Указывает конфигурацию сеанса, используемую для нового **PSSession**.

Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса. Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/PowerShell` .

Конфигурация сеанса для сеанса размещается на удаленном компьютере. Если на удаленном компьютере не существует указанной конфигурации сеанса, команда завершается ошибкой.

Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере. Если эта переменная предпочтений не задана, по умолчанию используется **Microsoft. PowerShell**. Дополнительные сведения см. в разделе [about_Preference_Variables](about/about_Preference_Variables.md).

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Задает универсальный код ресурса (URI), который определяет конечную точку подключения сеанса.
Значение URI должно быть указано полностью.

Строка имеет следующий формат:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Значение по умолчанию определяется следующим образом.

`http://localhost:5985/WSMAN`

Если не указать URI соединения, можно использовать параметры **UseSSL** и **Port** , чтобы указать значения универсального кода ресурса (URI) соединения.

Допустимые значения для сегмента **Transport** идентификатора URI: HTTP и HTTPS. Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс будет создан с использованием стандартов ports: 80 для HTTP и 443 для HTTPS. Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.

Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerId

Указывает массив идентификаторов контейнеров.

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя. Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров. Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.

Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере. Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение Dot ( `.` ), localhost или имя локального компьютера.

По умолчанию, сеансы замыкания на себя создаются с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.

Параметр **EnableNetworkAccess** действует только в петлевых сеансах. Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.

Можно разрешить удаленный доступ в сеансе замыкания на себя, используя значение **CredSSP** параметра **authentication** , которое делегирует учетные данные сеанса другим компьютерам.

Чтобы защитить компьютер от вредоносного доступа, отключенные сеансы замыкания на себя с интерактивными маркерами, которые созданы с помощью **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс. Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров. Для получения дополнительной информации см. `Disconnect-PSSession`.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Задает локальный скрипт, выполняемый этим командлетом на одном или нескольких удаленных компьютерах. Введите путь и имя файла скрипта или передайте путь к сценарию `Invoke-Command` . Сценарий должен существовать на локальном компьютере или в каталоге, к которому может получить доступ локальный компьютер. Используйте **ArgumentList** , чтобы указать значения параметров в скрипте.

При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта, передает блок сценария на удаленный компьютер и запускает его на удаленном компьютере.

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Хидекомпутернаме

Указывает, что этот командлет опускает имя компьютера для каждого объекта, отображаемого в выходных данных. По умолчанию имя компьютера, создавшего объект, отображается на экране.

Этот параметр влияет только на отображение выходных данных. Он не изменяет объект.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases: HCN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InDisconnectedSession

Указывает, что этот командлет запускает команду или сценарий в отключенном сеансе.

При использовании параметра **InDisconnectedSession** `Invoke-Command` создает постоянный сеанс на каждом удаленном компьютере, запускает команду, указанную параметром **ScriptBlock** или **FilePath** , а затем отключается от сеанса. Команды продолжают выполняться в отключенных сеансах. **InDisconnectedSession** позволяет выполнять команды без подключения к удаленным сеансам. И, поскольку сеанс отключается перед возвратом результатов, **InDisconnectedSession** гарантирует, что все результаты команды возвращаются к повторно подключенному сеансу, а не распределяются между сеансами.

Нельзя использовать **InDisconnectedSession** с параметром **Session** или **AsJob** .

Команды, использующие **InDisconnectedSession** , возвращают объект **PSSession** , представляющий отключенный сеанс. Они не возвращают выходные данные команды. Чтобы подключиться к отключенному сеансу, используйте `Connect-PSSession` `Receive-PSSession` командлеты или. Чтобы получить результаты команд, которые выполнялись в сеансе, используйте `Receive-PSSession` командлет. Чтобы выполнить команды, создающие выходные данные в отключенном сеансе, установите для параметра сеанса **аутпутбуфферингмоде** значение **Drop**. Если вы планируете подключиться к отключенному сеансу, установите время ожидания простоя в сеансе, чтобы обеспечить достаточное время для подключения перед удалением сеанса.

Можно задать режим буферизации вывода и время ожидания простоя в параметре **SessionOption** или в `$PSSessionOption` переменной предпочтений. Дополнительные сведения о параметрах сеанса см. в статьях `New-PSSessionOption` и [about_Preference_Variables](./about/about_preference_variables.md).

Дополнительные сведения о функции отключенных сеансов см. в разделе [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает входные данные команды. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

При использовании параметра **InputObject** используйте `$Input` автоматическую переменную в значении параметра **ScriptBlock** для представления входных объектов.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobName

Указывает понятное имя для фонового задания. По умолчанию задания именуются `Job<n>` , где `<n>` — порядковый номер.

Если в команде используется параметр **JobName** , команда выполняется как задание и `Invoke-Command` возвращает объект задания, даже если в команде не включена функция **AsJob** .

Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](./About/about_Jobs.md).

```yaml
Type: System.String
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ноневскопе

Указывает, что этот командлет выполняет указанную команду в текущей области. По умолчанию `Invoke-Command` выполняет команды в своей собственной области.

Этот параметр допустим только в командах, которые выполняются в текущем сеансе, т. е. в командах, которые пропускают как параметр **ComputerName** , так и параметр **Session**.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Указывает сетевой порт на удаленном компьютере, используемый для этой команды. Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением. Порты по умолчанию: 5985 (порт WinRM для HTTP) и 5986 (порт WinRM для HTTPS).

Перед использованием другого порта настройте прослушиватель WinRM на удаленном компьютере для прослушивания порта. Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Не используйте параметр **Port** , если не требуется. Порт, который задается в команде, применяется ко всем компьютерам или сеансам, в которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах.

```yaml
Type: System.Int32
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Рунасадминистратор

Указывает, что этот командлет вызывает команду от имени администратора.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Указывает выполняющиеся команды. Заключите команды в фигурные скобки, `{ }` чтобы создать блок скрипта.
Этот параметр обязателен.

По умолчанию все переменные в команде вычисляются на удаленном компьютере. Чтобы включить локальные переменные в команду, используйте **ArgumentList**.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, ContainerId
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Указывает массив сеансов, в которых этот командлет выполняет команду. Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как `New-PSSession` команда или `Get-PSSession` .

При создании **сеанса PSSession** PowerShell устанавливает постоянное подключение к удаленному компьютеру. Используйте **PSSession** для выполнения ряда связанных команд, которые совместно используют данные. Чтобы выполнить одну команду или ряд несвязанных команд, используйте параметр **ComputerName** . Дополнительные сведения см. в разделе [about_PSSessions](./About/about_PSSessions.md).

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session, FilePathRunspace
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionName

Задает понятное имя для отключенного сеанса. Имя можно использовать для ссылки на сеанс в последующих командах, таких как `Get-PSSession` команда. Этот параметр допустим только при использовании с параметром **InDisconnectedSession**.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionOption

Задает дополнительные параметры для сеанса. Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.

Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано. В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.

Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса. Однако они не имеют приоритета над максимальными значениями, квотами или ограничениями, установленными в конфигурации сеанса.

Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` . Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).
Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.

Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

```yaml
Type: System.Int32
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером. По умолчанию протокол SSL не используется.

WS-Management шифрует все содержимое PowerShell, передаваемое по сети. Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по протоколу HTTPS вместо HTTP.

Если вы используете этот параметр, но протокол SSL недоступен в порте, используемом для команды, команда завершается ошибкой.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### — VMId

Указывает массив идентификаторов виртуальных машин.

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Указывает массив имен виртуальных машин.

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. ScriptBlock

Команду можно передать в блок скрипта в `Invoke-Command` . Используйте `$Input` автоматическую переменную для представления входных объектов в команде.

## Выходные данные

### System. Management. Automation. Псремотингжоб, System. Management. Automation. пространства выполнения PSSession или выходные данные вызываемой команды

Этот командлет возвращает объект задания, если используется параметр **AsJob** . Если указан параметр **InDisconnectedSession** , `Invoke-Command` возвращает объект **PSSession** . В противном случае он возвращает выходные данные вызванной команды, которая является значением параметра **ScriptBlock** .

## ПРИМЕЧАНИЯ

В Windows Vista и более поздних версиях операционной системы Windows для использования параметра **ComputerName** `Invoke-Command` функции для выполнения команды на локальном компьютере необходимо запустить PowerShell с параметром **Запуск от имени администратора** .

При выполнении команд на нескольких компьютерах PowerShell подключается к компьютерам в том порядке, в котором они отображаются в списке. Однако выходные данные команды отображаются в порядке их получения с удаленных компьютеров, которые могут отличаться.

Ошибки, возникающие в результате выполнения команды, `Invoke-Command` включаются в результаты выполнения команды.
Ошибки, являющиеся неустранимыми в локальной команде, рассматриваются как устранимые в удаленной команде. Эта стратегия гарантирует, что завершающие ошибки на одном компьютере не закрывают команду на всех компьютерах, на которых он выполняется. Такой подход используется, даже если удаленная команда выполняется на одном компьютере.

Если удаленный компьютер не входит в домен, которому доверяет локальный компьютер, возможно, компьютер не сможет проверить подлинность учетных данных пользователя. Чтобы добавить удаленный компьютер в список надежных узлов в службе WS-Management, используйте следующую команду в `WSMAN` поставщике, где `<Remote-Computer-Name>` — имя удаленного компьютера:

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

При отключении **PSSession** с помощью параметра **InDisconnectedSession** состояние сеанса **отключается** , а доступность — **нет**. Значение свойства **State** определяется текущим сеансом. Значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу. Однако это не означает, что **сеанс PSSession** отключен от всех сеансов. Он может быть подключен к другому сеансу. Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability**.

Если свойство **Availability** имеет значение **None** , подключиться к сеансу можно. Значение **занято** указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу. Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате](/dotnet/api/system.management.automation.runspaces.runspacestate). Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## Связанные ссылки

[about_PSSessions](./About/about_PSSessions.md)

[about_Remote](./About/about_Remote.md)

[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)

[about_Remote_Troubleshooting](./About/about_remote_troubleshooting.md)

[about_Remote_Variables](./About/about_Remote_Variables.md)

[about_Scopes](./About/about_scopes.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession;](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Item](../Microsoft.PowerShell.Management/Invoke-Item.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
